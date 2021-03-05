<template>
  <div class="notes">
    <note :liList="liList" />
    <div class="n-send">
      <textarea
        v-model="text"
        type="text"
        :style="{ 'color': textColor }"
      />
      <div class="n-color">
        <span @click="setColor(0)"></span>
        <span @click="setColor(1)"></span>
        <span @click="setColor(2)"></span>
      </div>
      <button @click="toNote">添 加</button>
    </div>
  </div>
</template>

<script>
import note from "./note"
export default {
  name: 'notes',
  components: {
    note
  },
  data () {
    return {
      printf: "",
      text: "",
      textColor: "",
      liList: []
    }
  },
  methods: {
    toNote () {
      if (this.text == 0) {
        this.text
      } else {
        let tempData = { printf: "", textColor: "" };
        tempData.printf = this.text;
        tempData.textColor = this.textColor;
        this.liList.push(tempData);
      }
      this.text = ""
    },
    setColor (num) {
      if (num == 0) {
        this.textColor = "#42bb85";
      } else if (num == 1) {
        this.textColor = "#ffa93c";
      } else {
        this.textColor = "#3296fa";
      }
    }
  }
}
</script>

<style scoped>
.notes {
  width: 350px;
  height: 500px;
  border: 1px solid #ccc;
  position: relative;
}
.n-send {
  width: 100%;
  height: 80px;
  position: absolute;
  bottom: 0;
  display: flex;
  border-top: 1px solid #ccc;
  background-color: #eee;
}
.n-send textarea {
  width: 200px;
  height: 50px;
  margin: 10px;
  border: 1px solid #eee;
  border-radius: 10px;
  outline: none;
  resize: none;
}
.n-color {
  width: 30px;
  height: 80px;
}
.n-color span {
  display: block;
  width: 15px;
  height: 15px;
  margin: 8px 5px;
  border-radius: 50%;
}
.n-color span:nth-child(1) {
  background-color: #42bb85;
}
.n-color span:nth-child(2) {
  background-color: #ffa93c;
}
.n-color span:nth-child(3) {
  background-color: #3296fa;
}
.n-send button {
  width: 70px;
  height: 50px;
  margin: 15px 10px;
  border-radius: 20px;
  background-color: #bc85ff;
  color: #fff;
  border: none;
  outline: none;
}
</style>
