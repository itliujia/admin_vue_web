<template>
    <footer class="layout-footer">
        <div class="text-center p-2 text-xs text-tx-secondary max-w-[900px] mx-auto">
            <el-link @click="url(item.value)" :underline="false" v-for="item in copyright" :key="item.key">
                {{ item.key }}</el-link>
        </div>
    </footer>
</template>

<script setup lang="ts">
import useAppStore from '@/stores/modules/app'
import { filterAsyncRoutes } from '@/router'

const appStore = useAppStore()
const copyright = computed(() => appStore.config.copyright_config || [])

function url(params: string) {
    if (params) {
        window.location.href = params
    }
}
</script>


<style>
.p-2 {
    margin-bottom: 50px;
}

a:hover {
    text-decoration: none
}
</style>
