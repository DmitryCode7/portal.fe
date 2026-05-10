<template>
    <div class="row py-3">
        <div class="col">
            <h1 class="text-center text-success">Вход</h1>
        </div>
    </div>
    <div class="row">
        <div class="col-4 offset-4">
            <div class="mb-4">
                <label for="email" class="form-label">Email</label>
                <input 
                    type="email" 
                    class="form-control" 
                    id="email" 
                    placeholder="name@example.com"
                    v-model="email"
                >
            </div>
            <div class="mb-4">
                <label for="email" class="form-label">Пароль</label>
                <input 
                    type="email" 
                    class="form-control" 
                    id="email" 
                    placeholder="*****"
                    v-model="password"
                >
            </div>
            <button 
                class="btn btn-primary"
                @click="onSubmit"
            >Войти</button>
        </div>
    </div>
</template>

<script>
    import api from '@/api';

    export default {
        data() {
            return {
                email: '',
                password: ''
            };
        },
        methods: {
            async onSubmit() {
                const response = await api.post('/login', {
                    email: this.email,
                    password: this.password
                });
                console.log(response.data);
            }
        }
    }
</script>

<style scoped>

</style>