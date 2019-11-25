<template>
	<v-app>

		<v-app-bar
			app
			color="primary"
			dark
		>
			<div class="d-flex align-center">
				<v-img
					alt="Vuetify Logo"
					class="shrink mr-2"
					contain
					src="https://cdn.vuetifyjs.com/images/logos/vuetify-logo-dark.png"
					transition="scale-transition"
					width="40"
				/>

				<v-img
					alt="Vuetify Name"
					class="shrink mt-1 hidden-sm-and-down"
					contain
					min-width="100"
					src="https://cdn.vuetifyjs.com/images/logos/vuetify-name-dark.png"
					width="100"
				/>
			</div>

			<v-spacer></v-spacer>

			<v-btn
				href="https://github.com/vuetifyjs/vuetify/releases/latest"
				target="_blank"
				text
			>
				<span class="mr-2">Latest Release</span>
				<v-icon>mdi-open-in-new</v-icon>
			</v-btn>
		</v-app-bar>

		<!-- <v-content>
			<HelloWorld/>
		</v-content> -->
		<v-content>
			<v-container>
			<v-radio-group v-model="color" :mandatory="false">
				<ColorSpace
					:id="rgb.id"
					:label="rgb.label"
					:labels="rgb.labels"
				/>
				<ColorSpace
					:id="lab.id"
					:label="lab.label"
					:labels="lab.labels"
				/>
			</v-radio-group>
			</v-container>
		</v-content>
	</v-app>
</template>

<script>
// import NumberInput from './components/NumberInput';
import ColorSpace from './components/ColorSpace';

export default {
	name: 'App',

	components: {
		// NumberInput,
		ColorSpace,
	},

	data: () => ({
		rgb: {
			label: 'RGB',
			labels: ['R', 'G', 'B'],
			id: 'rgb',
		},
		lab: {
			label: 'L*a*b*',
			labels: ['L*', 'a*', 'b*', 'H*', 'C*'],
			id: 'lab',
		},
	}),
};
</script>
