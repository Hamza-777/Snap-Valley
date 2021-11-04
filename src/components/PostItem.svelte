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
</script>

<div class="card">
  {#if item.image}
    <div class="image">
      <img src={item.image} alt="" />
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
    width: 80%;
    height: 80%;
    margin: 10px auto;
  }

  .image img {
    width: 100%;
    height: 100%;
    object-fit: contain;
  }

  .text {
    margin: 10px auto;
    text-align: center;
    font-size: 19px;
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
