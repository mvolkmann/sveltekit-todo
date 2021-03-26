<script>
  import { page } from '$app/stores';
  $: path = $page.path;

  const routes = [
    { name: 'About', url: '/about' },
    { name: 'Todos', url: '/' }
  ];
</script>

<nav>
  {#each routes as { name, url }}
    <a class:current={url === path} href={url}>{name}</a>
  {/each}
</nav>

<main>
  <slot />
</main>

<style>
  a {
    color: var(--primary-color);
    margin-right: 1rem;
    text-decoration: none;
  }

  a.current {
    font-weight: bold;
  }

  main {
    padding: 1rem;
  }

  nav {
    background-color: var(--secondary-color);
    padding: 1rem;
  }
</style>
