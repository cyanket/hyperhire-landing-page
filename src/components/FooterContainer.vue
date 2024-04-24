<template>
  <q-footer class="footer">
    <div class="footer-bottom">
      <div class="row">
        <div class="col-12 col-md-4">
          <img src="/FooterLogo.svg"/>
          <p class="text-subtitle1 text-weight-bolder">우리는 국가의 장벽을 넘어 최고의 인재를 매<br />칭해드립니다.</p>
          <p class="text-weight-bolder text-sub-footer grey-color">010-0000-0000</p>
          <p class="text-weight-bolder text-sub-footer grey-color">aaaaa@naver.com</p>
        </div>
        <div class="col-12 col-md-8">
          <div class="row cards-row">
            <div v-for="(item, index) in footerDetails" :key="index" class="col-6 col-md-3">
              <q-card flat rounded-borders class="footer-card">
                <q-card-section>
                  <img :src="item.src"/>
                </q-card-section>
                <p class="footer-content-item text-weight-bolder text-subtitle2">{{ item.name }}</p>
                <div class="flex align-center items-start cursor-pointer text-arrow">
                  <p class="footer-content-item text-weight-bolder">바로가기</p>
                  <img src="/footer-arrow-right.svg" class="q-ml-sm"/>
                </div>
              </q-card>
            </div>
          </div>
        </div>
      </div>
      <div class="row" :class="$q.screen.lt.sm ? 'q-mt-md' : 'q-mt-xl'">
        <div class="col-12 col-md-4">
          <div class="row" :class="$q.screen.lt.sm ? 'q-mt-md' : ''">
            <div class="col-6">
              <p class="text-subtitle2 text-sub-footer text-weight-bolder">상호명</p>
              <p class="text-sub-footer grey-color text-weight-bolder">하이퍼하이어</p>
              <p class="text-weight-bolder text-sub-footer grey-color">Hyperhire India Private Limited</p>
            </div>
            <div class="col-6 q-pl-md">
              <p class="text-subtitle2 text-sub-footer text-weight-bolder">대표 CEO</p>
              <p class="text-sub-footer text-weight-bolder grey-color">김주현</p>
              <p class="text-weight-bolder text-sub-footer grey-color">Juhyun Kim</p>
            </div>
          </div>
        </div>
        <div class="col-12 col-md-8">
          <div class="row cards-row">
            <div class="row" :class="$q.screen.lt.sm ? 'q-mt-md' : ''">
              <div class="col-12 col-md-3">
                <p class="text-subtitle2 text-sub-footer text-weight-bolder">사업자등록번호 CIN</p>
                <p class="text-sub-footer text-weight-bolder grey-color">427-86-01187</p>
                <p class="text-weight-bolder text-sub-footer grey-color">U74110DL2016PTC290812</p>
              </div>
              <div class="col-12 col-md-8" :class="$q.screen.lt.sm ? 'q-mt-md' : 'q-ml-lg'">
                <p class="text-subtitle2 text-sub-footer text-weight-bolder">주소 ADDRESS</p>
                <p class="text-sub-footer text-weight-bolder grey-color">서울특별시 강남대로479, 지하 1층 238호</p>
                <p class="text-weight-bolder text-sub-footer grey-color">
                  D-138, Street number 11, Jagjeet Nagar, North East Delhi, New Delhi, 110053 India
                </p>
              </div>
            </div>
          </div>
        </div>
      </div>
      <br>
      <div class="col-12 col-md-4 q-pb-xl">
        <p class="text-weight-bolder text-sub-footer grey-color">ⓒ 2023 Hyperhire</p>
      </div>
    </div>
  </q-footer>
</template>

<script>
import { defineComponent, ref } from "vue";
export default defineComponent({
  name: "FooterContainer",
  setup() {
    const footerDetails = ref([
      {
        src: "/footer1.svg",
        name: "해외 개발자 원격 채용",
      },
      {
        src: "/footer2.svg",
        name: "외국인 원격 채용 (비개발)",
      },
      {
        src: "/footer3.svg",
        name: "한국어 가능 외국인 채용",
      },
      {
        src: "/footer4.svg",
        name: "해외 개발자 활용 서비스",
      },
    ]);
    return {
      footerDetails,
    };
  },
});
</script>

<style lang="scss" scoped>
.footer {
  background-color: #fbfbfb;
  color: #343741;
  position: static !important; /* Override fixed positioning */
  @media (max-width: 600px) {
    padding: 20px;
    padding-top: 40px;
    height: 900px;
  }
  @media (min-width: 601px) {
    padding-top: 60px;
    height: 400px;
  }
}
.grey-color {
  color: #5E626F;
}
.footer-bottom {
  max-width: 1200px;
  margin: 0px auto;
}
.text-sub-footer {
  margin-bottom: 4px;
}
.footer-content-item {
  margin-bottom: 4px;
  margin-left: 15px;
}
.footer-card {
  margin-bottom: 7px;
  @media (max-width: 600px) {
    width: 160px;
    height: 163px;
  }
  @media (min-width: 601px) {
    width: 187px;
    height: 142px;
  }
}
.cards-row {
  margin-bottom: 4px;
}
.text-arrow {
  color: #5e626f;
  @media (max-width: 600px) {
    margin-top: 25px;
  }
  @media (min-width: 601px) {
    margin-top: 15px;
  }
}
</style>
