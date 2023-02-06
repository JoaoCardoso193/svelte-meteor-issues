<script>
  import { onDestroy, onMount } from "svelte";
  import { fade } from "svelte/transition";
  import InnerComponent from "./InnerComponent.svelte";
  export let number;

  onMount(() => {
    console.log(`Outer component ${number} mounted`);
  });
  onDestroy(() => {
    console.log(`Outer component ${number} destroyed`);
  });
</script>

<div class="component" transition:fade>
  <span>Outer component {number}</span>
  <InnerComponent {number} />
</div>

<style>
  .component {
    background: blue;
    width: 50%;
    border-radius: 5px;
    text-align: center;
    color: white;
    font-weight: 800;
    margin: 10px;
  }
</style>
