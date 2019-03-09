<template>
  <div class="message">
    <Header title="我的消息"/>
    <template>
      <el-tabs v-model="activeName" @tab-click="handleClick">
        <el-tab-pane label="私信" name="first">
          <PeopleList class="item"/>
        </el-tab-pane>
        <el-tab-pane label="评论" name="second">评论</el-tab-pane>
        <el-tab-pane label="@我" name="third">@我</el-tab-pane>
        <el-tab-pane label="通知" name="fourth">通知</el-tab-pane>
      </el-tabs>
    </template>
  </div>
</template>
  </div>
</template>

<script>
import Header from "../../components/Header";
import PeopleList from "../../components/People_list";

export default {
  name: "Message",
  data() {
    return {
      activeName: "first"
    };
  },
  methods: {
    handleClick(tab, event) {
      // console.log(tab, event);
    }
  },
  components: {
    Header,
    PeopleList
  }
};
</script>

<style lang='less' scoped>
.item{
  padding: 0 10px;
}
</style>
<style lang='less'>
.message {
  .el-tabs__nav {
    width: 100%;
    .el-tabs__item {
      width: 25%;
      font-size: 14px;
      text-align: center;
    }
    .el-tabs__active-bar {
      background-color: #e41f6e;
    }
    .el-tabs__item.is-active {
      color: #e41f6e;
    }
  }
}
</style>