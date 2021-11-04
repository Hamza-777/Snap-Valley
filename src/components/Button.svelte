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
    background-color: #f33535;
    cursor: pointer;
    transition: 200ms;
    color: #fff;
  }

  button:hover {
    transform: scale(1.1);
  }

  button:disabled {
    background-color: transparent;
    cursor: auto;
    color: #fff;
    border: 1px solid #fff;
  }

  button:disabled:hover {
    transform: scale(1);
  }
</style>
