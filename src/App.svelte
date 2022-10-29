<script>
  import TodoForm from "./lib/TodoForm.svelte";
  import TodoItem from "./lib/TodoItem.svelte";
  import TodoList from "./lib/TodoList.svelte";

  let items = [1, 2, 3, 4, 5, 6];

  const onCreateItem = ({ detail: { inputValue } }) => {
    items = [...items, inputValue];
  };

  const onDeleteItem = ({ detail: { idx } }) => {
    items = items.filter((_, i) => i !== idx);
  };
</script>

<main>
  <TodoForm on:onCreateItem="{onCreateItem}" />
  <TodoList>
    {#each items as item, idx}
      <TodoItem item="{item}" idx="{idx}" on:onDeleteItem="{onDeleteItem}" />
    {/each}
  </TodoList>
</main>
