<link rel="stylesheet" href="https://demos.creative-tim.com/notus-js/assets/vendor/@fortawesome/fontawesome-free/css/all.min.css">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">

<script>
    import { images } from "$lib/components/imageData";
    import Slide from "$lib/components/slide.svelte";
    import Caption from "$lib/components/caption.svelte";
    import Thumbnail from "$lib/components/thumbnail.svelte";
    import Certifications from "$lib/components/certifications.svelte";
    import MiniNav from "$lib/components/miniNav.svelte";
    import MiniFoot from "$lib/components/miniFoot.svelte";
    import Testimonials from "$lib/components/testimonials.svelte";
    import BackToTop from "$lib/components/backToTop.svelte";

    let tada = false;
    let tada2 = false;
    let y;

    $: tada = y > 900;
    $: tada2 = y > 1400;
    let imageShowIndex = 0;
    // $: console.log(imageShowIndex);

    //const handleMouseenter = () => tada = true;
    //const handleMouseleave = () => tada = false;    

    const prevSlide = () => {
        if (imageShowIndex === 0) {
            imageShowIndex = images.length-1
        } else {
            imageShowIndex -= 1;
        }
    }

    const nextSlide = () => {
        if (imageShowIndex === images.length-1) {
            imageShowIndex = 0;
        } else {
            imageShowIndex += 1;
        }
    }

    const goToSlide = (idNumber) => imageShowIndex = idNumber;

</script>

<svelte:window bind:scrollY={y} />

<section class="pt-20 md:pt-0">

    <MiniNav />

    <BackToTop />
    
    <div class="text-center pt-8 px-7 md:pb-11 xl:px-72">
        <p class="basicText tracking-widest">"The grass is <b class="text-green-200">GREENEST</b> where we <b class="text-blue-300">WATER</b> it"</p>
    </div>
    
    <div class="p-5 grid grid-rows-1 gap-x-5 md:grid-cols-2 md:bg-green-100">

        <div class="img-move-wrapper mx-auto">
            <img alt="Lawn Mower" src="stock/volunteer.jpeg" class="mower img-move img-move-1 img-fluid">
            <img alt="Lawn Mower" src="stock/worker.jpeg" class="mower worker img-move img-move-2 img-fluid">
            <!-- this image is a placeholder so that the container has a responsive height. I am also hiding it on mobile because it is not needed when stacked. Here is more info on why this is needed > https://stackoverflow.com/questions/6319500/how-to-make-the-wrapping-div-element-with-relative-position-match-child-elements?rq=1 -->
            <img alt="Lawn Mower" src="stock/mower1.jpg" class="invisibleImage img-fluid invisible d-none d-md-block">
        </div>
    
        <div class="text-center xl:text-left lg:p-16">
            <p class="basicText2 py-3 md:py-10 xl:text-left">We use great quality tools that make sure we get the job done as clean as we possibly can. We leave absolutely nothing behind besides a fantastic looking yard!</p>
            <br class="para2">
            <p class="para2">Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Duis tristique sollicitudin nibh sit amet commodo. Risus viverra adipiscing at in. Tempus iaculis urna id volutpat</p>
            <br class="para3">
            <div class="para3 grid grid-rows-1 xl:grid-cols-2 xl:pt-10">
                <div class="text-center py-2 lg:py-8">
                    <div align="center"><a class="mainButton" href="#" target="_blank" rel="nofollow noopener noreferrer" draggable="false"><i class="text-white fa fa-file-text"></i> Schedule An Appointment</a></div>
                </div>
                <div class="text-center py-2 lg:py-8">
                    <div align="center"><a class="mainButton" href="#" target="_blank" rel="nofollow noopener noreferrer" draggable="false"><i class="text-white fa fa-phone"></i> Contact Us</a></div>
                </div>
            </div>
        </div>
    
    </div>
    
    <div class="text-center md:py-10 xl:grid xl:grid-cols-2 xl:gap-x-16">
        <div class="xl:p-10">
            <main>
                <!-- Container for the image gallery -->
                <div class="container mx-auto">
                    {#each images as {id, name, imgUrl, attribution} }
                    <Slide  image={imgUrl}
                            altTag={name}
                            attr={attribution} 
                            slideNumber={id+1}
                            totalSlides={images.length} 
                            imageShowing={id === imageShowIndex} />
                    {/each}
                </div>
                
                <Caption caption={images[imageShowIndex].name} on:prevClick={prevSlide} on:nextClick={nextSlide} />
            
                <div class="thumbnails-row">
                    {#each images as {id, imgUrl, name}}
                        <Thumbnail  thumbImg={imgUrl}
                                    altTag={name}
                                    selected={id === imageShowIndex}
                                    on:click={() => goToSlide(id)} />
                    {/each}
                </div>
        
            </main>
        </div>

        <div class="pt-10 md:pt-5 lg:p-10">
            <p class="titleText tracking-wider md:tracking-widest lg:rounded-3xl">Testimonials</p>
            <Testimonials />
        </div>
    </div>


    <div class="text-center pt-10 lg:pt-3 px-6">
        <p class="basicText tracking-wider font-semibold">
            When you book an appointment with us, we make sure to come prepared!
        </p>
    </div>

    <div class="relative text-center py-8">
        <div class="farmers">
            <img
            class="farmer1"
            class:curious={tada}
            alt="TADA!"
            src="farmer1.png"
            >
            
            <img
            class="farmer2"
            class:curious2={tada}
            alt="TADA!"
            src="farmer2.png"
            >

            <img
            class="farmer3"
            class:curious={tada2}
            alt="TADA!"
            src="farmer1.png"
            >
            
            <img
            class="farmer4"
            class:curious2={tada2}
            alt="TADA!"
            src="farmer2.png"
            >
        </div>
        <div class="text-center py-2 lg:py-8">
            <div align="center"><a class="mainButton2" href="#" target="_blank" rel="nofollow noopener noreferrer" draggable="false"><i class="text-white fa fa-file-text"></i> Schedule An Appointment</a></div>
        </div>
    </div>

    <div>
        <Certifications />
    </div>


    <div class="text-center py-10 lg:py-14">
        <p class="basicText tracking-wider">
            "We take our <b class="text-yellow-300">CLIENTS</b> seriously"
        </p>
    </div>

    <div class="grid grid-rows-1">
        <div class="xl:p-10 text-center xl:grid xl:grid-cols-2 bg-green-100">
            <img alt="Lawn Mower" class="blueMower mower2 mx-auto" src="stock/mower2.jpg">
            <img alt="Team" class="mower2 mx-auto" src="stock/team.jpeg">
        </div>
        <div class="text-left xl:px-24 xl:py-5">
            <p class="basicText p-3 lg:p-0">Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</p>
        </div>
    </div>

    <MiniFoot />

</section>

<style>
    .container {
        position: relative;
    }

    .thumbnails-row {
        width: 100%;
        display: flex;
        align-self: flex-end;
    }

    .mower, .mower2 {
        border: 3px solid black;
    }

    @media screen and (min-width:0px) and (max-width:768px) {
        main {
            width: 95vw;
            display: flex;
            flex-direction: column;
            margin: 3% auto;
            background-color: #222;
            box-shadow: 0 0 10px black;
        }

        .mainButton {
            font-size: 15px;
            font-family: Verdana, sans-serif;
            color: #fff !important;
            text-transform: uppercase;
            text-decoration: none;
            background: green;
            padding: 10px;
            border-radius: 50px;
            display: inline-block;
            border: none;
            transition: all 0.4s ease 0s;
        }

        .mainButton2 {
            font-family: Verdana, sans-serif;
            font-size: 15px;
            color: white !important;
            text-transform: uppercase;
            text-decoration: none;
            background: rgb(0, 173, 0);
            padding: 10px;
            border-radius: 50px;
            display: inline-block;
            border: none;
            transition: all 0.4s ease 0s;
        }

        .para2 {
            display: none;
        }

        .mower {
            width: 350px;
            height: 250px;
        }

        .basicText {
            color: white;
            font-family: Verdana, sans-serif;
            font-size: 17px;
        }

        .basicText2 {
            color:white;
            font-family: Verdana, sans-serif;
            font-size: 17px;
        }

        .titleText {
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            font-family: Verdana, sans-serif;
            color: white;
            font-size: 40px;
            background: green;
        }

        .invisibleImage, .farmer1, .farmer2, .farmer3, .farmer4 {
            display: none;
        }
    }

    @media screen and (min-width:768px) and (max-width:1024px) {
        main {
            width: 85vw;
            display: flex;
            flex-direction: column;
            margin: 3% auto;
            background-color: #222;
            box-shadow: 0 0 10px black;
        }

        .mainButton {
            font-size: 15px;
            font-family: Verdana, sans-serif;
            color: #fff !important;
            text-transform: uppercase;
            text-decoration: none;
            background: green;
            padding: 10px;
            border-radius: 50px;
            display: inline-block;
            border: none;
            transition: all 0.4s ease 0s;
        }

        .mainButton2 {
            font-family: Verdana, sans-serif;
            font-size: 15px;
            color: white !important;
            text-transform: uppercase;
            text-decoration: none;
            background: rgb(0, 173, 0);
            padding: 10px;
            border-radius: 50px;
            display: inline-block;
            border: none;
            transition: all 0.4s ease 0s;
        }

        .para2 {
            display: none;
        }

        .basicText {
            color:white;
            font-family: Verdana, sans-serif;
            font-size: 25px;
        }

        .basicText2 {
            color:black;
            font-family: Verdana, sans-serif;
            font-size: 24px;
        }

        .titleText {
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            font-family: Verdana, sans-serif;
            color: white;
            font-size: 60px;
            background: green;
        }

        .invisibleImage, .worker, .blueMower, .farmer1, .farmer2, .farmer3, .farmer4 {
            display: none;
        }

        .mower2 {
            width: 650px;
            height: 450px;
        }
    }

    @media screen and (min-width:1024px) and (max-width:1280px) {
        main {
            width: 85vw;
            display: flex;
            flex-direction: column;
            margin: 3% auto;
            background-color: #222;
            box-shadow: 0 0 10px black;
        }

        .mainButton {
            font-size: 15px;
            font-family: Verdana, sans-serif;
            color: #fff !important;
            text-transform: uppercase;
            text-decoration: none;
            background: green;
            padding: 10px;
            border-radius: 50px;
            display: inline-block;
            border: none;
            transition: all 0.4s ease 0s;
        }

        .mainButton2 {
            font-family: Verdana, sans-serif;
            font-size: 15px;
            color: white !important;
            text-transform: uppercase;
            text-decoration: none;
            background: rgb(0, 173, 0);
            padding: 10px;
            border-radius: 50px;
            display: inline-block;
            border: none;
            transition: all 0.4s ease 0s;
        }

        .para2 {
            display: none;
        }

        .basicText {
            color:white;
            font-family: Verdana, sans-serif;
            font-size: 25px;
        }

        .basicText2 {
            color:black;
            font-family: Verdana, sans-serif;
            font-size: 24px;
        }

        .titleText {
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            font-family: Verdana, sans-serif;
            color: white;
            font-size: 60px;
            background: green;
        }

        .invisibleImage, .worker, .blueMower, .farmer1, .farmer2, .farmer3, .farmer4 {
            display: none;
        }

        .mower2 {
            width: 650px;
            height: 450px;
        }
    }

    @media screen and (min-width:1280px) and (max-width:1536px) {
        main {
            width: 50vw;
            display: flex;
            flex-direction: column;
            margin: 0% auto;
            background-color: #222;
            box-shadow: 0 0 10px black;
        }

        .mainButton {
            font-size: 15px;
            font-family: Verdana, sans-serif;
            color: #fff !important;
            text-transform: uppercase;
            text-decoration: none;
            background: green;
            padding: 10px;
            border-radius: 50px;
            display: inline-block;
            border: none;
            transition: all 0.4s ease 0s;
        }

        .mainButton:hover {
            background: rgb(0, 172, 0);
            box-shadow: 0 0 35px rgb(0, 172, 0);
            -webkit-box-shadow: 0px 5px 60px -10px rgb(0, 172, 0);
            -moz-box-shadow: 0px 5px 60px -10px rgb(0, 172, 0);
            transition: all 0.4s ease 0s;
        }

        .mainButton2 {
            font-family: Verdana, sans-serif;
            font-size: 30px;
            color: #000000 !important;
            text-transform: uppercase;
            text-decoration: none;
            background: rgb(0, 173, 0);
            padding: 20px;
            border-radius: 50px;
            display: inline-block;
            border: none;
            transition: all 0.4s ease 0s;
        }

        .mainButton2:hover {
            background: lightgreen;
            box-shadow: 0 0 35px rgb(83, 136, 83);
            -webkit-box-shadow: 0px 5px 60px -10px rgb(83, 136, 83);
            -moz-box-shadow: 0px 5px 60px -10px rgb(83, 136, 83);
            transition: all 0.4s ease 0s;
        }

        .para2 {
            display: none;
        }

        .basicText {
            color:white;
            font-family: Verdana, sans-serif;
            font-size: 25px;
        }

        .basicText2 {
            color:black;
            font-family: Verdana, sans-serif;
            font-size: 24px;
        }

        .titleText {
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            font-family: Verdana, sans-serif;
            color: white;
            font-size: 35px;
            background: green;
        }

        .img-move {
            position:absolute;
            width:55%;
        }

        .img-move-1 {
            left:0;
        }

        .img-move-2 {
            right:0;  
            bottom:0;
        }

        .img-move-wrapper {
            /* border:1px solid red; */
            position:relative;
            overflow:hidden;
            max-width:1140px;
            margin:0 auto;
        }

        .mower2 {
            width: 650px;
            height: 450px;
        }

        .worker{
            width: 500px;
            height: 350px;
        }

        .farmer1 {
        width: 180px;
        height: 235px;
	    position: absolute;
        z-index: 1;
        top: 10%;
        left: 13%;
        transform: translate(-100%, 0);
	    transform-origin: 100% 100%;
	    transition: transform 0.4s;
        }

        .curious {
	    transform: translate(15%, 0) rotate(0deg);
        }

        .farmer2 {
        width: 180px;
        height: 250px;
        z-index: 1;
	    position: absolute;
        top: 10%;
        left: 70%;
	    transform: translate(150%, 0);
	    transform-origin: 100% 100%;
	    transition: transform 0.4s;
        }

        .curious2 {
	    transform: translate(12%, 0) rotate(0deg);
        }

        .farmer3, .farmer4 {
            display: none;
        }
    }

    @media screen and (min-width:1536px) {
        main {
            width: 50vw;
            display: flex;
            flex-direction: column;
            margin: auto;
            background-color: #222;
            box-shadow: 0 0 35px black;
        }

        .mainButton {
            font-family: Verdana, sans-serif;
            color: #fff !important;
            text-transform: uppercase;
            text-decoration: none;
            background: green;
            padding: 20px;
            border-radius: 50px;
            display: inline-block;
            border: none;
            transition: all 0.4s ease 0s;
        }

        .mainButton:hover {
            background: rgb(0, 172, 0);
            box-shadow: 0 0 35px rgb(0, 172, 0);
            -webkit-box-shadow: 0px 5px 60px -10px rgb(0, 172, 0);
            -moz-box-shadow: 0px 5px 60px -10px rgb(0, 172, 0);
            transition: all 0.4s ease 0s;
        }

        .mainButton2 {
            font-family: Verdana, sans-serif;
            font-size: 30px;
            color: #000000 !important;
            text-transform: uppercase;
            text-decoration: none;
            background: rgb(0, 173, 0);
            padding: 20px;
            border-radius: 50px;
            display: inline-block;
            border: none;
            transition: all 0.4s ease 0s;
        }

        .mainButton2:hover {
            background: lightgreen;
            box-shadow: 0 0 35px rgb(83, 136, 83);
            -webkit-box-shadow: 0px 5px 60px -10px rgb(83, 136, 83);
            -moz-box-shadow: 0px 5px 60px -10px rgb(83, 136, 83);
            transition: all 0.4s ease 0s;
        }

        .img-move {
            position:absolute;
            width:55%;
        }

        .img-move-1 {
            left:0;
        }

        .img-move-2 {
            right:0;  
            bottom:0;
        }

        .img-move-wrapper {
            /* border:1px solid red; */
            position:relative;
            overflow:hidden;
            max-width:1140px;
            margin:0 auto;
        }

        .mower {
            width: 600px;
            height: 450px;
        }

        .mower2 {
            width: 650px;
            height: 450px;
        }

        .para2 {
            display: inline-block;
            color:black;
            font-family: Verdana, sans-serif;
            font-size: 20px;
        }

        .basicText {
            color:white;
            font-family: Verdana, sans-serif;
            font-size: 35px;
        }

        .basicText2 {
            color:black;
            font-family: Verdana, sans-serif;
            font-size: 25px;
        }

        .titleText {
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            font-family: Verdana, sans-serif;
            color: white;
            font-size: 50px;
            background: green;
        }

        .farmer3 {
        width: 180px;
        height: 235px;
	    position: absolute;
        z-index: 1;
        top: 10%;
        left: 13%;
        transform: translate(-100%, 0);
	    transform-origin: 100% 100%;
	    transition: transform 0.4s;
        }

        .curious {
	    transform: translate(15%, 0) rotate(0deg);
        }

        .farmer4 {
        width: 180px;
        height: 250px;
        z-index: 1;
	    position: absolute;
        top: 10%;
        left: 75%;
	    transform: translate(150%, 0);
	    transform-origin: 100% 100%;
	    transition: transform 0.4s;
        }

        .curious2 {
	    transform: translate(12%, 0) rotate(0deg);
        }

        .farmer1, .farmer2 {
            display: none;
        }
    }

</style>