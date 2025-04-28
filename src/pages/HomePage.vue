<template lang="">
    <div>
        <h1>Welcome to the Homepage</h1>
        <p>This is the homepage of our application.</p>
        <BaseButton>
            Base button with custom margin
        </BaseButton>
        <BaseButton disabled>
            Base Button disabled
        </BaseButton>
        <BaseButton color="warn">
            Base button with color props
        </BaseButton>
        <BaseButton color="danger">
            Base button with color props
        </BaseButton>
    </div>
</template>
<script>
import BaseButton from '../components/BaseButton.vue';

export default {
    // eslint-disable-next-line vue/multi-word-component-names
    name: 'HomePage',
    components: {
        BaseButton,
    },
}
</script>
<style scoped>
    * {
        margin: 12px;
        padding: 40px;
        display:flex;
        flex-direction: column;
        align-items: center;
    }
</style>