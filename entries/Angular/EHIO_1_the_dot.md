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

Det intressanta med videon är att den till stor del förklarar scope inheritance. Han säger i videon att $scope inte skall tänkas på som ett objekt som man sätter properties på utan som en referens till det som händer i vyn som man kan tillskriva objekt på som sedan har properties som man watchar. Skriver man en property direkt på $scope objektet så kommer det ärvas nedåt precis som man har tänkt sig. Om dock någon av child scopsen försöker skriva något på den ärvda propertyn så kommer detta att skriva över propertyn i $scopet och några ändringar kommer inte längre att ärvas från parentScopet. Om man nu önskar att childcontrollers både skall kunna skriva till en property på parentcontroller så måste man skapa ett objekt i parentcontroller med en property som childcontroller får skriva till. Detta innebär alltså att childControllern skriver på en property på ett objekt på scopet istället för en property på scopet. Det skulle kunna se ut såhär i parentController $scope.data = {message: 'Hello'} och sedan se ut såhär i childController $scope.data.message =  'Well Well'. This would keep the inheritance from parentcontroller while still sharing data between parent and childController. 