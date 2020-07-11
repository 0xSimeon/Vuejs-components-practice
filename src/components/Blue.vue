<template>
	<div>
		<p>
			<button class="btn btn-info" @click="count++">Current Count:</button>
			<span>{{ count }}</span>
		</p>
		<div class="blue">
			<p>Blue Template</p>
		</div>
	</div>
</template>

<script>
export default {
	data() {
		return {
			count: 0,
		};
    }
};
</script>

<style>
div.blue {
	border: 1px solid blue;
	background-color: lightblue;
	padding: 30px;
	margin: 20px auto;
	text-align: center;
}

p, button {
	font-size: 18px;
}

span {
	font-size: 21px;
	font-weight: bold;
}
</style>
