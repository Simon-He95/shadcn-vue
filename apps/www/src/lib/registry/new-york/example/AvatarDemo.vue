<script setup lang="ts">
import { Avatar, AvatarFallback, AvatarImage } from '@/lib/registry/new-york/ui/avatar'
</script>

<template>
  <Avatar>
    <AvatarImage src="https://github.com/unovue.png" alt="@radix-vue" />
    <AvatarFallback>CN</AvatarFallback>
  </Avatar>
</template>
