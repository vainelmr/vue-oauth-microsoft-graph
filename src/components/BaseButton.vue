<template>
    <button
      :class="buttonClass"
      :disabled="disabled"
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
      color:{
        type:String,
        default:'primary',
        validator: function (value){
            return ['primary', 'warn', 'danger'].includes(value)
        }
      }
    },
    computed: {
      buttonClass() {
        const classes = {
          'base-button': true,
          'base-button--disabled': this.disabled,
          [`base-button--${this.color}`]: this.color,
        };
          if (this.disabled) {
      classes['base-button--disabled-colored'] = true;
    } else {
      classes['base-button--disabled'] = false;
       }
    return classes;
      }
    },
  };

  </script>
  
  <style scoped>
  .base-button {
    padding: 10px 20px;
    font-size: 16px;
    color: white;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    width: 50%;
    transition: background-color 0.3s, transform 0.3s;
  }
  
  .base-button--disabled {
    background-color: #4caf4fb3 !important;
    cursor: not-allowed;
  }

  .base-button--primary {
    background-color: #4CAF50;
  }

  .base-button--primary:hover {
    background-color: #4caf4fb3;
  }

  .base-button--primary:focus {
    outline: 2px solid #5bd45f; 
  }

  .base-button--warn {
        background-color: #FFA500;
    }
    
    .base-button--warn:hover {
    background-color: #fbbc46;
  }

  .base-button--warn:focus {
    outline: 2px solid #ffd000; 
  }

  .base-button--danger {
        background-color: #FF0000;
    }

    .base-button--danger:hover {
    background-color: #fd6767;
  }

  .base-button--danger:focus {
    outline: 2px solid #ff3406; 
  }

  </style>
 