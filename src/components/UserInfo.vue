<template>
<BaseSlot>
    <template v-slot:header>
        <div>
            <h3>{{ fullName }}</h3>
            <base-badge :type="role" :caption="role.toUpperCase()"></base-badge>
        </div>
    </template>
    <template v-slot:default>
        <p>{{ infoText }}</p>
    </template>
</BaseSlot>
</template>

<script>
import BaseBadge from './BaseBadge.vue';
import BaseSlot from './BaseSlot.vue';

export default {
    name: 'UserInfo',
    props: ['fullName', 'infoText', 'role'],
    components: {
        BaseSlot,
        BaseBadge
    }
};
</script>

<style lang="scss" scoped>
section {
    margin: 2rem auto;
    max-width: 30rem;
    border-radius: 12px;
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
    padding: 1rem;
}

section div {
    display: flex;
    justify-content: space-between;
    align-items: center;
}
</style>
