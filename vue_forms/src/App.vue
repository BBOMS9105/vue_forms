<script>
export default {
  data(){
    return {
      str: "",
      field: "init",
      combo: "b",
      checkboxField: ["ban"],
      radioField: "",
    };
  },
  methods: {
    onInputHander(event) {
      this.str = event.target.value;
    },
    printData() { 
      console.log("textarea : " + this.field);
      console.log("option : " + this.combo);
      console.log("checkbox : " + this.checkboxField);
      console.log("radio : " + this.radioField);
    },
  },
};
</script>
<template>
  <!-- v-model은 한국어, 중국어, 일본어 등 IME가 필요한 문자열을
       실시간으로 읽어오는 데 제약이 있다. -->
  <!-- <textarea v-model="str" /> -->
  <!-- IME가 필요한 문자의 경우 -->
  <textarea @input="onInputHander($event)" />
  <p>글자 수 : {{ str.length }}</p>

  <h2>textarea, select</h2>
  <textarea v-model="field" />
  <select v-model="combo">
    <option value="a">a</option>
    <option value="b">b</option>
  </select>
  <br>
  <h2>checkbox</h2>
  <input type="checkbox" v-model="checkboxField" value="ban" />ban<br/>
  <input type="checkbox" v-model="checkboxField" value="orn" />orn<br/>
  <br>
  <h2>radio</h2>
  <input type="radio" v-model="radioField" name="gender" value="male"/>male<br/>
  <input type="radio" v-model="radioField" name="gender" value="female"/>female<br/>
  <button @click="printData">출력</button>
</template>