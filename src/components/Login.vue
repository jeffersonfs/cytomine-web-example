<template>
    <div class="container">
        <h2>Faça login</h2>
        <form action="#" method="post">
            <div class="form-group">
                <label for="username">Usuário:</label>
                <input type="text" v-model="username" required>
            </div>
            <div class="form-group">
                <label for="password">Senha:</label>
                <input type="password" v-model="password" required>
            </div>
            <div class="form-group">
                <button  type="submit">Entrar</button>
            </div>
        </form>
    </div>
</template>

<style scoped>
    .container {
        background-color: #fff;
        padding: 20px;
        border-radius: 5px;
        box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        text-align: center;
    }
    .form-group {
        margin-bottom: 20px;
    }
    .form-group label {
        display: block;
        margin-bottom: 5px;
        font-weight: bold;
    }
    .form-group input {
        width: 100%;
        padding: 10px;
        border: 1px solid #ccc;
        border-radius: 5px;
    }
    .form-group button {
        background-color: #007bff;
        color: #fff;
        padding: 10px 20px;
        border: none;
        border-radius: 5px;
        cursor: pointer;
    }
</style>
