<script>
    let isActive = false;
</script>

<style>

    .miniNav {
        position: fixed;
        z-index: 1;
        top: 0px;
        width: 100%;
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

    @media screen and (min-width:768px) {
        .miniNav {
            display: none;
        }
    }
</style>

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