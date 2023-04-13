<div class="more">
  <span class="more-info"> More info </span>
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
</style>
