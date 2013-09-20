# ng-pdfviewer

AngularJS PDF viewer directive using pdf.js.

``` html
	<button ng-click="prevPage()">&lt;</button>
	<button ng-click="nextPage()">&gt;</button>
	<br>
	<span>{{currentPage}}/{{totalPages}}</span>
	<br>
	<pdfviewer src="test.pdf" on-page-load='pageLoaded(page,total)'></pdfviewer>
```

and in your AngularJS code:

``` js

var app = angular.module('testApp', [ 'ngPDFViewer' ]);

// ...

$scope.nextPage = function() {
	$scope.$broadcast('pdfviewer.nextPage');
};

$scope.prevPage = function() {
	$scope.$broadcast('pdfviewer.prevPage');
};

$scope.pageLoaded = function(curPage, totalPages) {
	$scope.currentPage = curPage;
	$scope.totalPages = totalPages;
};
```

## Requirements

* AngularJS (http://angularjs.org/)
* PDF.js (http://mozilla.github.io/pdf.js/)

## Usage

Include `ng-pdfviewer.js` as JavaScript file, along with `pdf.js` and `pdf.compat.js`.

Declare `ngPDFViewer` as dependency to your module.

You can now use the `pdfviewer` tag in your HTML source.

## License

MIT. See README.md for further details.

## Author

Andreas Krennmair <ak@synflood.at>