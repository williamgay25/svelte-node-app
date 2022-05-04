<script>
	import ToDoInputForm from './ToDoInputForm.svelte' 
	import ToDoList from './ToDoList.svelte'
	let nameEntered = false

	let firstName = 'John'
	let lastName = 'Doe'

	$: fullName = firstName + ' ' + lastName
</script>

<main class='flex flex-col content-center'>
	<div class="m-auto">
		{#if nameEntered}
			<h1>Welcome to task manager, {fullName}!</h1>
			<ToDoInputForm userName={fullName} />
			<ToDoList />
		{:else}
			<h1>Welcome to task manager!</h1>
			<h3>Please enter your name:</h3>
			<div>
				<input type="text" placeholder="First name" required>
			</div>
			<div>
				<input type="text" placeholder="Last name" required>
			</div>
		{/if}
	</div>
</main>


<style lang='postcss' global>
	@tailwind base;
	@tailwind components;
	@tailwind utilities;
  </style>