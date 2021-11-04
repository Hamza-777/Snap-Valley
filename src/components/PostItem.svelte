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

  i {
    cursor: pointer;
    color: red;
    font-size: 20px;
  }

  i:hover {
    transform: scale(1.1);
  }
</style>
