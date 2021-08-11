<template>
    <header>
        <h1>{{ title }}</h1>
        <h2>Welcome {{playerName}}</h2>
    </header>
</template>

<script>
export default {
    name: 'Header',
    props: {
        title: String,
        playerName: String
    }
}
</script>

<style scope>
    header {
        display: flex;
        justify-content: space-between;
        align-items: center;
        margin-bottom: 20px;
    }

</style>