<template>
    <div class="carrossel">
      <slot></slot>
      <button @click="next" class="next">Next</button>
      <button @click="prev" class="prev">Prev</button>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        
      }
    },
    methods: {
      next() {
        this.$emit('next')
      },

      prev() {
        this.$emit('prev')
      },
    }
  }
  </script>
  
  <style>
    .carrossel {
      position: relative;
      width: 600px;
      height: 350px;
      overflow: hidden;
    }

    button {
      position: absolute;
      height: 40px;
      width: 50px;
      top: calc(50% - 20px);
      background-color: blanchedalmond;
      border: none;
      color: red;
    }

    button:active, button:hover {
      outline: none;
      cursor: pointer;
      background-color: rgb(209, 184, 146);
    }

    .next {
right: 0;    }

    .prev {
      left: 0;
    }


  </style>

  