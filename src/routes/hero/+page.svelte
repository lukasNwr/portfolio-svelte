<script>
  // @ts-nocheck

  import IoIosArrowDown from "svelte-icons/io/IoIosArrowDown.svelte";
  import GitButton from "../../components/git-button.svelte";

  let scrollY;
</script>

<section class="hero">
  <container class="text">
    <span class="greeting"> Hi, I am </span>
    <span class="name">Lukas Novorolnik</span>
    <span class="subtitle"
      >Computer Science student and lover of refined simplicity</span
    >
  </container>
  <!-- <div class="goto">
    <span class="goto-text">About me</span>
    <div class="chevron-down">
      <IoIosArrowDown />
    </div>
  </div> -->
</section>

<svelte:window bind:scrollY />

<style>
  * {
    color: white;
  }

  span {
    text-align: left;
  }

  .hero {
    position: relative;
    height: 100vh;
    width: 100vw;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }

  .text {
    width: 50vw;
    text-align: left;
    display: flex;
    flex-direction: column;
  }

  .name {
    font-size: 5rem;
    font-weight: bold;
    font-family: "Alice";
  }
</style>
