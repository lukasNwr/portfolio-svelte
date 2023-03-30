<script>
  // @ts-nocheck

  import { scrollTo, setGlobalOptions } from "svelte-scrolling";

  let current = "home";
  let scrollY;
  let wHeight;

  setGlobalOptions({
    duration: 1000,
    easing: function easeInOutCirc(x) {
      return x < 0.5
        ? (1 - Math.sqrt(1 - Math.pow(2 * x, 2))) / 2
        : (Math.sqrt(1 - Math.pow(-2 * x + 2, 2)) + 1) / 2;
    },
  });

  function scrollIntoView({ target }) {
    const el = document.querySelector(target.getAttribute("href"));

    if (!el) {
      return;
    }

    el.scrollIntoView({ behavior: "smooth" });
  }
</script>

<svelte:window bind:scrollY bind:innerHeight={wHeight} />

<!-- {#if scrollY > wHeight / 3} -->
<nav class="navbar">
  <div class="navbar-content">
    <div class="logo">
      <!-- svelte-ignore a11y-img-redundant-alt -->
      <img src="/logo.png" alt="logo-image" class="logo" />
      <span class="logo-text">Lukas Novorolnik</span>
    </div>
    <div class="links">
      <a
        href="#home"
        class="link {current === 'home' ? 'selected' : ''}"
        on:click={() => (current = "home")}
        use:scrollTo={"home"}>Home</a
      >
      <a
        href="#about"
        class="link {current === 'about' ? 'selected' : ''}"
        on:click={() => (current = "about")}
        use:scrollTo={"about"}>About</a
      >
      <a
        href="#work"
        class="link {current === 'work' ? 'selected' : ''}"
        on:click={() => (current = "work")}
        use:scrollTo={"work"}>Work</a
      >
    </div>
  </div>
</nav>

<!-- {/if} -->
<style>
  * {
    font-family: "Inter";
  }

  .link {
    text-decoration: none;
    color: rgba(255, 255, 255, 0.5);
    transition: color 0.3s ease-in-out;
  }

  .selected {
    color: white;
  }

  .link:hover {
    color: white;
  }

  .navbar {
    margin-top: 1rem;
    position: fixed;
    top: 0;
    left: 20%;
    display: flex;
    justify-content: center;
    flex-direction: row;
    width: 60vw;
    background-color: rgba(39, 39, 39, 0.5);
    backdrop-filter: blur(40px);
    padding-top: 1rem;
    padding-bottom: 1rem;
    z-index: 10;
    border-radius: 20px;
    border: 1px solid rgba(255, 255, 255, 0.07);
    box-shadow: 0 0 15px rgba(10, 10, 10, 0.5);
  }

  .navbar-content {
    display: flex;
    width: 100%;
    padding-inline: 3rem;
    align-items: center;
    justify-content: space-between;
  }

  .logo {
    display: flex;
    align-items: center;
  }

  .logo {
    height: 30px;
    padding-right: 1rem;
  }

  .logo-text {
    color: white;
  }

  .links {
    display: flex;
    gap: 1rem;
    justify-content: center;
    align-items: center;
  }
</style>
