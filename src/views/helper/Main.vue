<template>
    <div>
        <el-card shadow="never" style="min-height: 600px;margin-bottom: 20px;">
            <el-collapse v-model="active" accordion>
                <el-collapse-item title="Work" name="deploy">
                    <el-carousel trigger="click" height="352px" :autoplay="false" @change="deployChange">
                        <el-carousel-item v-for="(item,index) in deploy.images" :key="'deploy'+index">
                            <div style="border-radius:5px; border: 1px solid #EBEEF5;height: 350px;" align="center">
                                <img :src="item" style="height:350px">
                            </div>
                        </el-carousel-item>
                    </el-carousel>
                    <el-steps :active="deploy.active" align-center style="margin-top: 20px;" :process-status="deploy.status">
                        <el-step title="Education" description="Tsinghua CS Master, BeiHang software B.E"></el-step>
                        <el-step title="Work Place" description="School of Information Science and Technology, Tsinghua University"></el-step>
                        <el-step title="Pay Method" description="If you want to give me a cup of coffee"></el-step>
                    </el-steps>
                </el-collapse-item>
                <el-collapse-item title="Hobbies" name="use">
                    <el-carousel trigger="click" height="352px" :autoplay="false" @change="useChange">
                        <el-carousel-item v-for="(item,index) in use.images" :key="'use'+index">
                            <div style="border-radius:5px; border: 1px solid #EBEEF5;height: 350px;" align="center">
                                <img :src="item" style="height:350px">
                            </div>
                        </el-carousel-item>
                    </el-carousel>
                    <el-steps :active="use.active" align-center style="margin-top: 20px;" :process-status="use.status">
                        <el-step title="Guitar" description="6 year"></el-step>
                        <el-step title="Piano" description="1 year"></el-step>
                        <el-step title="Fitness" description="1 year"></el-step>
                        <el-step title="Badminton" description="8 year"></el-step>
                        <el-step title="Art" description="life time"></el-step>
                    </el-steps>
                </el-collapse-item>
                <el-collapse-item title="Contact" name="develop">
                    <div style="padding: 10px;line-height: 30px;color: #303133;font-size: 16px">
                        E-mail：alordredness@gmail.com
   <!--                      配置文件读取的总是与
                        <tt>index.html</tt> 同级的
                        <tt>./static/configuration.json</tt> , 而修改配置的时候是通过
                        <tt>github-api</tt> 修改
                        <tt>你的用户名.github.io</tt> 下的
                        <tt>/static/configuration.json</tt>, 所以本地
                        <tt>npm run dev</tt> 的时候会出现修改配置无效的情况, 如果需要修改的话修改本地的配置文件就行, 发布到
                        <tt>github</tt> 之后不影响 -->
                    </div>
                </el-collapse-item>
            </el-collapse>
        </el-card>
    </div>
</template>
<script>

    export default {
        data() {
            return {
                active: "deploy",
                deploy: {
                    images: [
                        require('../../assets/me6.jpg'),
                        require('../../assets/pic1.jpg'),
                        require('../../assets/payPic.jpg')
                    ],
                    status: "process",
                    active: 0,
                },
                use: {
                    images: [
                        require('../../assets/me5.jpg'),
                        require('../../assets/me9.jpg'),
                        require('../../assets/me3.jpg'),
                        require('../../assets/me4.jpg'),
                        require('../../assets/me1.jpg'),
                    ],
                    status: "process",
                    active: 0,
                }
            }
        },
        mounted() {

        },
        methods: {
            deployChange(index) {
                this.deploy.status = index == 2 ? "success" : "process"
                this.deploy.active = index
            },
            useChange(index) {
                this.use.status = index == 4 ? "success" : "process"
                this.use.active = index
            }
        }
    }
</script>

<style>

</style>