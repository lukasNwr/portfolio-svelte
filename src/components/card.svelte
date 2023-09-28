<script>
  // @ts-nocheck
  import FaGithubAlt from "svelte-icons/fa/FaGithubAlt.svelte";
  import GiPlayButton from "svelte-icons/gi/GiPlayButton.svelte";
  import CardButton from "./cardButton.svelte";

  export var github = false;
  export var livePage = false;
  export var imageName;
  export var description;
  export var title;
  export var gitUrl;
  export var liveUrl;

  

  const imageSrc = imageName + ".png";
</script>

<div class="card">
  <div class="content-wrapper">
    

    <!-- svelte-ignore a11y-img-redundant-alt -->
      <img src={imageSrc} class='project-image' alt="project-image"  />
 

    <div class="text-wrapper">
      <span class="title">{title}</span>
      <span class="project-description">{description}</span>
    </div>
    <div class="buttons">
      {#if livePage}
        <CardButton buttonText="Live Page" url={liveUrl}>
          <GiPlayButton />
        </CardButton>
      {/if}
      {#if github}
        <CardButton buttonText="Code" url={gitUrl}>
          <FaGithubAlt />
        </CardButton>
      {/if}
    </div>
  </div>
</div>

<style>
  .buttons {
    width: 100%;
    display: flex;
    justify-content: space-between;
    gap: 2rem;
  }
  .card {
    position: relative;
    width: 300px;
    height: 380px;
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
    background-color: rgba(45, 45, 45, 0.6);

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
