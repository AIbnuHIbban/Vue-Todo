<template>
    <form @submit="addTodo">
        <input type="text" name="judul" v-model="title" placeholder="Isi Kegiatan">
        <input type="submit" value="Tambah" class="btn">
    </form>
</template>

<script>

export default {
    name: "AddTodo",
    data(){
        return{
            title: ''
        }
    },
    methods: {
        addTodo(e) {
            e.preventDefault();
            const newTodo = {
                title : this.title,
                completed: false
            }
            // Send to Parent
            this.$emit('add-todo', newTodo);

            this.title = "";
        }
    },
}
</script>

<style scoped>
    form{
        display: flex
    }

    input[type="text"]{
        flex: 10;
        padding: 5px;
    }
    input[type="submit"]{
        flex: 2;
    }
</style>