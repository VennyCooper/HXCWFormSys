<template>
    <div class="dashboard-container">
        <el-row :gutter="10">
            <el-col :span="16" :md="16" :xs="24" :sm="24">
                <el-row :gutter="10">
                    <el-col :span="12" :xs="24">
                        <el-card shadow="hover">
                            <div slot="header">快捷方式</div>
                            <el-row class="lump-wrap" :gutter="10">
                                <el-col :span="6" v-for="item of shortcutList" :key="item.Value">
                                    <el-link @click="onPush(item.Url)" :underline="false"><i :class="[item.Icon ? item.Icon : 'el-icon-edit']"></i>
                                        <div class="link-ctx">{{ item.Text }}</div>
                                    </el-link>
                                </el-col>
                                <el-col :span="6">
                                    <el-link target="_blank" href="https://wtmdoc.walkingtec.cn/" :underline="false"><i class="el-icon-document"></i>
                                        <div class="link-ctx">项目文档</div>
                                    </el-link>
                                </el-col>
                                <el-col :span="6">
                                    <el-link target="_blank" href="/_codegen?ui=vue" :underline="false"><i class="el-icon-s-platform"></i>
                                        <div class="link-ctx">代码生成</div>
                                    </el-link>
                                </el-col>
                            </el-row>
                        </el-card>
                    </el-col>
                </el-row>
            </el-col>
        </el-row>
    </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import indexMixin from "./index-mixin";
@Component({
    mixins: [indexMixin]
})
export default class extends Vue {
    created() {
        console.log("默认页面：index");
    }
}
</script>
<style lang="less" rel="stylesheet/less" scoped>
@import "~@/assets/css/mixin.less";
.dashboard-container {
    padding: 10px;
    p {
        text-indent: 2em;
    }
    .title {
        margin-bottom: 5px;
        font-weight: 300;
        font-size: 16px;
    }
    .category {
        text-indent: 0;
        color: #999999;
        .text-success {
            color: red;
        }
    }
    .stats {
        color: #999999;
    }

    .el-row {
        margin-bottom: 20px;
    }
    .el-card__header {
        color: #333;
        font-size: 14px;
    }
    .el-card {
        font-size: 14px;
        color: #666;
    }
    .lump-wrap {
        margin-bottom: 0;
        min-height: 160px;
        text-align: center;
        &.cxt-left {
            .el-col {
                .flexalign(flex-start);
                box-sizing: border-box;
                padding-bottom: 10px;
                div {
                    background-color: #f8f8f8;
                    width: 100%;
                    box-sizing: border-box;
                    padding: 0 10px;
                }
            }
        }
        .el-col {
            .center(column);
            i {
                width: 100%;
                height: 60px;
                line-height: 60px;
                text-align: center;
                border-radius: 2px;
                font-size: 30px;
                background-color: #f8f8f8;
            }
            h3 {
                padding: 5px 0;
                font-size: 12px;
            }
            p {
                font-style: normal;
                font-size: 30px;
                font-weight: 300;
                color: #009688;
                text-indent: 0;
            }
            .link-a {
                color: #666;
                font-size: 14px;
                text-align: center;
            }
        }
        .link-ctx {
            min-width: 80px;
        }
    }
}
</style>
