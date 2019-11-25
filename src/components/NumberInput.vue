<template>
	<div class="number-control">
	<v-slider
		v-model="value"
		:min="min"
		:max="max"
		:label="label"
		class="number-slider"
		hide-details
	>
		<template v-slot:append>
			<v-text-field
				v-model="value"
				class="number-input"
				type="number"
				:min="min"
				:max="max"
				outlined
				hide-details
				single-line
			></v-text-field>
		</template>
	</v-slider>
	</div>
</template>

<style scoped>
.number-slider >>> .v-label {
	width: 32px;
}
.number-slider.v-input__slider >>> .v-input__control {
	flex-grow: 1 !important;
}
.number-input {
	width: 64px;
}
.number-input.v-text-field >>> .v-input__control > .v-input__slot {
	padding-left: 12px;
	padding-right: 4px;
	min-height: 32px;
}
.number-input >>> input {
	text-align: right;
}
</style>

<script>
export default {
	name: 'NumberInput',

	props: {
		label: String,
		value: { type: Number, default: 0 },
		min: { type: Number, default: 0 },
		max: { type: Number, default: 255 },
	},
	data: () => ({
	}),
};
</script>
