<script>
  import { Route } from "tinro";
  import Home from "./Home.svelte";
  import TransitionTest from "./TransitionTest.svelte";
</script>

<Route path="/">
  <Home />
</Route>

<Route path="transition-test">
  <TransitionTest />
</Route>
