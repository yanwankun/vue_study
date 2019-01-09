<template>
  <div>
    <h1>{{ title }}</h1>
    <input v-model="personName">
    <input v-model="personAge">
    <button v-on:click="addPerson()">添加</button>
    <button v-on:click="dothis()">展示</button>
    <div v-if="isShow">
        <ul>
            <li v-for="(person,index) in personList">
                姓名： {{person.name}} 年龄：{{person.age}} 下标:{{index}}
            </li>
        </ul>
    </div>
  </div>
</template>

<script>
import Store from '../store'
export default {
    name: 'MyTest',
    data () {
        return {
            title: "个人信息",
            isShow:true,
            personList: Store.fetch(),
            personName:"",
            personAge:""
        }
    },
    methods: {
        dothis: function () {
            this.isShow = !this.isShow;
        },
        addPerson:function() {
            console.log(this.personName);
            this.personList.push({
                name:this.personName,
                age:this.personAge
            });
            this.personName = '';
            this.personAge = '';
        }
    },
    watch: {
        personList: {
            handler: function (personList) {
                Store.save(personList)
            },
            deep: true
        }
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
