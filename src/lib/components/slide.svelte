<script>
    export let image;
    export let altTag;
    export let attr;
    export let totalSlides;
    export let slideNumber;
    export let imageShowing;
</script>

<style>
    /* Hide the images by default */
    .mySlides {
        display: none;
    }

    /* Number text (1/3 etc) */
    .numbertext {
        color: #f2f2f2;
        position: absolute;
        font-size: 12px;
        padding: 8px 12px;
        top:0;
    }

    img {
        width: 100%;
    }

    .show {
        display: block;
    }

</style>

<!-- Full-width images with number text -->
<div class="mySlides" class:show={imageShowing}>
    <div class="numbertext">{slideNumber} / {totalSlides}</div>
        <img src={image} title={attr} alt={altTag}>
</div>