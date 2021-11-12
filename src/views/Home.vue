<template>
  <div class="bg-image">
    <PageSidebar></PageSidebar>
    <LoginNavBar></LoginNavBar>
    <b-container fluid class="login-content-container">
      <b-row align-v="center" class="login-content-child">
        <b-col>
          <b-row align-v="center" align-h="start">
            <p class="mt-4 mx-3 text-light h2 fw-bold text-left slogan">
              {{ slogan }}
            </p>
          </b-row>
          <b-row align-v="center" align-h="start">
            <b-col md="6">
              <div class="panel-bg-1 p-2 mt-2">
                <b-input-group class="address-group">
                  <template :v-slot="prepend">
                    <b-icon icon="geo-alt-fill" class="m-2"></b-icon>
                  </template>
                  <b-form-input
                    class="address-input"
                    v-model="address"
                    placeholder="輸入外送地址"
                  ></b-form-input>
                </b-input-group>
              </div>
            </b-col>
            <b-col md="auto">
              <div
                class="panel-bg-2 delivery p-2 mt-2"
                style="display: flex; justify-content: space-between"
              >
                <div class="m-2"><b-icon icon="clock-fill"></b-icon></div>
                <div class="m-2">立即外送</div>
                <div class="m-2"><b-icon icon="caret-down-fill"></b-icon></div>
              </div>
            </b-col>
            <b-col md="auto">
              <b-button size="lg" class="find-food w-100 mt-2"
                >尋找食物</b-button
              >
            </b-col>
          </b-row>
          <b-row align-h="start">
            <b-col cols="auto">
              <div class="mt-2">
                <b-link href="#" class="dark">登入</b-link
                ><span class="text-light">即可選擇您最近的地址</span>
              </div>
            </b-col>
          </b-row>
        </b-col>
      </b-row>
    </b-container>
    <b-container fluid>
      <b-row align-h="around">
        <b-col
          v-for="guide in guides"
          :key="guide.title"
          cols="auto"
          class="guide-panel"
        >
          <GuideCard
            :image="guide.image"
            :url="guide.url"
            :title="guide.title"
            :description="guide.description"
          ></GuideCard>
        </b-col>
      </b-row>
    </b-container>
    <PageFooter></PageFooter>
  </div>
</template>

<script>
import LoginNavBar from "@/components/LoginNavBar";
import GuideCard from "@/components/GuideCard";
import PageFooter from "@/components/PageFooter";
import PageSidebar from "@/components/PageSidebar";
export default {
  data() {
    return {
      address: "",
      guides: [
        {
          image: this.getGuideImage(),
          url: "",
          title: "以美食慰勞員工",
          description: "新增企業帳號",
        },
        {
          image: this.getGuideImage(),
          url: "",
          title: "協助貴餐廳外送美食",
          description: "新增您的餐廳",
        },
        {
          image: this.getGuideImage(),
          url: "",
          title: "透過平台上線外送",
          description: "註冊成為合作外送夥伴",
        },
      ],
    };
  },
  computed: {
    slogan() {
      const slogans = [
        "訂購美食，外送到府",
        "早午晚三餐，美味輪番登場",
        "簡單一指一按，盡享世界美食",
      ];
      return slogans[Math.floor(Math.random() * 3)];
    },
  },
  methods: {
    getGuideImage() {
      const id = [425, 490, 42];
      return `https://picsum.photos/480/270/?image=${
        id[Math.floor(Math.random() * 3)]
      }`;
    },
  },
  components: {
    LoginNavBar,
    GuideCard,
    PageFooter,
    PageSidebar,
  },
};
</script>

<style scoped>
.bg-image {
  background-image: url("~@/assets/images/lily-banse--YHSwy6uqvk-unsplash.jpg");
  height: 100vh;
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
}
.panel-bg-1 {
  background-color: #eee;
}
.panel-bg-2 {
  background-color: #ddd;
}
.address-input {
  border: none;
  background-color: transparent;
}
.address-input:focus {
  outline: none !important;
  box-shadow: none;
  background-color: transparent;
}
.address-group {
  align-items: center;
}
.delivery {
  height: 3rem;
  align-items: center;
}
.find-food {
  border-radius: 0;
}
.login-content-container {
  height: 100%;
}
.guide-panel {
  margin-bottom: 3rem;
}
@media (min-width: 576px) {
  .login-content-container {
    height: 100%;
    margin-top: -3rem;
  }
  .login-content-child {
    height: 100%;
  }
  .slogan {
    font-size: 2.5rem;
    font-weight: 500;
    line-height: 1.2;
  }
  .guide-panel {
    margin-top: 3rem;
    margin-bottom: 3rem;
  }
}
</style>
