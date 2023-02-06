<script>
  import { onDestroy, onMount } from "svelte";
  import { fade } from "svelte/transition";
  export let number;

  onMount(() => {
    console.log(`Inner component ${number} mounted`);
  });
  onDestroy(() => {
    console.log(`Inner component ${number} destroyed`);
  });
</script>

<div class="component" transition:fade>
  <span>Inner component {number}</span>
</div>

<style>
  .component {
    background: green;
    width: 100%;
    border-radius: 5px;
    text-align: center;
    color: white;
    font-weight: 800;
  }
</style>
