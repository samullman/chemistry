<script>
import Header from "./header.svelte";
import "../app.css";
</script>

<Header />

<main>
    <slot />

    <footer>
        <p>Visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to read the documentation</p>
    </footer>
</main>

<style>
main {
  flex: 1;
  display: flex;
  flex-direction: column;
  padding: 0 1rem;
  width: 100%;
  max-width: 1024px;
  margin: 0 auto;
  box-sizing: border-box;
}

footer {
  display: flex;
  flex-direction: column;
}
</style>
