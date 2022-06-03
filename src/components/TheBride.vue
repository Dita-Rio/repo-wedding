<template>
  <section class="bride flex flex-col text-white w-screen h-screen">
    <h4
      class="muli-light px-8 py-6 text-2xl font-light"
      :class="state.isShow ? 'surat-animate' : ''"
    >
      The <br />
      Bride
    </h4>
    <div
      class="car flex flex-col name-animate justify-around bg-black/[.25] border-2 w-2/3 p-5 h-1/5 rounded-3xl m-auto muli-light"
    >
      <span class="hairline"></span>
      <span class="name muli-light"
        >DITA NUR <br />
        FADILAH
      </span>
      <br />
      <div class="muli-light text-xs">
        <strong>Putri pertama dari</strong>
        <span> Bapak Ahmad Supriadi dan Ibu Rita Rahyuni</span>
      </div>
    </div>
  </section>
</template>
<script lang="ts" setup>
import { onMounted, reactive, ref } from 'vue';
import { isInViewport } from '../utils/screen';

const state = reactive({
  isShow: false
});

const scrollEvent = (e: any) => {
  const element = document.querySelector('.bride') as HTMLElement;
  isInViewport(element) ? (state.isShow = true) : (state.isShow = false);
};

onMounted(() => {
  window.addEventListener('scroll', scrollEvent, true);
});
</script>

<style>
.hairline {
  margin: auto;
  width: 50px;
  border: 1px solid white;
  content: '';
  height: 1px;
}
</style>
