<script>
  import { onDestroy, onMount } from "svelte";
  import InnerHybrid from "./InnerHybrid.svelte";

  export let show;
  export let visible;

  onDestroy(() => console.log("onDestroy Outer"));
  onMount(() => console.log("onMount Outer"));
</script>

<div style="border: 1px solid green; padding: 10px">
  <span style="color:green">Outer</span><br />
  <InnerHybrid bind:show bind:visible />
</div>
