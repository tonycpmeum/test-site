<script>
   const root = document.querySelector(':root');

   let darkTheme = false;

   $: {
      if (darkTheme == true) {
         root.style.setProperty('--bg', '#242424')
         root.style.setProperty('--bg2', '#343434')
         root.style.setProperty('--text', '#fff')
         root.style.setProperty('--border', '#a6a6a6')
      } else {
         root.style.setProperty('--bg', 'rgb(214, 214, 214)')
         root.style.setProperty('--bg2', '#a6a6a6')
         root.style.setProperty('--text', '#242424')
         root.style.setProperty('--border', '#5e5e5e')
      }
   }
</script>

<header>
   <h1 class="logo" on:click={() => {
      darkTheme = !darkTheme
      console.log(darkTheme)
   }}>BURNUZ*</h1>

   <nav>
      <a href="/shop" class="link shop">Shop</a>
   </nav>
</header>

<style>

   header {
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 2rem 0.5rem;
      position: sticky;
      top: 0;
      z-index: +1;
   }

   .logo {
      cursor: pointer;
   }

   nav {
      display: flex;
      gap: 2rem;
      padding-right: 1rem;
      
      /* background-color: var(--bg2); */
      
   }

   a {
      font-family: RalewayB;
      font-size: 1.5rem;
      padding-block: 0.45rem;
   }

   a:first-child {
      margin-left: auto;
   }

   .shop {
      margin-left: auto;
      padding-inline: 0.5rem;
      position: relative;
      overflow: hidden;
   }

   .shop::before {
      content: '';
      background-color: var(--text);
      position: absolute;
      bottom: 0px;
      height: 3px;
      width: 4ch;
      transition: transform 0.16s 0.16s;
      
   }
   
   .shop:hover::before {
      transform: translateX(150%);
      transition: transform 0.16s;
   }

   .shop::after {
      content: '';
      background-color: var(--text);
      position: absolute;
      bottom: 0px;
      height: 3px;
      width: 4ch;
      left: 50%;
      transform: translateX(-200%);
      transition: transform 0.16s;
   }
   
   .shop:hover::after {
      transform: translateX(-50%);
      transition: transform 0.16s 0.16s;
   }

  h1 {
      font-family: RalewayB;
      font-size: 2.5rem;
   }
</style>