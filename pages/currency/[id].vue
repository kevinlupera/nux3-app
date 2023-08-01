<script setup>
const route = useRoute();
const { data } = await useFetch('/api/ticker?id=' + route.params.id);
const coin = data.value[0];
</script>

<template>
    <div class='flex items-center justify-center min-h-screen from-gray-800 via-greeen-300 to-blue-500 bg-gradient-to-br'>
        <div class='w-full max-w-lg px-0 py-8 mx-auto bg-white rounded-lg shadow-xl'>
            <div class='max-w-md mx-auto space-y-6'>
                <div class="py-8 px-0 mx-auto max-w-screen-xl lg:py-16">
                    <div class="mx-auto max-w-screen-sm text-center">
                        <div>
                            <h2 class="mb-4 text-4xl font-extrabold tracking-tight leading-none md:text-5xl lg:text-6xl">{{
                                coin.name }} Detail page</h2>
                            <table border="1 px solid" class="table-auto">
                                <thead class="bg-gray-200 border-b">
                                    <th scope="col" class="text-sm font-medium text-gray-900 px-6 py-4 text-left">Symbol
                                    </th>
                                    <th scope="col" class="text-sm font-medium text-gray-900 px-6 py-4 text-left">Rank</th>
                                    <th scope="col" class="text-sm font-medium text-gray-900 px-6 py-4 text-left">Price - US
                                        $</th>
                                    <th scope="col" class="text-sm font-medium text-gray-900 px-6 py-4 text-left">Market Cap
                                        - US $</th>
                                </thead>
                                <tr class="bg-white border-b transition duration-300 ease-in-out hover:bg-gray-100">
                                    <td class="px-6 py-4 whitespace-nowrap text-sm font-medium text-gray-900">{{ coin.symbol
                                    }}</td>
                                    <td class="px-6 py-4 whitespace-nowrap text-sm font-medium text-gray-900">{{ coin.rank
                                    }}</td>
                                    <td class="px-6 py-4 whitespace-nowrap text-sm font-medium text-gray-900">{{
                                        coin.price_usd }}</td>
                                    <td class="px-6 py-4 whitespace-nowrap text-sm font-medium text-gray-900">{{
                                        coin.market_cap_usd }}</td>
                                </tr>
                            </table>
                        </div>
                </div>
            </div>

        </div>
    </div>
</div></template>