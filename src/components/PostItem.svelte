<script>
  import { createEventDispatcher } from 'svelte';
  export let item;

  let cls = 'far fa-heart';

  let dispatch = createEventDispatcher();

  const handleLikes = (e) => {
    if (cls === 'far fa-heart') {
      cls = 'fas fa-heart';
    } else {
      cls = 'far fa-heart';
    }
  };

  const handleDblClick = (e) => {
    cls = 'fas fa-heart';
  };

  const handleDelete = (e) => {
    dispatch('on-delete', item.id);
  };
</script>

<div class="card">
  {#if item.image}
    <div class="image">
      <img src={item.image} on:dblclick={handleDblClick} alt="" />
    </div>
  {/if}
  <p class="text">{item.text}</p>
  <div class="like-remove">
    <i class={cls} id="like" on:click={handleLikes} />
    <i class="far fa-trash-alt" id="delete" on:click={handleDelete} />
  </div>
</div>

<style>
  .card {
    color: #fff;
    background-color: #0f0f0f;
    border-radius: 15px;
    padding: 40px 50px;
    margin: 20px 0;
    border: 3px solid #f33535;
  }

  .image {
    width: 70%;
    margin: 10px auto;
    border-radius: 10px;
    text-align: center;
  }

  .image img {
    width: 100%;
    height: 100%;
    object-fit: contain;
    border-radius: 10px;
    cursor: pointer;
    border: 3px solid #fff;
  }

  .text {
    width: 70%;
    margin: 10px auto;
    font-size: 19px;
    word-wrap: break-word;
  }

  .like-remove {
    display: flex;
    align-items: center;
    justify-content: space-between;
  }

  i {
    cursor: pointer;
    font-size: 20px;
  }

  #like {
    color: red;
  }

  #delete {
    color: #fff;
  }

  i:hover {
    transform: scale(1.1);
  }
</style>
