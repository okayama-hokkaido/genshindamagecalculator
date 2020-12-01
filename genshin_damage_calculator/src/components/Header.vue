<template>
    <div>
        <h1>{{ title }}</h1>
        <p>{{ text }}</p>
        <p>ダメージを与える敵、キャラクターレベル、元素反応ダメージ、蒸発・融解は順次追加予定</p>
    </div>
</template>

<script>
export default {
    data(){
        return {
            title: "原神ダメージ計算機",
            text: "†この瞬間、おまえは永遠を手にする。†"
        }
    }
}
</script>

<style scoped>
div{
    min-width: 700px;
    background-color: rgb(100, 98, 98);
}
h1{
    text-align: center;
    color: blue;
}
p{
    text-align: center;
    color:blue
}
</style>