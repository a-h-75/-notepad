<template>
<!-- template内には１つしかタグを入れることが出来ない為divで囲う必要がある -->
  <div class="new">
    <h1>New Memo</h1>
    <textarea name="memo" v-model="memoBody" id="" cols="" rows=""></textarea>
    <button @click="save">保存</button>
  </div>
</template>

<style scoped>
textarea {
  width: 100%;
  height: 10em;
  margin-bottom: 10px;
}

button {
  border: 1px solid #333;
  background-color: #333;
  color: #fff;
  padding: 10px 20px;
}

</style>
<script>
export default {
  name: "new",
  data: function() {
    return {
      memoBody: ""
    }
  },
  methods: {
    save: function() {
      // alert('保存されました');
      this.$store.commit("save", {
        body: this.memoBody
      });

      this.$router.push("/")
    }
  }

}

</script>