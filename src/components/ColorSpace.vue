<template>
	<v-card class="pa-4 my-4" min-width="421">
		<v-radio :label="label" :value="id" class="font-weight-bold"></v-radio>
		<v-content class="pt-3">
			<NumberInput :key="index" v-for="(label, index) in labels" :label="label"/>
		</v-content>
	</v-card>
</template>

<style scoped>
.number-control:nth-child(4) {
	margin-top: 12px;
}
</style>

<script>
import NumberInput from './NumberInput';

export default {
	name: 'ColorSpace',

	components: {
		NumberInput,
	},

	props: {
		id: { type: String },
		label: { type: String },
		labels: { type: Array },
	},
	data: () => ({
	}),
};
</script>
