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
                <nav aria-label="">
                    <ul class="inline-flex items-center -space-x-px">
                        <li>
                            <a href="#" class="block px-3 py-2 ml-0 leading-tight text-gray-500 bg-white border border-gray-300 rounded-bl-lg hover:bg-gray-100 hover:text-gray-700 dark:bg-gray-800 dark:border-gray-700 dark:text-gray-400 dark:hover:bg-gray-700 dark:hover:text-white">
                                <span class="sr-only">Previous</span>
                                <svg aria-hidden="true" class="w-5 h-5" fill="currentColor" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg"><path fill-rule="evenodd" d="M12.707 5.293a1 1 0 010 1.414L9.414 10l3.293 3.293a1 1 0 01-1.414 1.414l-4-4a1 1 0 010-1.414l4-4a1 1 0 011.414 0z" clip-rule="evenodd"></path></svg>
                            </a>
                        </li>
                        <li>
                            <a href="#" class="px-3 py-2 leading-tight text-gray-500 bg-white border border-gray-300 hover:bg-gray-100 hover:text-gray-700 dark:bg-gray-800 dark:border-gray-700 dark:text-gray-400 dark:hover:bg-gray-700 dark:hover:text-white">1</a>
                        </li>
                        <li>
                            <a href="#" class="px-3 py-2 leading-tight text-gray-500 bg-white border border-gray-300 hover:bg-gray-100 hover:text-gray-700 dark:bg-gray-800 dark:border-gray-700 dark:text-gray-400 dark:hover:bg-gray-700 dark:hover:text-white">2</a>
                        </li>
                        <li>
                            <a href="#" aria-current="page" class="z-10 px-3 py-2 leading-tight text-blue-600 border border-blue-300 bg-blue-50 hover:bg-blue-100 hover:text-blue-700 dark:border-gray-700 dark:bg-gray-700 dark:text-white">3</a>
                        </li>
                        <li>
                            <a href="#" class="px-3 py-2 leading-tight text-gray-500 bg-white border border-gray-300 hover:bg-gray-100 hover:text-gray-700 dark:bg-gray-800 dark:border-gray-700 dark:text-gray-400 dark:hover:bg-gray-700 dark:hover:text-white">4</a>
                        </li>
                        <li>
                            <a href="#" class="px-3 py-2 leading-tight text-gray-500 bg-white border border-gray-300 hover:bg-gray-100 hover:text-gray-700 dark:bg-gray-800 dark:border-gray-700 dark:text-gray-400 dark:hover:bg-gray-700 dark:hover:text-white">5</a>
                        </li>
                        <li>
                            <a href="#" class="block px-3 py-2 leading-tight text-gray-500 bg-white border border-gray-300 rounded-r-lg hover:bg-gray-100 hover:text-gray-700 dark:bg-gray-800 dark:border-gray-700 dark:text-gray-400 dark:hover:bg-gray-700 dark:hover:text-white">
                                <span class="sr-only">Next</span>
                                <svg aria-hidden="true" class="w-5 h-5" fill="currentColor" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg"><path fill-rule="evenodd" d="M7.293 14.707a1 1 0 010-1.414L10.586 10 7.293 6.707a1 1 0 011.414-1.414l4 4a1 1 0 010 1.414l-4 4a1 1 0 01-1.414 0z" clip-rule="evenodd"></path></svg>
                            </a>
                        </li>
                    </ul>
                </nav>
            </div>
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
    props: ['columns', 'rows', 'action', 'is-iterate-number','is-pagination'],
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
    mounted(){
    }
}
</script>
