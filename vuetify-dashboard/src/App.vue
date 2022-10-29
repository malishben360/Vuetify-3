<template>
	<v-app>
		<v-app-bar app dark color="primary">
			<v-app-bar-title>Vuetify Dashboard</v-app-bar-title>
			<v-spacer></v-spacer>
			<v-btn
				v-for="link in links"
				:key="`${link.label}-header-link`"
				:to="link.link"
				>{{ link.label }}</v-btn
			>
		</v-app-bar>
		<v-main>
			<router-view></router-view>
		</v-main>
		<v-footer app absolute color="primary" padless>
			<v-row justify="center" no-gutters>
				<v-btn
					v-for="link in links"
					:key="`${link.label}-footer-link`"
					:to="link.link"
					color="primary"
					class="my-2"
				>
					{{ link.label }}
				</v-btn>
				<v-col class="primary lighten-2 py-4 text-center white--text" cols="12">
					{{ new Date().getFullYear() }} — <strong>Vuetify Dashboard</strong>
				</v-col>
			</v-row>
		</v-footer>
	</v-app>
</template>

<script>
export default {
	name: 'App',

	components: {},

	data: () => ({
		showPassword: false,
		links: [
			{
				label: 'Home',
				link: '/',
			},
			{
				label: 'Login',
				link: '/login',
			},
		],
	}),
}
</script>
