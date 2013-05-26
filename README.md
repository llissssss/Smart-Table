# Smart Table— an easy to use table/grid 

This project is a lightweight table/grid builder. It is meant to be easy configurable but also easy customisable
(if you want to use it as a base for your own grid development). In The current version (0.1.0) the features are

* table markup: it is a table and follows the semantic of an HTML table.
* manage your layout: you can choose the number of columns and how the should be mapped to your data model
* format data: you can choose how the data are formatted within a given column:
    * by giving your own format function
    * using one of the built-in angular filters
* Sort data
    * using your own algorithm
    * using the 'orderBy' angular algorithm: in this case you'll be able to provide predicates as explained in [orderBy filter documentation](http://docs.angularjs.org/api/ng.filter:orderBy)
* Filter data
    * using a global search input box
    * using the controller API to filter according to a particular column
* Select data row(s) according to different modes:
    * single: one row selected at the time
    * multiple: many row selected at the time. In this case you can also add a selection column with checkboxes
* Simple style: you can easily give class name to all the cells of a given column and to the header as well
* template cell:
    * you can provide template for a given column header (it will be compiled so that you can attach directves to it)
    * same for the data cells
* Edit cells: you can make cells editable and specify a type for the input so that validation rules, etc will be applied
* Client side pagination : you can choose the number of rows you want to display and use the [angular-ui.bootstrap](http://angular-ui.github.io/bootstrap/) pagination directive to navigate.
* All the directives of the table use the table controller API. It means that you can easily change the templates and directives but still using the API to perform any operation

You'll find running examples and more documentation at [the demo website](http://lorenzofox3.github.io/smart-table-website/)

## How to use Smart-Table

* You can clone the repository: the source code will be under smart-table-module directory.
* You can add the Smart-Table.debug.js file to your application and then add the module 'SmartTable.Table' to your own app module.
Note that for the moment the build does not inject the templates in the TemplateCache, so you'll also have to add the template files that you can
find in the smart-table-module/partials directory (if you use another directories layout don't forget to change the paths in the source code)

### Running the app during development

Follow the steps:

1. clone this repository
2. install node.js and run `scripts/web-server.js`
3. you'll find a running example app at http://localhost:<port>/example-app/index.html after you have started the web-server

### Running unit tests

Tests can be run with [Testacular](http://karma-runner.github.io/0.8/index.html): you'll find the config file under config folder. Note, the coverage is done by [Istanbul.js](http://gotwarlost.github.io/istanbul/)

### End to end testing

Angular ships with a baked-in end-to-end test runner that understands angular, your app and allows
you to write your tests with jasmine-like BDD syntax.

Requires a webserver, node.js + `./scripts/web-server.js` or your backend server that hosts the angular static files.


## Directory Layout

    config/testacular.conf.js        --> config file for running unit tests with Testacular
    config/testacular-e2e.conf.js    --> config file for running e2e tests with Testacular
    example-app/                --> a runing example app
      css/                      --> css files
        app.css                 --> default stylesheet
        bootstrap.css           --> twitter bootstrap style sheet
      img/                      --> image files
      js/                       --> javascript files
        app.js                  --> application and main controller
        Smart-Table.debug.js    --> the souce code (js) of the smart table module
      lib/                      --> angular and 3rd party javascript libraries
        angular/
          angular.min.js        --> the latest minified angular js
      partials/                 --> smart table view partials (templates of all the smart-table directives)
        defaultCell.html
        defaultHeader.html
        editableCell.html
        globalSearch.html
        pagination.html
        selectAllCheckBox.html
        selectionCheckBox.html
        smartTable.html
      index.html                --> app layout file (the main html template file of the app)
    smart-table-module/          --> The smart table source code
      js/                       --> javascript files
        Column.js               --> Column module
        Directives.js           --> all the directives used in the smart table (except for the pagination bootstrap)
        Filters.js              --> the Filters used by smart table (format the data)
        Table.js                --> The controller that offers a global API to all the children directives
        ui-bootstrap-custom..js --> the source code of the pagination directive (form angular-ui.bootsrap project)
        Utilities.js            --> some helper to manipulate arrays
      partials/                 --> smart table view partials (templates of all the smart-table directives)
        defaultCell.html
        defaultHeader.html
        editableCell.html
        globalSearch.html
        pagination.html
        selectAllCheckBox.html
        selectionCheckBox.html
        smartTable.html
    scripts/            --> handy shell/js/ruby scripts
      e2e-test.sh       --> runs end-to-end tests with Testacular (*nix)
      e2e-test.bat      --> runs end-to-end tests with Testacular (windows)
      test.bat          --> autotests unit tests with Testacular (windows)
      test.sh           --> autotests unit tests with Testacular (*nix)
      web-server.js     --> simple development webserver based on node.js
    test/               --> test source files and libraries
      e2e/              -->
        runner.html     --> end-to-end test runner (open in your browser to run)
        scenarios.js    --> end-to-end specs
      lib/
        angular/                --> angular testing libraries
          angular-mocks.js      --> mocks that replace certain angular services in tests
          angular-scenario.js   --> angular's scenario (end-to-end) test runner library
          version.txt           --> version file
      unit/                     --> unit level specs/tests
        ColumnSoec.js           --> specs for column module
        DirectivesSpec.js       --> specs for all directives
        FiltersSpec.js          --> specs for format filter
        TableSpec.js            --> specs for table controller
        UtilitiesSpec.js        --> specs for utilities service
        
## License

Smart Table module is under MIT license:

> Copyright (C) 2011-2013 Laurent Renard.
>
> Permission is hereby granted, free of charge, to any person
> obtaining a copy of this software and associated documentation files
> (the "Software"), to deal in the Software without restriction,
> including without limitation the rights to use, copy, modify, merge,
> publish, distribute, sublicense, and/or sell copies of the Software,
> and to permit persons to whom the Software is furnished to do so,
> subject to the following conditions:
>
> The above copyright notice and this permission notice shall be
> included in all copies or substantial portions of the Software.
>
> THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
> EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
> MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND
> NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS
> BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN
> ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN
> CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
> SOFTWARE.

## Contact

For more information on Smart Table, please contact the author at laurent34azerty@gmail.com
