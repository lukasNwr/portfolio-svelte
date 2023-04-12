<script>
  import Home from "./home/+page.svelte";
</script>

<Home />

<svelte:body />

<svelte:head>
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" />
  <link
    href="https://fonts.googleapis.com/css2?family=Inter:wght@200;400;500;700;800&display=swap"
    rel="stylesheet"
  />
  <link
    href="https://fonts.googleapis.com/css2?family=Alice&display=swap"
    rel="stylesheet"
  />
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" />
  <link
    href="https://fonts.googleapis.com/css2?family=Rubik:ital,wght@0,300;0,400;0,500;0,600;0,700;1,300;1,400;1,500;1,600;1,700&display=swap"
    rel="stylesheet"
  />
</svelte:head>

<style>
  :global(:root) {
    --background-color: #101010;
    --light-shade: #404040;
    --secondary-text: #bbbbbb;
  }

  :global(body) {
    font-family: "Rubik";
    padding: 0;
    margin: 0;
    background-color: var(--background-color);
    scroll-behavior: smooth;
  }
</style>
