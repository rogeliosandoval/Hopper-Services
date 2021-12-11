<script>
    export let thumbImg;
    export let altTag;
    export let selected;
</script>

<style>

    .thumbnail-container {
        width: 25%;
	    display: flex;
	    justify-content: center;
	    align-items: center;
	    background-color: #ddd;
    }

    /* Add a transparency effect for thumnbail images */
    .sample {
        opacity: 0.6;
    }

    img {
        width: 100%;
        height: 100%;
        transition: all .1s ease-in-out;
    }

    .cursor {
        cursor: pointer;
    }

    .active {
        opacity: 1;
        padding: 5px;
    }
</style>

<div class="thumbnail-container">
    <img class="sample cursor" class:active={selected} src={thumbImg} style="width:100%" on:click alt={altTag}>
</div>