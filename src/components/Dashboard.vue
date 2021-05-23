<template>
<div class="dashboard">
    <Who />
    <Nav />
</div>
</template>

<script>
import Nav from "./Nav.vue"
import Who from "./Who.vue"

export default {
    name: 'Dashboard',
    components: {
        Who,
        Nav,
    }
};
</script>

<style lang="scss" scoped>
.dashboard {
    min-height: inherit;
    width: 30% !important;
    position: relative;
    top: 0;
    left: 0;
    background-color: rgba(255, 255, 255, 0.3);
    border-radius: inherit;

}

@media (max-width: 678px) {
    .dashboard {
        display: none;
    }
}
</style>
