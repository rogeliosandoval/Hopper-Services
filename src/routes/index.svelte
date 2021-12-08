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

    let imageShowIndex = 0;
    $: console.log(imageShowIndex);

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

<section class="pt-20">

    <MiniNav />
    
    <div class="text-center pt-8 px-7">
        <p class="basicText">There is always a beautiful yard under the tall grass. Let us be your go-to lawn service company where we strive to bring out the best of your yard.</p>
    </div>
    
    <div class="p-5 grid grid-rows-1 gap-x-5">
    
        <div class="pb-2">
            <img class="mower" alt="Lawn Mower" src="stock/mower1.jpg">
        </div>
    
        <div class="text-center">
            <p class="basicText">We use great quality tools that make sure we get the job done as clean as we possibly can. We leave absolutely nothing behind besides a fantastic looking yard!</p>
        </div>
    
    </div>
    
    <div class="text-center">
        <p class="titleText tracking-wider">Check out some of our clients!</p>
    </div>

    <!-- Container for the image gallery -->
    <div class="container">
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

    <div class="text-center pt-3 px-6">
        <p class="basicText">
            When you book an appointment with us we make sure to come prepared!
        </p>
    </div>

    <div class="text-center py-8">
        <a class="bg-green-500 hover:bg-green-400 text-black font-bold py-2 px-4 border-b-4 border-black hover:border-green-500 rounded" href="#">Schedule An Appointment <i class="text-white fa fa-file-text"></i></a>
    </div>

    <Certifications />

    <div class="p-5 grid grid-rows-1">
        <div class="pb-2 text-center">
            <img alt="Lawn Mower" class="mower" src="stock/mower2.jpg">
        </div>
        <div class="text-center">
            <p class="basicText">Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</p>
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

    @media screen and (min-width:0px) and (max-width:640px) {
        .basicText {
            color: white;
            font-family: Verdana, sans-serif;
            font-size: 17px;
        }

        .titleText {
            font-weight: bold;
            font-family: Verdana, sans-serif;
            color: white;
            font-size: 18px;
        }
    }

    .mower {
        border: 3px solid black
    }

</style>