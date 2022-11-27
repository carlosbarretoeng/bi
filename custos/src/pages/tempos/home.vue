<template>
    <div class="row q-gutter-sm ">
        <div class="col">
            <q-card class="text-center">
                <q-linear-progress stripe rounded size="25px" :value="0.2" color="positive" class="q-mt-sm">
                    <div class="absolute-full flex flex-center">
                        <q-badge color="white" text-color="positive" label="20%" />
                    </div>
                </q-linear-progress>
                <q-card-section class="text-center text-positive text-subtitle1 q-py-none q-px-xs text-weight-bold">
                    RECEITAS
                </q-card-section>
                <q-card-section class="text-center text-positive text-subtitle1 q-py-none q-px-xs text-weight-bold">
                    R$ 999.999,99
                </q-card-section>
            </q-card>
        </div>

        <div class="col">
            <q-card class="text-center">
                <q-linear-progress stripe rounded size="25px" :value="0.6" color="negative" class="q-mt-sm">
                    <div class="absolute-full flex flex-center">
                        <q-badge color="white" text-color="negative" label="60%" />
                    </div>
                </q-linear-progress>
                <q-card-section class="text-center text-negative text-subtitle1 q-py-none q-px-xs text-weight-bold">
                    DESPESAS
                </q-card-section>
                <q-card-section class="text-center text-negative text-subtitle1 q-py-none q-px-xs text-weight-bold">
                    R$ 999.999,99
                </q-card-section>
            </q-card>
        </div>
    </div>

    <div class="row q-mt-xs q-gutter-xs">
        <div class="col">
            <q-card class="text-center">
                <ChartLine />
            </q-card>
        </div>
    </div>

    <div class="row q-mt-xs q-gutter-xs">
        <div class="col">
            <div class="text-center text-white text-subtitle1 q-pa-xs text-weight-bold">
                EXTRATO
            </div>
            <div>
                <q-timeline dense color="white">
                    <q-timeline-entry v-for="i in 4" :key="i" subtitle="26 de Novembro de 2022"
                        class="text-white q-pa-none">
                        <q-card class="">
                            <q-item>
                                <q-item-section>
                                    <q-item-label caption class="text-black text-weight-bold">1.1.1.1 - Aluguel
                                    </q-item-label>
                                    <q-item-label caption class="text-black">Observação aslkdn laksjdla laksjd alksjd
                                        alskdjkjdal la sdjla lskd jalkjsd al sldkja lsd</q-item-label>
                                </q-item-section>
                                <q-item-section side top class="q-pt-xs">
                                    <q-item-label overline class="text-positive">R$ 33.000,00</q-item-label>
                                </q-item-section>
                            </q-item>
                        </q-card>
                    </q-timeline-entry>

                </q-timeline>

                <q-btn color="primary" class="full-width" label="Carregar mais" />
            </div>
        </div>
    </div>
</template>
  
<script setup>
    import ChartLine from '~components/ChartLine.vue'
</script>
  