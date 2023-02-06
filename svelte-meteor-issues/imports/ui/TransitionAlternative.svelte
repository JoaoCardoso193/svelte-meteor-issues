<script>
  import { onDestroy, onMount } from "svelte";
  import OuterAlt from "./OuterAlt.svelte";
  let show = true;
  let visible = false;

  onMount(() => {
    console.log("onMount Page");

    setTimeout(() => {
      visible = true;
    }, 200);
  });
  onDestroy(() => console.log("onDestroy Page"));
</script>

{#if show}
  <div class={visible ? "visible" : "hidden"}>
    <OuterAlt bind:show bind:visible />
  </div>
{:else}
  <button
    on:click={() => {
      show = true;

      setTimeout(() => {
        visible = true;
      }, 200);
    }}
  >
    Open
  </button>
{/if}

<style>
  .visible {
    visibility: visible;
    opacity: 1;
    transition: opacity 0.2s linear;
  }

  .hidden {
    visibility: hidden;
    opacity: 0;
    transition: visibility 0s 0.2s, opacity 0.2s linear;
  }
</style>
