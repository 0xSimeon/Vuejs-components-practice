<template>
	<div class="container">
		<div class="row">
			<div class="col-xs-4 col-lg-12">
				<br />
				<button @click="selectedComponent = 'appBlue'" class="btn btn-primary">Load Blue Template</button>
				<button @click="selectedComponent = 'appGreen'" class="btn btn-success">Load Green Template</button>
				<button @click="selectedComponent = 'appRed'" class="btn btn-danger">Load Red Template</button>
				<hr/>


                <p v-if="selectedComponent == 'appBlue'">
                    Selected Template: Blue
                </p>

                <p v-else-if="selectedComponent == 'appRed'">
                    Selected Template: Red
                </p>

                <p v-else>
                    Selected Template: Green
                </p>
                

                <keep-alive>
                    <component :is="selectedComponent"></component>
                </keep-alive>
                
				<!-- <app-blue>
					<h2 slot="blue">{{ blue }}</h2>
				</app-blue>
				<app-green>
					<h2 slot="green">{{ green }}</h2>
				</app-green>
				<app-red>
					<h2 slot="red">{{ red }}</h2>
				</app-red> -->

			</div>
		</div>
	</div>
</template>

<script>
import Blue from './components/Blue.vue';
import Green from './components/Green.vue';
import Red from './components/Red.vue';

export default {
    data: function() {
        return {
            red: 'red template',
            green: 'green template',
            blue: 'blue template',
            selectedComponent: 'appBlue'
        }
    },
    components: {
        appBlue: Blue,
        appGreen: Green,
        appRed: Red
    }
}
</script>

<style></style>
