<template>

  <div id="nav">
    <el-row class="navrow" type="flex" justify="center">
      <el-col :span="4" class="block" @click="handleEnter('/')">
        <router-link to="/">首頁 Home</router-link>
      </el-col>
      <el-col :span="5" class="block" @click="handleEnter('2')">
        <router-link to="/example2">關於我 About Me</router-link>
      </el-col>
      <el-col :span="5" class="block" @click="handleEnter('3')">
        <router-link to="/example3">作品集 Profolio</router-link>
      </el-col>
      <el-col :span="5" class="block" @click="handleEnter('4')">
        <router-link to="/example4">文字工作 Writing</router-link>
      </el-col>
      <el-col :span="4" class="block" @click="handleEnter('5')">
        <router-link to="/example5">參與計畫 Project</router-link>
      </el-col>
    </el-row>
  </div>

  <router-view :key="$route.fullPath"/>
</template>

<script>
var html = document.documentElement;

export default {
  methods: {
    handleEnter(id) {
      if (id === '/') {
        this.$router.push("/");
      } else {
        this.$router.push("example" + id);
      }
    },
  },
};
</script>

<style>
.el-row{
  padding: 0;
}
.el-col {
  padding: 0;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: white;
}
.navrow{
  width: 95vw;
  height: 4vh;
  position: absolute;
  font-size: 0.1rem;
}
#nav {
  background-color: black;
  height: 5vh;
  width: 95vw;
  border-style: solid;
  border-color: white;
  border-width:2px;
  padding: 2px;
  position: fixed;
  z-index: 100;
  left: 2vw;
}

#nav a {
  font-weight: bold;
  color: white;
}

#nav a.router-link-exact-active {
  color: dimgray;
}
.block{
  cursor: pointer;
  background-color: black;
  border-width: 1px;
  border-style: solid;
  border-color: white;
  padding: 2px;
  height: 4vh;
  text-align:center;
  line-height: 4vh;
  float: left;
  margin-left: 2px;

}
.block:hover{
  transform: scale(1.1,1.1);
  z-index: 10;
}

</style>


