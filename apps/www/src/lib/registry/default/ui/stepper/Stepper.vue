<script lang="ts" setup>
import type { StepperRootEmits, StepperRootProps } from 'radix-vue'
import { cn } from '@/lib/utils'
import { StepperRoot, useForwardPropsEmits } from 'radix-vue'

import { computed, type HTMLAttributes } from 'vue'

const props = defineProps<StepperRootProps & { class?: HTMLAttributes['class'] }>()
const emits = defineEmits<StepperRootEmits>()

const delegatedProps = computed(() => {
  const { class: _, ...delegated } = props

  return delegated
})

const forwarded = useForwardPropsEmits(delegatedProps, emits)
</script>

container flex-1 items-start md:grid md:grid-cols-[220px_min-[max(0,1fr)] md:gap-6 lg:grid-cols-[240px_min-[max(0,1fr)] lg:gap-10
<template>
  <StepperRoot
    v-slot="slotProps"
    :class="cn(
      'flex gap-2',
      props.class,
    )"
    v-bind="forwarded"
  >
    <slot v-bind="slotProps" />
  </StepperRoot>
</template>
