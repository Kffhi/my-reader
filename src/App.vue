<template>
    <div id="app">
        <div id="nav">
            <router-link to="/">Home</router-link>
            |
            <router-link to="/about">About</router-link>
        </div>
        <router-view/>
    </div>
</template>
<script>
    document.addEventListener('DOMContentLoader', () => {
        const html = document.querySelector('html')
        let fontSize = window.innerWidth / 10
        fontSize = fontSize > 50 ? 50 : fontSize
        html.style.fontSize = fontSize + 'px'
    })
</script>
<style>
</style>
