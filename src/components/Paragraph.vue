<template>
    <p>{{ msg }}</p>
</template>

<script>
export default {
    name: 'DefaultParagraph',
    props: {
        msg:String,
        size: {
            type: Number,
            default: 8
        }
    }
}
</script>

