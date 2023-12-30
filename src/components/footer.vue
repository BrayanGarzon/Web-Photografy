<script>
export default {
  data() {
    return {
      currentYear: null,
    };
  },
  created() {
    // Calcula el año actual y asigna a currentYear
    this.currentYear = new Date().getFullYear();
  },
};
</script>


<template>

    <footer>
        <h2>Egaf</h2>
        <div class="icons">
            <a href=""><i class="fa-brands fa-facebook-f"></i></a>
            <a href=""><i class="fa-brands fa-twitter"></i></a>
            <a href=""><i class="fa-brands fa-instagram"></i></a>
            <a href=""><i class="fa-brands fa-pinterest"></i></a>
        </div>
        <p><span>&copy;</span> {{ currentYear }} EAGAF | Photography by <a href="www.brayangarzon.site" target="_blank">Brayan Garzón</a></p>
    </footer>
</template>


<style scoped>
    footer{
        width: 100%;
        height: auto;
        margin-bottom: 10px;
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;
    }
    footer h2{
        font-family: var(--font-family-footer);
        color: white;
        margin: 0;
        padding: 0;
        font-size: 40px;
    }

    footer .icons{
        width: 100%;
        display: flex;
        justify-content: center;
        align-items: center;
    }
    footer .icons a{
        background-color: var(--color-secundary);
        width: 40px;
        height: 40px;
        margin: 15px;
        display: flex;
        justify-content: center;
        align-items: center;
        text-decoration: none;
        border-radius: 2px;
    }
    a > i{
        color: var(--color-icons-primary);
    }
    a > i:hover{
        color: var(--color-icons-secundary);
    }
    footer > p{
        color: white;
        margin: 0;
        
    }
    footer p > a{
        text-decoration: none;
        color: brown;
    }
    footer p > a:hover{
        color: rgb(217, 29, 29);
    }
    span{
        color: brown;
    }
</style>