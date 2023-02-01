<script setup>
const user = useUser()

definePageMeta({
    layout:'plain'
})

</script>

<template>
    <div>
        <h1>Login</h1>
       <form @submit.prevent="user.login"> 
        <label>
            Username
            <input type="text"/>
        </label>
        <label>
            Password
            <input type="password"/>
        </label>
        <button>
            Login
        </button>
       </form>
    </div>
</template>