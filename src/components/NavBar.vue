<template>
  <q-header class="navigation" :class="{ 'header-background': isScrolled }">
    <q-toolbar class="flex justify-between">
      <img class="logo-image cursor-pointer" src="/LogoMain.svg" />
      <div v-if="$q.screen.gt.sm" class="flex">
        <q-select class="dropdown-label" borderless v-model="dropdownModel" :options="options" dropdown-icon="expand_more" />
        <q-btn class="text-white text-subtitle1 text-weight-bold q-ml-lg" flat>해외 개발자 활용 서비스</q-btn>
      </div>
      <q-btn v-if="$q.screen.gt.sm" unelevated border-radius="10px" rounded-borders
        class="text-weight-bolder bg-white rounded-borders btn-head">
        문의하기
      </q-btn>
      <q-btn v-if="$q.screen.lt.md" flat rounded-borders dense icon="menu">
        <q-menu>
          <q-list style="min-width: 80px">
            <q-item clickable v-close-popup>
              <q-select borderless v-model="dropdownModel" :options="options" dropdown-icon="expand_more" class="q-ml-sm"/>
            </q-item>
            <q-item clickable v-close-popup>
              <q-btn unelevated border-radius="10px" rounded-borders class="text-weight-bolder bg-white rounded-borders btn-head">문의하기</q-btn>
            </q-item>
          </q-list>
        </q-menu>
      </q-btn>
    </q-toolbar>
  </q-header>
</template>

<script>
import { defineComponent, ref, onMounted } from "vue";

export default defineComponent({
  name: "NavBar",
  setup() {
    const isScrolled = ref(false);

    const handleScroll = () => {
      isScrolled.value = window.scrollY > 0;
    };

    onMounted(() => {
      window.addEventListener("scroll", handleScroll);
    });

    return {
      isScrolled,
      dropdownModel: ref('채용'),
      options: [
        '채용', '해외 개발자 원격 채용', '외국인 원격 채용 (비개발 직군)', '한국어 가능 외국인 채용',
      ],
    };
  },
});
</script>

<style lang="scss">
.navigation {
  position: fixed;
  background-color: transparent;
  max-width: 100%;
  margin: 0px auto;
  color: white;
  @media (max-width: 600px) {
    padding: 20px;
  }
  @media (min-width: 601px) {
    padding: 15px;
  }
}

.q-list {
  border-radius: 8px;
}

.logo-image {
  width: 114px;
  height: 21px;
  position: relative;
  left: 10%;
}

.q-btn.rounded-borders {
  border-radius: 8px;
}

.header-background {
  background: linear-gradient(to right, rgba(38, 194, 185), rgba(40, 139, 231));
  transition: transform 1s ease-in-out;
}

.btn-head {
  position: relative;
  right: 10%;
  color: #4A77FF;
}

.dropdown-label div {
  color: white;
  font-size: 16px;
  font-weight: 900;
}

.dropdown-label div div div:nth-child(2) {
  font-size: 24px;
}
</style>
