<template>
    <header>
        <nav>
            <ul>
                <li><nuxt-link to="/">Starting page</nuxt-link></li>
                <li><nuxt-link to="/airbnb">Rooms</nuxt-link></li>
                <li><nuxt-link to="/login">Login</nuxt-link></li>
            </ul>
        </nav>
    </header>
</template>

<style scoped>
header {
    width: 100%;
    height: 30px;
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: #ff5a60
}

ul {
    list-style: none;
    padding: 0;
    margin: 0;
    display: flex;
    justify-content: center;
    align-items: center;
}

li {
    margin: 0 10px;
}

a {
    text-decoration: none;
    color: white;
}
</style>
