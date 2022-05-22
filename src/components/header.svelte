<nav>
    <div class="title">
        <a sveltekit:prefetch href="/">
            <h2>Svelte Starter</h2>
        </a>
    </div>

    <div>
        <ul>
            <li><a href="/">Home</a></li>
            <li><a href="/about">About</a></li>
        </ul>
    </div>
</nav>

<style lang="scss">
nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0 1rem;
  width: 100%;
  max-width: 1024px;
  margin: 0 auto;
  box-sizing: border-box;
}

.title {
  font-size: 1.5em;
  font-weight: bold;
}

ul {
  list-style: none;
  display: flex;
  justify-content: flex-end;
  align-items: center;
  gap: 1rem;
}
</style>
