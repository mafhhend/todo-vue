<template>
    <div class="task-input">
        <form @submit.prevent="formHandler">
            <input type="text" name="input" v-model="input">
            <p v-show="!isInputValid" :class="[isInputValid ? '' : 'red']">Plz</p>
        </form>,
    </div>
</template>
<script>

export default {
    data() {
        return {
            input: "",
            isInputValid: true,
            isTouched: false
        }
    },
    methods: {
        formHandler() {
            if (this.isTouched == false || this.isInputValid == false) return;

            this.$emit("addTodo", {
                id: new Date().getTime(),
                body: this.input,
                complete: false
            })

        }
    },
    watch: {
        input(newName, oldName) {
            console.log(newName)
            if (newName.length < 4) this.isInputValid = false
            else this.isInputValid = true

            this.isTouched = true
        }
    }
}

</script>

<style scoped>
.red {
    color: red;
}
</style>