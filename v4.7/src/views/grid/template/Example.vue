<template>
  <div>
    <CodeLight path="grid/template/Demo10">
      <template #tip>
        <div>
          功能模板，支持自定义插槽模板或 JSX 渲染函数
        </div>
        <div>
          <grid-api-link prop="form"/>：自定义表单模板<br>
          <grid-api-link prop="toolbar"/>：自定义工具栏模板<br>
          <grid-api-link prop="top"/>：自定义顶部模板<br>
          <grid-api-link prop="bottom"/>：自定义底部模板<br>
          <grid-api-link prop="left"/>：自定义左侧模板<br>
          <grid-api-link prop="right"/>：自定义右侧模板<br>
          <grid-api-link prop="pager"/>：自定义分页模板<br>
        </div>
      </template>
    </CodeLight>

    <CodeLight path="grid/template/Demo1">
      <template #tip>
        <div>
          单元格模板，使用插槽 <table-column-api-link prop="default"/> 来自定义模板（提前转换好数据（最优） > <table-column-api-link prop="formatter"/>（field值发生变化时） > <table-column-api-link prop="slots"/>（实时响应））<br>
        </div>
      </template>
    </CodeLight>

    <CodeLight path="grid/template/Demo2">
      <template #tip>
        <div>
          表头单元格模板，使用插槽 <table-column-api-link prop="header"/> 来自定义模板
        </div>
      </template>
    </CodeLight>

    <CodeLight path="grid/template/Demo3">
      <template #tip>
        <div>
          表尾单元格模板，使用插槽 <table-column-api-link prop="footer"/> 来自定义模板
        </div>
      </template>
    </CodeLight>

    <CodeLight path="grid/template/Demo4">
      <template #tip>
        <div>
          复选框模板，使用插槽 <table-column-api-link prop="checkbox"/> 来自定义模板
        </div>
      </template>
    </CodeLight>

    <CodeLight path="grid/template/Demo5">
      <template #tip>
        <div>
          单选框模板，使用插槽 <table-column-api-link prop="radio"/> 来自定义模板
        </div>
      </template>
    </CodeLight>

    <CodeLight path="grid/template/Demo6">
      <template #tip>
        <div>
          展开行模板，使用插槽 <table-column-api-link prop="content"/> 来自定义模板
        </div>
      </template>
    </CodeLight>

    <CodeLight path="grid/template/Demo7">
      <template #tip>
        <div>
          筛选模板，使用插槽 <table-column-api-link prop="filter"/> 来自定义模板
        </div>
      </template>
    </CodeLight>

    <CodeLight path="grid/template/Demo8">
      <template #tip>
        <div>
          可编辑模板，使用插槽 <table-column-api-link prop="edit"/> 来自定义模板
        </div>
      </template>
    </CodeLight>

    <CodeLight path="grid/template/Demo9">
      <template #tip>
        <div>
          校验提示模板，使用插槽 <table-column-api-link prop="valid"/> 来自定义模板
        </div>
      </template>
    </CodeLight>
  </div>
</template>
