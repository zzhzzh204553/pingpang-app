<template>
    <div class="data-table">
        <h2>{{ title }}</h2>
        <table>
            <thead>
                <tr>
                    <th v-for="(header, index) in headers" :key="index">{{ header }}</th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="(row, index) in data" :key="index">
                    <td v-for="(item, i) in row" :key="i">{{ item }}</td>
                </tr>
            </tbody>
        </table>
    </div>
</template>

<script>
export default {
    name: 'DataTable',
    props: {
        title: {
            type: String,
            required: true
        },
        headers: {
            type: Array,
            default: () => ['A', 'B', 'C', 'D', 'E']
        },
        data: {
            type: Array,
            required: true
        }
    }
};
</script>

<style scoped>
.data-table {
    margin-bottom: 20px;
    border: 1px solid #ccc;
    padding: 15px;
    border-radius: 5px;
}

h2 {
    margin-top: 0;
    margin-bottom: 10px;
    font-size: 1.5em;
    color: #333;
    text-align: center;
    /* 可以选择将标题也居中 */
}

table {
    width: 100%;
    border-collapse: collapse;
}

th,
td {
    border: 1px solid #ddd;
    padding: 8px;
    text-align: center;
    /* 将表头和单元格文字居中 */
}

th {
    background-color: #f2f2f2;
    font-weight: bold;
}
</style>