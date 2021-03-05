<template>
  <div class="note">
    <ul>
      <li
        class="li"
        v-for="(item,index) in liList"
        :key="index"
      >
        <div
          class="no-content"
          :style="{'color': item.textColor}"
        >
          {{item.printf}}
        </div>
        <button @click="noRemove(index)">删 除</button>
      </li>
    </ul>
  </div>
</template>
<script>
export default {
  data () {
    return {
    }
  },
  props: {
    printf: String,
    color: String,
    liList: Array

  },
  methods: {
    noRemove (index) {
      alert("确认要删除吗？");
      this.liList.splice(index, 1);
      return
    }
  }
}
</script>
<style scoped>
.note {
  background: #254546;
  min-height: 400px;
  padding: 20px 0px;
}
.note ul {
  list-style: none;
  margin: 0;
  padding: 0;
}
.note ul li {
  display: flex;
  margin: 10px;
  align-items: center;
}
.note .no-content {
  width: 250px;
  min-height: 20px;
  background-color: #fff;
  margin: 10px;
  padding: 5px;
  border-radius: 10px;
}
.note button {
  width: 50px;
  height: 30px;
  justify-content: center;
  border-radius: 5px;
  border: none;
}
</style>
