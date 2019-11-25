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

		<v-content>
			<v-container>
			<v-radio-group v-model="current" :mandatory="false">
				<ColorSpace v-for="cs in css" :key="cs.id"
					:id="cs.id"
					:label="cs.label"
					:elements="cs.elements"
				/>
			</v-radio-group>
			</v-container>
		</v-content>
	</v-app>
</template>

<script>
// import NumberField from './components/NumberField';
import ColorSpace from './components/ColorSpace';

export default {
	name: 'App',

	components: {
		// NumberField,
		ColorSpace,
	},

	data: () => ({
		current: 'srgb',
		css: [
			{
				id: 'srgb',
				label: 'sRGB',
				elements: [
					{ label: 'R', min: 0, max: 255 },
					{ label: 'G', min: 0, max: 255 },
					{ label: 'B', min: 0, max: 255 },
				],
			},
			{
				id: 'lab',
				label: 'L*a*b*',
				elements: [
					{ label: 'L*', min: 0, max: 100 },
					{ label: 'a*', min: -100, max: 100 },
					{ label: 'b*', min: -100, max: 100 },
					{ label: 'H*', min: 0, max: 359 },
					{ label: 'C*', min: 0, max: 100 },
				],
			},
		]
	}),
};
</script>
