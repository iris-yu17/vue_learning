<script>
import { onMounted, ref } from "vue";
export default {
  props: {},

  // 聲明emit, 讓人知道有個這邊有東西emit
  // 可這樣寫
  // emits:["CallBack"]

  // 另一種寫法, 可以做驗證emit資料是否正確
  // 若錯誤, emit仍會傳上去, 但console會有warning讓開發者知道
  emits: {
    CallBack: (num) => {
      if (num.value === 0) {
        return true;
      } else {
        return false;
      }
    },
  },

  // setup裏面第二個參數我們通常叫他content, 裡面有個emit函式, 可以幫我們把東西傳到父組件
  // setup(props, content) {
  setup(props, { emit }) {
    const num = ref(1);

    onMounted(() => {
      // 第一個參數: 父層要接收的事件名稱
      // 第二個參數: 要往上傳的內容
      emit("CallBack", num);
    });

    return {
      num,
    };
  },
};
</script>
<template>
  <h1>{{ num }}</h1>
</template>
<style></style>
