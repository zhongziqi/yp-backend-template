<template lang="html">
  <div class="">
    <el-row :gutter='20' class="line_title">
      <el-col :span='16' style="display:flex;flex-direction:row;justify-content:space-content;">
        <el-col >
          <span class="title_head">筛选类别</span>
        </el-col>
        <el-col >
          <el-dropdown >
            <el-button type="primary" size='medium'>
              更多菜单<i class="el-icon-arrow-down el-icon--right"></i>
            </el-button>
            <el-dropdown-menu slot="dropdown">
              <el-dropdown-item>黄金糕</el-dropdown-item>
              <el-dropdown-item>狮子头</el-dropdown-item>
              <el-dropdown-item>螺蛳粉</el-dropdown-item>
              <el-dropdown-item>双皮奶</el-dropdown-item>
              <el-dropdown-item>蚵仔煎</el-dropdown-item>
            </el-dropdown-menu>
          </el-dropdown>
        </el-col>
        <el-col >
          <span class="title_head">筛选内容</span>
        </el-col>
        <el-col >
          <el-dropdown>
            <el-button type="primary" size='medium'>
              安装<i class="el-icon-arrow-down el-icon--right"></i>
            </el-button>
            <el-dropdown-menu slot="dropdown">
              <el-dropdown-item>黄金糕</el-dropdown-item>
              <el-dropdown-item>狮子头</el-dropdown-item>
              <el-dropdown-item>螺蛳粉</el-dropdown-item>
              <el-dropdown-item>双皮奶</el-dropdown-item>
              <el-dropdown-item>蚵仔煎</el-dropdown-item>
            </el-dropdown-menu>
          </el-dropdown>
        </el-col>
        <el-col >
          <el-date-picker
            type="date"
            style="width:160px;"
            placeholder="请选择下单时间">
          </el-date-picker>
        </el-col>
        <el-col >
          <el-input
            placeholder="搜索商家名称/订单编号"
            style="width:210px;"
            prefix-icon="el-icon-search">
          </el-input>
        </el-col>
        <el-col >
            <el-button type="primary" size='medium'>查询</el-button>
        </el-col>
      </el-col>
    </el-row>


    <!--全部订单  开始-->
    <div class="order_list box_radius">
      <el-tabs v-model="activeName2" type="card" >
        <el-tab-pane label="全部订单" name="first">
          <el-table
            :data="tableData"
            style="width: 100%;margin-top:20px;"
            >
            <el-table-column
              prop="date"
              label="订单编号"
              align='center'>
            </el-table-column>
            <el-table-column
              prop="name"
              label="商家名称"
              align='center'>
            </el-table-column>
            <el-table-column
              prop="address"
              align='center'
              label="客户姓名">
            </el-table-column>
            <el-table-column
              prop="address"
              align='center'
              label="派单客服">
            </el-table-column>
            <el-table-column
              prop="address"
              align='center'
              label="服务小哥">
            </el-table-column>
            <el-table-column
              prop="address"
              align='center'
              label="服务类型">
            </el-table-column>
            <el-table-column
              prop="address"
              align='center'
              label="服务地址">
            </el-table-column>
            <el-table-column
              prop="address"
              align='center'
              label="订单金额(元)">
            </el-table-column>
            <el-table-column
              prop="address"
              align='center'
              label="下单时间">
            </el-table-column>
            <el-table-column
              prop="address"
              align='center'
              label="完成时间">
            </el-table-column>
            <el-table-column
              prop="address"
              align='center'
              label="订单明细">
            </el-table-column>
            <el-table-column
              prop="address"
              align='center'
              label="状态">
            </el-table-column>

            <el-table-column
              prop="address"
              align='center'
              label="操作">
              <template  slot-scope="scope">
                <el-button size="mini" @click='btn_click(0)' type='primary' plain>查看详情</el-button>
              </template>
            </el-table-column>
          </el-table>

          <div class="pagination">
            <el-row type="flex"  justify="center">
              <el-pagination
                background
                layout="prev, pager, next"
                :total="1000">
              </el-pagination>
            </el-row>
          </div>
        </el-tab-pane>
        <el-tab-pane label="待预约" name="second">配置管理</el-tab-pane>
        <el-tab-pane label="待上门" name="third">角色管理</el-tab-pane>
        <el-tab-pane label="待服务" name="fourth">定时任务补偿</el-tab-pane>
        <el-tab-pane label="待确认" name="fifth">用户管理</el-tab-pane>
        <el-tab-pane label="已失效" name="sixth">配置管理</el-tab-pane>
        <el-tab-pane label="已取消" name="seventh">角色管理</el-tab-pane>
        <el-tab-pane label="异常" name="eighth">定时任务补偿</el-tab-pane>
      </el-tabs>
      <el-button class="excel" plain size='medium'>导出Excel</el-button>
    </div>
    <!--全部订单  结束-->

  </div>
</template>

<script>
export default {
  data(){
    return{
      activeName2: 'first',
      tableData: [{
           date: '2016-05-02',
           name: '王小虎',
           address: '上海市普陀区金沙江路 1518 弄'
         }, {
           date: '2016-05-04',
           name: '王小虎',
           address: '上海市普陀区金沙江路 1517 弄'
         }
       ]
    }
  }
}
</script>

<style lang="css" scoped>
  .excel{
    position: absolute;
    top: 4%;
    right: 2.5%;
  }
  .order_list{
    background: #fff;
    padding: 2% 2.5% 2.5% 3%;
    width: 95%;
    margin-top: 25px;
    position: relative;
  }
  .line_title{
    line-height: 40px;
  }
  .title_head{
    width: 64px;
    display: inline-block;
  }
</style>
