<script setup>

const route = useRoute();
useHead({
  title: `${route.params.make} in ${route.params.city}`
})

definePageMeta({
  layout: 'custom',
})

</script>
<template>
  <div>
        <div class="mt-32 flex">
          <NuxtErrorBoundary>
             <CarSidebar />
             <NuxtPage />
            <template #error="{error}">
              <div>
                <div class="text-center mx-auto flex flex-col">
                  <h1 class="text-5xl text-red-400 mb-4">Sorry, something went wrong</h1>
                  <code>{{ error }}</code>
                  <button @click="error.value = null" class="text-white bg-blue-400 px-10 py-3 rounded mt-4">Go Back</button>
                </div>
              </div>
            </template>
          </NuxtErrorBoundary>
        </div>
    </div>
</template>
