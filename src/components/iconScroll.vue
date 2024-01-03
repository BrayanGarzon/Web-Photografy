<!-- FloatingButton.vue -->

<template>
    <div v-show="showButton" @click="scrollToTop" class="floating-button">
        <i class="fa-solid fa-chevron-up"></i>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        showButton: false
      };
    },
    methods: {
      scrollToTop() {
        window.scrollTo({ top: 0, behavior: 'smooth' });
      },
      handleScroll() {
        this.showButton = window.scrollY > 100; // Mostrar el botón cuando el usuario haya bajado 100 píxeles
      }
    },
    mounted() {
      window.addEventListener('scroll', this.handleScroll);
    },
    beforeDestroy() {
      window.removeEventListener('scroll', this.handleScroll);
    }
  };
  </script>
  
  <style scoped>
  .floating-button {
    position: fixed;
    width: 20px;
    bottom: 20px;
    right: 20px;
    background-color: var(--color-icons-primary);
    color: #fff;
    border: none;
    border-radius: 50%;
    padding: 10px;
    cursor: pointer;
    font-size: 20px;
    display: flex;
    align-items: center;
    justify-content: center;
    opacity: 0.8;
    transition: opacity 0.3s;
  }
  
  .floating-button:hover {
    opacity: 1;
  }

  .floating-button > i:hover{
    color: white;
  }
  </style>
  
  

