<script>
  import { onDestroy, onMount } from "svelte";
  import OuterHybrid from "./OuterHybrid.svelte";
  import { fade } from "svelte/transition";
  let show = true;
  let visible = true;

  onMount(() => {
    console.log("onMount Page");
  });
  onDestroy(() => console.log("onDestroy Page"));
</script>

{#if show}
  <div in:fade class:hidden={!visible}>
    <OuterHybrid bind:show bind:visible />
  </div>
{:else}
  <button
    on:click={() => {
      show = true;
      visible = true;
    }}
  >
    Open
  </button>
{/if}

<style>
  .hidden {
    visibility: hidden;
    opacity: 0;
    transition: visibility 0s 0.2s, opacity 0.2s linear;
  }
</style>
