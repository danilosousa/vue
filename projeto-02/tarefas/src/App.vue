<template>
	<div id="app">
		<h1>Tarefas</h1>
		<Newtask @taskAdded="addTask" />
		<TaskGrid @taskDeleted="deleteTask" :tasks="tasks"/>
	</div>
</template>

<script>
import Newtask from './components/NewTask.vue'
import TaskGrid from './components/TaskGrid.vue'

export default {
	components: { Newtask, TaskGrid },
	data(){
		return {
			// tasks: [
			// 	{ name: 'Lavar louça', pending: false },
			// 	{ name: 'Comprar Blusa', pending: true },
			// ]
			tasks: []
		}
	},
	methods: {
		addTask(task){
			const sameName = t => t.name === task.name
			const realyNew = this.tasks.filter(sameName).length == 0
			if(realyNew){
				this.tasks.push({
					name:task.name,
					pending: task.pending || true
				})
			}
		},
		deleteTask(i){
			this.tasks.splice(i, 1)
		}
	},
}
</script>

<style>
	body {
		font-family: 'Lato', sans-serif;
		background: linear-gradient(to right, rgb(22, 34, 42), rgb(58, 96, 115));
		color: #FFF;
	}

	#app {
		display: flex;
		flex: 1;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		height: 100vh;
	}

	#app h1 {
		margin-bottom: 5px;
		font-weight: 300;
		font-size: 3rem;
	}
</style>
