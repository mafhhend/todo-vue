<template>
    <ul class="task-box">
        <template v-for="todo in todos" :key="todo.id">

            <ul v-if="tab == 'completed'">
                <li v-if="todo.complete === true">
                    <span class="text-body" @click="toggleComplete(todo.id)">{{ todo.body }}</span>
                </li>
            </ul>
            <ul v-else-if="tab == 'pending'">
                <li v-if="todo.complete === false" @click="toggleComplete(todo.id)">
                    <span class="text-body">{{ todo.body }}</span>
                </li>
            </ul>
            <ul v-else>
                <li>
                    <span class="text-body" @click="toggleComplete(todo.id)">{{ todo.body }}</span>
                </li>
            </ul>

        </template>
    </ul>
</template>

<script>
export default {
    props: ["todos", "tab"],

    methods: {
        toggleComplete(id) {
            console.log(this.tab)
            this.$emit("toggleComplete", id)
        }
    }
}
</script>