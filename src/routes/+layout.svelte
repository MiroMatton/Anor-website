<script>
  import "../app.css";

  let { children } = $props();
</script>

<div class="app">
  <main>
    {@render children()}
  </main>

  <footer>
    <p>
      made bij miro matton <a href="https://miromatton.be">have a looksie :)</a>
    </p>
  </footer>
</div>

<style>
  .app {
    display: flex;
    flex-direction: column;
    min-height: 100vh;
  }

  main {
    flex: 1;
    display: flex;
    flex-direction: column;
    box-sizing: border-box;
  }
  footer {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    padding: 12px;
  }

  footer a {
    font-weight: bold;
  }

  :global(.section-wrapper) {
    padding-left: 5rem;
    padding-right: 5rem;
    max-width: 120rem;
    margin-left: auto;
    margin-right: auto;
  }

  @media (min-width: 480px) {
    footer {
      padding: 12px 0;
    }
  }
</style>
