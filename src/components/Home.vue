<script>
export default {
  data() {
    return {
      currentSlide: 0,
      slides: [
        'img/08.jpg',
        'img/09.jpg',
        'img/10.jpg',
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
            </div>
            
        </div>

        <!--SECTION DESCRIPTION PROFILE-->
        <div class="texto">
            <div class="description">
                <h2>Photography has become my language to express my thinking, emotions to people. I love working with people's life style. I love Photography.</h2>
            </div>
            <div class="firma">
                <img src="../../public/img/sign.png" alt="">
            </div>
        </div>


        <!--SECTION CARDS-->
        <div class="container-cards">
            <div class="gallery-wrap">
                <img src="../../public/img/gallery-1.jpg" alt="">
                <div class="gallery-content">
                    <h3>Everything for <br> the comfort of your <br> bedroom</h3>
                    <a href="img/gallery-1.jpg" class="gallery-link img-popup" target="_blank">Explore <i class="fa-solid fa-arrow-right"></i></a>
                </div>
            </div>
            <div class="gallery-wrap" id="gallery-2">
                <img  src="../../public/img/gallery-2.jpg" alt="">
                <div class="gallery-content">
                    <h3>Everything for <br> the comfort of your <br> bedroom</h3>
                    <a href="img/gallery-2.jpg" class="gallery-link img-popup" target="_blank">Explore <i class="fa-solid fa-arrow-right"></i></a>
                </div>
            </div>
            <div class="gallery-wrap">
                <img src="../../public/img/gallery-3.jpg" alt="">
                <div class="gallery-content">
                    <h3>Everything for <br> the comfort of your <br> bedroom</h3>
                    <a href="img/gallery-3.jpg" class="gallery-link img-popup" target="_blank">Explore <i class="fa-solid fa-arrow-right"></i></a>
                </div>
            </div>

            <div class="gallery-wrap" id="gallery-4">
                <img  src="../../public/img/gallery-4.jpg" alt="">
                <div class="gallery-content">
                    <h3>Everything for <br> the comfort of your <br> bedroom</h3>
                    <a href="img/gallery-4.jpg" class="gallery-link img-popup" target="_blank">Explore <i class="fa-solid fa-arrow-right"></i></a>
                </div>
            </div>

            <div class="gallery-wrap" id="gallery-6">
                <img  src="../../public/img/gallery-6.jpg" alt="">
                <div class="gallery-content">
                    <h3>Everything for <br> the comfort of your <br> bedroom</h3>
                    <a href="img/gallery-6.jpg" class="gallery-link img-popup" target="_blank">Explore <i class="fa-solid fa-arrow-right"></i></a>
                </div>
            </div>

            <div class="gallery-wrap" id="gallery-5">
                <img  src="../../public/img/gallery-5.jpg" alt="">
                <div class="gallery-content">
                    <h3>Everything for <br> the comfort of your <br> bedroom</h3>
                    <a href="img/gallery-5.jpg" class="gallery-link img-popup" target="_blank">Explore <i class="fa-solid fa-arrow-right"></i></a>
                </div>
            </div>
        </div>
    </section>
</template>


<style scoped>
    section{
        width: 100%;
        height: auto;
    }
 
    /*SECTION SLIDER */
    .slider {
        position: relative;
        
    }

    .profile-info {
        position: absolute;
        top: 0;
        left: 0;
        z-index: 2;
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



    
    /*SECTION IMAGE PROFILE */
    section .profile{
        width: 100%;
        display: flex;
        justify-content: center;
        align-items: center;
        position: relative;
    }
    section .profile .img-profile{
        width: 350px;
        height: 350px;
        border-radius: 50%;
        position: absolute;
        z-index: 2;
        background-image: url('../../public/img/profile.jpg');
        background-size: cover; 
        background-position: center;
        background-repeat: no-repeat;
    }
   



    /* SECTION DESCRIPTION PROFILE */
   section .texto{
    margin: 200px 100px 20px 100px;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
   }
   section .texto .description{
    width: 40%;
    text-align: center;
   }
   section .texto .description h2{
    font-size: 26px;
    color: white;
    font-weight: 800;
    line-height: 1.2;
   }
   section .texto .firma{
    margin-top: 20px;
   }
   section .texto .firma img{
    width: 200px;
   }



   /* SECTION GALLERY */
   section .container-cards{
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    align-items: center;
    margin: 40px 400px 20px 400px;
    
   }
   section .container-cards .gallery-wrap{
    position: relative;
   }
   section .container-cards .gallery-wrap > img{
    width: 450px;
    margin: 30px;
    opacity: 0.5;
   }

   
   .container-cards #gallery-2{
        margin-top: -100px;
    }
    .container-cards #gallery-4{
        margin-top: -400px;
    }
    .container-cards #gallery-6{
        margin-top: -100px;
    }
    .container-cards #gallery-5{
        margin-top: -200px;
    }


   section .container-cards .gallery-wrap .gallery-content{
    position: absolute;
    z-index: 1;
    top: 100px;
   }
   section .container-cards .gallery-wrap .gallery-content h3{
    font-size: 28px;
    color: white;
    line-height: 1.3;
    margin: 0;
   }
   section .container-cards .gallery-wrap .gallery-content a{
    margin-top: 10px;
    color: var(--color-icons-primary);
    text-decoration: none;
    cursor: pointer;
    transition: all 0.3s ease-in-out;
    display: flex;
    justify-content: flex-start;
    align-items: center;
    flex-direction: row;
   }
   section .container-cards .gallery-wrap .gallery-content a:hover{
    color: white;
    margin-left: 5px;
   }
   section .container-cards .gallery-wrap .gallery-content a > i{
    margin-left: 5px;
    cursor: pointer;
   }
   

   /* MOBILE */
   @media only screen and (max-width: 600px){
        .slider{
            width: 100%;
            height: auto;
        }


        .profile-info .text{
            width: 100%;
            padding: 10px;
            margin: 10px;
        }
        .profile-info .text h2{
            font-size: 26px;
            line-height: 20px;
        }





        /*SECTION IMAGE PROFILE */

        section .profile .img-profile{
            width: 300px;
            height: 300px;
            position: relative;
            margin-top: 50px;
        }

        section .texto{
            margin: 0;
            width: 100%;
        }
        section .texto .description{
            width: 100%;
        }
        section .texto .description h2{
            margin: 20px 10px;
        }




        /* SECTION GALLERY */

        section .container-cards{
            margin: 20px 10px;
        }
        section .container-cards .gallery-wrap > img{
            width: 320px;
        }

        .container-cards #gallery-2{
            margin-top: 0;
        }
        .container-cards #gallery-4{
            margin-top: 0;
        }
        .container-cards #gallery-6{
            margin-top: 0;
        }
        .container-cards #gallery-5{
            margin-top: 0;
        }

        section .container-cards .gallery-wrap .gallery-content{
            margin-left: 50px;
        }
        section .container-cards .gallery-wrap .gallery-content h3{
            font-size: 20px;
        }
    }



    /* TABLET */
    @media only screen and (max-width: 768px){

        /* SECTION DESCRIPTION PROFILE */
    section .texto{
        margin: 200px 20px 0px 20px;
        width: auto;
    }
    section .texto .description{
        width: 100%;
        text-align: center;
    }
    section .texto .description h2{
        font-size: 30px;
    }
    section .texto .firma img{
        width: 250px;
    }



    /* SECTION GALLERY */
    section .container-cards{
        margin: 0;
        
    }
    section .container-cards .gallery-wrap > img{
        width: 550px;
        margin: 30px;
        opacity: 0.5;
    }
    .container-cards #gallery-2{
        margin-top: 0;
    }
    .container-cards #gallery-4{
        margin-top: 0;
    }
    .container-cards #gallery-6{
        margin-top: 0;
    }
    .container-cards #gallery-5{
        margin-top: 0;
    }
    }


    /*LAPTOP AND LARGE SCREEN*/
    @media only screen and (min-width: 992px)  and (max-width: 1200px){
    section .container-cards{
        width: 100%;
        margin: 40px 0px;
    } 
    }
</style>
