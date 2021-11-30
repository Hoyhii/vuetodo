<template>
  <div>
    <li>
      <div v-if="!edit">
        {{ title }}
        <button @click="edit">Edit</button>
      </div>
      <div v-if="edit">
          <input type="text" v-model="title">
          <button @click="Save">Save</button>
      </div>
      
    </li>
  </div>
</template>

<script>
export default {
  props: ["todo"],
  data() {
    return {
        title: this.title,
      edit: false,

    };
  },
  methods: {
      Edit(){
          this.edit = true;
      },
      Save(){
          this.edit = false;
          this.$emit('todo-item-changed',{
              original:this.todo,
              new:{
                  titel:this.text
              },
          });
      }
  }
};
</script>