<template>
    <el-menu>
        <el-menu-item
            v-for="(item, index) in fullMenu"
            :index="item.pathname"
            :key="index"
            class="menu" @click="change(item.pathname)">
            <span slot="title">{{ item.name }}</span>
        </el-menu-item>
    </el-menu>
</template>

<script>
export default {
    data() {
        return {
            fullMenu: [
                {
                   name: '团队出勤统计',
                   pathname: '/team_attendance'
               }, {
                   name: '团队请假统计',
                   pathname: '/team_vocation'
               }, 
            ]
        }
    },
    methods: {
        change(index){
            this.$router.replace(index)
        }
    },
}
</script>

<style lang="css">
.menu {
    text-align: center;
    font-size: 16px;
}
</style>
