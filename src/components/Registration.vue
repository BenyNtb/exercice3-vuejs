<template>
<div>
    <div class="btn btn-primary mb-3">{{button}}</div>
</div>
</template>

<script>
    export default {
        name: 'Registration',
        props: {
            value: {
        type: String,
        default: ''
        },
        button: String,
        },
    data() {
        return {
        model: this.value
        }
    },
    watch: {
        model(currentValue) {
        this.$emit('input', currentValue)
        }
    }
    }
</script>