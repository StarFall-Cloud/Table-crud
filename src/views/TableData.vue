<template>
    <div id="tableData">

        <el-table
                :data="tableData.filter(data => !search || data.name.toLowerCase().includes(search.toLowerCase()))"
                style="width: 100%">
            <el-table-column
                    label="姓名"
                    prop="name">
            </el-table-column>
            <el-table-column
                    label="地址"
                    prop="address">
            </el-table-column>
            <el-table-column
                    label="日期"
                    prop="date">
            </el-table-column>
            <el-table-column
                    label="电话"
                    prop="phone">
            </el-table-column>

            <el-table-column
                    align="right">

                <template slot-scope="scope">
                    <el-button
                            size="mini"
                            @click="handleEdit(scope.$index,tableData)">编辑</el-button>
                    <el-button
                            size="mini"
                            type="danger"
                            @click="handleDelete(scope.$index, tableData)">删除</el-button>
                </template>
            </el-table-column>
        </el-table>


        <el-form ref="form" :model="form" label-width="80px">
            <el-form-item label="名称">
                <el-input v-model="form.name"></el-input>
            </el-form-item>
            <el-form-item label="日期">
                <el-input v-model="form.date"></el-input>
            </el-form-item>
            <el-form-item label="地址">
                <el-input v-model="form.address"></el-input>
            </el-form-item>
            <el-form-item label="电话">
                <el-input v-model="form.phone"></el-input>
            </el-form-item>

            <el-form-item>
                <el-button type="primary" @click="handleSave">增加</el-button>
            </el-form-item>
        </el-form>

    </div>
</template>


<script>
    export default {
        name: "TableData",
        data() {
            return {
                tableData: [{
                    name: '李小龙',
                    address: '湛江码头',
                    date: '2016-05-02',
                    phone: '12352356897'
                }, {
                    name: '周星驰',
                    address: '湛江码头',
                    date: '2016-05-02',
                    phone: '12352356897'
                }, {
                    name: '肖战',
                    address: '湛江码头',
                    date: '2016-05-02',
                    phone: '12352356897'
                }, {
                    name: '王一博',
                    address: '湛江码头',
                    date: '2016-05-02',
                    phone: '12352356897'
                }],
                form: {
                    name: '',
                    address: "",
                    date: '',
                    phone: ''

                }
            }
        },
        methods: {
            handleSave(){
                console.log(this.form);
                this.tableData.push(this.form)
            },
            handleEdit(index, row) {
                console.log(index, row);
                this.form=row[index]
            },
            handleDelete(index, row) {
                console.log(index, row);
                row.splice(index,1);
            }
        }
    }
</script>

<style scoped>

</style>