Feature: Registrieren
As a unregistered user 
I want to register an account
so that I can use the website
Background: User is unregistered

Scenario: Succesful registration
	Given User is on the mainpage
		And the user clicks on registration button
		And the user is not registered
When User enters his username
And enter his password
And the two entered passwords match
And enter his E-Mail
And enter the name of the university
And enter the field of study
		And clicks on the save-button
	Then user will be created on database 
		And user will be logged in

Scenario: The two passwords do not match
	Given user is on the mainpage
		And user clicks on registration
		And the user is not register
	When user enter his username
And enter his password
And the two entered passwords do not match
And enter his E-Mail
And enter the name of the university
And enter the field of study
		And clicks on the save-button
	Then user will not be created on database 
		And error message will be shown

Scenario: user is already registered
	Given user is on the mainpage
		And user clicks on registration
		And the user is not registered
	When user enter an existing username
And enter his password
And the two entered passwords match
And enter his E-Mail
And enter the name of the university
And enter the field of study
		And clicks on the save-button
	Then user will not created on database 
	And error message will be show


Scenario: user does not enter every field
	Given user is on the mainpage
		And user clicks on registration
		And the user is not registered
	When one of the fields is empty
	Then user will not be created on database 
		And error message will be shown

_________________________________________________________________________




Feature: Semester anlegen
As a user 
I want to add a new semester
Background: User is registered and logged in

Scenario: the add semester form was filled in correct
	Given user is registered
		And user is logged in
		And user has clicked “Semester anlegen”
	When start date is filled in
		And end date is filled in
		And end date is after start date
		And semester name is filled in
	Then semester is created on database
		And user is forwarded to “Vorlesung anlegen”

Scenario: semester name already exists
	Given user is registered
		And user is logged in
		And user has clicked “Semester anlegen”
	When start date is filled in
		And end date is filled in
		And end date is after start date
		And semester name already exists
	Then semester is not created on database
		And error message is shown



Scenario: not every field is filled out
	Given user is registered
		And user is logged in
		And user has clicked “Semester anlegen”
	When one of the fields is empty
	Then semester is not created on database
		And error message is shown

Scenario: end date is before start date
	Given user is registered
		And user is logged in
		And user has clicked “Semester anlegen”
	When start date is filled in
		And end date is filled in
		And end date is on or before start date
		And semester name already exists
	Then semester is not created on database
		And error message is shown
