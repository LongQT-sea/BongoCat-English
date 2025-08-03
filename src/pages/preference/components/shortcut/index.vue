<script setup lang="ts">
import { storeToRefs } from 'pinia'

import ProList from '@/components/pro-list/index.vue'
import ProShortcut from '@/components/pro-shortcut/index.vue'
import { useTauriShortcut } from '@/composables/useTauriShortcut'
import { toggleWindowVisible } from '@/plugins/window'
import { useCatStore } from '@/stores/cat'
import { useShortcutStore } from '@/stores/shortcut.ts'

const shortcutStore = useShortcutStore()
const { visibleCat, visiblePreference, mirrorMode, penetrable, alwaysOnTop } = storeToRefs(shortcutStore)
const catStore = useCatStore()

useTauriShortcut(visibleCat, () => {
  catStore.visible = !catStore.visible
})

useTauriShortcut(visiblePreference, () => {
  toggleWindowVisible('preference')
})

useTauriShortcut(mirrorMode, () => {
  catStore.mirrorMode = !catStore.mirrorMode
})

useTauriShortcut(penetrable, () => {
  catStore.penetrable = !catStore.penetrable
})

useTauriShortcut(alwaysOnTop, () => {
  catStore.alwaysOnTop = !catStore.alwaysOnTop
})
</script>

<template>
  <ProList title="Shortcuts">
    <ProShortcut
      v-model="shortcutStore.visibleCat"
      description="Toggle cat window visibility."
      title="Show/Hide Cat"
    />

    <ProShortcut
      v-model="shortcutStore.visiblePreference"
      description="Toggle preferences window visibility."
      title="Show/Hide Preferences"
    />

    <ProShortcut
      v-model="shortcutStore.mirrorMode"
      description="Toggle cat mirror mode."
      title="Mirror Mode"
    />

    <ProShortcut
      v-model="shortcutStore.penetrable"
      description="Toggle whether the cat window is click-through."
      title="Click Through"
    />

    <ProShortcut
      v-model="shortcutStore.alwaysOnTop"
      description="Toggle whether the cat window stays on top."
      title="Always on Top"
    />
  </ProList>
</template>
