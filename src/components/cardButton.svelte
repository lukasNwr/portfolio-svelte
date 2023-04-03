<script>
  export var buttonText = "More info";
  export var url = "";
</script>

<div class="more">
  <a href={url} class="more-info"><slot />{buttonText}</a>
</div>

<style>
  .more-info :global(> :first-child) {
    height: 16px;
    width: 16px;
  }

  .more {
    color: var(--secondary-text);
    font-size: 1rem;
    position: relative;
    display: flex;
    align-items: start;
    cursor: pointer;
    height: full;
  }

  .more-info {
    text-decoration: none;
    color: var(--secondary-text);
    position: relative;
    transition: color 0.2s ease-in-out;
    display: flex;
    gap: 0.5rem;
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
</style>
