<script>
  import { todo } from '../stores/todo'

  let text = ''
  const registerTodo = () => {
    $todo = [...$todo, {text, 'isDone': false}]

    text = ''
  }
</script>

<form class="main_form">
<input
  bind:value={text}
  class="main_form_txt"
  type="text"
  placeholder="TODO">
  <button
    on:click={registerTodo}
    class="main_form_submit"
    type="button">
    追加
  </button>
{$todo}
</form>

<style>
  .main_form {
  width: 800px;
  margin: 100px auto 0;
  display: flex;
  justify-content: space-between;
}
.main_form_txt {
  width: 700px;
  padding: 12px 0;
  padding-left: 20px;
  font-size: 20px;
  border-radius: 7px;
  color: #000;
  border: 1px solid #707070;
  background-color: #fff;
}
.main_form_submit {
  display: block;
  width: 70px;
  border-radius: 7px;
  padding: 12px 18px;
  color: #000;
  border: 1px solid #707070;
  background-color: #fff;
}
</style>
