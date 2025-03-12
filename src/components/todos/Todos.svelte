<script>
  // @ts-nocheck

  import Todo from './Todo.svelte'
  export let todos = []
</script>

<div class="todos-list">
  {#each todos as todo (todo.id)}
    <Todo {todo} on:deleteTodo />
  {/each}
</div>
