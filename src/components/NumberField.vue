<template>
	<div class="number-field">
		<v-slider class="number-slider" hide-details
			:label="label" :min="min" :max="max"
			:value="value"
			@change="update"
		>
			<template v-slot:append>
				<v-text-field class="number-input" type="number" outlined hide-details single-line
					:min="min" :max="max" :value="value"
					@input="update"
				/>
			</template>
		</v-slider>
	</div>
</template>


<!----------------------------------------------------------------------------->


<script>
export default {
	name: 'NumberField',
	methods: {
		update(e) {
			this.$emit('input', e);
		}
	},
	props: {
		label: String,
		min: { type: Number, default: 0 },
		max: { type: Number, default: 255 },
		value: Number,
	},
};
</script>


<!----------------------------------------------------------------------------->


<style lang="scss" scoped>
.number-slider {
	& ::v-deep .v-label {
		width: 32px;
	}
	&.v-input__slider ::v-deep .v-input__control {
		flex-grow: 1 !important;
	}
}
.number-input {
	width: 64px;

	& ::v-deep input {
		text-align: right;
	}
	&.v-text-field ::v-deep .v-input__control > .v-input__slot {
		padding: { left: 12px; right: 4px; }
		min-height: 32px;
	}
}
</style>
