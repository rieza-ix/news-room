<template>
    <nav aria-label="Page navigation example">
        <ul class="flex items-center -space-x-px h-10 text-base">
            <li>
                <a href="#"
                    class="flex items-center justify-center px-4 h-9 ms-0 leading-tight text-black bg-white border border-gray-300 hover:bg-gray-100 hover:text-gray-700 dark:bg-gray-800 dark:border-gray-700 dark:text-gray-400 dark:hover:bg-gray-700 dark:hover:text-white">
                    <span class="sr-only">Previous</span>
                    <svg class="w-2 h-2 rtl:rotate-180" aria-hidden="true" xmlns="http://www.w3.org/2000/svg"
                        fill="none" viewBox="0 0 6 10">
                        <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                            d="M5 1 1 5l4 4" />
                    </svg>
                </a>
            </li>

            <!-- Loop until 57 pages -->
            <div v-for="i in 57" :key="i">
                <!-- Display the number for pages 1, 2, 8-14, and 56-57 -->
                <div v-if="i === 1 || i === 2 || i === 56 || i === 57 || (i >= 8 && i <= 15) || (i >= 56 && i <= 58)">
                    <li>
                        <!-- Add a color for page 11 only -->
                        <div v-if="i == 11">
                            <a href="#"
                                class="flex text-white items-center justify-center text-sm px-4 h-9 leading-tight text-black bg-red-600 border border-gray-300 hover:bg-gray-100 hover:text-gray-700 dark:bg-gray-800 dark:border-gray-700 dark:text-gray-400 dark:hover:bg-gray-700 dark:hover:text-white">{{ i }}</a>
                        </div>
                        <div v-else>
                            <a href="#"
                                class="flex items-center justify-center text-sm px-4 h-9 leading-tight text-black bg-white border border-gray-300 hover:bg-gray-100 hover:text-gray-700 dark:bg-gray-800 dark:border-gray-700 dark:text-gray-400 dark:hover:bg-gray-700 dark:hover:text-white">{{ i }}</a>
                        </div>
                    </li>
                </div>
                <!-- Display ... for these pages -->
                <div v-else-if="i === 3 || i === 55">
                    <li>
                        <a href="#"
                            class="flex items-center justify-center text-sm px-4 h-9 leading-tight text-black bg-white border border-gray-300 hover:bg-gray-100 hover:text-gray-700 dark:bg-gray-800 dark:border-gray-700 dark:text-gray-400 dark:hover:bg-gray-700 dark:hover:text-white">...</a>
                    </li>
                </div>
            </div>

            <li>
                <a href="#"
                    class="flex items-center justify-center px-4 h-9 leading-tight text-black bg-white border border-gray-300 hover:bg-gray-100 hover:text-gray-700 dark:bg-gray-800 dark:border-gray-700 dark:text-gray-400 dark:hover:bg-gray-700 dark:hover:text-white">
                    <span class="sr-only">Next</span>
                    <svg class="w-2 h-2 rtl:rotate-180" aria-hidden="true" xmlns="http://www.w3.org/2000/svg"
                        fill="none" viewBox="0 0 6 10">
                        <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                            d="m1 9 4-4-4-4" />
                    </svg>
                </a>
            </li>
        </ul>
    </nav>
</template>
