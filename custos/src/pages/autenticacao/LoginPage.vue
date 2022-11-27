<template>
    <div class="flex flex-center bg-primary fullscreen">
        <q-card class="my-card">
            <img class="q-pa-md" src="https://agostiniconsultoria.com.br/wp-content/uploads/2022/07/LogoAgostiniAlt.png">

            <q-card-section>
                <div class="text-h6">Acesso Restrito</div>
            </q-card-section>

            <q-card-section class="q-pt-none">
                <q-form
                    @submit="onSubmit"
                    @reset="onReset"
                    class="q-gutter-md"
                >
                    <q-input
                        filled
                        v-model="username"
                        label="Usuário ou email *"
                    />

                    <q-input
                        filled
                        type="password"
                        v-model="age"
                        label="Senha *"
                    />

                    <div class="row q-col-gutter-xs">
                        <div class="col-4">
                            <q-btn label="Acessar" type="submit" color="primary" class="full-width"/>
                        </div>
                        <div class="col-8">
                            <q-btn label="Recuperar Senha" type="reset" color="primary" flat class="full-width" disabled />
                        </div>
                    </div>
                </q-form>
            </q-card-section>
        </q-card>
    </div>
</template>
<style scoped>
.my-card{
    max-width: 300px;
}
</style>