<template>
  <div id="employee-form">
    <form v-on:submit.prevent="handleSubmit">
      <label>Employee name</label>
      <input type="text" v-model="employee.name"/>
      <label>Employee role</label>
      <input type="text" v-model="employee.role" />
      <button>Add Employee</button>
    </form>
  </div>
</template>

<script>
  export default {
    name: 'employee-form',
    data() {
      return {
        employee: {
          name: '',
          role: '',
        },
      }
    },
    methods: {
        handleSubmit() {
            this.$emit("add:employee", this.employee)
        },
    },
  }
</script>

<style scoped>
  form {
    margin-bottom: 2rem;
  }
</style>