<script>
  import { onDestroy, onMount } from "svelte";
  import { fade } from "svelte/transition";
  export let show;

  onDestroy(() => console.log("onDestroy Inner"));
  onMount(() => console.log("onMount Inner"));
</script>

<div style="border: 1px solid red; padding: 10px" transition:fade>
  <span style="color:red">Inner</span><br />
  <button
    on:click={() => {
      show = false;
    }}>Close</button
  >
</div>
