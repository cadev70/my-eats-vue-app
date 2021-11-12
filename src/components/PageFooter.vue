<template>
  <div class="footer-bg">
    <b-container fluid>
      <b-row>
        <b-col md="6">
          <b-container class="h-100 pt-4">
            <b-row class="h-50">
              <b-col class="p-3"
                ><BrandLabel
                  textClass="h2"
                  textVariant="white"
                  class="brand-label"
                ></BrandLabel
              ></b-col>
            </b-row>
            <b-row class="h-50" align-v="center">
              <b-col>
                <b-img
                  class="img-fluid"
                  :src="require('@/assets/images/app-store-badge.png')"
                ></b-img>
              </b-col>
              <b-col>
                <b-img
                  class="img-fluid"
                  :src="require('@/assets/images/google-play-badge.png')"
                ></b-img>
              </b-col>
            </b-row>
          </b-container>
        </b-col>
        <b-col md="3">
          <b-container class="h-100 pt-4">
            <b-row>
              <b-col><div class="text-link my-2">取得協助</div></b-col>
            </b-row>
            <b-row>
              <b-col><div class="text-link my-2">新增您的餐廳</div></b-col>
            </b-row>
            <b-row>
              <b-col
                ><div class="text-link my-2">註冊成為合作外送夥伴</div></b-col
              >
            </b-row>
            <b-row>
              <b-col><div class="text-link my-2">建立企業帳戶</div></b-col>
            </b-row>
            <b-row>
              <b-col
                ><div class="text-link my-2">首份訂單可享折扣優惠</div></b-col
              >
            </b-row>
          </b-container>
        </b-col>
        <b-col md="3">
          <b-container class="h-100 pt-4">
            <b-row>
              <b-col><div class="text-link my-2">我附近的美食外送</div></b-col>
            </b-row>
            <b-row>
              <b-col><div class="text-link my-2">檢視所有城市</div></b-col>
            </b-row>
            <b-row>
              <b-col><div class="text-link my-2">查看所有國家/地區</div></b-col>
            </b-row>
            <b-row>
              <b-col><div class="text-link my-2">閱讀我們的部落格</div></b-col>
            </b-row>
            <b-row>
              <b-col><div class="text-link my-2">關於 Uber Eats</div></b-col>
            </b-row>
            <b-row>
              <b-col><div class="text-link my-2">中文</div></b-col>
            </b-row>
          </b-container>
        </b-col>
      </b-row>
    </b-container>
  </div>
</template>
<script>
import BrandLabel from "@/components/BrandLabel";
export default {
  components: {
    BrandLabel,
  },
};
</script>
<style scoped>
.footer-bg {
  color: white;
  background-color: #010101;
}
.text-link {
  text-align: left;
  font-size: 0.9rem;
}
.brand-label {
  text-align: left;
}
</style>
