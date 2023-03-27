# Component Testing

I created a simple calendar component that is in my github: https://github.com/deejaygraham/calendar/tree/main/deskal

Get source and run npm run start. Should launch a browser and show the calendar control.

For components we need to install cypress as an npm component.

Start cypress again npx cypress open --browser chrome --component

Samll container for just this component, sandbox.

Test that the correct day of the week is shown, find the correct day of the month

Find the ++ button and press it. does it increment the date?
Find the -- button and press it multiple times. Does it decrease the date and the day and date change?

Reloading, Time travel, dev portal,
Finding something that doesn't exist.

Redux etc we need to look at. 

Also commands for cypress too. Using logs.
