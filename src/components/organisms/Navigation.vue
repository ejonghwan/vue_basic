<template>
    
    <BasicLayoutVue :theme="`blue`">
        <div class="navigation">
            <div class="navigation__sub-menu__button-box">
                <BasicButton v-for="item in topMenu" :key="item.label" :data="item" />
            </div>
            <div class="navigation__sub-menu__button-box">
                <span class="navigation__sub-menu__title">Recruitment</span>
                <div class="navigation__sub-menu__button-box">
                    <BasicButton v-for="item in middleMenu" :key="item.label" :data="item" />
                </div>
            </div>
            <div class="navigation__sub-menu__button-box">
                <span class="navigation__sub-menu__title">Oraganization</span>
                <div class="navigation__sub-menu__button-box">
                    <BasicButton v-for="item in bottomMenu" :key="item.label" :data="item" />
                </div>
            </div>
        </div>
    </BasicLayoutVue>

</template>

<script setup lang="ts">
import BasicLayoutVue from "@components/atoms/layout/BasicLayout.vue";
import { computed } from "vue";
import BasicButton from "../atoms/button/BasicButton.vue";

const menu = [
    { icon: 'Dashboard', label: 'Dashboard' },
    { icon: 'Index', label: 'Index' },
    { icon: 'Calender', label: 'Calender' },
    { icon: 'Jobs', label: 'Jobs' },
    { icon: 'Reference', label: 'Reference' },
    { icon: 'Document', label: 'Document' },
    { icon: 'CareerSite', label: 'CareerSite' },
    { icon: 'Employee', label: 'Employee' },
    { icon: 'Structure', label: 'Structure' },
    { icon: 'Settings', label: 'Settings' },
]

const topMenu = computed(() => {
    return menu.slice(0, 3)
})
const middleMenu = computed(() => {
    return menu.slice(3, 7)
})
const bottomMenu = computed(() => {
    return menu.slice(7, menu.length)
})

</script>

<style lang="scss" scoped>

    .navigation {
        display: flex;
        flex-direction: column;
        align-items: flex-start;
        justify-content: center;
        width: 100%;
        gap: 40px;

        &__sub-menu {
            display: flex;
            flex-direction: column;
            align-content: flex-start;
            justify-content: center;
            width: 100%;

            &__title {
                margin-bottom: 12px;
                font-family: 'SUITE-ragular';
                color: $color-white-000;

            }

            &__button-box {
                display: calc(100% - 24px);
            }
        }

    }

</style>