<template>
  <div>
    <vxe-pulldown ref="pulldownRef" popup-class-name="my-dropdown4" transfer>
      <template #default>
        <vxe-input v-model="searchName" suffix-icon="vxe-icon-table" placeholder="实现下拉分页表格" @keyup="keyupEvent" @focus="focusEvent" @suffix-click="suffixClick"></vxe-input>
      </template>

      <template #header>
        <div class="my-headdown4">
          <vxe-button mode="text" status="primary">按钮1</vxe-button>
          <vxe-button mode="text" status="danger">按钮2</vxe-button>
        </div>
      </template>

      <template #dropdown>
        <div class="my-bodydown4">
          <vxe-grid
            border
            auto-resize
            height="auto"
            :row-config="{isHover: true}"
            :loading="loading"
            :pager-config="pagerConfig"
            :data="tableData"
            :columns="tableColumn"
            @cell-click="cellClickEvent"
            @page-change="pageChangeEvent">
          </vxe-grid>
        </div>
      </template>

      <template #footer>
        <div class="my-footdown4">
          <vxe-button mode="text" status="primary">底部</vxe-button>
        </div>
      </template>
    </vxe-pulldown>
  </div>
</template>

<script>
export default {
  data () {
    return {
      searchName: '',
      loading: false,
      tableColumn: [
        { field: 'name', title: 'Name' },
        { field: 'role', title: 'Role' },
        { field: 'sex', title: 'Sex' }
      ],
      tableData: [],
      tableList: [
        { name: 'Test1', role: '前端', sex: '男' },
        { name: 'Test2', role: '后端', sex: '男' },
        { name: 'Test3', role: '测试', sex: '男' },
        { name: 'Test4', role: '设计师', sex: '女' },
        { name: 'Test5', role: '前端', sex: '男' },
        { name: 'Test6', role: '前端', sex: '男' },
        { name: 'Test7', role: '前端', sex: '男' }
      ],
      pagerConfig: {
        total: 0,
        currentPage: 1,
        pageSize: 10
      }
    }
  },
  mounted () {
    this.keyupEvent()
  },
  methods: {
    focusEvent () {
      const $pulldown = this.$refs.pulldownRef
      if ($pulldown) {
        $pulldown.showPanel()
      }
    },
    keyupEvent  () {
      this.loading = true
      setTimeout(() => {
        this.loading = false
        if (this.searchName) {
          this.tableData = this.tableList.filter((row) => row.name.indexOf(this.searchName) > -1)
        } else {
          this.tableData = this.tableList.slice(0)
        }
      }, 100)
    },
    suffixClick  () {
      const $pulldown = this.$refs.pulldownRef
      if ($pulldown) {
        $pulldown.togglePanel()
      }
    },
    cellClickEvent ({ row }) {
      const $pulldown = this.$refs.pulldownRef
      if ($pulldown) {
        this.searchName = row.name
        $pulldown.hidePanel()
      }
    },
    pageChangeEvent ({ currentPage, pageSize }) {
      this.pagerConfig.currentPage = currentPage
      this.pagerConfig.pageSize = pageSize
    }
  }
}
</script>

<style lang="scss">
.my-dropdown4 {
  background-color: #fff;
  box-shadow: 0 0 6px 2px rgba(0, 0, 0, 0.1);
  .my-bodydown4 {
    width: 600px;
    height: 300px;
  }

  .my-footdown4 {
    border-top: 1px solid #e8eaec;
  }
}
</style>
