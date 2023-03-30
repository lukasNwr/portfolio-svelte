<script>
  import FaGithubAlt from "svelte-icons/fa/FaGithubAlt.svelte";

  function doClick() {
    console.log("first");
  }
</script>

<button on:click={doClick}>
  <div class="icon">
    <FaGithubAlt />
  </div>
  GitHub
</button>

<style>
  .icon {
    width: 24px;
    height: 24px;
  }

  button {
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 1rem;
    padding: 8px 20px 8px 20px;
    border: 1px solid white;
    border-radius: 10px;
    background-color: transparent;
    color: white;
    z-index: 30;
  }

  button:hover {
    color: gray;
    background-color: red;
  }
</style>
