<!DOCTYPE html>
<html lang="en">
<head>
 <meta charset="UTF-8">
 <title>AngularJS Date Display</title>
 <script 
src="https://ajax.googleapis.com/ajax/libs/angularjs/1.8.2/angular.min.js"></script>
</head>
<body ng-app="myApp">
<div ng-controller="myController">
 <h2>Date Display</h2>
 <label>Date Format:
 <select ng-model="selectedFormat" ng-change="updateDate()">
 <option value="fullDate">Full Date</option>
 <option value="shortDate">Short Date</option>
 <option value="mediumTime">Medium Time</option>
 <option value="shortTime">short Time</option>
 <option value="yyyy-MM-dd HH:mm:ss">Custom Format (yyyy-MM-dd 
HH:mm:ss)</option>
 </select>
 </label>
 <p>Selected Date Format: {{ selectedFormat }}</p>
 <p>Formatted Date: {{ formattedDate }}</p>
</div>
<script src= “P12.js”></script>
</body>
</html>
P12.js
var app = angular.module('myApp', []);
 app.controller('myController', function ($scope, $filter) {
 $scope.selectedFormat = 'fullDate'; // Default date format
 $scope.updateDate = function () {
 var currentDate = new Date();
 $scope.formattedDate = $filter('date')(currentDate, $scope.selectedFormat);
 };
 $scope.updateDate();
 });
