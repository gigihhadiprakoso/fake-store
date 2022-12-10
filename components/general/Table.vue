<template>
    <div class="w-full rounded-lg bg-white">
        <div class="overflow-x-auto relative shadow-md sm:rounded-lg">
            <table class="text-sm text-left text-gray-500 dark:text-gray-400 w-full">
                <thead class="text-xs text-black uppercase bg-gray-200 dark:bg-gray-700 dark:text-gray-400 rounded-lg">
                    <tr>
                        <th v-if="isIterateNumber" scope="col" class="py-3 px-3 w-4">
                            <span>No.</span>
                        </th>
                        <th v-for="column in columns" :key="`column-${column}`" scope="col" class="py-3 px-3">
                            <span>{{column}}</span>
                        </th>
                        <th v-if="action" class="py-3 px-3 w-36">
                            <span>action</span>
                        </th>
                    </tr>
                </thead>
                <tbody>
                    <tr v-for="(row, index) in rows" :key="row.id" class="bg-white border-b dark:bg-gray-800 dark:border-gray-700">
                        <td v-if="isIterateNumber" class="py-4 px-3 w-4">
                            <span>{{index+1}}</span>
                        </td>
                        <td v-for="column in columns" :key="`value-${column}-${row.id}`" class="py-4 px-3">
                            {{row[column]}}
                        </td>
                        <td v-if="action" :key="`value-action-${row.id}`" class="py-2 px-3 w-36">
                            <span v-for="act in action" :key="`value-${act}-${row.id}`">
                                <component v-if="buttons[act]" :is="buttons[act]"></component>
                            </span>
                        </td>
                    </tr>
                </tbody>
            </table>
            <div v-if="isPagination">
                <Pagination :per-page="perPage" :total="totalItems" :total-page="getTotalPage" :current-page="currentPage"/>
            </div>
        </div>
    </div>
</template>
<script>
import EditButton from "@/components/buttons/Edit.vue";
import DeleteButton from "@/components/buttons/Delete.vue";
import DetailButton from "@/components/buttons/Detail.vue";
import Pagination from "@/components/general/Pagination.vue"

export default {
    components:{
        EditButton, DeleteButton, DetailButton, Pagination
    },
    props: ['columns', 'rows', 'action', 'is-iterate-number','is-pagination','per-page','total-items','current-page'],
    name:'Table',
    data(){
        return {
            buttons:{
                edit: 'EditButton',
                delete: 'DeleteButton',
                detail: 'DetailButton'
            },
        }
    },
    computed:{
        getTotalPage(){
            return Math.ceil(this.totalItems/this.perPage)
        }
    }
}
</script>
