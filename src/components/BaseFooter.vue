<template>
    <div class="footer">
       <p>
        this work is protected by international laws ⎟ © 2021 ⎟ <a href="thomas-veillard.fr" > thomas-veillard.fr </a>
       </p>
    </div>
</template>
 
<script>
export default {
    name: 'BaseFooter',
}
</script>
 
<style scoped>
    * {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
    }
 
    .footer {
        position: fixed;
        left: 0;
        bottom: 0;
        width: 100%;
        background-color: #000000;
        color: white;
        text-align: center;
    }
    .footer a {
        color: white;
    }
</style>
 