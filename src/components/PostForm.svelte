<script>
  import { v4 as uuidv4 } from 'uuid';
  import { createEventDispatcher } from 'svelte';
  import Button from './Button.svelte';

  $: image = '';
  let text = '';
  let btnDisabled = true;

  let dispatch = createEventDispatcher();

  const handleInput = () => {
    if (text) {
      btnDisabled = false;
    } else {
      btnDisabled = true;
    }
  };

  const handleChange = (e) => {
    image = URL.createObjectURL(e.target.files[0]);
  };

  const handleSubmit = () => {
    const newPost = {
      id: uuidv4(),
      image,
      text,
    };
    if (text !== '') {
      dispatch('new-post', newPost);
    }
    text = '';
    image = '';
  };
</script>

<div class="container">
  <form on:submit|preventDefault={handleSubmit}>
    <h2 class="para">Tell us something about your day</h2>
    <div class="photo">
      <label for="img">Upload an image</label>
      <input
        type="file"
        on:change={handleChange}
        id="img"
        name="img"
        accept="image/*"
      />
      {#if image}
        <div class="preview">
          <img src={image} alt="" />
        </div>
      {/if}
    </div>
    <textarea
      type="text"
      bind:value={text}
      on:input={handleInput}
      placeholder="Add some description or share something..."
    />
    <Button disabled={btnDisabled} />
  </form>
</div>

<style>
  form {
    width: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    gap: 20px;
    margin-top: 70px;
  }

  input[type='file'] {
    display: none;
  }

  .photo {
    display: flex;
    gap: 20px;
    align-items: center;
    justify-content: center;
    cursor: pointer;
    border: 2px solid #333;
    border-radius: 10px;
    padding: 5px 10px;
    transition: 200ms;
  }

  .photo label {
    font-size: 19px;
    cursor: pointer;
    font-weight: 600;
  }

  .photo .preview {
    width: 75px;
    height: 75px;
  }

  .photo .preview img {
    width: 100%;
    height: 100%;
    object-fit: contain;
  }

  .photo:hover {
    transform: scale(1.1);
  }

  textarea {
    width: 75%;
    height: 100px;
    font-size: 16px;
    padding: 5px 10px;
    border-radius: 10px;
    outline: none;
    border: 2px solid #333;
    background-color: transparent;
  }
</style>
