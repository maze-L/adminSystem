<template>
    <div>
        <div class="crumbs">
            <el-breadcrumb separator="/">
                <el-breadcrumb-item><i class="el-icon-setting"></i> 系统概述</el-breadcrumb-item>
            </el-breadcrumb>
        </div>
        <div class="ms-doc">
            <h3>README.md</h3>
            <article>
                <h1>adminSystem</h1>
                <p>基于Node.js+Express+mysql+webpack+Vue2 +vuex+axios+Element UI 的后台管理系统解决方案</p>
                <h2>前言</h2>
                <p>这是一套基于node.js开发的全栈MVC后台管理系统，也就是前端人员自己进行数据库的增删改查，输出API接口，然后通过代理，调用API接口进行页面展示。</p>
                <p>在开发过程中，我们需要同时启动两套端口服务:
                <br>一套是后端服务（Node.js+Express+mysql），搭建好node的运行环境，cd到项目根目录，输入命令 supervisor app.js启动（开发环境笔者喜欢用supervisor，便于修改，当然你也可以用forever或者PM2），启动后可以通过http://localhost:3000进行访问;
                <br>一套是前端服务（webpack+Vue2+vuex+axios+Element UI），cd到项目根目录，输入npm run dev启动,启动后可以通过http://localhost:8080进行访问。端口号可以自己根据情况配置，3000与8080端口是项目默认的端口。后端服务主要是对数据库进行增删改查，输出API接口；前端服务主要是调用API接口，进行页面的展示。</p>
                <p>此套系统，我们引入了Element UI，方便用户进行页面视图展示，当然还可以引用其他的UI系统，具体根据项目需要引入就行。</p>
                <h2>功能</h2>
                <el-checkbox disabled checked>Node.js+Express+mysql</el-checkbox>
                <br>
                <el-checkbox disabled checked>Element UI</el-checkbox>
                <br>
                <el-checkbox disabled checked>登录/注销</el-checkbox>
                <br>
                <el-checkbox disabled checked>表格</el-checkbox>
                <br>
                <el-checkbox disabled checked>表单</el-checkbox>
                <br>
                <el-checkbox disabled checked>图表</el-checkbox>
                <br>
                <el-checkbox disabled checked>富文本编辑器</el-checkbox>
                <br>
                <el-checkbox disabled checked>markdown编辑器</el-checkbox>
                <br>
                <el-checkbox disabled checked>图片拖拽/裁剪上传</el-checkbox>
                <br>
                <el-checkbox disabled checked>支持切换主题色</el-checkbox>
                <br>
                <el-checkbox disabled checked>列表拖拽排序</el-checkbox>
                <br><br>
                <h1>代理数据调用展示</h1>
                <pre v-if="getData!=null">
                    {{getData}}
                </pre>
            </article>
        </div>

    </div>
</template>

<script>
    export default {
        data(){
            return {
                getData:null
            }
        },
        created(){
            var _this=this;
            this.$axios({
                method: 'get',
                url: '/apis/testApi'
             }).then(function(result){
                _this.getData=result.data;
                console.log(JSON.stringify(result))
             });
        }
    }
</script>

<style scoped>
    .ms-doc{
        width:100%;
        max-width: 980px;
        font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Helvetica, Arial, sans-serif;
    }
    .ms-doc h3{
        padding: 9px 10px 10px;
        margin: 0;
        font-size: 14px;
        line-height: 17px;
        background-color: #f5f5f5;
        border: 1px solid #d8d8d8;
        border-bottom: 0;
        border-radius: 3px 3px 0 0;
    }
    .ms-doc article{
        padding: 45px;
        word-wrap: break-word;
        background-color: #fff;
        border: 1px solid #ddd;
        border-bottom-right-radius: 3px;
        border-bottom-left-radius: 3px;
    }
    .ms-doc article h1{
        font-size:32px;
        padding-bottom: 10px;
        margin-bottom: 15px;
        border-bottom: 1px solid #ddd;
    }
    .ms-doc article h2 {
        margin: 24px 0 16px;
        font-weight: 600;
        line-height: 1.25;
        padding-bottom: 7px;
        font-size: 24px;
        border-bottom: 1px solid #eee;
    }
    .ms-doc article p{
        margin-bottom: 15px;
        line-height: 1.5;
    }
    .ms-doc article .el-checkbox{
        margin-bottom: 5px;
    }
</style>