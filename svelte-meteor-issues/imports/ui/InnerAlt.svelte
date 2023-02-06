<script>
  import { onDestroy, onMount } from "svelte";
  export let show;
  export let visible;

  onDestroy(() => console.log("onDestroy Inner"));
  onMount(() => console.log("onMount Inner"));
</script>

<div style="border: 1px solid red; padding: 10px">
  <span style="color:red">Inner</span><br />
  <button
    on:click={() => {
      //initiate transition
      visible = false;

      //destroy element once transition is complete
      setTimeout(() => {
        show = false;
      }, 2000);
    }}>Close</button
  >
</div>
