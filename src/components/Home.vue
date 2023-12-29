<script>
export default {
  data() {
    return {
      currentSlide: 0,
      slides: [
        '../../public/img/08.jpg',
        '../../public/img/09.jpg',
        '../../public/img/10.jpg',
      ],
    };
  },
  mounted() {
    this.startSlider();
  },
  methods: {
    startSlider() {
        setInterval(() => {
            this.nextSlide();
        }, 3500);
    },
    nextSlide() {
        const nextIndex = (this.currentSlide + 1) % this.slides.length;

        // Oculta la imagen actual
        const currentImage = this.$refs.sliderImage;
        if (currentImage) {
            currentImage.style.opacity = 0;
        }

        // Cambia el índice de la diapositiva
        this.currentSlide = nextIndex;

        // Muestra la nueva imagen después de un breve retraso
        setTimeout(() => {
            if (currentImage) {
                currentImage.style.opacity = 1;
            }
        },300);
    },
},

};
</script>


<template>
    <section>

        <!--SECTION SLIDER-->
        <div class="slider">
            <div class="profile-info">
                <div class="text">
                    <h2>Elkin Esteban González</h2>
                    <span>Photographer</span>
                </div>            
            </div>
            <div class="slider-item">   
                <img v-if="slides.length" :src="slides[currentSlide]" alt="" ref="sliderImage">
                <div class="overlay"></div>
            </div>
        </div>

        <!--SECTION PROFILE-->
        <div class="profile">
            <div class="img-profile">
                <img src="" alt="">
            </div>
        </div>
    </section>
</template>


<style scoped>
    section{
        width: 100%;
        height: auto;
    }
 
    .slider {
        position: relative;
        
    }

    .profile-info {
        position: absolute;
        top: 0;
        left: 0;
        z-index: 2; /* Ajusta según sea necesario para colocar el perfil por encima del slider */
        width: 100%;
        height: 100%;
        display: flex;
        justify-content: center;
        align-items: center;
    }

    .profile-info .text {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    padding: 20px;
    position: relative;
}

    .profile-info .text:before,
    .profile-info .text:after{
        content: "";
        position: absolute;
        width: 20px;
        height: 20px; 
        border: 3px solid white;
    }

    .profile-info .text:before {
        border-bottom: none;
        border-right: none;
        top: 0;
        left: 0;
    }


    .profile-info .text:after {
        border-top: none;
        border-left: none;
        bottom: 0;
        right: 0;
    }



    .profile-info .text h2{
        font-size: 50px;
        font-weight: 800;
        color: white;
        margin: 0;
        padding: 0;
        text-transform: uppercase;
        line-height: 48px;
    }
    .profile-info .text span{
        font-size: 20px;
        font-weight: 800;
        color: white;
        text-transform: uppercase;
        letter-spacing: 6px;
    }

    .slider-item {
        position: relative;
        width: 100%;
        height: 100vh;
        overflow: hidden;
    }

    .slider-item img {
        margin: 0;
        padding: 0;
        height: 100%;
        width: 100%;
        object-fit: cover;
        transition: opacity 0.5s cubic-bezier(0.45, 0.05, 0.55, 0.95);
    }


    .slider-item .overlay {
        content: "";
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        background-color: rgba(0, 0, 0, 0.5); /* Fondo negro con opacidad ajustable */
        z-index: 1;
    }


    /*section prifile */
    section .profile{
        width: 100%;
        display: flex;
        justify-content: center;
        align-items: center;
    }
    section .profile .img-profile{
        width: 300px;
        height: 300px;
        background-color: aqua;
        border-radius: 50%;
    }
</style>
