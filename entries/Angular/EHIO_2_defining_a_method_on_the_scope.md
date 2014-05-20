# Defining a method on the scope

- Try not to reference $scope inside of a function, instead pass in a parameter from the function

- function testFunction (parameter) {
		return $scope.data.message.split('').reverse().join('');
};

In the view:
	