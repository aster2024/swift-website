<script lang="ts" setup>

const tableData = [
    {
        reward_model: 'Eurus-7B',
        llama32_3b: 46.8,
        llama31_8b: 52.2,
        ministral_8b: 55.0,
        avg: 51.0,
    },
    {
        reward_model: 'Skywork-Llama3.1-8B',
        llama32_3b: 48.8,
        llama31_8b: 53.4,
        ministral_8b: 61.6,
        avg: 52.9,
    },
    {
        reward_model: 'Starling-7B',
        llama32_3b: 39.8,
        llama31_8b: 49.0,
        ministral_8b: 47.0,
        avg: 46.7,
    },
    {
        reward_model: 'Ultra-13B',
        llama32_3b: 44.4,
        llama31_8b: 50.4,
        ministral_8b: 54.0,
        avg: 50.1,
    },
    {
        reward_model: 'RLHFlow-8B-Deepseek',
        llama32_3b: 47.6,
        llama31_8b: 49.8,
        ministral_8b: 57.8,
        avg: 51.1,
    },
    {
        reward_model: 'Math-Shepherd-7B',
        llama32_3b: 43.6,
        llama31_8b: 49.0,
        ministral_8b: 54.8,
        avg: 49.8,
    },
    {
        reward_model: 'SWIFT (ours)',
        llama32_3b: 53.6,
        llama31_8b: 62.6,
        ministral_8b: 62.8,
        avg: 57.5,
    },
]
</script>

<template>
    <div>
        <el-divider />

        <el-row justify="center">
            <h1 class="section-title">Results (MATH Best-of-N @64)</h1>
        </el-row>
        
        <!-- 数据表格 -->
        <el-row justify="center">
            <el-col :xs="24" :sm="20" :md="16" :lg="12" :xl="12">

                <!-- 卡片 -->
                <el-card class="card">

                    <el-table
                        :data="tableData"
                        :default-sort="{ prop: 'avg', order: 'descending' }"
                        scrollbar-always-on
                    >
                        <el-table-column prop="reward_model" label="Reward Model" min-width="220" sortable />
                        <el-table-column prop="llama32_3b" label="Llama-3.2-3B" min-width="140" sortable />
                        <el-table-column prop="llama31_8b" label="Llama-3.1-8B" min-width="140" sortable />
                        <el-table-column prop="ministral_8b" label="Ministral-8B" min-width="140" sortable />
                        <el-table-column prop="avg" label="Avg." min-width="100" sortable />
                    </el-table>

                </el-card>
            </el-col>
        </el-row>

    </div>
</template>

<style scoped>
.card {
    margin-top: 20px;
}
</style>
  