<script>
  export let disabled;
</script>

<button type="submit" {disabled}>Post</button>

<style>
  button {
    width: 75px;
    height: 35px;
    border-radius: 10px;
    border: none;
    outline: none;
    background-color: #6ddccf;
    cursor: pointer;
    transition: 200ms;
  }

  button:hover {
    transform: scale(1.1);
  }

  button:disabled {
    background-color: #777;
    cursor: auto;
    color: #000;
  }

  button:disabled:hover {
    transform: scale(1);
  }
</style>
