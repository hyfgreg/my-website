<template>
    <v-container ma-auto pa-0>
        <v-layout>
            <v-flex xs12 d-flex align-center text-xs-center>
                <div class="custom-rooter">
                    <span>&copy; 2018</span>
                </div>
            </v-flex>
        </v-layout>
    </v-container>
</template>

<script>
export default {
  name: 'RooterComponent'
}
</script>

<style>
.custom-rooter{
    height: 32px;
    display: flex;
    align-items: center;
    justify-content:center;
}
</style>
