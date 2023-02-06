<script>
  import { Route } from "tinro";
  import Home from "./Home.svelte";
  import TransitionTest from "./TransitionTest.svelte";
  import TransitionAlternative from "./TransitionAlternative.svelte";
</script>

<Route path="/">
  <Home />
</Route>

<Route path="transition-test">
  <TransitionTest />
</Route>

<Route path="transition-alternative">
  <TransitionAlternative />
</Route>
