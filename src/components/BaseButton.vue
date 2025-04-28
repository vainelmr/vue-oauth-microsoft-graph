<template>
    <button
      :class="buttonClass"
      :style="buttonStyle"
      :disabled="disabled"
      @click="handleClick"
    >
      <slot></slot> 
    </button>
  </template>
  
  <script>
  export default {
    name: 'BaseButton',
    props: {
      disabled: {
        type: Boolean,
        default: false,
      },
      customStyle: {
        type: Object,
        default: () => ({}),
      },
    },
    computed: {
      buttonClass() {
        return {
          'base-button': true,
          'base-button--disabled': this.disabled,
        };
      },
      buttonStyle() {
        return this.customStyle;
      },
    },
    methods: {
      handleClick(event) {
        if (!this.disabled) {
          this.$emit('click', event); 
        }
      },
    },
  };
  </script>
  
  <style scoped>
  .base-button {
    padding: 10px 20px;
    font-size: 16px;
    color: white;
    background-color: #4CAF50;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    transition: background-color 0.3s, transform 0.3s;
  }
  
  .base-button:hover {
    background-color: #4caf4fb3;
  }
  
  .base-button:focus {
    outline: 2px solid #5bd45f; 
  }
  
  .base-button--disabled {
    background-color: #4caf4fb3; 
    cursor: not-allowed;
  }
  </style>
 