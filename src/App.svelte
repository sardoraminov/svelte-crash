<script>
  // @ts-nocheck

  import Modal from "./lib/Modal.svelte";
  import Sidebar from "./lib/Sidebar.svelte";
  import User from "./lib/User.svelte";

  let showModal = false;

  let list = [
    { fullname: "Sardor", position: "Programmer", city: "Tashkent", age: 16 },
    { fullname: "John", position: "Designer", city: "London", age: 16 },
    { fullname: "G'ishmat", position: "YouTuber", city: "Andijan", age: 16 },
  ];

  let newUser = {
    fullname: "",
    age: 0,
    city: "",
    position: "",
  };

  const deleteByIndex = (index) => {
    list.splice(index, 1);

    list = list;
  };

  const deleteAll = () => {
    list = [];
  };

  const createUser = () => {
    const { fullname, age, city, position } = newUser;
    if (!fullname || !age || !city || !position) {
      alert("Please, fill all field");
    } else {
      list.unshift(newUser);
      list = list;
      showModal = false;
    }
  };

  const toggleModal = () => {
    showModal = !showModal;
  };
</script>

<Modal {showModal} hideModal={toggleModal}>
  <h1 class="title">Create user</h1>
  <div class="modal-inputs">
    <input type="text" bind:value={newUser.fullname} placeholder="Fullname" />
    <input type="number" bind:value={newUser.age} placeholder="Age" />
    <input type="text" bind:value={newUser.position} placeholder="Position" />
    <input type="text" bind:value={newUser.city} placeholder="City" />
  </div>
  <button on:click={createUser} class="modal-create-btn">Create</button>
</Modal>
<main class="wrapper">
  <Sidebar />
  <div class="template">
    <div class="template-title">
      <h1>Users here</h1>
      <p>All users: <b>{list.length}</b></p>
    </div>
    <section class="users-section">
      <div class="users">
        {#each list as item, index}
          <User user={item} {index} {deleteByIndex} />
        {:else}
          <p class="no-users-text">No users found</p>
        {/each}
      </div>
      <div class="btns">
        <button on:click={toggleModal} class="add-user-btn">Add user</button>
        <button on:click={deleteAll} class="delete-all-btn">Delete all</button>
      </div>
    </section>
  </div>
</main>

<style scoped>
  .wrapper {
    display: flex;
    flex-direction: row;
    align-items: flex-start;
  }

  .template {
    width: 100%;
    height: 100vh;
    overflow-y: scroll;
    padding: 20px;
  }

  .template-title {
    margin-bottom: 30px;
    margin-top: 10px;
  }

  .template-title h1 {
    margin-bottom: 4px;
  }

  .template b {
    color: #ff3e00;
  }

  .users {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 15px;
  }

  .add-user-btn {
    margin: 40px 0;
    background: #b0b0b0;
    color: #fff;
    padding: 10px 16px;
    border: none;
    border-radius: 4px;
    cursor: pointer;
  }

  .delete-all-btn {
    background: #ff3e00;
    color: #fff;
    padding: 10px 16px;
    border: none;
    border-radius: 4px;
    cursor: pointer;
  }

  .modal-inputs {
    margin-top: 8px;
    display: flex;
    flex-direction: column;
  }

  .modal-inputs input {
    outline: none;
    padding: 7px 13px;
    margin: 10px 0;
  }

  .modal-create-btn {
    padding: 10px;
    margin-top: 20px;
    cursor: pointer;
  }

  .no-users-text {
    opacity: 0.8;
    font-style: italic;
    font-weight: 600;
    font-size: 18px;
  }
</style>
