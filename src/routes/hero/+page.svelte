<script>
  // @ts-nocheck

  import IoIosArrowDown from "svelte-icons/io/IoIosArrowDown.svelte";
  import { scrollTo, setGlobalOptions } from "svelte-scrolling";
  import { fade } from "svelte/transition";
  import GitButton from "../../components/git-button.svelte";

  let scrollY;
  export let currentPage;

  setGlobalOptions({
    duration: 1000,
    easing: function easeInOutCirc(x) {
      return x < 0.5
        ? (1 - Math.sqrt(1 - Math.pow(2 * x, 2))) / 2
        : (Math.sqrt(1 - Math.pow(-2 * x + 2, 2)) + 1) / 2;
    },
  });
</script>

<section class="hero">
  <container class="text">
    <span class="greeting"> Hi, I am </span>
    <span class="name">Lukas Novorolnik</span>
    <span class="subtitle"
      >Computer Science student and lover of refined simplicity</span
    >
  </container>
  {#if scrollY < 20}
    <div class="about-arrow" transition:fade={{ duration: 150 }}>
      <span>About me</span>
      <button
        class="arrow-icon"
        use:scrollTo={"about"}
        on:click={() => {
          currentPage = "about";
        }}
      >
        <IoIosArrowDown />
      </button>
    </div>
  {/if}
</section>

<svelte:window bind:scrollY />

<style>
  * {
    color: white;
  }

  span {
    text-align: left;
  }

  .about-arrow {
    color: var(--secondary-text);
    display: flex;
    flex-direction: column;
    justify-content: center;
    position: absolute;
    bottom: 1rem;
  }

  .about-arrow > span {
    font-size: 0.9rem;
  }

  .arrow-icon {
    height: 2.8rem;
    background-color: transparent;
    border: none;
    cursor: pointer;
  }

  .hero {
    position: relative;
    min-height: 100vh;
    display: flex;
    width: 100vw;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }

  .text {
    width: 60vw;
    text-align: left;
    display: flex;
    flex-direction: column;
  }

  .name {
    font-size: 5rem;
    font-weight: bold;
    font-family: "Alice";
  }

  @media screen and (max-width: 600px) {
    .text {
      width: 70vw;
    }
    .name {
      font-size: 3.5rem;
    }
  }
</style>
