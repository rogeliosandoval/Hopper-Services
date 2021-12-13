<style>
	
	.logo{
		padding: 1px;
		position: absolute;
		margin-top: -90px;
	}

	@media screen and (min-width:0px) and (max-width:768px) {

	}

	@media screen and (min-width:768px) and (max-width:1024px) {
		.logo {
			display: none;
		}

		.navText {
			font-size: 15px;
			font-style: italic;
		}
	}

	@media screen and (min-width:1024px) and (max-width:1280px) {
		.navText {
			font-size: 25px;
			font-style: italic;
		}
	}

	@media screen and (min-width:1280px) and (max-width:1536px) {
		.navText {
			font-size: 25px;
			font-style: italic;
		}
	}

	@media screen and (min-width:1536px) {
		.navText {
			font-size: 30px;
			font-style: italic;
		}
	}

</style>

<div class="flex flex-wrap place-items-center mx-auto">
	<section class="relative mx-auto w-full">
		<!-- navbar -->
	  <nav class="flex justify-between text-white">
		<div class="px-2 xl:px-12 py-6 flex w-full items-center">
		  <a class="font-bold font-heading" href="/">
			<img class="logo" src="logo.png" alt="logo">
		  </a>
		  <!-- Nav Links -->
		  <div class="ml-auto">
			  <ul class="flex px-4 ml-auto font-semibold font-heading space-x-12 text-center">
				<!-- <li><a class="bg-blue-500 hover:bg-blue-400 text-yellow-200 font-bold py-2 px-4 border-b-4 border-blue-700 hover:border-blue-500 rounded" href="#">Schedule An Inspection <i class="text-white fas fa-file-text"></i></a></li> -->
				<li><a class="navText hover:text-green-200" href="/">Home</a></li>
				<li><a class="navText hover:text-green-200" href="/review">Reviews</a></li>
				<li><a class="navText hover:text-green-200" href="/service">Services</a></li>
				<li><a class="navText hover:text-green-200" href="/career">Careers</a></li>
				<li><a class="navText hover:text-green-200" href="/about">About</a></li>
				<li><a class="navText hover:text-green-200" href="/faq">FAQs</a></li>
				<li><a class="navText hover:text-green-200" href="/contact">Contact</a></li>
			  </ul>
			  <hr>
		  </div>
		</div>
	  </nav>
	</section>
  </div>