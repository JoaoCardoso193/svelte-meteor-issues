<script>
  import OuterComponent from "./OuterComponent.svelte";
  import { fade } from "svelte/transition";

  let numbers = [1, 2, 3];
  let showNumbers = { 1: true, 2: true, 3: true };

  const toggleNumber = (number) => {
    showNumbers[number] = !showNumbers[number];
  };
</script>

<div>
  <div transition:fade>Test</div>
  {#each numbers as number}
    {#if showNumbers[number]}
      <div transition:fade>
        <OuterComponent {number} />
      </div>
    {/if}
  {/each}
</div>

<button
  on:click={() => {
    toggleNumber(1);
  }}
>
  Toggle 1
</button>

<button
  on:click={() => {
    toggleNumber(2);
  }}
>
  Toggle 2
</button>

<button
  on:click={() => {
    toggleNumber(3);
  }}
>
  Toggle 3
</button>
