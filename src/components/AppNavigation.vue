<template>
	<span>
		<v-navigation-drawer app v-model="drawer" class="brown lighten-2" dark disable-resize-watcher> <!-- side menu for smaller screens -->
            <v-list>
                <template v-for="(item, index) in items">
                    <v-list-tile :key="index">
                        <v-list-tile-content>
                            {{item.title}}
                        </v-list-tile-content>
                    </v-list-tile>
                    <v-divider :key="`divider-${index}`"></v-divider>
                </template>
            </v-list>
        </v-navigation-drawer>
		<v-toolbar app color="blue dark-3" dark>  <!-- the navigation bar on top -->
		    <v-toolbar-side-icon class="hidden-md-and-up" @click="drawer = !drawer"></v-toolbar-side-icon>
		    <v-spacer class="hidden-md-and-up"></v-spacer>
		    <router-link to="/" style="color: white; text-decoration:none"> 
		    <v-toolbar-title to="/">{{appTitle}}</v-toolbar-title>
			</router-link> 
		    <v-btn class="hidden-sm-and-down" to="/menu" flat>Menu</v-btn>
		    <v-spacer class="hidden-sm-and-down"></v-spacer>
		    <v-btn class="hidden-sm-and-down" to="/sign-in" flat>SIGN IN</v-btn>
	    	<v-btn class="hidden-sm-and-down" to="/join" color="blue lighten-3">JOIN</v-btn>
	    </v-toolbar>
	</span>
</template>
<script>
export default {  // exporting by giving it a name which can be used later on SPC 
	name:"AppNavigation",
	data() {
        return {
            appTitle: 'Meal Prep',
            drawer: false,
            items: [
                { title: 'Menu' },
                { title: 'Sign In' },
                { title: 'Join' }
            ]
        };
    }
};
</script>

<style scoped>
.a {
	color: white;
	text-decoration: none;
}
</style>