<script>
  import Img from "../assets/svelte.svg";
</script>

<aside class="aside sidebar">
  <div class="aside-top">
    <h3>
      <img src={Img} alt="icon" />
      User management
    </h3>
  </div>
  <div class="aside-links">
    <a href="https://dasturchioka.uz" target="_blank">Dasturchioka</a>
    <a href="https://dasturchioka.uz" target="_blank">Best developer</a>
    <a href="https://dasturchioka.uz" target="_blank">Coldest man</a>
    <a href="https://dasturchioka.uz" target="_blank">Billionaire</a>
    <a href="https://dasturchioka.uz" target="_blank">Influencer</a>
    <a href="https://dasturchioka.uz" target="_blank">Your teacher</a>
  </div>
  <div class="aside-copy">
    <p>&copy; 2022 <a href="https://dasturchioka.uz">dasturchioka.uz</a></p>
  </div>
</aside>

<style>
  .aside {
    width: 400px;
    height: 100vh;
    background: #fff;
    border-right: 2px solid #b7b7b7;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    padding: 30px 15px;
  }

  .aside-top h3 {
    display: flex;
    flex-direction: row;
    align-items: center;
  }

  .aside h3 img {
    margin-right: 15px;
  }

  .aside-links {
    display: flex;
    flex-direction: column;
  }

  .aside-links a {
    margin: 10px 0;
    font-weight: 600;
    font-size: 18px;
    transition: all 0.2s ease;
    background: #f4f4f4;
    padding: 10px;
    border-radius: 6px;
  }

  .aside-links a:hover {
    color: #fff;
    background: #ff3e00;
    padding-left: 20px;
  }
</style>
