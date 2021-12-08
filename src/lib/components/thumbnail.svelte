<script>
    export let thumbImg;
    export let altTag;
    export let selected;
</script>

<style>
    .thumbnails-row:after {
        content: "";
        display: table;
        clear: both;
    }

    /* Six columns side by side */
    .column {
        float: left;
        width: 16.66%;
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
    }
</style>

<div class="thumbnail-container">
    <img class="sample cursor" class:active={selected} src={thumbImg} style="width:100%" on:click alt={altTag}>
</div>