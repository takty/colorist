<template>
	<v-card class="pa-4 my-4" min-width="421">
		<v-radio :label="label" :value="id" class="font-weight-bold"></v-radio>
		<v-content class="pt-3">
			<NumberField v-for="(elm, idx) in elements" :key="elm.label"
				:label="elm.label"
				:min="elm.min"
				:max="elm.max"
				v-model.number="vals[idx]"
				@input="change"
			/>
		</v-content>
	</v-card>
</template>


<!----------------------------------------------------------------------------->


<script>
import NumberField from './NumberField';

export default {
	name: 'ColorSpace',

	components: {
		NumberField,
	},
	props: {
		id: { type: String },
		label: { type: String },
		count: { type: Number, default: 3 },
		elements: { type: Array },
	},
	data: () => ({
		vals: [0, 0, 0, 0, 0]
	}),
	methods: {
		change() {
			window.console.log(this.vals);
			// this.vals[1] = this.vals[0];
			// window.console.log(this.val_1, this.val_0);
		}
	}
};
</script>


<!----------------------------------------------------------------------------->


<style scoped>
.number-field:nth-child(4) {
	margin-top: 12px;
}
</style>
