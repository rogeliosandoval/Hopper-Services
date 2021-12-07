<script>
    import {fade} from 'svelte/transition'

    let isActive = false;

    const carouselPhotos = [
		'stock/yard1.jpg',
		'stock/yard2.jpg',
		'stock/yard3.jpg',
        'stock/yard4.jpg'
	]
	
	let index = 0
	
	const next = () => {
		index = (index + 1) % carouselPhotos.length
	}
</script>

<section class="pt-20">
    <div class="miniNav">
        <div class="modGrid">
            <div class="dropdown shrink">
                <button on:click={() => isActive = !isActive} class="dropbtn"><i class="fa fa-navicon"></i></button>
                <div id="myDropdown" on:click={() => isActive = !isActive} class:show={isActive} class="dropdown-content">
                    <a href="#">Home</a>
                    <a href="#">Reviews</a>
                    <a href="#">Services</a>
                    <a href="#">Careers</a>
                    <a href="#">About</a>
                    <a href="#">FAQ</a>
                    <a href="#">Contact</a>
                </div>
            </div>
        
            <!-- <div class="text-white bg-green-800 font-bold text-3xl text-center tracking-wider expand">Hopper Services</div> -->
            <div class="expand">
                <img class="logo" alt="logo" src="logo.png">
            </div>
        </div>
    </div>
    
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
    
    <div class="">
        {#each [carouselPhotos[index]] as src (index)}
            <img class="slideImage border-solid border-4 border-black" transition:fade src={src} alt="" />	
        {/each}
        <button class="slideButton p-2 font-bold tracking-wider border-solid border-4 bg-white border-black" on:click={next}>Next!</button>
    </div>
</section>


<style>

    @media screen and (min-width:0px) and (max-width:640px) {
        .miniNav {
            position: fixed;
            top: 0px;
            width: 100%;
        }
        
        .basicText {
            color: white;
            font-family: Verdana, sans-serif;
            font-size: 17px;
        }

        .titleText {
            font-weight: bold;
            color: white;
            font-size: 35px;
        }
    }
        
    @media screen and (min-width:640px) {
        .miniNav {
            display: none;
        }
    }

    .mower {
        border: 3px solid black
    }

    .slideImage, .slideButton {
		position: absolute;
	}

    .modGrid {
        display: table;
        table-layout: auto;
        width: 100%;
    }

    .expand {
        background-image: linear-gradient(#4CAF50,green);
        display: table-cell;
        width: 100%;
        max-width: 0;
        white-space: nowrap;
        overflow: hidden;
        text-overflow: ellipsis;
    }

    .shrink {
        display: table-cell;
        white-space: nowrap;
    }

    .logo {
        /* position:fixed; top:0; right:0; */
		height: 175px;
		width: 145px;
		padding: 1px;
		position: absolute;
		margin-top: -75px;
        margin-left: 80px;
    }

    .dropbtn {
        background-image: linear-gradient(#4CAF50,green);
        color: white;
        padding: 16px;
        font-size: 40px;
        border: none;
        cursor: pointer;
    }
    
    .dropbtn:hover, .dropbtn:focus {
        background-color: #3e8e41;
    }
    
    .dropdown {
        position: relative;
        display: inline-block;
    }
    
    .dropdown-content {
        display: none;
        position: absolute;
        background-color: #f9f9f9;
        min-width: 160px;
        overflow: auto;
        box-shadow: 0px 8px 16px 0px rgba(0,0,0,0.2);
    }
    
    .dropdown-content a {
        color: black;
        padding: 12px 16px;
        text-decoration: none;
        display: block;
    }
    
    .dropdown a:hover {background-color: #f1f1f1}
    
    .show {display:block;}
</style>