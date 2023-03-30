<script>
  import FaArrowRight from "svelte-icons/fa/FaArrowRight.svelte";
  import GitButton from "./git-button.svelte";
</script>

<div class="card">
  <div class="content-wrapper">
    <!-- svelte-ignore a11y-img-redundant-alt -->
    <img
      src="/emdit-welcome-big.png"
      alt="poject-image"
      class="project-image"
    />

    <div class="text-wrapper">
      <span class="title">This is some title</span>
      <span class="project-description"
        >This is some short descriptioin of the project</span
      >
    </div>
    <div class="more">
      <span class="more-info"> More info </span>
    </div>
  </div>
</div>

<style>
  .more {
    color: var(--secondary-text);
    font-size: 1rem;
    position: relative;
    display: flex;
    align-items: start;
    cursor: pointer;
    height: full;
    width: 100%;
  }

  .more-info {
    position: relative;
    transition: color 0.2s ease-in-out;
  }

  .more-info::after {
    color: var(--secondary-text);
    content: "";
    position: absolute;
    width: 100%;
    height: 2px;
    top: 1.3rem;
    left: 0;
    bottom: 0;
    background-color: white;
    transform-origin: bottom left;
    transform: scaleX(0);
    transition: all 0.2s ease-in-out;
  }

  .more-info:hover {
    color: white;
  }

  .more-info:hover::after {
    transform: scaleX(1);
    color: white;
  }

  .card {
    position: relative;
    width: 300px;
    height: 350px;
    background-color: rgba(39, 39, 39, 0.4);
    border-radius: 10px;
    padding: 1rem;
    padding-bottom: 2rem;
    border: 1px solid rgba(255, 255, 255, 0.07);
    transition: all 0.15s ease-in;
    box-shadow: 0 0 15px rgba(10, 10, 10, 0.5);
  }

  .card:hover {
    border: 1px solid rgba(255, 255, 255, 0.25);
    box-shadow: inset 0 0 10px rgba(255, 255, 255, 0.02);
    background-color: rgba(39, 39, 39, 0.6);

    /* background-color: rgba(255, 255, 255, 0.015); */
  }

  .content-wrapper {
    height: 100%;
    display: flex;
    flex-direction: column;
    justify-content: space-evenly;
    align-items: center;
    padding-inline: 1rem;
    gap: 1rem;
  }

  .text-wrapper {
    position: relative;
    display: flex;
    flex-direction: column;
    text-align: start;
    margin-bottom: auto;
    gap: 1rem;
    color: white;
  }

  .title {
    font-size: 1.2rem;
    font-weight: bold;
  }

  .project-description {
    color: var(--secondary-text);
    font-size: 0.9rem;
  }

  .project-image {
    width: calc(100% + 2rem);
    margin-bottom: auto;
    border-radius: 5px;
  }
</style>
