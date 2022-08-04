<script>
  export let user;
  export let index
  export let deleteByIndex

  const handleDelete = (i) => {
    deleteByIndex(i)
  }
</script>

<div class="user-card">
  <div class="user-info">
    <div class="info-top">
      <h2>{user.fullname}</h2>
      <p>{user.age} y.o</p>
    </div>
    <div class="info-body">
      <p>{user.position} from {user.city}</p>
    </div>
  </div>
  <button on:click={() => handleDelete(index)} class="user-managing">Delete</button>
</div>

<style>
  .user-card {
    background: #fff;
    padding: 15px;
    border-radius: 5px;
    cursor: pointer;
    transition: all 0.4s ease;
    position: relative;
    overflow: hidden;
  }

  .user-card::after {
    content: "";
    position: absolute;
    right: 0;
    top: 0;
    width: 3px;
    height: 100%;
    background: #ff3e00;
    transition: all 0.4s ease;
  }

  .user-card h2 {
    transition: all 0.4s ease;
  }

  .user-card:hover h2 {
    color: #ff3e00;
  }

  .user-card:hover::after {
    transform: scaleX(8);
  }

  .user-card:hover {
    box-shadow: 0px 20px 62px 0px rgba(0, 0, 0, 0.111);
  }

  .info-top {
    margin-bottom: 15px;
  }

  .info-body p {
    font-size: 16px;
    font-style: italic;
  }

  .info-body {
    margin-bottom: 15px;
  }

  button {
    background: #ff3e00;
    color: #fff;
    border: none;
    padding: 10px 15px;
    border-radius: 5px;
    cursor: pointer;
  }
</style>
