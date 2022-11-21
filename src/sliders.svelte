<script>
let red = 71;
let green = 0;
let blue = 56; 


let hex = '';

function chex(num)
{
  var res =  num.toString(16).toUpperCase();

  return res.length == 1? '0' + res: res
}

function convert(r,g,b){
    hex = chex(r) + chex(g) + chex(b);
}
convert(red,green,blue)


let rootElement;

$: rootElement && rootElement.style.setProperty('--container-background', `rgb(${red}, ${green}, ${blue})`);
</script>

<div class="info">
    <h3>RGB:( {red}, {green}, {blue} )</h3>
    <div class="hex">
        <h3>HEX: #{hex}</h3>
        <button class="button" type="button" on:click={convert(red,green,blue)}>Get Hex</button> 
    </div>
</div>
<div class="slider-box" bind:this={rootElement}>
    <div class="sliders">
        <div class="slider">
                <input class="slide red" type="range" min="0" max="255" bind:value={red}>
        </div>
        <div class="slider">
                <input class="slide green" type="range" min="0" max="255" bind:value={green}>
        </div>
        <div class="slider">
            <input class="slide blue" type="range" min="0" max="255" bind:value={blue}>
        </div>
    </div>
</div>


<style>
    h3{
        font-size: 1vw;
        padding:0.5vh;
    }
    :root {
    --container-background: inherit;
    }
    .info{
        height:13vh;
    }
    .slider-box{
        height:73vh;
        width:100vw;
        background-color: var(--container-background);
        margin-top:3vh;  
    }
    .sliders{
        display:flex;
        align-items: center;
        justify-content: center;
        padding:10%;
        display:flex;
    }
    .slider{
        margin-top:2%;
    }
    .info{
        text-align: center;
    }
    .hex{
        display: flex;
        justify-content: center;
        align-items: center;
    }
    .button{
        margin-left: 3vh;
        width:7vw;
        height:4vh;
        border-radius: 20%/50%;
        border:1px solid #05386b;
        background-color: #56db95;
        color: #05386b;
        font-family: monospace;
        font-size: 1vw;
    }
    .button:hover{
        background-color: #9B414A;
        color:#56db95;
        cursor: pointer;
    }
    .slide{
        -webkit-appearance: none;
        background: transparent;
        cursor:pointer;
        width:15vw;
        margin:10vh;
    }
    .red{
        background:red;
        height:0.5vh;
        border-radius: 5%/100%;
    }
    .red::-webkit-slider-thumb,.red::-moz-range-thumb{
        background-color: red;
        border: red;
    }
    .green{
        background:green;
        height:0.5vh;
        border-radius: 5%/100%;
    }
    .green::-webkit-slider-thumb,.green::-moz-range-thumb{
        background-color: green;
        border: green;
    }
    .blue{
        background:blue;
        height:0.5vh;
        border-radius: 5%/100%;
    }
    .blue::-webkit-slider-thumb,.blue::-moz-range-thumb{
        background-color: blue;
        border: blue;
    }
</style>