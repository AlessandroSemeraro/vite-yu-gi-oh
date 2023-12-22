<script>
export default{
    data(){
        return {
            title:'Yu-gi-oh Api'
    }
},
}

</script>

<template >
    <div class="myHeader">
        <img src="C:\Users\alese\OneDrive\Desktop\Boolean\js\vite-yu-gi-oh\src\style\1200px-Yu-Gi-Oh!_(Logo).jpg" alt="yu-gi-oh logo">
        <h1>{{ title }}</h1>
    </div>
</template>

<style lang="scss" scoped>
.myHeader{
    height: 3rem;
    width: 100%;
    background-color: white;
    display: flex;
    align-items: center;
    margin-left: 0.5rem;

    img{
        width: 2.5rem;
    }

    h1{
        font-size: 2rem;
        font-family: sans-serif;
    }
}
</style>