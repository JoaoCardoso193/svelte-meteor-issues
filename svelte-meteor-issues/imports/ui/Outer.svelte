<script>
  import { onDestroy, onMount } from "svelte";
  import { fade } from "svelte/transition";
  import Inner from "./Inner.svelte";

  export let show;

  onDestroy(() => console.log("onDestroy Outer"));
  onMount(() => console.log("onMount Outer"));
</script>

<div style="border: 1px solid green; padding: 10px" transition:fade>
  <span style="color:green">Outer</span><br />
  <Inner bind:show />
</div>
