<script>
    let todo = [
    ];
  
    function addTodo() {
      const text = document.getElementById("todo-input").value;
      if (text) {
        todo = [...todo, { id: todo.length + 1, text }];
        document.getElementById("todo-input").value = "";
      }
    }
  
    function removeTodo(id) {
      todo = todo.filter((item) => item.id !== id);
    }
  </script>
  
  <nav>
    <span class="flex items-center justify-center border-b-4 border-yellow-600 bg-yellow-300 py-2 text-3xl font-bold" title="😅 Because I don't know when I will do These task.">To-do list 😅</span>
  </nav>
  <section class="mx-auto h-screen w-screen max-w-6xl border-x-4 border-gray-600 bg-gray-200">
    <div class="flex items-center justify-center gap-3 p-2">
      <form id="todo-form" action="" class="flex items-center justify-center gap-3">
        <input id="todo-input" type="text" placeholder="What needs to be done?" class="focus:ring-2 focus:ring-yellow-500 focus:border-yellow-500 focus:outline-none appearance-none w-full text-lg  text-slate-900 rounded-md p-2 ring-1 ring-slate-200 shadow-sm border-2 border-black" />
        <button on:click={addTodo} id="todo-submit" type="submit" class="flex h-10 w-10 items-center justify-center rounded-md border-2 border-green-600 bg-green-300 text-2xl text-green-800">+</button>
      </form>
    </div>
    {#each todo as item}
    <div class="flex items-center justify-center gap-3 p-2">
      <div class="flex items-center justify-center gap-3">
        <span class="sm:w-96 rounded-md border-2 border-gray-600 bg-white p-2 focus:border-green-600">{item.text}</span>
        <button on:click={() => removeTodo(item.id)} class="flex h-10 w-10 items-center justify-center rounded-md border-2 border-red-600 bg-red-300 text-2xl text-red-800">x</button>
      </div>
    </div>
    {/each}
  </section>
