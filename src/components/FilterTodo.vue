<template>
    <div class="controls">
        <div class="filters">
            <span :class="[active == 'all' ? 'active' : '']" @click="changeTab">All</span>
            <span :class="[active == 'pending' ? 'active' : '']" @click="changeTab">Pending</span>
            <span :class="[active == 'completed' ? 'active' : '']" @click="changeTab">Completed</span>
        </div>
        <button @click="clearTodos" class="clear-btn">Clear All</button>
    </div>
</template>
<script>

export default {
    data() {
        return {
            active: "all"
        }
    },
    methods: {
        clearTodos() {
            this.$emit("clearTodos")
        },
        changeTab(e) {
            const active = e.target.textContent.toLowerCase()
            this.$emit("changeTab", active)
            this.active = active
        }
    }
}
</script>

<style>
</style>