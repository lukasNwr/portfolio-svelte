<script>
  let year = new Date().getFullYear();
</script>

<section class="footer">
  <div class="content">Created by Lukas Novorolnik, {year}</div>
</section>

<style>
  .footer {
    width: 100%;
    height: 5rem;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .content {
    width: 60%;
    color: rgba(255, 255, 255, 0.7);
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 0.8rem;
  }
</style>
