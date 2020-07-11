<template>
	<div class="container">
		<div class="row">
			<div class="col-lg-12">
				<br/>
				<button  @click="selectedComponent = 'appBlue'" class="btn btn-primary">Load Blue Template</button>
				<button  @click="selectedComponent = 'appGreen'" class="btn btn-success">Load Green Template</button>
				<button  @click="selectedComponent = 'appRed'" class="btn btn-danger">Load Red Template</button>
				<hr/>
                <p>These components are kept alive. <br> Don't believe?  Click the button below, <span :style="{fontWeight: bold}">switch to another template </span> and <u>count</u> would remain!</p>


                <p v-if="selectedComponent == 'appBlue'">
                    Selected Template: <span class="blue">Blue</span>
                </p>
                <p v-else-if="selectedComponent == 'appRed'">
                    Selected Template: <span class="red">Red </span> 
                </p>

                <p v-else>
                    Selected Template: <span class="green">Green</span>
                </p>
                

                <keep-alive>
                    <component :is="selectedComponent"></component>
                </keep-alive>
                
				
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
            selectedComponent: 'appBlue', 
 
        }
    },
    
    components: {
        appBlue: Blue,
        appGreen: Green,
        appRed: Red
    }
}
</script>

<style scoped>
.blue {
    color: blue;
}
.green {
    color: green;
}

.red {
    color: red; 
}

button {
    margin: 10px; 
}

@media only screen and (max-width: 500px) {
    button {
        width: 100%; 
        margin: 10px 0;
    }
}




</style>
