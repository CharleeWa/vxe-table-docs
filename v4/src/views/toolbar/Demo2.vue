<template>
  <div>
    <vxe-toolbar ref="toolbarRef" custom>
      <template #buttons>
        <vxe-button content="自定义模板"></vxe-button>
        <vxe-button content="按钮2"></vxe-button>
        <vxe-button content="按钮3"></vxe-button>
        <vxe-button content="下拉按钮">
          <template #dropdowns>
            <vxe-button content="按钮1"></vxe-button>
            <vxe-button content="按钮2"></vxe-button>
            <vxe-button content="按钮3"></vxe-button>
          </template>
        </vxe-button>
      </template>
      <template #tools>
        <vxe-button mode="text" icon="vxe-icon-undo" class="tool-btn"></vxe-button>
        <vxe-button mode="text" icon="vxe-icon-funnel" class="tool-btn" @click="funnelEvent"></vxe-button>
      </template>
    </vxe-toolbar>

    <vxe-table ref="tableRef" :data="tableData">
      <vxe-column field="name" title="Name"></vxe-column>
      <vxe-column field="role" title="Role"></vxe-column>
      <vxe-column field="sex" title="Sex"></vxe-column>
    </vxe-table>
  </div>
</template>

<script lang="ts" setup>
import { ref, nextTick } from 'vue'
import { VXETable, VxeTableInstance, VxeToolbarInstance } from 'vxe-table'

const tableData = ref([
  { name: 'Test1', role: '前端', sex: '男' },
  { name: 'Test2', role: '后端', sex: '男' },
  { name: 'Test3', role: '测试', sex: '男' },
  { name: 'Test4', role: '设计师', sex: '女' }
])

const tableRef = ref<VxeTableInstance>()
const toolbarRef = ref<VxeToolbarInstance>()

const funnelEvent = () => {
  VXETable.modal.alert({ content: '点击事件' })
}

nextTick(() => {
  // 将表格和工具栏进行关联
  const $table = tableRef.value
  const $toolbar = toolbarRef.value
  if ($table && $toolbar) {
    $table.connect($toolbar)
  }
})
</script>

<style lang="scss" scoped>
.tool-btn {
  font-size: 20px;
  cursor: pointer;
}
.tool-btn:hover {
  color: #409eff;
}
</style>
