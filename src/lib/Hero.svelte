<script>
   import { fade } from "svelte/transition";

   let slogan = ['Embrace', 'Nurture', 'Embody','Ignite']
   let index = 1;

   let selectedSlogan = slogan[0];

   setInterval(() => {
      selectedSlogan = slogan[index];
      index = (index + 1) % slogan.length;
   }, 3000);

   

</script>

<section>


    <div class="img">
      <!-- <p>We stand for passion, love, and the undying spirit that drives you forward. Nurture this inner flame into an inferno of self-expression, determination, and purpose.</p> -->
      <img src="./images/burnuz-1.jpg" alt="asd">
    </div>

    <div class="slogan">
      <h1> <span class="span-container"> 
        <span class="square-bracket">[</span>
         
        {#key selectedSlogan}
         <span class="embrace"> 
            {selectedSlogan} 
         </span>
        {/key}

        <span class="square-bracket">]</span> 
      </span> the flames within </h1>
    </div>
    
</section>

<style>
   section {
    height: 80vh;
    display: flex;
    justify-content: space-between;
    padding-inline: 4rem;
  }

  .slogan {
    width: min-content;
    margin-block: auto;
  }
  
  h1 {
    font-family: DGrotesque;
    font-size: 5rem;
    text-align: right;
    line-height: 6rem;
  }

  .span-container {
    width: 19rem;
    display: flex;
    justify-content: space-between;
  }

  .embrace {
    /* padding-top: 0.35rem; */
    animation: fade 3s;
  }

  .square-bracket {
   user-select: none;
  }

  .img {
    display: flex;
    align-items: center;
    background-color: #e5e5f7;
    background: repeating-linear-gradient( 45deg, var(--text), var(--text) 7px, var(--bg) 5px,  var(--bg) 45px );
  }

  .img {
    height: 300px;
    width: 45vw;
    transform: translate(2%, 20%);
  }

  img {
    width: 97%;
    height: 85%;
    transform: translateX(-5%);
    aspect-ratio: 16 / 9;
    object-fit: cover;
   
  }

  @keyframes fade {
   0% { opacity: 0; transform: translateY(1rem); }
   20% {opacity: 100; transform: translateY(0.35rem)}

   80% {opacity: 100; transform: translateY(0.35rem)}
   100% { opacity: 0; transform: translateY(-1rem);}
  }
</style>