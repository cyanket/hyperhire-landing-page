<template>
  <q-page class="page-container">
    <div class="row page-container-row">
      <div class="col-12 col-md-6">
        <img class="tooltip" v-if="$q.screen.gt.sm" src="/Tooltip1.svg" ref="tooltipDesktop"/>
        <img v-else class="tooltip" src="/Tooltip1Mobile.svg" ref="tooltipMobile"/>
        <p class="first-text" ref="firstText">최고의 실력을 가진<br />외국인 인재를 찾고 계신가요?</p>
        <p class="sub-text" ref="subText">
          법률 및 인사관리 부담없이 <br v-if="$q.screen.gt.sm" />1주일 이내에
          원격으로 채용해보세요.
        </p>
        <p class="text-three" v-if="$q.screen.gt.sm">
          개발자가 필요하신가요?
        </p>
        <div class="row q-gutter tabs-container" ref="tabs" v-if="$q.screen.gt.sm">
          <div class="col-3">
            <hr class="hr-line" />
            <p class="tab-main-text">월 120만원</p>
            <p class="tab-sub-text">임금을 해당 국가를 기준으로 계산합니다.</p>
          </div>
          <div class="col-3 q-mx-lg">
            <hr class="hr-line" />
            <p class="tab-main-text">평균 월 120만원</p>
            <p class="tab-sub-text">임금을 해당 국가를 기준으로 계산합니다.</p>
          </div>
          <div class="col-3">
            <hr class="hr-line" />
            <p class="tab-main-text">평균 월 120만원</p>
            <p class="tab-sub-text">임금을 해당 국가를 기준으로 계산합니다.</p>
          </div>
        </div>
      </div>
      <div class="col-12 col-md-6">
        <div class="flex justify-center">
          <img class="tooltip" src="/Tooltip2.svg" ref="tooltipMobile"/>
        </div>
        <div class="flex justify-between cards-container" ref="carouselContainer">
          <div class="flex items-center">
            <q-icon class="cursor-pointer" size="lg" name="chevron_left"></q-icon>
          </div>
          <div class="carousel-container">
            <q-card class="carousel-card card-1">
              <div class="flex justify-center img-container">
                <img src="/Abhishek.png"/>
              </div>
              <p class="person-name-label text-center">Abhishek Gupta</p>
              <p class="person-experience-label text-center">마케팅 · 2y+</p>
              <div class="flex justify-center">
                <p class="person-badge">마케팅 콘텐츠 제작</p>
              </div>
              <div class="flex justify-center">
                <p class="person-badge">인스타그램 관리</p>
              </div>
              <div class="flex justify-center">
                <p class="person-badge">트위터 관리</p>
                <p class="person-badge">블로그 글 작성</p>
              </div>
            </q-card>
            <q-card class="carousel-card card-2">
              <div class="flex justify-center img-container">
                <img src="/Abhishek.png"/>
              </div>
              <p class="person-name-label text-center">Abhishek Gupta</p>
              <p class="person-experience-label text-center">마케팅 · 2y+</p>
              <div class="flex justify-center">
                <p class="person-badge">마케팅 콘텐츠 제작</p>
              </div>
              <div class="flex justify-center">
                <p class="person-badge">인스타그램 관리</p>
              </div>
              <div class="flex justify-center">
                <p class="person-badge">트위터 관리</p>
                <p class="person-badge">블로그 글 작성</p>
              </div>
            </q-card>
            <q-card class="carousel-card card-3">
              <div class="flex justify-center img-container">
                <img src="/Abhishek.png"/>
              </div>
              <p class="person-name-label text-center">Abhishek Gupta</p>
              <p class="person-experience-label text-center">마케팅 · 2y+</p>
              <div class="flex justify-center">
                <p class="person-badge">마케팅 콘텐츠 제작</p>
              </div>
              <div class="flex justify-center">
                <p class="person-badge">인스타그램 관리</p>
              </div>
              <div class="flex justify-center">
                <p class="person-badge">트위터 관리</p>
                <p class="person-badge">블로그 글 작성</p>
              </div>
            </q-card>
          </div>
          <div class="flex items-center">
            <q-icon class="cursor-pointer" size="lg" name="chevron_right"></q-icon>
          </div>
        </div>
        <div v-if="$q.screen.lt.sm" class="checkbox-container">
          <div class="flex" v-if="$q.screen.lt.sm">
            <div class="flex checkbox-img-label">
              <img src="/Checkbox.svg"/>
              <p>한국어 능력</p>
            </div>
            <div class="flex checkbox-img-label">
              <img src="/Checkbox.svg"/>
              <p>업무 수행 능력</p>
            </div>
          </div>
          <div class="flex" v-if="$q.screen.lt.sm">
            <div class="flex items-center checkbox-img-label">
              <img src="/Checkbox.svg"/>
              <p>한국어 능력</p>
            </div>
            <div class="flex items-center checkbox-img-label">
              <img src="/Checkbox.svg"/>
              <p>업무 수행 능력</p>
            </div>
          </div>
        </div>
        <p class="mob-text" v-if="$q.screen.lt.sm">발자가 필요하신가요?</p>
      </div>
    </div>
    <div v-if="$q.screen.gt.sm" class="card-slides-container">
      <div class="card-wrapper flex">
        <q-card flat class="features-card" :style="{ transform: `translateX(${translateX}px)` }"
          v-for="(feature, index) in infiniteFeatures" :key="index">
          <img :src="feature.src"/>
          <q-card-section>{{ feature.name }}</q-card-section>
        </q-card>
      </div>
    </div>
  </q-page>
</template>

<script>
import { defineComponent, ref, onMounted } from "vue";
const features = [
  {
    src: "/img1.svg",
    name: "해외 마케팅",
  },
  {
    src: "/img2.svg",
    name: "퍼블리셔",
  },
  {
    src: "/img3.svg",
    name: "캐드원(제도사)",
  },
  {
    src: "/img4.svg",
    name: "해외 세일즈",
  },
  {
    src: "/img5.svg",
    name: "해외 CS",
  },
];
export default defineComponent({
  name: "ContentPage",
  setup() {
    const firstText = ref(null);
    const subText = ref(null);
    const tabs = ref(null);
    const tooltipDesktop = ref(null);
    const tooltipMobile = ref(null);
    const carouselContainer = ref(null);
    const currentIndex = ref(0);
    const translateX = ref(0);
    const infiniteFeatures = ref([]);
    const initInfiniteFeatures = () => {
      const iterations = 60;
      const repeatedFeatures = [];
      for (let i = 0; i < iterations; i++) {
        repeatedFeatures.push(...features);
      }
      infiniteFeatures.value = repeatedFeatures;
    };

    initInfiniteFeatures();

    const startSlider = () => {
      setInterval(() => {
        currentIndex.value = (currentIndex.value + 1) % features.length;
        translateX.value -= 340;
      }, 5000);
    };
    onMounted(() => {
      if (firstText.value) firstText.value.classList.add("fade-in-up");
      if (subText.value) subText.value.classList.add("fade-in-up");
      if (tabs.value) tabs.value.classList.add("fade-in");
      if (tooltipDesktop.value) tooltipDesktop.value.classList.add("fade-in-800");
      if (tooltipMobile.value) tooltipMobile.value.classList.add("fade-in-800");
      if (carouselContainer.value)
        carouselContainer.value.classList.add("fade-in");
    });
    startSlider();

    return {
      tooltipDesktop,
      tooltipMobile,
      tabs,
      firstText,
      carouselContainer,
      subText,
      features,
      translateX,
      infiniteFeatures,
    };
  },
});
</script>

<style lang="scss" scoped>
.page-container-row {
  @media (min-width: 601px) {
    margin-bottom: 40px;
  }
}
.cards-container {
  opacity: 0;
  transition: opacity 0.5s ease-in-out;
  height: 85%;
  @media (max-width: 600px) {
    margin-top: 20px;
  }
}
.first-text,
.sub-text {
  opacity: 0;
  transform: translateY(20px);
  transition: opacity 0.5s ease-in-out, transform 0.5s ease;
}
.fade-in-up {
  opacity: 1;
  transform: translateY(0);
}
.tabs-container {
  opacity: 0;
  transition: opacity 0.5s ease-in-out;
}
.fade-in {
  opacity: 1;
}
.tooltip {
  opacity: 0;
  transition: opacity 1.4s ease-in-out;
}
.fade-in-800 {
  opacity: 1;
}

.page-container {
  @media (max-width: 600px) {
    padding: 20px;
    padding-top: 40px;
  }
  @media (min-width: 601px) {
    padding-top: 60px;
  }
}
.first-text {
  @media (max-width: 600px) {
    font-size: 36px;
    font-weight: 900;
  }
  @media (min-width: 601px) {
    font-size: 45px;
    font-weight: 900;
  }
}
.sub-text {
  font-size: 24px;
  font-weight: 900;
  @media (max-width: 600px) {
    font-size: 18px;
    font-weight: 900;
  }
  @media (min-width: 601px) {
    font-size: 24px;
    font-weight: 900;
  }
}
.hr-line {
  margin-top: 50px;
  border-top: 0px;
}
.text-three {
  text-decoration: underline;
  font-weight: 900;
  font-size: 18px;
}
.tab-main-text {
  margin-top: 15px;
  font-weight: 900;
  font-size: 18px;
}
.tab-sub-text {
  margin-top: -10px;
  font-size: 16px;
}
.card-slides-container {
  width: 100%;
}

.card-wrapper {
  width: 100%;
  flex-wrap: nowrap;
  overflow-x: hidden;
}
.features-card {
  min-width: 332px !important;
  height: 88px;
  transition: transform 1s ease-in-out;
  background: rgba(255, 255, 255, 0.2);
  color: white;
  border-radius: 8px;
  margin-right: 8px;
  display: flex;
  align-items: center;
  padding: 0px 20px;
  img {
    width: 56px;
    height: 56px;
  }
  font-size: 24px;
  font-weight: bold;
}

.carousel-container {
  display: flex;
  justify-content: center;
  align-items: center;
  position: relative;
}

.carousel-card {
  @media (max-width: 600px) {
    width: 215.41px;
    height: 287px;
  }

  @media (min-width: 601px) {
    width: 259px;
    height: 370px;
  }
  border-radius: 12px;
  transition: transform 0.5s ease-in-out, opacity 0.5s ease-in-out;
  .img-container img {
    width: 120px;
    height: 120px;
    margin-top: 40px;
    @media (max-width: 600px) {
      width: 80px;
      height: 80px;
      margin-top: 20px;
    }
  }
  .person-name-label {
    color: #24252f;
    font-size: 24px;
    font-weight: 900;
    margin-top: 20px;
    @media (max-width: 600px) {
      font-size: 18px;
      font-weight: 900;
      margin-top: 10px;
    }
  }
  .person-experience-label {
    color: #4a77ff;
    font-size: 16px;
    font-weight: 900;
    margin-top: -15px;
    @media (max-width: 600px) {
      font-size: 14px;
      font-weight: 900;
      margin-top: -10px;
    }
  }
  .person-badge {
    color: #5e626f;
    border: 1.4px solid #c1c5cf;
    border-radius: 6px;
    padding: 4px 6px;
    font-weight: 900;
    font-size: 16px;
    max-width: 150px;
    margin: 4px 2px;
    @media (max-width: 600px) {
      font-size: 12px;
      font-weight: 900;
    }
  }
}

.card-1 {
  background-color: rgba(237, 252, 255, 1);
  position: absolute;
  left: -20px;
  @media (max-width: 600px) {
    left: -80px;
  }
  @media (min-width: 601px) {
    width: 259px;
    height: 370px;
  }
  .img-container img {
    width: 90px;
    height: 90px;
    margin-top: 40px;
    @media (max-width: 600px) {
      width: 40px;
      height: 40px;
      margin-top: 20px;
    }
  }
}

.card-2 {
  background-color: rgba(237, 252, 255, 1);
  position: absolute;
  right: -10px;
  @media (max-width: 600px) {
    right: -80px;
  }
  .img-container img {
    width: 90px;
    height: 90px;
    margin-top: 40px;
    @media (max-width: 600px) {
      width: 40px;
      height: 40px;
      margin-top: 20px;
    }
  }
}

.card-3 {
  background-color: white;
  position: absolute;
  width: 292px;
  height: 415px;
  @media (max-width: 600px) {
    width: 200.41px;
    height: 307px;
  }
}
.checkbox-container {
  margin-top: 30px;
  .checkbox-img-label {
    margin-left: 13px;
    padding-top: 4px;
    p {
      font-size: 16px;
      font-weight: 900;
      margin-top: 12px;
      margin-left: 4px;
    }
  }
}
.mob-text {
  color: #fbff23;
  font-size: 16px;
  font-weight: 900;
  margin-top: 12px;
  margin-left: 12px;
  text-decoration: underline;
}
</style>
