<template>
  <div>
    <p class="tip">
      表尾合并行或列，通过 <table-api-link prop="merge-footer-items"/> 临时合并，或者自定义 <table-api-link prop="footer-span-method"/> 合并方法<br>
      <span class="red">（注：<table-api-link prop="footer-span-method"/> ，不能用于虚拟滚动、树形结构、展开行、固定列，合并的逻辑都是自行实现的，该示例仅供参考）</span>
    </p>

    <vxe-table
      border
      show-footer
      height="400"
      :merge-footer-items="mergeFooterItems"
      :footer-method="footerMethod"
      :data="tableData">
      <vxe-column type="seq" width="60"></vxe-column>
      <vxe-column field="name" title="Name" sortable></vxe-column>
      <vxe-column field="role" title="Role" sortable></vxe-column>
      <vxe-column field="rate" title="Rate" footer-align="center"></vxe-column>
      <vxe-column field="age" title="Age" footer-align="center"></vxe-column>
    </vxe-table>

    <p class="demo-code">{{ $t('app.body.button.showCode') }}</p>

    <pre>
      <pre-code class="xml">{{ demoCodes[0] }}</pre-code>
      <pre-code class="javascript">{{ demoCodes[1] }}</pre-code>
    </pre>

    <p class="tip">合并列</p>

    <vxe-table
      border
      show-footer
      height="400"
      :footer-span-method="footerColspanMethod"
      :footer-method="footerMethod"
      :data="tableData">
      <vxe-column type="seq" width="60"></vxe-column>
      <vxe-column field="name" title="Name" sortable></vxe-column>
      <vxe-column field="role" title="Role" sortable></vxe-column>
      <vxe-column field="rate" title="Rate" footer-align="center"></vxe-column>
      <vxe-column field="age" title="Age" footer-align="center"></vxe-column>
    </vxe-table>

    <p class="demo-code">{{ $t('app.body.button.showCode') }}</p>

    <pre>
      <pre-code class="xml">{{ demoCodes[2] }}</pre-code>
      <pre-code class="javascript">{{ demoCodes[3] }}</pre-code>
    </pre>

    <p class="tip">合并行</p>

    <vxe-table
      border
      show-footer
      height="400"
      :footer-span-method="footerRowspanMethod"
      :footer-method="footerMethod"
      :data="tableData">
      <vxe-column type="seq" width="60"></vxe-column>
      <vxe-column field="name" title="Name" sortable></vxe-column>
      <vxe-column field="role" title="Role" sortable></vxe-column>
      <vxe-column field="rate" title="Rate" footer-align="center"></vxe-column>
      <vxe-column field="age" title="Age" footer-align="center"></vxe-column>
    </vxe-table>

    <p class="demo-code">{{ $t('app.body.button.showCode') }}</p>

    <pre>
      <pre-code class="xml">{{ demoCodes[4] }}</pre-code>
      <pre-code class="javascript">{{ demoCodes[5] }}</pre-code>
    </pre>
  </div>
</template>

<script>
export default {
  data () {
    return {
      tableData: [
        { id: 10001, name: 'Test1', nickname: 'T1', role: 'Develop', sex: 'Man', age: 28, address: 'test abc' },
        { id: 10002, name: 'Test2', nickname: 'T2', role: 'Test', sex: 'Women', age: 22, address: 'Guangzhou' },
        { id: 10003, name: 'Test3', nickname: 'T3', role: 'PM', sex: 'Man', age: 32, address: 'Shanghai' },
        { id: 10004, name: 'Test4', nickname: 'T4', role: 'Designer', sex: 'Women', age: 23, address: 'test abc' },
        { id: 10005, name: 'Test5', nickname: 'T5', role: 'Develop', sex: 'Women', age: 30, address: 'Shanghai' },
        { id: 10006, name: 'Test6', nickname: 'T6', role: 'Designer', sex: 'Women', age: 21, address: 'test abc' },
        { id: 10007, name: 'Test7', nickname: 'T7', role: 'Test', sex: 'Man', age: 29, address: 'test abc' },
        { id: 10008, name: 'Test8', nickname: 'T8', role: 'Develop', sex: 'Man', age: 35, address: 'test abc' }
      ],
      mergeFooterItems: [
        { row: 0, col: 1, rowspan: 1, colspan: 3 }
      ],
      demoCodes: [
        `
        <vxe-table
          border
          show-footer
          height="400"
          :merge-footer-items="mergeFooterItems"
          :footer-method="footerMethod"
          :data="tableData">
          <vxe-column type="seq" width="60"></vxe-column>
          <vxe-column field="name" title="Name" sortable></vxe-column>
          <vxe-column field="role" title="Role" sortable></vxe-column>
          <vxe-column field="rate" title="Rate" footer-align="center"></vxe-column>
          <vxe-column field="age" title="Age" footer-align="center"></vxe-column>
        </vxe-table>
        `,
        `
        export default {
          data () {
            return {
              mergeFooterItems: [
                { row: 0, col: 1, rowspan: 1, colspan: 3 }
              ],
              tableData: [
                { id: 10001, name: 'Test1', nickname: 'T1', role: 'Develop', sex: 'Man', age: 28, address: 'test abc' },
                { id: 10002, name: 'Test2', nickname: 'T2', role: 'Test', sex: 'Women', age: 22, address: 'Guangzhou' },
                { id: 10003, name: 'Test3', nickname: 'T3', role: 'PM', sex: 'Man', age: 32, address: 'Shanghai' },
                { id: 10004, name: 'Test4', nickname: 'T4', role: 'Designer', sex: 'Women', age: 23, address: 'test abc' },
                { id: 10005, name: 'Test5', nickname: 'T5', role: 'Develop', sex: 'Women', age: 30, address: 'Shanghai' },
                { id: 10006, name: 'Test6', nickname: 'T6', role: 'Designer', sex: 'Women', age: 21, address: 'test abc' },
                { id: 10007, name: 'Test7', nickname: 'T7', role: 'Test', sex: 'Man', age: 29, address: 'test abc' },
                { id: 10008, name: 'Test8', nickname: 'T8', role: 'Develop', sex: 'Man', age: 35, address: 'test abc' }
              ]
            }
          },
          methods: {
            meanNum (list, field) {
              let count = 0
              list.forEach(item => {
                count += Number(item[field])
              })
              return count / list.length
            },
            sumNum (list, field) {
              let count = 0
              list.forEach(item => {
                count += Number(item[field])
              })
              return count
            },
            footerMethod ({ columns, data }) {
              const footerData = [
                columns.map((column, _columnIndex) => {
                  if (_columnIndex === 0) {
                    return '平均'
                  }
                  if (['age', 'rate'].includes(column.field)) {
                    return this.meanNum(data, 'age')
                  }
                  if (['name'].includes(column.field)) {
                    return '合并了'
                  }
                  if (['content'].includes(column.field)) {
                    return '合并了'
                  }
                  return null
                }),
                columns.map((column, _columnIndex) => {
                  if (_columnIndex === 0) {
                    return '和值'
                  }
                  if (['age', 'rate'].includes(column.field)) {
                    return this.sumNum(data, 'age')
                  }
                  return null
                })
              ]
              return footerData
            }
          }
        }
        `,
        `
        <vxe-table
          border
          show-footer
          height="400"
          :footer-span-method="footerColspanMethod"
          :footer-method="footerMethod"
          :data="tableData">
          <vxe-column type="seq" width="60"></vxe-column>
          <vxe-column field="name" title="Name" sortable></vxe-column>
          <vxe-column field="role" title="Role" sortable></vxe-column>
          <vxe-column field="rate" title="Rate" footer-align="center"></vxe-column>
          <vxe-column field="age" title="Age" footer-align="center"></vxe-column>
        </vxe-table>
        `,
        `
        export default {
          data () {
            return {
              tableData: [
                { id: 10001, name: 'Test1', nickname: 'T1', role: 'Develop', sex: 'Man', age: 28, address: 'test abc' },
                { id: 10002, name: 'Test2', nickname: 'T2', role: 'Test', sex: 'Women', age: 22, address: 'Guangzhou' },
                { id: 10003, name: 'Test3', nickname: 'T3', role: 'PM', sex: 'Man', age: 32, address: 'Shanghai' },
                { id: 10004, name: 'Test4', nickname: 'T4', role: 'Designer', sex: 'Women', age: 23, address: 'test abc' },
                { id: 10005, name: 'Test5', nickname: 'T5', role: 'Develop', sex: 'Women', age: 30, address: 'Shanghai' },
                { id: 10006, name: 'Test6', nickname: 'T6', role: 'Designer', sex: 'Women', age: 21, address: 'test abc' },
                { id: 10007, name: 'Test7', nickname: 'T7', role: 'Test', sex: 'Man', age: 29, address: 'test abc' },
                { id: 10008, name: 'Test8', nickname: 'T8', role: 'Develop', sex: 'Man', age: 35, address: 'test abc' }
              ]
            }
          },
          methods: {
            meanNum (list, field) {
              let count = 0
              list.forEach(item => {
                count += Number(item[field])
              })
              return count / list.length
            },
            sumNum (list, field) {
              let count = 0
              list.forEach(item => {
                count += Number(item[field])
              })
              return count
            },
            footerMethod ({ columns, data }) {
              const footerData = [
                columns.map((column, _columnIndex) => {
                  if (_columnIndex === 0) {
                    return '平均'
                  }
                  if (['age', 'rate'].includes(column.field)) {
                    return this.meanNum(data, 'age')
                  }
                  if (['name'].includes(column.field)) {
                    return '合并了'
                  }
                  if (['content'].includes(column.field)) {
                    return '合并了'
                  }
                  return null
                }),
                columns.map((column, _columnIndex) => {
                  if (_columnIndex === 0) {
                    return '和值'
                  }
                  if (['age', 'rate'].includes(column.field)) {
                    return this.sumNum(data, 'age')
                  }
                  return null
                })
              ]
              return footerData
            },
            footerColspanMethod ({ _columnIndex }) {
              if ($rowIndex === 0) {
                if (_columnIndex === 1) {
                  return {
                    rowspan: 1,
                    colspan: 2
                  }
                } else if (_columnIndex === 2) {
                  return {
                    rowspan: 0,
                    colspan: 0
                  }
                }
              }
            }
          }
        }
        `,
        `
        <vxe-table
          border
          show-footer
          height="400"
          :footer-span-method="footerRowspanMethod"
          :footer-method="footerMethod"
          :data="tableData">
          <vxe-column type="seq" width="60"></vxe-column>
          <vxe-column field="name" title="Name" sortable></vxe-column>
          <vxe-column field="role" title="Role" sortable></vxe-column>
          <vxe-column field="rate" title="Rate" footer-align="center"></vxe-column>
          <vxe-column field="age" title="Age" footer-align="center"></vxe-column>
        </vxe-table>
        `,
        `
        export default {
          data () {
            return {
              tableData: [
                { id: 10001, name: 'Test1', nickname: 'T1', role: 'Develop', sex: 'Man', age: 28, address: 'test abc' },
                { id: 10002, name: 'Test2', nickname: 'T2', role: 'Test', sex: 'Women', age: 22, address: 'Guangzhou' },
                { id: 10003, name: 'Test3', nickname: 'T3', role: 'PM', sex: 'Man', age: 32, address: 'Shanghai' },
                { id: 10004, name: 'Test4', nickname: 'T4', role: 'Designer', sex: 'Women', age: 23, address: 'test abc' },
                { id: 10005, name: 'Test5', nickname: 'T5', role: 'Develop', sex: 'Women', age: 30, address: 'Shanghai' },
                { id: 10006, name: 'Test6', nickname: 'T6', role: 'Designer', sex: 'Women', age: 21, address: 'test abc' },
                { id: 10007, name: 'Test7', nickname: 'T7', role: 'Test', sex: 'Man', age: 29, address: 'test abc' },
                { id: 10008, name: 'Test8', nickname: 'T8', role: 'Develop', sex: 'Man', age: 35, address: 'test abc' }
              ]
            }
          },
          methods: {
            meanNum (list, field) {
              let count = 0
              list.forEach(item => {
                count += Number(item[field])
              })
              return count / list.length
            },
            sumNum (list, field) {
              let count = 0
              list.forEach(item => {
                count += Number(item[field])
              })
              return count
            },
            footerMethod ({ columns, data }) {
              const footerData = [
                columns.map((column, _columnIndex) => {
                  if (_columnIndex === 0) {
                    return '平均'
                  }
                  if (['age', 'rate'].includes(column.field)) {
                    return this.meanNum(data, 'age')
                  }
                  if (['name'].includes(column.field)) {
                    return '合并了'
                  }
                  if (['content'].includes(column.field)) {
                    return '合并了'
                  }
                  return null
                }),
                columns.map((column, _columnIndex) => {
                  if (_columnIndex === 0) {
                    return '和值'
                  }
                  if (['age', 'rate'].includes(column.field)) {
                    return this.sumNum(data, 'age')
                  }
                  return null
                })
              ]
              return footerData
            },
            footerRowspanMethod ({ _rowIndex, _columnIndex }) {
              if (_rowIndex === 0) {
                if (_columnIndex === 1) {
                  return { rowspan: 2, colspan: 1 }
                }
              } else if (_rowIndex === 1) {
                if (_columnIndex === 1) {
                  return { rowspan: 0, colspan: 0 }
                }
              }
            }
          }
        }
        `
      ]
    }
  },
  methods: {
    meanNum (list, field) {
      let count = 0
      list.forEach(item => {
        count += Number(item[field])
      })
      return count / list.length
    },
    sumNum (list, field) {
      let count = 0
      list.forEach(item => {
        count += Number(item[field])
      })
      return count
    },
    footerMethod ({ columns, data }) {
      const footerData = [
        columns.map((column, _columnIndex) => {
          if (_columnIndex === 0) {
            return '平均'
          }
          if (['age', 'rate'].includes(column.field)) {
            return this.meanNum(data, 'age')
          }
          if (['name'].includes(column.field)) {
            return '合并了'
          }
          if (['content'].includes(column.field)) {
            return '合并了'
          }
          return null
        }),
        columns.map((column, _columnIndex) => {
          if (_columnIndex === 0) {
            return '和值'
          }
          if (['age', 'rate'].includes(column.field)) {
            return this.sumNum(data, 'age')
          }
          return null
        })
      ]
      return footerData
    },
    footerColspanMethod ({ $rowIndex, _columnIndex }) {
      if ($rowIndex === 0) {
        if (_columnIndex === 1) {
          return {
            rowspan: 1,
            colspan: 2
          }
        } else if (_columnIndex === 2) {
          return {
            rowspan: 0,
            colspan: 0
          }
        }
      }
    },
    footerRowspanMethod ({ _rowIndex, _columnIndex }) {
      if (_rowIndex === 0) {
        if (_columnIndex === 1) {
          return { rowspan: 2, colspan: 1 }
        }
      } else if (_rowIndex === 1) {
        if (_columnIndex === 1) {
          return { rowspan: 0, colspan: 0 }
        }
      }
    }
  }
}
</script>
