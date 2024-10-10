<template>
  <div class="container">
    <div
      class="list-item border-0 border-start border-4 border-bottom p-1 d-flex"
      :class="{
        'border-start-0': !border,
        [borderClass]: color,
        disabled: disabled,
      }"
    >
      <template v-if="!anySlotSet">
        <img
          class="avatar"
          src="https://img.freepik.com/free-vector/smiling-young-man-illustration_1308-173524.jpg?size=626&ext=jpg"
          alt="Default Logo"
        />
        <div class="flex-grow-1">
          <h5 class="mb-1">Default Title</h5>
          <p class="description">Default Description</p>
          <small class="sub-description text-muted">Default Sub Description</small>
        </div>
        <span class="badge bg-success rounded-pill">action</span>
      </template>

      <template v-else>
        <slot name="logo" alt="Logo" class="avatar"></slot>
        <div class="flex-grow-1">
          <h5 class="mb-1"><slot name="title" v-if="isTitleSlotSet">Default Title</slot></h5>
          <p class="description"><slot name="desc" v-if="isDescSlotSet">Default Description</slot></p>
          <small class="sub-description text-muted"
            ><slot name="subDesc"v-if="isSubDescSlotSet">Default Sub Description</slot
          ></small>
        </div>
        <slot name="action" v-if="isActionSlotSet">
          <span class="badge bg-success rounded-pill">action</span>
        </slot>
      </template>
    </div>
  </div>
</template>

<script setup lang="ts">
import { defineProps, computed, useSlots } from "vue";
import type { IListItem } from "@/meta/interfaces/i-list-item";

const props = defineProps<IListItem>() as IListItem;
const slots = useSlots();

const borderClass = computed(() => {
  return `border-${props.color}`;
});

const isLogoSlotSet = !!slots.logo;
const isTitleSlotSet = !!slots.title;
const isDescSlotSet = !!slots.desc
const isSubDescSlotSet = !!slots.subDesc
const isActionSlotSet = !!slots.action

const anySlotSet = isLogoSlotSet || isTitleSlotSet || isDescSlotSet || isSubDescSlotSet || isActionSlotSet
</script>

<style scoped>
.border-red {
  border-left-color: red !important;
}
.border-blue {
  border-left-color: blue !important;
}
.border-green {
  border-left-color: green !important;
}
.border-yellow {
  border-left-color: yellow !important;
}
.disabled {
  color: rgba(0, 0, 0, 0.479);
  opacity: 0.8;
}
.row:hover {
  background-color: rgb(172, 171, 171);
}
.list-item {
  background-color: lightgray;
  align-items: center;
  position: relative;
  transition: background-color 0.3s;
  border-radius: 0%;
}
.action-btn {
  margin-left: auto;
  align-self: center;
}
@media (max-width: 576px) {
  .list-item {
    flex-direction: column;
    align-items: flex-start;
  }
  .action-btn {
    margin-left: 0;
    margin-top: 10px;
  }
}
</style>
