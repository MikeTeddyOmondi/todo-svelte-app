<script>
	import { addTodo } from '../stores/todoStore.js';
	let todo = '';
	const handleSubmit = () => {
		// console.log('Submitting...');
		if (todo === '') {
			todo = '';
			return alert('Please enter a todo as required!');
		}
		addTodo(todo);
		todo = '';
	};
</script>

<form class="my-6 mx-3" on:submit|preventDefault={handleSubmit}>
	<div class="flex flex-col text-sm mb-2">
		<label for="todo" class="font-bold mb-2 text-gray-800">Todo:</label>
		<input
			type="text"
			name="todo"
			bind:value={todo}
			placeholder="What's on your mind?"
			class="appearance-none shadow-sm border border-gray-200 p-2 focus:outline-none focus:border-gray-500 rounded-lg"
		/>
	</div>
	<button
		type="submit"
		class="w-full shadow-sm rounded bg-blue-500 hover:bg-blue-600 text-white py-2 px-4">Add</button
	>
</form>
