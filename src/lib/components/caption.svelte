<script>
    import { createEventDispatcher } from 'svelte';
    export let caption;

    const dispatch = createEventDispatcher();
</script>

<style>

    @media screen and (min-width:640px) {
    /* On hover, add a black background color with a little bit see-through */
        .prev:hover, .next:hover {
            background-color: rgba(0, 0, 0, 0.8);
        }
    }

    /* Container for image text */
    .caption-container {
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

</style>

<!-- Image text -->
<div class="caption-container">
    <a class="prev" on:click={() => dispatch('prevClick')}>&#10094;</a>
    <p id="caption">{caption}</p>
    <a class="next" on:click={() => dispatch('nextClick')}>&#10095;</a>
</div>