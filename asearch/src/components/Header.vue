<template>
    <div class="header">
      <div class="logo_img" @click="logoClick">
        <img id="header-img" src="../assets/logo.png" >
        <div class="header-important">
          <div class="company_name">ARSEARCH</div>
          <div class="header-title company_name">ENTERNAL SPIRIT</div>
        </div>
      </div>
      <div id="menu_index">
        <el-menu menu-trigger="click" text-color="#333" style="height: 65px; border:0;" mode="horizontal" @select="handleSelect">
          <el-menu-item index="1" class="header-title">ABOUT US</el-menu-item>
          <el-menu-item index="2" class="header-title">NEWS</el-menu-item>
          <el-menu-item index="3" class="header-title">DEVELOPERS</el-menu-item>
          <el-menu-item index="4" class="header-title">JOBS</el-menu-item>
          <el-menu-item index="5" class="header-title">CONNECTS</el-menu-item>
        </el-menu>
        </div>
    </div>
</template>

<script>
export default {

}
</script>

<style scoped>
.logo_img{
  float:left;
  width: 30%;
  margin-top: 12px;
  cursor: pointer;
}
#back_to_top{
  position: fixed;
  bottom: 50px;
  right: 30px;
  cursor: pointer
}
.header-title{
  font-size: 1em;
}
.company_name{
  font-weight: normal;
  font-size: 1em;
}
.footer_font{
  font-size: 1em;
}
#menu_index{
  float: left;
  width: 50%;
  height: 100%
}
.header{
  margin: auto;
  width: 90%;
  height: 65px;
}
@media screen and (max-device-width: 415px) {
  .logo_img{
    float:left;
    width: auto;
    cursor: pointer;
  }
  #back_to_top{
    position: fixed;
    bottom: 50px;
    right: 5px;
    cursor: pointer
  }
  .footer_font{
    font-size: 0.875em;
  }
  #menu_index{
    float: right;
    width: auto;
    height: 100%
  }
}
.main{
  margin: auto;
  float: left;
  width: 100%;
  border: 0;
 }
#header-img{
  width: 50px;
  height: 50px;
  float: left;
  margin: auto;
    }
.header-important{
  float: left;
  margin-left: 6px;
  align-self: center;
}
</style>
