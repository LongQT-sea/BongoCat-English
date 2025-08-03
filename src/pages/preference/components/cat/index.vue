<script setup lang="ts">
import { InputNumber, Slider, Switch } from 'ant-design-vue'

import ProList from '@/components/pro-list/index.vue'
import ProListItem from '@/components/pro-list-item/index.vue'
import { useCatStore } from '@/stores/cat'

const catStore = useCatStore()
</script>

<template>
  <ProList title="Model Settings">
    <ProListItem
      description="When enabled, the model will be horizontally mirrored."
      title="Mirror Mode"
    >
      <Switch v-model:checked="catStore.mirrorMode" />
    </ProListItem>

    <ProListItem
      description="When enabled, each hand will only show the last pressed key."
      title="Single Key Mode"
    >
      <Switch v-model:checked="catStore.singleMode" />
    </ProListItem>

    <ProListItem
      description="When enabled, mouse movements will mirror hand movements."
      title="Mouse Mirror"
    >
      <Switch v-model:checked="catStore.mouseMirror" />
    </ProListItem>
  </ProList>

  <ProList title="Window Settings">
    <ProListItem
      description="When enabled, the window will not interfere with other applications."
      title="Click Through"
    >
      <Switch v-model:checked="catStore.penetrable" />
    </ProListItem>

    <ProListItem
      description="When enabled, the window will always stay on top of other applications."
      title="Always on Top"
    >
      <Switch v-model:checked="catStore.alwaysOnTop" />
    </ProListItem>

    <ProListItem
      description="Move mouse to window edge, or hold Shift and right-click drag to resize the window."
      title="Window Size"
    >
      <InputNumber
        v-model:value="catStore.scale"
        class="w-28"
        :min="1"
      >
        <template #addonAfter>
          %
        </template>
      </InputNumber>
    </ProListItem>

    <ProListItem
      title="Opacity"
      vertical
    >
      <Slider
        v-model:value="catStore.opacity"
        class="m-0!"
        :max="100"
        :min="10"
        :tip-formatter="(value) => `${value}%`"
      />
    </ProListItem>
  </ProList>
</template>
