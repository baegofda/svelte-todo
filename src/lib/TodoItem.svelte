<script>
  import { createEventDispatcher } from "svelte";

  export let item;
  export let idx;

  const dispatch = createEventDispatcher();

  const onDeleteItem = () => {
    dispatch("onDeleteItem", { idx });
  };
</script>

<style>
  .item {
    display: flex;
    align-items: center;
    text-align: left;
  }

  .checkbox {
    margin-right: 4px;
  }

  .btn {
    margin-left: auto;
  }
</style>

<li class="item">
  <input class="checkbox" type="checkbox" />
  <span>
    {item}
  </span>
  <button class="btn" type="button" on:click="{onDeleteItem}">삭제</button>
</li>
