<template>
  <div>
    <UTable :columns="columns" :data="data"/>
  </div>
</template>
<script setup lang="ts">
  const {data} = await useFetch('http://127.0.0.1:8000/therapeuts')
  const columns = [
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
  ]
</script>
