
# Custom Input Component for VueJS 2.*
Creating input field isn't same anymore. :D

## Features
- Support v-model
- Generate radio and checkbox from array

## Requirement
- Vue 2.*

## Available Input Components
- Radio (VueRadio and VueRadioBlock)
- Checkbox (VueCheckbox and VueCheckboxBlock)

## Components
### Non-Block Components
#### Radio and Checkbox

| Parameter | Usage |
| ------------ | ------------ |
|id|The "id" attribute for input element and label element.|
|values|The value of the radio or checkbox element.|
|nameGroup|The "name" attribute for grouping the element.|
|label|The value for the label element.|
|modelValue|Optional. It is used to mimic the v-model behaviour for checkbox element. Filled with the name of the v-model. Only for checkbox (VueCheckbox)|

### Block Components
#### Radio Block and Checkbox Block
| Parameter | Usage |
| ------------ | ------------ |
|blockTitle|Title of the block.|
|radioData / checkboxData|radio or checkbox data|


## How To Use
### Installing the module
`$ npm i vue-2-custom-input-component --save`

### Usage
##### Importing the components
    import {VueRadio,VueRadioBlock,VueCheckbox,VueCheckboxBlock} from 'vue-2-custom-input-component'
##### Register the components
- Global
```javascript
Vue.component("vue-radio", VueRadio)
Vue.component("vue-radio-block", VueRadioBlock)
Vue.component("vue-checkbox", VueCheckboxBlock)
Vue.component("vue-checkbox-block", VueCheckboxBlock)
```
- Local
```javascript
export default {
	components: {
		 VueRadio,
		 VueRadioBlock,
		 VueCheckbox,
		 VueCheckboxBlock
	},
	data(){
		return {

		}
	}
}
```
#### Sample
- VueRadio
[![VueRadio Sample](https://i.imgur.com/Q0FsoVv.gif "VueRadio Sample")](https://i.imgur.com/Q0FsoVv.gif "VueRadio Sample")
```javascript
// component.vue
<template
	<div>
		<vue-radio
			v-for="(item, index) in radioGender.data"
			:id="radioGender.name+index"
			:key="index"
			:nameGroup="radioGender.name"
			:values="item.value"
			:label="item.label"
			v-model="form.gender"></vue-radio>

			<div>
			<p>Selected : {{form.gender}}</p>
			</div>
	</div>
</template>
<script>
export default{
	data(){
		return {
			form:{
				gender : ""
			},
			radioGender : {
				name : 'gender',
				titile : 'Gender',
				data: [
					{value:"M", label: "Male"},
					{value:"F", label: "Female"}
				]
			}
		}
	}
}
</script>
```

- VueCheckbox
![VueCheckbox Sample](https://i.imgur.com/95CdBft.gif "VueCheckbox Sample")
```javascript
// component.vue
<template
	<div>
		<vue-checkbox
			v-for="(item, index) in checkboxHobby.data"
			:id="checkboxHobby.name+index"
			:key="index"
			:nameGroup="checkboxHobby.name"
			:values="item.value"
			:label="item.label"
			:modelValue = "form.hobby"
			v-model="form.hobby"></vue-checkbox>

			<div>
			<p>Selected : {{form.hobby}}</p>
			</div>
	</div>
</template>
<script>
export default{
	data(){
		return {
			form:{
				hobby : ""
			},
			checkboxHobby : {
				name : 'hobby',
				titile : 'Hobby',
				data: [
					{value:"soccer", label: "Soccer"},
					{value:"watching_anime", label: "Watching Anime"},
					{value:"playing_with_cat", label: "Playing with Cat"},
					{value:"read_history_books", label: "Read History Books"},
				]
			}
		}
	}
}
</script>
```

## Repository
[https://github.com/OnielN14/custom-input-component-vuejs2](https://github.com/OnielN14/custom-input-component-vuejs2)

## Author
- Daniyal Ahmad Rizaldhi (Github: [onieln14](https://github.com/OnielN14))

## Credits
Thanks to humanity. Love You Everyone!!! Because You All Are Great!!!
