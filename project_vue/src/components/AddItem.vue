<template>
  <form v-on:submit.prevent="onSubmit">  <!--возможность не перезагружать форму всякий раз при нажатии на кнопку-->
    <input type="text" v-model="title">
    <button type="submit">Create</button>
  </form>   <!--тип кнопки submit -- отправить данные формы-->
</template>

<script>
export default {
  name: "AddItem",
  data(){
    return{
      title: ''
    }
  },
  methods: {
    onSubmit(){
      //console.log('sub', this.title)
      if (this.title.trim()) {
        const newItem = {
          id: Date.now(),
          title: this.title,
          completed: false
        }

        this.$emit('add_todo', newItem)
        //console.log(newItem)
        this.title=''
      }
    }
  }

}
</script>

<style scoped>
  form {
    display: flex;
  }
  input {
    margin-inline: 1rem;
    width: 12rem;
  }
</style>