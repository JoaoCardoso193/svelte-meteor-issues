<script>
  import { onDestroy, onMount } from "svelte";
  import { fade } from "svelte/transition";
  import Outer from "./Outer.svelte";
  let show = true;

  onMount(() => console.log("onMount Page"));
  onDestroy(() => console.log("onDestroy Page"));
</script>

{#if show}
  <div transition:fade>
    <Outer bind:show />
  </div>
{:else}
  <button on:click={() => (show = true)}> Open </button>
{/if}
