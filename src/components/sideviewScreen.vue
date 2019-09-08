<template>
    <div class="screen-wrapper">
        <div class="screenItem" v-for="(item, index) in list" :key="index">
            <div class="leftSide">
                <div class="timestamp">Timestamp</div>
                <div class="value">{{item.timeStamp}}</div>
            </div>
            <div class="rightSide">
                <div class="raw">Raw</div>
                <div class="value">{{item.raw}}</div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        list: {

        }
    },
    data() {
        return {
            
        }
    }
}
</script>

<style lang="scss" scoped>
    .screen-wrapper {
        height: auto;
        width: 100%;
        overflow: auto;
        outline: 1px solid gray;
        .screenItem {
            width: 100%;
            height: 10%;
            display: inline-block;
            border-top: 1px solid gray;
            .leftSide {
                float: left;
                height: 100%;
                width: 20%;
                .timestamp {
                    width: 100%;
                    height: 50%;
                }
                .value {
                    width: 100%;
                    height: 50%;
                }
            }
            .rightSide {
                float: left;
                height: 100%;
                width: 80%;
                .raw {
                    width: 100%;
                    height: 50%;
                }
                .value {
                    width: 100%;
                    height: 50%;
                }
            }
        }
    }
</style>