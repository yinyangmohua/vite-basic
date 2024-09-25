<template>
    <div>
        <Card>
            <template #header>
                <p>
                    Lorem ipsum dolor sit amet, consectetur adipisicing elit. Itaque nemo dolorum mollitia sequi hic suscipit dolores vel tempore enim asperiores, voluptas commodi exercitationem, corrupti labore eum distinctio maxime expedita qui!
                </p>
            </template>
                <p>这是中间的主体内容</p>
            <template #footer>
                <p>
                    Lorem ipsum dolor sit amet consectetur adipisicing elit. Tempore accusamus blanditiis atque nemo, aperiam non praesentium dolorum illum doloribus dolores incidunt id quod, distinctio totam consectetur! Voluptatibus, vero. Accusantium, voluptatum?
                </p>
            </template>
        </Card>
    </div>
</template>

<script setup lang="ts">
import Card from './Card.vue';
</script>

<style scoped>

</style>