<script>
  
  import { CircleIcon, Edit2Icon, Trash2Icon } from 'svelte-feather-icons'
  import { createEventDispatcher } from 'svelte'
  const dispatch = createEventDispatcher()

 

  // استقبال بيانات المهمة (todo)
  export let todo = {}

  // إطلاق حدث التعديل
  function handleEdit() {
    if (todo?.id) {
      dispatch('editTodo', todo.id )
    }
  }

  // إطلاق حدث الحذف
  function handleDelete() {
    if (todo?.id) {
      dispatch('deleteTodo',   todo.id )
    }
  }
</script>

<div class="todos-todo" class:done={todo.done}>
  <div class="todos-todo_icon">
    <CircleIcon />
  </div>
  <div class="todos-todo_text">{todo.title}</div>
  <div class="todos-todo_cta">
    <div class="todos-todo_cta-edit" on:click={handleEdit}>
      <Edit2Icon />
    </div>

    <div class="todos-todo_cta-delete" on:click={handleDelete}>
      <Trash2Icon />
    </div>
  </div>
</div>
