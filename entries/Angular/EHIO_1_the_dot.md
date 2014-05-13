#The Dot
*12/5/2014 Anguljar JS*

Börja med att titta på följande länk:
[Angular video](https://egghead.io/lessons/angularjs-the-dot)

Videon behandlar i huvudsak punkten i exempelvis

### ng-model = "data.message"

och varför och när den skall användas.


Vår vän som presenterar videon skapar först ett html dokument med en struktur som ser ut såhär:

###<div>
	<div ng-app="">
		<input type="text" ng-model="message">
		<h1>{{message}}</h1>

		<div ng-controller="FirstController">
			<input type="text" ng-model="message">
			<h1>{{message}}</h1>
		</div>

		<div ng-controller="FirstController">
			<input type="text" ng-model="message">
			<h1>{{message}}</h1>
		</div>
	<div>
</div>