<template>
  <div class="container" v-if="list.header">
    <div
      class="list-item border-0 border-start border-4 border-bottom p-1 d-flex"
      style="background-color: lightgray"
    >
      {{ list.header }}
    </div>
  </div>
  <template v-for="item in list.items" :key="item.title">
    <v-list-item :color="item.color" :border="item.border" :disabled="item.disabled">
      <template #title>{{ item.title }}</template>
      <template #logo v-if="item.logo"
        ><img :src="item.logo" alt="Logo" class="avatar"
      /></template>
      <template #desc>{{ item.desc }}</template>
      <template #subDesc>{{ item.subDesc }}</template>
      <template #action>
        <div v-if="item.action == actionsEnum.pending">
          <div
            class="btn-group btn-group-sm"
            role="group"
            aria-label="Basic outlined example"
          >
            <button type="button" class="btn btn-success">Approve</button>
            <button type="button" class="btn btn-danger">Reject</button>
          </div>
        </div>
        <div v-if="item.action == actionsEnum.request">
          <button type="button" class="btn btn-secondary btn-sm">Request</button>
        </div>
        <div v-if="item.action == actionsEnum.export">
          <button type="button" class="btn btn-warning btn-sm">Export</button>
        </div>
      </template>
    </v-list-item>
  </template>
  <br />
</template>

<script setup lang="ts">
import { defineAsyncComponent, defineProps } from "vue"
import { actionsEnum } from "@/meta/enums/actions"
import type { IListGroup } from "@/meta/interfaces/i-list-group"

const props = defineProps<IListGroup>() as IListGroup

const VListItem = defineAsyncComponent(()=>
  import('@/components/listitem.vue')
)

</script>

<style scoped>

</style>
