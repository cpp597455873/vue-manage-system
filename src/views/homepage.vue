<template>
  <div>
    <el-table :data="urlList" style="width: 100%">
      <el-table-column label="url" width="300">
        <template #default="scope">
          <el-link :href="scope.row.url" target="_blank"><span class="url_hint">{{ scope.row.name }}</span></el-link>
        </template>
      </el-table-column>

      <el-table-column label="url">
        <template #default="scope">
          <el-link :href="scope.row.url" target="_blank"><span class="url_hint">{{ scope.row.url }}</span></el-link>
        </template>
      </el-table-column>
    </el-table>

<!--    <el-row :gutter="20">-->
<!--      <el-col :span="6" v-for="item in urlList">-->
<!--        <el-link :href="item.url" target="_blank"><span class="url_hint">{{ item.name }}</span>-->
<!--          {{ item.url }}-->
<!--        </el-link>-->
<!--      </el-col>-->
<!--    </el-row>-->
  </div>
</template>

<script setup lang="ts" name="dashboard">
import {reactive, ref} from 'vue';

const name = localStorage.getItem('ms_username');
const role: string = name === 'admin' ? '超级管理员' : '普通用户';

const urlList = ref([
  {
    "url": "http://182.43.15.227:7500",
    "name": "frps admin"
  },
  {
    "url": "http://182.43.15.227:17400",
    "name": "frpc201"
  },
  {
    "url": "http://182.43.15.227:17401",
    "name": "frpc200"
  },
  {
    "url": "http://182.43.15.227:18500",
    "name": "consul"
  },
  {
    "url": "http://182.43.15.227:13000",
    "name": "grafana"
  },
  {
    "url": "http://182.43.15.227:18848",
    "name": "nacos"
  },
  {
    "url": "http://182.43.15.227:19001",
    "name": "minio"
  },
  {
    "url": "http://182.43.15.227:19090",
    "name": "prometheus"
  }
    ])

const options = {
  type: 'bar',
  title: {
    text: '最近一周各品类销售图'
  },
  xRorate: 25,
  labels: ['周一', '周二', '周三', '周四', '周五'],
  datasets: [
    {
      label: '家电',
      data: [234, 278, 270, 190, 230]
    },
    {
      label: '百货',
      data: [164, 178, 190, 135, 160]
    },
    {
      label: '食品',
      data: [144, 198, 150, 235, 120]
    }
  ]
};
const options2 = {
  type: 'line',
  title: {
    text: '最近几个月各品类销售趋势图'
  },
  labels: ['6月', '7月', '8月', '9月', '10月'],
  datasets: [
    {
      label: '家电',
      data: [234, 278, 270, 190, 230]
    },
    {
      label: '百货',
      data: [164, 178, 150, 135, 160]
    },
    {
      label: '食品',
      data: [74, 118, 200, 235, 90]
    }
  ]
};
const todoList = reactive([
  {
    title: '今天要修复100个bug',
    status: false
  },
  {
    title: '今天要修复100个bug',
    status: false
  },
  {
    title: '今天要写100行代码加几个bug吧',
    status: false
  },
  {
    title: '今天要修复100个bug',
    status: false
  },
  {
    title: '今天要修复100个bug',
    status: true
  },
  {
    title: '今天要写100行代码加几个bug吧',
    status: true
  }
]);
</script>

<style scoped>
.el-row {
  margin-bottom: 20px;
}

.grid-content {
  display: flex;
  align-items: center;
  height: 100px;
}

.grid-cont-right {
  flex: 1;
  text-align: center;
  font-size: 14px;
  color: #999;
}

.grid-num {
  font-size: 30px;
  font-weight: bold;
}

.grid-con-icon {
  font-size: 50px;
  width: 100px;
  height: 100px;
  text-align: center;
  line-height: 100px;
  color: #fff;
}

.grid-con-1 .grid-con-icon {
  background: rgb(45, 140, 240);
}

.grid-con-1 .grid-num {
  color: rgb(45, 140, 240);
}

.grid-con-2 .grid-con-icon {
  background: rgb(100, 213, 114);
}

.grid-con-2 .grid-num {
  color: rgb(100, 213, 114);
}

.grid-con-3 .grid-con-icon {
  background: rgb(242, 94, 67);
}

.grid-con-3 .grid-num {
  color: rgb(242, 94, 67);
}

.user-info {
  display: flex;
  align-items: center;
  padding-bottom: 20px;
  border-bottom: 2px solid #ccc;
  margin-bottom: 20px;
}

.user-info-cont {
  padding-left: 50px;
  flex: 1;
  font-size: 14px;
  color: #999;
}

.user-info-cont div:first-child {
  font-size: 30px;
  color: #222;
}

.user-info-list {
  font-size: 14px;
  color: #999;
  line-height: 25px;
}

.user-info-list span {
  margin-left: 70px;
}

.mgb20 {
  margin-bottom: 20px;
}

.todo-item {
  font-size: 14px;
}

.todo-item-del {
  text-decoration: line-through;
  color: #999;
}

.schart {
  width: 100%;
  height: 300px;
}

.url_hint {
  color: dodgerblue;
  font-size: 20px;
  display: inline-block;
  margin-right: 4px;
  font-weight: bold;
}

</style>
