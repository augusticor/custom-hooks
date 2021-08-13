# useForm

### Description

Use this hook when you need to keep track of a form and it's fields.

### Return state of the hook:

An [ ... ] array of the form values, a function to get the data on the form and a function to reset the form to the initial values.

|      Return       |   Type   |            Description            |
| :---------------: | :------: | :-------------------------------: |
|    formValues     |  object  |            Form fields            |
| handleInputChange | function | Tracks form fields and its values |
|     resetForm     | function |      Resets the form values       |

### Example

**initialState = { ... }**

The initial values for a form fields, for example if you have an input for writing the username and other for writing the favorite food, it would look like this:

```javascript
const initialState = {
	userName: '',
	food: '',
};

const [formValues, handleInputChange] = useForm(initialState);

const { userName, food } = formValues;
```

And the HTML:

```html
<form>
	<div className="form-group">
		<label htmlFor="nameinput">Name</label>
		<input id="nameinput" name="userName" type="text" value="{userName}" placeholder="Pepito Alimania" onChange="{handleInputChange}" />
	</div>

	<div className="form-group">
		<label htmlFor="foodinput">Favorite food</label>
		<input id="foodinput" name="food" type="text" value="{food}" placeholder="Pizza" onChange="{handleInputChange}" />
	</div>
</form>
```

**handleInputChange**

This function will only work if the input has the same "name" attribute as the key of the object, in the above example the userName input has the name "userName" and the key of the object is also "userName: ''", by applying this the input that the user writes will be assigned to the variable, as well the "value" property of the html should be the variable name, for updating on the U.I.

```html
<input id="nameinput" name="userName" type="text" value="{userName}" placeholder="Pepito Alimania" onChange="{handleInputChange}" />
```
