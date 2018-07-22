<template>
    <v-toolbar app>
        <v-toolbar-title>Vuetify News</v-toolbar-title> 
        <v-spacer></v-spacer>
        <v-toolbar-items class="hidden-sm-and-down">            
            <v-btn flat to="/">Current News</v-btn>            

            <v-btn flat to="/saved">              
              <v-badge right>
                <span v-if="totalSaved>0" slot="badge">{{totalSaved}}</span>
                <span>Saved</span>
              </v-badge>
            </v-btn>    

            <v-btn flat to="/about">About</v-btn>            
        </v-toolbar-items>
    </v-toolbar>
</template>

<script>
export default {
    name: 'Header',
    props: {
        totalSaved: Number
    }
}
</script>

<style>

</style>
