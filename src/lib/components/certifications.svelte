<script>
  let tada = false;
  let y;

  $: tada = y > 2000;
</script>

<svelte:window bind:scrollY={y} />

<div class="relative">

  <img
  class="coolImage"
  class:curious={tada}
  alt="TADA!"
  src="lawnmower.png"
  >
  
  <img
  class="coolImage2"
  class:curious2={tada}
  alt="TADA!"
  src="trophy.png"
  >

  <div class="mx-auto text-center sm:py-6 md:py-8 lg:py-12 font-sans">
      <p class="title tracking-widest bg-green-800 p-4">Our Certifications</p>
  </div>
  
  <div class="container mx-auto lg:pt-10">
    <div class="certBox grid grid-cols-5 gap-2 text-center p-5">
  
      <div class="mx-auto">
        <img alt="cert1" src="cert.png">
      </div>
  
      <div class="mx-auto">
        <img alt="cert2" src="cert.png">
      </div>
  
      <div class="mx-auto">
        <img alt="cert3" src="cert.png">
      </div>
  
      <div class="mx-auto">
        <img alt="cert4" src="cert.png">
      </div>
  
      <div class="mx-auto">
        <img alt="cert5" src="cert.png">
      </div>
  
      <div class="mx-auto">
        <img alt="cert6" src="cert.png">
      </div>
  
      <div class="mx-auto">
        <img alt="cert7" src="cert.png">
      </div>
  
      <div class="mx-auto">
        <img alt="cert8" src="cert.png">
      </div>
  
      <div class="mx-auto">
        <img alt="cert9" src="cert.png">
      </div>
  
      <div class="mx-auto">
        <img alt="cert10" src="cert.png">
      </div>
  
      <div class="mx-auto">
        <img alt="cert11" src="cert.png">
      </div>
  
      <div class="mx-auto">
        <img alt="cert12" src="cert.png">
      </div>
  
      <div class="mx-auto">
        <img alt="cert13" src="cert.png">
      </div>
  
      <div class="mx-auto">
        <img alt="cert14" src="cert.png">
      </div>
  
      <div class="mx-auto">
        <img alt="cert15" src="cert.png">
      </div>
  
    </div>
  </div>
</div>

<style>

  @media screen and (min-width:0px) and (max-width:768px) {
    .title {
      color:white;
      font-weight: semibold;
      font-size: 30px;
      font-family: Verdana, sans-serif;
    }

    .certBox {
    /* color: green; */
    background-image: url("wood.jpg");
    background-repeat: no-repeat;
    /* background-attachment: fixed; */
    background-size: cover;
    }
  }

  @media screen and (min-width:768px) and (max-width:1024px) {
    .title {
    color:white;
    font-weight: semibold;
    font-size: 45px;
    font-family: Verdana, sans-serif;
    }

    .certBox {
    /* color: green; */
    border: 5px solid yellow;
    background-image: url("wood.jpg");
    background-repeat: no-repeat;
    /* background-attachment: fixed; */
    background-size: cover;
    }
  }

  @media screen and (min-width:1024px) and (max-width:1280px) {
    .title {
    color:white;
    font-weight: semibold;
    font-size: 60px;
    font-family: Verdana, sans-serif;
    }

    .certBox {
    /* color: green; */
    border: 5px solid yellow;
    background-image: url("wood.jpg");
    background-repeat: no-repeat;
    /* background-attachment: fixed; */
    background-size: cover;
    }
  }

  @media screen and (min-width:1280px) and (max-width:1536px) {
    .title {
    color:white;
    font-weight: semibold;
    font-size: 60px;
    font-family: Verdana, sans-serif;
    }

    .certBox {
    /* color: green; */
    border: 5px solid yellow;
    background-image: url("wood.jpg");
    background-repeat: no-repeat;
    /* background-attachment: fixed; */
    background-size: cover;
    }
  }

  @media screen and (min-width:1536px) {
    .title {
      color:white;
      font-weight: semibold;
      font-size: 50px;
      font-family: Verdana, sans-serif;
    }

    .certBox {
      /* color: green; */
      border: 5px solid yellow;
      background-image: url("wood.jpg");
      background-repeat: no-repeat;
      /* background-attachment: fixed; */
      background-size: cover;
    }

    .coolImage {
	    position: absolute;
      top: 60%;
      left: -3%;
      transform: translate(-100%, 0) rotate(-30deg);
	    transform-origin: 100% 100%;
	    transition: transform 0.4s;
    }

    .curious {
	    transform: translate(15%, 0) rotate(0deg);
    }

    .coolImage2 {
	    position: absolute;
      top: 60%;
      left: 79%;
	    transform: translate(100%, 0) rotate(30deg);
	    transform-origin: 100% 100%;
	    transition: transform 0.4s;
    }

    .curious2 {
	    transform: translate(12%, 0) rotate(0deg);
    }
  }

</style>

<!-- @media screen and (min-width:0px) and (max-width:768px) {

}

@media screen and (min-width:768px) and (max-width:1024px) {

}

@media screen and (min-width:1024px) and (max-width:1280px) {

}

@media screen and (min-width:1280px) and (max-width:1536px) {

}

@media screen and (min-width:1536px) {

} -->