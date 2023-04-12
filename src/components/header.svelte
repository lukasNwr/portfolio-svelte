<script>
  // @ts-nocheck
  import FaBars from "svelte-icons/fa/FaBars.svelte";
  import FaTimes from "svelte-icons/fa/FaTimes.svelte";
  import { scrollTo, setGlobalOptions } from "svelte-scrolling";
  import { fade } from "svelte/transition";

  export let currentPage = "home";

  let mobileMenu = false;
  let scrollY;
  let wHeight;
  let menuHeight = "full";

  $: mobileMenu ? (menuHeight = "25vh") : (menuHeight = "2rem");

  setGlobalOptions({
    duration: 1000,
    easing: function easeInOutCirc(x) {
      return x < 0.5
        ? (1 - Math.sqrt(1 - Math.pow(2 * x, 2))) / 2
        : (Math.sqrt(1 - Math.pow(-2 * x + 2, 2)) + 1) / 2;
    },
  });

  // functio for displaying a blue circle on the page
</script>

<svelte:window bind:scrollY bind:innerHeight={wHeight} />

{#if scrollY > wHeight / 3}
  <nav
    class="navbar"
    style="height: {menuHeight}"
    transition:fade={{ duration: 200 }}
  >
    <div class="navbar-content">
      <div class="inline-content">
        <div class="logo">
          <!-- svelte-ignore a11y-img-redundant-alt -->
          <img src="/logo.png" alt="logo-image" class="logo" />
          <span class="logo-text">Lukas Novorolnik</span>
        </div>
        <div class="links">
          <a
            href="#home"
            class="link {currentPage === 'home' ? 'selected' : ''}"
            on:click={() => (currentPage = "home")}
            use:scrollTo={"home"}>Home</a
          >
          <a
            href="#about"
            class="link {currentPage === 'about' ? 'selected' : ''}"
            on:click={() => (currentPage = "about")}
            use:scrollTo={"about"}>About</a
          >
          <a
            href="#work"
            class="link {currentPage === 'work' ? 'selected' : ''}"
            on:click={() => (currentPage = "work")}
            use:scrollTo={"work"}>Work</a
          >
        </div>
        <div class="menu-icons">
          {#if !mobileMenu}
            <button
              class="hamburger-icon"
              on:click={() => {
                mobileMenu = !mobileMenu;
              }}
            >
              <FaBars />
            </button>
          {:else}
            <button
              class="close-icon"
              on:click={() => {
                mobileMenu = !mobileMenu;
              }}
            >
              <FaTimes />
            </button>
          {/if}
        </div>
      </div>
      {#if mobileMenu}
        <div class="links-mobile" in:fade={{ duration: 200, delay: 300 }}>
          <a
            href="#home"
            class="link {currentPage === 'home' ? 'selected' : ''}"
            on:click={() => (currentPage = "home")}
            use:scrollTo={"home"}>Home</a
          >
          <a
            href="#about"
            class="link {currentPage === 'about' ? 'selected' : ''}"
            on:click={() => (currentPage = "about")}
            use:scrollTo={"about"}>About</a
          >
          <a
            href="#work"
            class="link {currentPage === 'work' ? 'selected' : ''}"
            on:click={() => (currentPage = "work")}
            use:scrollTo={"work"}>Work</a
          >
        </div>
      {/if}
    </div>
  </nav>
{/if}

<style>
  * {
    font-family: "Rubik";
  }

  .inline-content {
    display: flex;
    width: inherit;
    align-items: center;
    justify-content: space-between;
  }

  .menu-icons {
    display: none;
    justify-content: center;
    align-items: center;
    height: 2rem;
    width: 2rem;
  }

  .links-mobile {
    display: none;
    flex-direction: column;
    gap: 2rem;
    padding-top: 2rem;
    padding-bottom: 1.2rem;
    font-size: 1.1rem;
  }

  .hamburger-icon {
    height: 1.8rem;
    color: white;
    background-color: transparent;
    border: none;
  }

  .close-icon {
    height: 1.8rem;
    color: white;
    background-color: transparent;
    border: none;
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
    left: 15%;
    display: flex;
    justify-content: center;
    flex-direction: row;
    width: 70vw;
    background-color: rgba(39, 39, 39, 0.5);
    backdrop-filter: blur(40px);
    -webkit-backdrop-filter: blur(40px);
    padding-top: 1rem;
    padding-bottom: 1rem;
    z-index: 10;
    border-radius: 20px;
    border: 1px solid rgba(255, 255, 255, 0.07);
    box-shadow: 0 0 15px rgba(10, 10, 10, 0.5);
    transition: height 0.5s ease-in-out;
  }

  .navbar-content {
    display: flex;
    flex-direction: column;
    width: 100%;
    align-items: center;
    padding-inline: 3rem;
    justify-content: space-between;
  }

  .logo {
    display: flex;
    align-items: center;
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

  @media only screen and (max-width: 1000px) {
    .logo-text {
      display: none;
    }
    .navbar {
      width: 80vw;
      left: 10%;
    }

    .navbar-content {
      padding-inline: 1rem;
    }
  }

  @media only screen and (max-width: 600px) {
    .navbar {
      width: 90vw;
      left: 5%;
    }

    .navbar-content {
      padding-inline: 1rem;
    }
    .links {
      display: none;
    }

    .links-mobile {
      display: flex;
    }

    .menu-icons {
      display: flex;
    }
  }
</style>
