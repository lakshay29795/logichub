<template>
    <div class="sideBar">
        <div class="sideHead">Events Name</div>
        
        <div v-for="(item, index) in list" class="sideTab" @click="selectItem(item)" :key="index">Event Type {{item}}</div>
    </div>
</template>

<script>
import sideBarTab from './sideBarTab.vue';
export default {
    props: {
        list: {
        },
        setTabIndex: {
        }
    },
    data() {
        return {
            sideItems: [
                {
                    action: 'event1',
                    label: 'Event 1',
                },
                {
                    action: 'event2',
                    label: 'Event 2',
                },
                {
                    action: 'event3',
                    label: 'Eventt3',
                },
                {
                    action: 'event4',
                    label: 'Event 4',
                },
                {
                    action: 'event5',
                    label: 'Event 5',
                },
                {
                    action: 'event6',
                    label: 'Event 6',
                },
                {
                    action: 'event7',
                    label: 'Event 7',
                },
                {
                    action: 'event8',
                    label: 'Event 8',
                },
            ]
        }
    },
    methods: {
        selectItem(item) {
            this.setTabIndex(item);
        },
    },
    components: {
        sideBarTab,
    }
}
</script>

<style lang="scss" scoped>
    .sideBar {
        width: 100%;
        height: auto;
        overflow: auto;
        outline: 1px solid gray;
        .sideHead {
            position: relative;
            width: 100%;
            height: 10%;
            display: flex;
            justify-content: center;
            align-items: center;
            background-color: rgb(149, 153, 154);
        }
        .sideTab {            
            position: relative;
            width: 100%;
            height: 10%;
            display: flex;
            justify-content: center;
            align-items: center;
            background-color: rgb(236, 240, 241);
            outline: 1px solid gray;
            // background-color: pink;

        }
    }
</style>