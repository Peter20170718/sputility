### Choice
{{
// Get a single select dropdown field
var myChoiceField = SPUtility.GetSPField('Single Choice Field');

// Set the dropdown to Completed
myChoiceField.SetValue('Completed');

// Gets the value, value = 'Completed'
var value = myChoiceField.GetValue();

// Make the Title field read only
myChoiceField.MakeReadOnly();

// Hide the field
myChoiceField.Hide();

// This is the same for a radio button select field
// The value should be equal to the label displayed next to the radio button in the UI
SPUtility.GetSPField('Radio Button Choice').SetValue('Green');


// Multi-select fields are the same except you can call SetValue multiple times
// For example, to check the Alpha, Charlie, and Echo checkboxes:
var myMultiSelectField = SPUtility.GetSPField('Multiselect Column');
myMultiSelectField.SetValue('Alpha');
myMultiSelectField.SetValue('Charlie');
myMultiSelectField.SetValue('Echo');

// for fill-in fields, simply pass a value that does not exist in the list of choices
myMultiSelectField.SetValue('Christmas'); // Christmas is not a choice so Fill-in gets set

// GetValue returns an array of strings
var values = myMultiSelectField.GetValue();
// Value = ["Alpha", "Bravo", "Charlie"](_Alpha_,-_Bravo_,-_Charlie_)
}}