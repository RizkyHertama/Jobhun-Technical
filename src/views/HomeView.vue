<template>
    <section id="home">
       <div class="container">
           <div class="row align-items-center ">
               <div class="col-sm-12 col-lg-6">
                   <div class="home_text">
                       <h2>More Movie, More Fun!</h2>
                       <p>TV maze is a community of TV lovers and dedicated contributors that discuss and help maintain tv information on the web.</p>         
                       <div class="home-btn">
                            <a href="/movie" target="_blank"  class="btn btn-bordered mt-4"><span class="ti-control-play"></span>Watch Now!</a>
                        </div>  
                    </div>
               </div>
               <div class="col-sm-12 col-lg-6">
                   <div class="home-image">
                        
                           <img src="@/assets/img/Movie.svg" alt="home-image">
                   </div>
               </div>
           </div>
       </div>
   </section>

   
 
</template>

<script>
export default {
    data() {
      return {
      }
    }
  }
  
  
</script>

<style scoped>

/* HOME START */
#home{
        width: 100%;
        height: 100%;
        background: rgba(0, 0, 0, 0) url(@/assets/img/background.png) no-repeat scroll left center;
        background-size: cover;
        display:flex;
        align-items: center;
        justify-content:center;
        overflow:hidden;
        height: 650px;
   }

   #home .home_text h2 {
       font-size: 3rem;
       font-weight: 700;
       line-height: 3.938rem;
       color: white;
       padding:1.063rem  0;
   }
   #home .home_text p{
       font-size: 1rem;
       color: white;
   }

   #home .home-btn{
        display:flex;
        align-items:center;
        justify-content:flex-start;
        flex-wrap: wrap;
        margin-bottom: 5%;
    }
    #home .home-btn .btn {
        padding: 1rem 3rem;
        margin-left: 1.5rem;
        color:white;
        display:flex;
        align-items:center;  
        justify-content:center;
        background-color: #a70000;
    }
    #home .home-btn .btn:first-child{
        margin-left:0;
    }

   .home-image{
       text-align: right;   
   }

   .home-image img{
       animation: float 12s ease-in-out infinite;
       width: 450px;
       height: auto;
    }

   @keyframes float{
       0%, 100%{
           transform: translateY(0rem);
       }
       50%{
           transform: translateY(-3.5rem);
       }
   }


    @media(max-width: 767px) {
    #home .home_text h2 {
        font-size: 34px;
        line-height: 2.938rem;
    }

    .home-image{
      display: flex;
      justify-content: center;
      margin-top: 20%; 
   }
    .home-image img{
       width: 250px;
    }

    
    
   }

</style>