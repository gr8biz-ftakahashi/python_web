<template>
    <div>
        HedgeHog Page
    </div>
</template>

<script>
import router from "../../router";
export default {
    name: "HedgeHogs",
    mounted() {
        this.checkLoggedIn();
    },
    methods: {
        checkLoggedIn() {
        this.$session.start();
        if (!this.$session.has("token")) {
            router.push("/auth");
        }
        }
    }
};
</script>