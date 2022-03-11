<template>
  <div class="home-container">
    <Search />
    <div class="a-d-c" id="a">
      <template v-if="handleItemChecked === 1">
        <div class="a-d-c-i black-active">
          <img class="img-icon img-active" src="@/assets/images/1_3.png" />
          <i class="el-icon-plus item-active"></i>
          <h2 class="item-active">About Us</h2>
          <div class="item-content item-active">
            Read articles and whitepaper
          </div>
        </div>
      </template>
      <template v-else>
        <div class="a-d-c-i" @click="handleCheck(1)">
          <img class="img-icon" src="@/assets/images/1_3.png" />
          <i class="el-icon-plus"></i>
          <h2>About Us</h2>
          <div class="item-content">Read articles and whitepaper</div>
        </div>
      </template>

      <template v-if="handleItemChecked === 2">
        <div class="a-d-c-i black-active a-d-c-i-active">
          <img class="img-icon img-active" src="@/assets/images/1_2.png" />
          <i class="el-icon-plus item-active"></i>
          <h2 class="item-active">Developer Portal</h2>
          <div class="item-content item-active">
            Help us to enjoy a “first mover” advantage <br />
            by contributing early to the protocol.
          </div>
        </div>
      </template>
      <template v-else>
        <div class="a-d-c-i" @click="handleCheck(2)">
          <img class="img-icon" src="@/assets/images/1_2.png" />
          <i class="el-icon-plus"></i>
          <h2>Developer Portal</h2>
          <div class="item-content">
            Help us to enjoy a “first mover” advantage <br />
            by contributing early to the protocol.
          </div>
        </div>
      </template>

      <template v-if="handleItemChecked === 3">
        <div class="a-d-c-i black-active">
          <img class="img-icon img-active" src="@/assets/images/1_1.png" />
          <i class="el-icon-plus item-active"></i>
          <h2 class="item-active">Contact Us</h2>
          <div class="item-content item-active">
            Your individual transactions <br />
            are kept secure, always.
          </div>
        </div>
      </template>
      <template v-else>
        <div class="a-d-c-i" @click="handleCheck(3)">
          <img class="img-icon" src="@/assets/images/1_1.png" />
          <i class="el-icon-plus"></i>
          <h2>Contact Us</h2>
          <div class="item-content">
            Your individual transactions <br />
            are kept secure, always.
          </div>
        </div>
      </template>
    </div>
    <div id="b" class="developer-container"></div>
  </div>
</template>

<script>
export default {
  name: 'Home',
  data () {
    return {
      handleItemChecked: 1
    }
  },
  components: {},
  mounted () {
    /**
     * @param id 需要被 active 的内容
     */
    this.$bus.$on('handleItemChecked', id => {
      this.handleCheck(id)
    })
    // 子组件this.$bus.$emit('handleItemChecked',1);
  },
  methods: {
    handleCheck (id) {
      this.handleItemChecked = id
    }
  }
}
</script>
<style lang="less" scoped>
.home-container {
  width: 1600px;
  margin: 0 auto;
  .a-d-c {
    width: 1600px;
    height: 450px;
    display: flex;
    flex: 1;
    .a-d-c-i {
      width: 100%;
      position: relative;
      padding-left: 60px;
      background-color: #ffffff;

      .img-icon {
        margin: 60px 0 0 0;
        height: 50px;
      }
      .el-icon-plus {
        font-size: 35px;
        position: absolute;
        left: 430px;
        top: 80px;
      }
      h2 {
        font-size: 30px;
        margin: 40px 0 70px 0;
        color: #444f8c;
      }
      .item-content {
        font-size: 18px;
        color: #9f9f9f;
      }
      //供选中时使用
      .item-active {
        color: #ffffff;
      }
    }
    .a-d-c-i-active {
      &::after {
        height: 40px;
        width: 2px;
        content: "";
        background-color: #cecece;
      }
    }
    .img-active {
      // 只切了彩色图 过滤处理颜色成黑白
      filter: grayscale(100%) brightness(300%);
    }

    //供选中时使用
    .black-active {
      background-color: #7786eb;
    }
  }

  .developer-container {
    background-image: url(./images/icons.png);
  }
}
</style>
