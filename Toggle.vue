<template>
  <div @click="$emit('update:active', !active)">
    <label :for="id">{{ label }}</label>
    <input type="checkbox" :name="name" :id="id" :checked="active" hidden aria-hidden="true">
    <div class="toggle"></div>
  </div>
</template>

<script>
  export default {
    name: 'Toggle',
    props: {
      name: {
        type: String,
        default: ''
      },
      id: {
        type: String,
        default: () => {
          return  'toggle-' + Math.random().toString(36).substr(2, 9);
        }
      },
      label: {
        type: String,
        default: ''
      },
      active: {
        type: Boolean,
        default: false
      }
    }
  }
</script>

<style scoped>
  label {
    display: inline-block;
    width: 120px;
  }
  .toggle {
    border: 2px solid black;
    border-radius: 12px;
    cursor: pointer;
    display: inline-block;
    height: 16px;
    position: relative;
    transition: all;
    vertical-align: middle;
    width: 45px;
  }
  .toggle:after {
    background-color: black;
    border-radius: 50%;
    content: '';
    display: block;
    position: absolute;
    right: 32px;
    height: 10px;
    top: 3px;
    transition: all 400ms;
    width: 10px;
  }
  input:checked + .toggle {
    background-color: rgb(67, 119, 211);
    border: 2px solid rgb(67, 119, 211);
  }
  input:checked + .toggle:after {
    background-color: #fff;
    right: 2px;
  }

</style>