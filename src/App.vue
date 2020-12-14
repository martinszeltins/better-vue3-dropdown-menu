<template>
    <div v-if="showThing">a<br v-for="n in 9" /></div>

    <better-dropdown-menu v-model="showMenu">
        <button @click="showMenu = !showMenu">
            Button
        </button>

        <template #dropdown>
            <div class="menu">Menu Menu Menu Menu Menu Menu </div>
            <div class="menu">Menu</div>
        </template>
    </better-dropdown-menu>

    <div>
        <br /><br /><br /><br />
        <better-dropdown-menu v-model="showMenu2" placement="right">
            <button @click="showMenu2 = !showMenu2">
                Button
            </button>

            <template #dropdown>
                <div class="menu">Menu Menu </div>
                <div class="menu">Menu</div>
            </template>
        </better-dropdown-menu>
    </div>
</template>

<script setup>
    import { ref } from 'vue'
    import BetterDropdownMenu from './components/BetterDropdownMenu.vue'

    const showMenu = ref(false)
    const showMenu2 = ref(false)
    const showThing = ref(false)

    setTimeout(() => {
        showThing.value = true
    }, 200)
</script>

<style>
    * {
        font-family: Roboto,sans-serif;
    }
    button {
        border: 0px;
        background: #63baec;
        padding: 18px 83px;
        display: inline-block;
        color: #fff;
        border-radius: 4px;
        font-size: 18px;
        top: 120px;
        left: 542px;
        cursor: pointer;
    }

    button:active {
        outline: none;
        border: 0;
    }

    .menu {
        background: #fff;
        color: #000;
        padding: 20px 20px;
    }
</style>