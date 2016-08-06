# angularjs1-5-modules
AngularJS 1.5 Modules

For an introduction see 'What is AngularJS' at https://www.youtube.com/watch?v=zKkUN-mJtPQ&list=PL6n9fhu94yhWKHkcL7RJmmXyxkuFB3KSl

See also 'Modules in AngularJS' at https://www.youtube.com/watch?v=gWmOKmgnQkU&list=PL6n9fhu94yhWKHkcL7RJmmXyxkuFB3KSl&index=2

#What is a module

A module is a container for different parts of your application, i.e. controllers, services, directives, filters, etc.

You can think of a module as a Main() method in other types of applications.

#How to create a module

Use the angular object's module() method to create a module.

```javascript
var myApp = angular.module("myModule", []);
```

#What is a controller

In angular a controller is a JavaScript constructor function. The job of the controller is to build a model for the view to display.

#How to create a controller function

```javascript
var myController = function($scope) {
  $scope.message = "Angular Tutorial";
}
```

#What is a model

In AngularJS, the data that you attach to the scope is the model. Here e.g. 'message' is the model.

#How to register a controller with a module

```javascript
// Register the controller with the module
// Takes a parameters; what you want to name the controller, the controller function
myApp.controller("myController", myController);

/**
 * Alternatively, declare the controller function inside the registration
 * myApp.controller("myController", function($scope) {
 *   $scope.message = "AngularJS Tutorial";
 * });
 */
```

#How to use the module that we created to bootstrap the angular application

To bootstrap the angular application using the module, add the module name to the ng-app directive inside the html file

```javascript
<!DOCTYPE html>
<html lang="en" data-ng-app="myModule">
...
</html>
```

We can now show the property of the controller function 'message' inside a DOM element

```javascript
<!DOCTYPE html>
<html lang="en" data-ng-app="myModule">
<head>
    <meta charset="UTF-8">
    <title>My Angular App</title>
    <script src="https://ajax.googleapis.com/ajax/libs/angularjs/1.5.6/angular.min.js"></script>
    <script src="script.js"></script>
</head>
<body>
  <div data-ng-controller="myController">
      {{ message }}
  </div>
</body>
</html>
```





