<template>
    <div>
        <nav class="navbar navbar-expand navbar-dark bg-dark">
            <div class="container">
                <div class="nav navbar-nav">
                    <router-link to="/" class="nav-tem nav-link active">Home</router-link>
                    <a class="nav-item nav-link" href="#">Product</a>
                </div>

                <div>
                    <div class="dropdown open">
                        <button
                                class="btn btn-secondary dropdown-toggle"
                                type="button"
                                id="triggerId"
                                data-toggle="dropdown"
                                aria-haspopup="true"
                                aria-expanded="false"
                        >{{cartItemCount}} Cart</button>
                        <div @click="$event.stopPropagation()">
                            <MiniCardComponent />
                        </div>
                    </div>
                </div>
            </div>
        </nav>
    </div>
</template>

<script>
    import MiniCardComponent from "./MiniCardComponent";
    export default {
        name: "HeaderComponent",
        components : {
            MiniCardComponent
        },
        computed : {
            cartItemCount(){
                return this.$store.getters.cartItemCount;
            }
        }
    }
</script>

<style scoped>

</style>