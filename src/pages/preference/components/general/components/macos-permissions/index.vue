<script setup lang="ts">
import { getCurrentWebviewWindow } from '@tauri-apps/api/webviewWindow'
import { message } from '@tauri-apps/plugin-dialog'
import { Space } from 'ant-design-vue'
import { checkInputMonitoringPermission, requestInputMonitoringPermission } from 'tauri-plugin-macos-permissions-api'
import { onMounted, ref } from 'vue'

import ProList from '@/components/pro-list/index.vue'
import ProListItem from '@/components/pro-list-item/index.vue'
import { isMac } from '@/utils/platform'

const authorized = ref(false)

onMounted(async () => {
  authorized.value = await checkInputMonitoringPermission()

  if (authorized.value) return

  const appWindow = getCurrentWebviewWindow()

  await appWindow.setAlwaysOnTop(true)

  await message('If permission is already enabled, first select it and click the "-" button to remove it, then manually add it again and restart the app to ensure permissions take effect.', {
    title: 'Input Monitoring Permission',
    okLabel: 'Go to Enable',
    kind: 'warning',
  })

  await appWindow.setAlwaysOnTop(false)

  requestInputMonitoringPermission()
})
</script>

<template>
  <ProList
    v-if="isMac"
    title="Permission Settings"
  >
    <ProListItem
      description="Enable input monitoring permission to receive system keyboard and mouse events to respond to your actions."
      title="Input Monitoring Permission"
    >
      <Space
        v-if="authorized"
        class="text-success font-bold"
        :size="4"
      >
        <div class="i-solar:verified-check-bold text-4.5" />

        <span>Authorized</span>
      </Space>

      <Space
        v-else
        class="cursor-pointer text-danger font-bold"
        :size="4"
        @click="requestInputMonitoringPermission"
      >
        <div class="i-solar:round-arrow-right-bold text-4.5" />

        <span>Authorize</span>
      </Space>
    </ProListItem>
  </ProList>
</template>
