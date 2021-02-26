<template>
  <div>
    <el-table
      :data="tableData"
      style="width: 100%;margin-bottom: 20px;"
      row-key="id"
      border
      default-expand-all
      :tree-props="{ children: 'children', hasChildren: 'hasChildren' }"
    >
      <el-table-column
        prop="date"
        label="日期"
        sortable
        width="180"
      />
      <el-table-column
        prop="name"
        label="姓名"
        sortable
        width="180"
      />
      <el-table-column prop="address" label="地址" />
    </el-table>
  </div>
</template>
<script>
export default {
  data() {
    return {
      tableData: [
        {
          id: 1,
          date: '2016-05-02',
          name: '1',
          address: '上海市普陀区金沙江路 1518 弄',
          children: [
            {
              id: 11,
              date: '2016-05-01',
              name: '11',
              address: '上海市普陀区金沙江路 1519 弄',
              children: [
                {
                  id: 111,
                  date: '2016-05-01',
                  name: '111',
                  address: '上海市普陀区金沙江路 1519 弄',
                },
                {
                  id: 112,
                  date: '2016-05-01',
                  name: '112',
                  address: '上海市普陀区金沙江路 1519 弄',
                  children: [
                    {
                      id: 1121,
                      date: '2016-05-01',
                      name: '1121',
                      address: '上海市普陀区金沙江路 1519 弄',
                    },
                    {
                      id: 1122,
                      date: '2016-05-01',
                      name: '1122',
                      address: '上海市普陀区金沙江路 1519 弄',
                    },
                    {
                      id: 1123,
                      date: '2016-05-01',
                      name: '1123',
                      address: '上海市普陀区金沙江路 1519 弄',
                    },
                  ],
                },
                {
                  id: 113,
                  date: '2016-05-01',
                  name: '113',
                  address: '上海市普陀区金沙江路 1519 弄',
                },
              ],
            },
            {
              id: 12,
              date: '2016-05-01',
              name: '12',
              address: '上海市普陀区金沙江路 1519 弄',
            },
          ],
        },
        {
          id: 3,
          date: '2016-05-01',
          name: '王小虎',
          address: '上海市普陀区金沙江路 1519 弄',
          children: [
            {
              id: 31,
              date: '2016-05-01',
              name: '王小虎',
              address: '上海市普陀区金沙江路 1519 弄',
            },
            {
              id: 32,
              date: '2016-05-01',
              name: '王小虎',
              address: '上海市普陀区金沙江路 1519 弄',
            },
          ],
        },
      ],
      tableData1: [
        {
          id: 1,
          date: '2016-05-02',
          name: '王小虎',
          address: '上海市普陀区金沙江路 1518 弄',
        },
        {
          id: 2,
          date: '2016-05-04',
          name: '王小虎',
          address: '上海市普陀区金沙江路 1517 弄',
        },
        {
          id: 3,
          date: '2016-05-01',
          name: '王小虎',
          address: '上海市普陀区金沙江路 1519 弄',
          hasChildren: true,
        },
        {
          id: 4,
          date: '2016-05-03',
          name: '王小虎',
          address: '上海市普陀区金沙江路 1516 弄',
        },
      ],
    }
  },
  methods: {
    load(tree, treeNode, resolve) {
      setTimeout(() => {
        resolve([
          {
            id: 31,
            date: '2016-05-01',
            name: '王小虎',
            address: '上海市普陀区金沙江路 1519 弄',
          },
          {
            id: 32,
            date: '2016-05-01',
            name: '王小虎',
            address: '上海市普陀区金沙江路 1519 弄',
          },
        ])
      }, 1000)
    },
  },
}
</script>

<style>
.el-table__row {
  position: relative;
}

/* 根据数据 level 层级动态插入伪元素 */
.el-table__row--level-1 .el-table__indent::after {
  content: ' ';
  position: absolute;
  height: 102%;
  /* 宽度等于 indent（缩进） 值 */
  width: 16px;
  background: linear-gradient(90deg, transparent 40%, #eee 40%, transparent 50%);
  top: 0;
  background-size: 16px;
  left: 10px;
}

.el-table__row--level-2 .el-table__indent::after {
  content: ' ';
  position: absolute;
  height: 102%;
  width: 32px;
  background: linear-gradient(90deg, transparent 40%, #eee 40%, transparent 50%);
  top: 0;
  background-size: 16px;
  left: 10px;
}

.el-table__row--level-3 .el-table__indent::after {
  content: ' ';
  position: absolute;
  height: 102%;
  width: 48px;
  background: linear-gradient(90deg, transparent 40%, #eee 40%, transparent 50%);
  top: 0;
  background-size: 16px;
  left: 10px;
}
</style>
