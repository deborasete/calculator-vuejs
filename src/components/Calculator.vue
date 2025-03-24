<script setup>
    import { ref, computed } from 'vue';

    const num1 = ref(0);
    const num2 = ref(0);
    const operation = ref('+');

    const result = computed(() => {
        switch (operation.value) {
            case '+': 
                return num1.value + num2.value;
            case '-': 
                return num1.value - num2.value;
            case '*':
                return num1.value * num2.value;
            case '/': 
                return num1.value / num2.value;
            default: 
                return 0;
        } 
    });
</script>


<template>
    <div class="calculator shadow p-4 rounded-3 bg-dark text-light">
        <div class="container mt-5">
            <div class="row justify-content-center">
                <div class="col-12 col-md-6">
                    <h2 class="text-center text-warning mb-4">Calculadora</h2>
                    <div class="form-group mb-3">
                        <label for="num1" class="form-label">Primeiro número:</label>
                        <input type="number" id="num1" class="form-control input-lg" v-model.number="num1" placeholder="Digite um número" />
                    </div>
                    <div class="form-group mb-3">
                        <label for="num2" class="form-label">Segundo número:</label>
                        <input type="number" id="num2" class="form-control input-lg" v-model.number="num2" placeholder="Digite um número" />
                    </div>
                    <div class="mb-4">
                        <label class="form-label me-2" for="operation">Operação:</label>
                        <select class="form-select" id="operation" v-model="operation">
                            <option value="+">Adição (+)</option>
                            <option value="-">Subtração (-)</option>
                            <option value="*">Multiplicação (*)</option>
                            <option value="/">Divisão (/)</option>
                        </select>
                    </div>
                    <div class="mt-4">
                        <h4 class="text-center result-highlight">Resultado: <span class="display-7 result-box">{{ result }}</span></h4>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>


<style scoped>
.calculator {
    margin: 50px 50px;
    background-color: #343a40;
    border-radius: 15px;
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.3);
}

h2 {
    font-family: 'Roboto', sans-serif;
}

input[type="number"], select {
    font-size: 1.1rem;
    padding: 10px;
    border-radius: 8px;
    color: #f8f9fa;
}

.form-select {
    background-color: #495057;
    color: #f8f9fa;
}

input[type="number"] {
    background-color: #495057;
    color: #f8f9fa;
}

h4 {
    font-family: 'Roboto', sans-serif;
}

.result-box {
    display: inline-block;
    padding: 10px;
    margin-top: 10px;
    font-size: 1.5rem;
    font-weight: bold;
    border: 1px solid #fff;
    border-radius: 8px;
    background-color: #495057;
    color: #f8f9fa;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.2);
}
</style>