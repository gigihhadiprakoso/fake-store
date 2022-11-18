<template>
    <div class="w-full rounded-lg">
        <div class="overflow-x-auto relative shadow-md sm:rounded-lg">
            <table class="text-sm text-left text-gray-500 dark:text-gray-400 ">
                <thead class="text-xs text-black uppercase bg-gray-200 dark:bg-gray-700 dark:text-gray-400 rounded-lg">
                    <tr>
                        <th v-for="column in columns" :key="`column-${column}`" scope="col" class="py-3 px-6">
                            <span>{{column}}</span>
                        </th>
                        <th v-if="action">
                            <span>action</span>
                        </th>
                    </tr>
                </thead>
                <tbody>
                    <tr v-for="row in rows" :key="row.id" class="bg-white border-b dark:bg-gray-800 dark:border-gray-700">
                        <td v-for="column in columns" :key="`value-${column}-${row.id}`" class="py-4 px-6">
                            {{row[column]}}
                        </td>
                        <td v-if="action" :key="`value-action-${row.id}`">
                            <span v-for="act in action" :key="`value-${act}-${row.id}`">
                                <component v-if="buttons[act]" :is="buttons[act]"></component>
                            </span>
                        </td>
                    </tr>
                </tbody>
            </table>
        </div>
    </div>
</template>
<script>
import EditButton from "@/components/buttons/Edit.vue";
import DeleteButton from "@/components/buttons/Delete.vue";
import DetailButton from "@/components/buttons/Detail.vue";

export default {
    components:{
        EditButton, DeleteButton, DetailButton
    },
    props: ['columns', 'rows', 'action'],   
    name:'Table',
    data(){
        return {
            buttons:{
                edit: 'EditButton',
                delete: 'DeleteButton',
                detail: 'DetailButton'
            }
        }
    },
}
</script>
