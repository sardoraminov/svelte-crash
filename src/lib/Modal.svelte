<script>
  export let showModal;
  export let hideModal
</script>

{#if showModal}
  <div class="modal-layout" on:click|self={hideModal}>
    <div class="modal-box">
      <slot />
    </div>
  </div>
{/if}

<style>
  .modal-layout {
    height: 100vh;
    width: 100%;
    position: fixed;
    top: 0;
    right: 0;
    left: 0;
    bottom: 0;
    background: rgba(0, 0, 0, 0.6);
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    z-index: 9999;
  }

  .modal-box {
    display: flex;
    flex-direction: column;
    background-color: #fff;
    border-radius: 3px;
    border: 1px solid #ccc;
    padding: 30px;
    z-index: 9999;
  }
</style>
