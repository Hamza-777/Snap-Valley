<script>
  export let item;

  let cls = 'far fa-heart';

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
</script>

<div class="card">
  {#if item.image}
    <div class="image">
      <img src={item.image} on:dblclick={handleDblClick} alt="" />
    </div>
  {/if}
  <p class="text">{item.text}</p>
  <i class={cls} on:click={handleLikes} />
</div>

<style>
  .card {
    color: #333;
    background-color: #fff;
    border-radius: 15px;
    padding: 40px 50px;
    margin: 20px 0;
    border: 3px solid #333;
  }

  .image {
    width: 70%;
    height: 70%;
    margin: 10px auto;
  }

  .image img {
    width: 100%;
    height: 100%;
    object-fit: contain;
    border-radius: 10px;
    cursor: pointer;
  }

  .text {
    width: 60%;
    margin: 10px auto;
    font-size: 19px;
    word-wrap: break-word;
  }

  i {
    cursor: pointer;
    color: red;
    font-size: 20px;
  }

  i:hover {
    transform: scale(1.1);
  }
</style>
