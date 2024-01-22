<script>
export default {
  data() {
    return {
      id: "lee",
    };
  }
};
</script>
<template>
  <!-- 단방향 데이터 바인딩 -->
  <input tupe="text" name="uid" :value="id" />
  {{ id }}
  <br>
  <!-- 양방향 데이터 바인딩 -->
  <input tupe="text" name="uid" v-model="id" />
  {{ id }}
</template>