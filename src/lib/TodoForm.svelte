<script>
  import { createEventDispatcher } from "svelte";

  const dispatch = createEventDispatcher();
  let formRef;
  let inputRef;

  const onCreateItem = () => {
    dispatch("onCreateItem", { inputValue: inputRef.value });
    inputRef.value = "";
  };
</script>

<style>
  .form {
    margin-bottom: 8px;
  }
</style>

<form
  class="form"
  bind:this="{formRef}"
  on:submit|preventDefault="{onCreateItem}"
>
  <input bind:this="{inputRef}" type="text" />
  <button type="submit">생성</button>
</form>
