<script>
  // @ts-nocheck

  import GitButton from "./git-button.svelte";

  let card;
  function onMouseMove(e) {
    const rect = card.getBoundingClientRect(),
      x = e.clientX - rect.left,
      y = e.clientY - rect.top;

    card.style.setProperty("--mouse-x", `${x}px`);
    card.style.setProperty("--mouse-y", `${y}px`);
  }
</script>

<div bind:this={card} on:mousemove={onMouseMove} class="card">
  <div class="card-border" />
  <div class="card-content">
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
      <GitButton />
    </div>
  </div>
</div>

<style>
  :root {
    --card-color: rgba(20, 20, 20);
    /* --card-color: transparent; */
  }

  .project-image {
    width: calc(100% - 1rem);
    margin-bottom: auto;
    position: relative;
  }

  .text-wrapper {
    position: relative;
    display: flex;
    flex-direction: column;
    text-align: center;
    margin-bottom: auto;
    gap: 1rem;
  }

  .content-wrapper {
    position: relative;
    height: 90%;
    display: flex;
    opacity: 0.5;
    flex-direction: column;
    align-items: center;
    padding: 2rem;
    z-index: 5;
    opacity: 1;
    background-color: transparent;
  }

  .title {
    font-size: 1.2rem;
    font-weight: bold;
  }

  .project-description {
    color: var(--secondary-text);
    font-size: 0.9rem;
  }

  .card {
    position: relative;
    width: 350px;
    height: 400px;
    background-color: rgba(255, 255, 255, 0.08);
    cursor: pointer;
    border-radius: 10px;
    z-index: 0;
  }

  .card:hover > .card-border,
  .card:hover::before {
    opacity: 1;
  }

  .card > .card-border,
  .card::before {
    opacity: 0;
    transition: opacity 500ms;
    border-radius: inherit;
    content: "";
    height: 100%;
    left: 0;
    position: absolute;
    top: 0;
    width: 100%;
    z-index: 2;
  }

  .card::before {
    background: radial-gradient(
      800px circle at var(--mouse-x) var(--mouse-y),
      rgba(200, 200, 200, 0.06),
      transparent 50%
    );
    z-index: 2;
  }

  .card > .card-border {
    background: radial-gradient(
      500px circle at var(--mouse-x) var(--mouse-y),
      rgba(255, 255, 255, 0.15),
      transparent 50%
    );
    z-index: 1;
  }

  .card > .card-content {
    height: calc(100% - 2px);
    width: calc(100% - 2px);
    background-color: var(--card-color);
    margin: 1px;
    border-radius: inherit;
    position: relative;
    z-index: 1;
    color: white;
  }

  .card > .card-content > .content-wrapper {
    z-index: 4;
  }
</style>
