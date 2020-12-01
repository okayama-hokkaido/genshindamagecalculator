<template>
    <div>
        <h2>{{ title }}</h2>
        <p>基礎ダメージ量 : {{ basicDamage }}</p>
        <p>会心ダメージ量 : {{ criticalDamage }}</p>
        <p>ダメージ期待値 : {{ damageExpectations }}</p>
        <p>元素反応ダメージ : {{ elementDamage }}</p>

    </div>
</template>

<script>
export default {
    data(){
        return {
            title: "計算結果",
            basicDamage:0,
            criticalDamage:0,
            damageExpectations:0,
            elementDamage:0,
        }
    }
}
</script>

<style scoped>
div{
    border: 1px solid red
}
h2{
    color: red
}
</style>