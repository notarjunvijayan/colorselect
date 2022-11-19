<script>
let red = 0;
let blue = 0; 
let green = 0;

let rootElement;

$: rootElement && rootElement.style.setProperty('--container-background', `rgb(${red}, ${green}, ${blue})`);
</script>

<div class="info">
    <h3>RGB:( {red}, {green}, {blue} )</h3>
</div>
<div class="slider-box" bind:this={rootElement}>
    <div class="sliders">
        <div class="red slider">
                <input type="range" min="0" max="255" bind:value={red}>
        </div>
        <div class="blue slider">
                <input type="range" min="0" max="255" bind:value={blue}>
        </div>
        <div class="green slider">
            <input type="range" min="0" max="255" bind:value={green}>
        </div>
    </div>
</div>


<style>
    :root {
    --container-background: inherit;
    }
    .info{
        height:13vh;
    }
    .slider-box{
        height:74vh;
        width:100vw;
        background-color: var(--container-background);  
    }
    .sliders{
        display:flex;
        align-items: center;
        justify-content: center;
        padding:10%;
        display:flex;
    }
    .slider{
        margin:3%;
    }
</style>