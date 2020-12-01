<template>
    <div>
        <div class="container">
        <div class="statusContainer">
        <h2>{{ title }}</h2>

        <!--ステータス入力-->

        <div class="status">

        <p><label for="power">攻撃力</label><br>
        <input id="power" class="no-spin" type="number" value="value" v-model="atk" @input="damCal" onfocus="this.select()"></p>

        <p><label for="physicalBuff">ダメージバフ(物理or元素)</label><br>
        <input id="physicalBuff" class="no-spin" type="number" value="value" v-model="peBuff" @input="damCal" onfocus="this.select()">%</p>

        <p><label for="critcalDamage">会心ダメージ</label><br>
        <input id="criticalDamage" class="no-spin" type="number" value="value" v-model="cDam" @input="damCal" onfocus="this.select()">%</p>

        <p><label for="criticalProbability">会心率</label><br>
        <input id="criticalProbability" class="no-spin" type="number" value="value" v-model="cPro" @input="damCal" onfocus="this.select()">%</p>

        <p><label for="giftDamage">天賦倍率</label><br>
        <input id="giftDamage" class="no-spin" type="number" value="value" v-model="gDam" @input="damCal" onfocus="this.select()">%</p>
        
        </div>
        </div>
        <!-- 倍率の確認 -->
        <!-- <p>{{ pB }}</p>
        <p>{{ cD }}</p>
        <p>{{ cP }}</p>
        <p>{{ gD }}</p> -->
        
        <!--ダメージ計算結果-->
     
        <div class="resultContainer">
            <h2>計算結果</h2>
            <div class="result">
            <p>基礎ダメージ量  <span>{{ Math.floor(basicDamage) }}</span></p>
            <p>会心ダメージ量  <span>{{ Math.floor(criticalDamage) }}</span></p>
            <p>ダメージ期待値  <span>{{ Math.floor(damageExpectations) }}</span></p>
            </div>
        </div>
        </div>
        <!-- <p>元素反応ダメージ : {{ elementDamage }}</p> -->
    </div>
</template>

<script>
export default {

    data() {
        return {
            title: "ステータス入力欄",
            atk: "",
            peBuff: 0,
            cDam: 50,
            cPro: 5,
            gDam: 100,
            pB: 0,
            cD: 1.5,
            cP: 0.05,
            gD: 1,
            basicDamage: 0,
            criticalDamage: 0,
            damageExpectations: 0,
            // elementDamage: 0,
        }
    },
    methods: {
        damCal() {
        this.pB = (((1*this.peBuff)+100) / 100)
        this.cD = (((1*this.cDam)+100) / 100)
        this.cP = ((1*this.cPro) / 100)
        this.gD = (this.gDam / 100)
        this.basicDamage = this.atk * this.pB * this.gD
        this.criticalDamage = this.basicDamage * this.cD
        this.damageExpectations = (this.basicDamage * (1-(1 * this.cP))) + (this.basicDamage * this.cD * this.cP)
        }
    }
}
</script>

<style scoped>
div{
    font-family: "Meiryo","ヒラギノ角ゴ","sans-serif";
}
h2{
    text-align: center;
    color: black;
}
h3{
    text-align: center;
}
.container{
    display: table;
    border-radius: 10px;
    padding: 10px 0;
    background-color: #4fc9fa;
}
.statusContainer{
    display: table-cell;
    padding: 10px;
    border-radius: 5px;
    }
    .status{
        padding: 0 20px;
    }
.resultContainer{
    display: table-cell;
    padding: 0 20px;
    border-radius: 5px;
}
    .result {
        display: block;
        font-size: 18px;
    }
    .result span{
        font-family: "Impact","sans-serif";
        display: block;
        text-align: right;
        padding-right: 10px;
        background-color: white;
        font-size: 36px;
    }
input{
    font-size: 18px;
    text-align: right;
    font-family: "Impact","sans-serif";
}

.no-spin::-webkit-inner-spin-button,
.no-spin::-webkit-outer-spin-button {
    -webkit-appearance: none;
    margin: 0;
    -moz-appearance:textfield;
}
</style>