<script setup>
const { data } = await useFetch('/api/tickers/?limit=10')
console.log("🚀 ~ file: index.vue:3 ~ data:", data)
</script>

<template>
  <main>
    <div class='flex items-center justify-center min-h-screen from-gray-800 via-greeen-300 to-blue-500 bg-gradient-to-br'>
      <div class='w-full max-w-lg px-0 py-8 mx-auto bg-white rounded-lg shadow-xl'>
        <div class='max-w-md mx-auto space-y-6'>
          <div class="py-8 px-0 mx-auto max-w-screen-xl lg:py-16">
            <div class="mx-auto max-w-screen-sm text-center">
              <h1 class="mb-4 text-4xl font-extrabold tracking-tight leading-none md:text-5xl lg:text-6xl">Index Page</h1>
              <table>
                <thead class="bg-gray-200 border-b">
                  <tr>
                    <th scope="col" class="text-sm font-medium text-gray-900 px-6 py-4 text-left">Name</th>
                    <th scope="col" class="text-sm font-medium text-gray-900 px-6 py-4 text-left">Symbol</th>
                    <th scope="col" class="text-sm font-medium text-gray-900 px-6 py-4 text-left">Price</th>
                    <th scope="col" class="text-sm font-medium text-gray-900 px-6 py-4 text-left">Details</th>
                  </tr>
                </thead>
                <tr v-for="currency in data.data" :key="data.data.id"
                  class="bg-white border-b transition duration-300 ease-in-out hover:bg-gray-100">
                  <td class="px-6 py-4 whitespace-nowrap text-sm font-medium text-gray-900">{{ currency.name }}</td>
                  <td class="text-sm text-gray-900 font-light px-6 py-4 whitespace-nowrap">{{ currency.symbol }}</td>
                  <td class="text-sm text-gray-900 font-light px-6 py-4 whitespace-nowrap">{{ currency.price_usd }}</td>
                  <td class="text-sm text-blue-800 font-light px-6 py-4 whitespace-nowrap">
                    <NuxtLink :to="'/currency/' + currency.id">{{ currency.id }}</NuxtLink>
                  </td>
                </tr>
              </table>
            </div>
          </div>

        </div>
      </div>
    </div>
  </main>
</template>