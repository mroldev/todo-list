<template>
    <div>
        <section class="todoapp">
            <header class="header">
                <h1>Todos</h1>
                <input type="text" class="new-todo" placeholder="Ajouter une tache" v-model="newTodo" @keyup.enter="addTodo">
            </header>

            <div class="main">
                <ul class="todo-list">
                    <li class="todo" v-for="todo in todos" :key="todo" >
                        <div class="view">
                            <input type="checkbox" v-model="computed">
                            <label>{{todo.name}}</label>
                        </div>
                    </li>
                </ul>
            </div>

        </section>
    </div>
</template> 


<script>
export default {

    data(){
        return{
             todos : [],
            newTodo: ''
        }
    },

    methods: {
        addTodo(){
            this.todos.push({
                completed : false,
                name : this.newTodo
            })
            this.newTodo = ''
        }
    }
    
}
</script>


<style  src="./todo.css">
    
</style>