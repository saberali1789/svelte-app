<script>
  // @ts-nocheck

  import Todos from '../components/todos/Todos.svelte'
  import TodosForm from '../components/todos/TodosForm.svelte'
  let todos = [
    {
      id: 1,
      title: 'شراء المستلزمات',
      done: false,
    },
    {
      id: 2,
      title: 'المنتجات',
      done: true,
    },
    {
      id: 3,
      title: 'مشاهدة الكورس',
      done: false,
    },
    {
      id: 4,
      title: 'كتابة اكواد',
      done: true,
    },
  ]

  let activeEditTodo = null

  const addTodo = (e) => {
    const title = e.detail
    const id = new Date().getTime()
    todos = [{
      title, id, done: false
    }, ...todos]
  }

  const deleteTodo = (e) => {
    const id = e.detail
    console.log(e , id);
    todos = todos.filter(t => t.id !== id)
  }

  const editTodo = (e) => {
    activeEditTodo = e.detail
  }
</script>

<main>
  <div class="container">
    <div class="todos">
      <TodosForm on:addTodo={addTodo}/>
      <Todos {todos} {activeEditTodo} on:deleteTodo={deleteTodo} on:editTodo{editTodo} />
    </div>
  </div>
</main>
