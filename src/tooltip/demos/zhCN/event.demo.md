# 事件

```html
<n-space>
  <n-tooltip placement="bottom" trigger="hover" @update:show="handleUpdateShow">
    <template #trigger>
      <n-button> 悬浮 </n-button>
    </template>
    <span> I wish they all could be California girls </span>
  </n-tooltip>
  <n-tooltip placement="bottom" trigger="click" @update:show="handleUpdateShow">
    <template #trigger>
      <n-button> 点击 </n-button>
    </template>
    <span> I wish they all could be California girls </span>
  </n-tooltip>
  <n-tooltip :show="showPopover" placement="bottom">
    <template #trigger>
      <n-button @click="showPopover = !showPopover">
        手动（不会有事件发出来）
      </n-button>
    </template>
    <span> I wish they all could be California girls </span>
  </n-tooltip>
</n-space>
```

```js
export default {
  inject: ['message'],
  data () {
    return {
      showPopover: false
    }
  },
  methods: {
    handleUpdateShow (show) {
      this.message.success(show)
    }
  }
}
```