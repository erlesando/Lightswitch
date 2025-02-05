<script>
    let lightstate=$state("on");
    let textinput=$state("on");

    $effect(() => {
        if (textinput==="on"){
            lightstate="on";
        }
        else if (textinput==="off"){
            lightstate="off";
        }
    });
</script>

<h1>lightswitch'ish</h1>
<button id="lightswitch"
		style="background: {lightstate === "on" ? "yellow" : "black"}"
		onclick={() => lightstate === "on" ? lightstate=textinput="off" : lightstate=textinput="on"}
></button>
<br><br>

<input bind:value={textinput}/>

<br><br>

<button id="on" class="onoff"
	onclick={lightstate=textinput="on"}
	style="background: {lightstate === "on" ? "green" : "white"}">
	on
</button>
<button id="off" class="onoff"
	onclick={lightstate=textinput="off"}
	style="background: {lightstate === "on" ? "white" : "green"}">
	off
</button>
<br>

<style>
    #lightswitch{
        aspect-ratio: 1;
        border-radius: 50%;
        background: var(--color, #fff);
        transform: translate(-2px,-2px);
      
  filter: drop-shadow(2px 2px 3px rgba(0,0,0,0.2));
        transition: all 0.1s;
        width: 100px
	}
	.onoff{
		font-size: 15px;
		padding: 20px 40px;
		border-color:"darkgray";
		border: 3px solid darkgray;
	}
</style>