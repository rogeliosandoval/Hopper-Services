<script>
    import { createEventDispatcher } from 'svelte';
    export let caption;

    const dispatch = createEventDispatcher();
</script>

<style>

    @media screen and (min-width:0px) and (max-width:768px) {
        /* Container for image text */
        .caption-container {
            font-size: 12px;
            display: flex;
            align-items: center;
            justify-content: space-between;
            text-align: center;
            background-color: #222;
            padding: 2px 16px;
            color: white;
        }

        /* Next & previous buttons */
        .prev, .next {
            cursor: pointer;
            /* position: absolute; */
            /* top: 100%; */
            width: auto;
            /* padding: 16px;
            margin-top: -50px; */
            color: white;
            font-weight: bold;
            font-size: 20px;
            border-radius: 0 3px 3px 0;
            user-select: none;
            -webkit-user-select: none;
        }

        /* Position the "next button" to the right */
        .next {
            /* right: 0; */
            border-radius: 3px 0 0 3px;
        }
    }

    @media screen and (min-width:768px) and (max-width:1024px) {
        /* Container for image text */
        .caption-container {
            font-size: 20px;
            display: flex;
            align-items: center;
            justify-content: space-between;
            text-align: center;
            background-color: #222;
            padding: 2px 16px;
            color: white;
        }

        /* Next & previous buttons */
        .prev, .next {
            cursor: pointer;
            /* position: absolute; */
            /* top: 100%; */
            width: auto;
            /* padding: 16px;
            margin-top: -50px; */
            color: white;
            font-weight: bold;
            font-size: 20px;
            border-radius: 0 3px 3px 0;
            user-select: none;
            -webkit-user-select: none;
        }

        /* Position the "next button" to the right */
        .next {
            /* right: 0; */
            border-radius: 3px 0 0 3px;
        }
    }

    @media screen and (min-width:1024px) and (max-width:1280px) {
        /* Container for image text */
        .caption-container {
            font-size: 35px;
            display: flex;
            align-items: center;
            justify-content: space-between;
            text-align: center;
            background-color: #222;
            padding: 2px 16px;
            color: white;
        }

        /* Next & previous buttons */
        .prev, .next {
            cursor: pointer;
            /* position: absolute; */
            /* top: 100%; */
            width: auto;
            /* padding: 16px;
            margin-top: -50px; */
            color: white;
            font-weight: bold;
            font-size: 50px;
            border-radius: 0 3px 3px 0;
            user-select: none;
            -webkit-user-select: none;
        }

        /* Position the "next button" to the right */
        .next {
            /* right: 0; */
            border-radius: 3px 0 0 3px;
        }
    }

    @media screen and (min-width:1280px) and (max-width:1536px) {
                /* Container for image text */
                .caption-container {
            font-size: 35px;
            display: flex;
            align-items: center;
            justify-content: space-between;
            text-align: center;
            background-color: #222;
            padding: 2px 16px;
            color: white;
        }

        /* Next & previous buttons */
        .prev, .next {
            cursor: pointer;
            /* position: absolute; */
            /* top: 100%; */
            width: auto;
            /* padding: 16px;
            margin-top: -50px; */
            color: white;
            font-weight: bold;
            font-size: 50px;
            border-radius: 0 3px 3px 0;
            user-select: none;
            -webkit-user-select: none;
        }

        /* Position the "next button" to the right */
        .next {
            /* right: 0; */
            border-radius: 3px 0 0 3px;
        }

        /* On hover, add a black background color with a little bit see-through */
        .prev:hover,
        .next:hover {
            color: green;
        }	
            
        .prev:active,
        .next:active {
            color: hsla(125, 86%, 64%, 1);
            text-decoration: none;
        }
    }

    @media screen and (min-width:1536px) {
        /* Container for image text */
        .caption-container {
            font-size: 35px;
            display: flex;
            align-items: center;
            justify-content: space-between;
            text-align: center;
            background-color: #222;
            padding: 2px 16px;
            color: white;
        }

        /* Next & previous buttons */
        .prev, .next {
            cursor: pointer;
            /* position: absolute; */
            /* top: 100%; */
            width: auto;
            /* padding: 16px;
            margin-top: -50px; */
            color: white;
            font-weight: bold;
            font-size: 50px;
            border-radius: 0 3px 3px 0;
            user-select: none;
            -webkit-user-select: none;
        }

        /* Position the "next button" to the right */
        .next {
            /* right: 0; */
            border-radius: 3px 0 0 3px;
        }

        /* On hover, add a black background color with a little bit see-through */
        .prev:hover,
        .next:hover {
            color: green;
        }	
            
        .prev:active,
        .next:active {
            color: hsla(125, 86%, 64%, 1);
            text-decoration: none;
        }
    }

</style>

<!-- Image text -->
<div class="caption-container">
    <a class="prev" on:click={() => dispatch('prevClick')}>&#10094;</a>
    <p id="caption">{caption}</p>
    <a class="next" on:click={() => dispatch('nextClick')}>&#10095;</a>
</div>