<script>
	import {
		Accordion,
		AccordionItem,
		Form,
		FormGroup,
		Checkbox,
		RadioButtonGroup,
		RadioButton,
		Select,
		SelectItem,
		Button,
		ComboBox,
        TextInput,
		SkeletonText
	} from 'carbon-components-svelte';

	function shouldFilterItem(item, value) {
		if (!value) return true;
		return item.text.toLowerCase().includes(value.toLowerCase());
	}
</script>

<Accordion>
	<AccordionItem open title="Personal Information">
		<Form on:submit>
            <FormGroup legendText="Names">
                <TextInput id="first_name" labelText="First name" placeholder="Enter first name..." required />
                <TextInput id="middle_name" labelText="Middle name" placeholder="Enter middle name..."  />
                <TextInput id="last_name" labelText="Last name" placeholder="Enter last name..." required />
            </FormGroup>
			<FormGroup legendText="Checkboxes">
				<Checkbox id="checkbox-0" labelText="Checkbox Label" checked />
				<Checkbox id="checkbox-1" labelText="Checkbox Label" />
				<Checkbox id="checkbox-2" labelText="Checkbox Label" disabled />
			</FormGroup>

			<FormGroup legendText="Radio buttons">
				<RadioButtonGroup name="radio-button-group" selected="default-selected">
					<RadioButton id="radio-1" value="standard" labelText="Standard Radio Button" />

					<RadioButton
						id="radio-2"
						value="default-selected"
						labelText="Default Selected Radio Button"
					/>

					<RadioButton id="radio-4" value="disabled" labelText="Disabled Radio Button" disabled />
				</RadioButtonGroup>
			</FormGroup>

			<FormGroup>
				<Select id="select-1" labelText="Select menu" value="placeholder-item">
					<SelectItem disabled hidden value="placeholder-item" text="Choose an option" />

					<SelectItem value="option-1" text="Option 1" />
					<SelectItem value="option-2" text="Option 2" />
					<SelectItem value="option-3" text="Option 3" />
				</Select>
			</FormGroup>

			<FormGroup>
				<ComboBox
					titleText="Preferred Contact Method"
					placeholder="Select contact method"
					items={[
						{ id: '0', text: 'Phone' },
						{ id: '1', text: 'WhatsApp' },
						{ id: '2', text: 'Email' }
					]}
					{shouldFilterItem}
				/>
			</FormGroup>
			<Button type="submit">Submit</Button>
		</Form>
	</AccordionItem>
	<AccordionItem title="Family Info">
		<p>
			<SkeletonText />
		</p>
	</AccordionItem>
	<AccordionItem title="Church Affiliations">
		<p>
			<SkeletonText />
		</p>
	</AccordionItem>

	<AccordionItem title="Skills and Education">
		<p>
			<SkeletonText />
		</p>
	</AccordionItem>
</Accordion>
