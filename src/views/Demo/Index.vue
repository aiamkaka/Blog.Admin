<template>
    <el-card>
        测试页面{{ msg }}
    </el-card>
</template>
<script>
import { getDemos, removeDemo, addDemo } from "../../api/api";
export default {
    name: 'Index',
    data() {
        return {
            msg: 'hi!'
        }
    },
    methods: {

    },
    mounted() {
        getDemos().then(res => {
            this.msg = res.data;
        });
        // let para = { id: 1 };
        // removeDemo(para).then(res => {
        //     this.msg = res.data;
        // });
        let para = { Name: "测试", Code: "test", TotalAmount: 18 };
        addDemo(para).then(res => {
            this.msg = res.data;
        });
    }
}
</script>