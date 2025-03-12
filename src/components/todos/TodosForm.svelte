<script>
import {CircleIcon} from "svelte-feather-icons"
import { createEventDispatcher } from 'svelte'
const dispatch = createEventDispatcher()

let value = ''

const handleAddTodo = () => {
  dispatch('addTodo', value)
}
</script>

<div class="todos-form">
  <div class="todos-form_icon">
    <CircleIcon />
  </div>

  <div class="todos-form_form">
    <input bind:value={value} type="text" placeholder="اضف مهمة جديدة ..." />
  </div>
  <div class="todos-form_submit" on:click={handleAddTodo}>
    <button class="btn">اضافة</button>
  </div>
</div>
