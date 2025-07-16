<template>
  <div>
    <UIcon name="i-lucide-lightbulb" class="size-5" />

    <UTable :columns="columns" :data="data.result"/>
  </div>
</template>
<script setup lang="ts">
import { h, resolveComponent } from 'vue'
import type { TableColumn } from '@nuxt/ui'
import type { Row } from '@tanstack/vue-table'
const UButton = resolveComponent('UButton')
const UIcon = resolveComponent('UIcon')
const {data} = await useFetch('http://127.0.0.1:8000/therapeuts')
const columns:TableColumn<never> = [
  {
    accessorKey: 'name',
    header: 'Name'
  },
  {
    accessorKey: 'email',
    header: 'Email'
  },
  {
    accessorKey: 'contacted_date',
    header: 'Contacted On'
  },
  {
    accessorKey: 'response_received',
    header: 'Response Received'
  },
  {
    accessorKey: 'answer_status',
    header: 'Answer'
  },
  {
    header: 'Visit Profile',
    id: 'visit_profile',
    cell: ({ row }) => {
      return h(
          UIcon,
          {
            name: 'i-lucide-lightbulb',

          }
      )

    }
  }
]
</script>
