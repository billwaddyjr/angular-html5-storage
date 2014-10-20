# angular-html5-storage (ngHTML5Storage)

HTML5 web storage for Angular.js

## Install

    bower install angular-html5-storage --save

## Usage

create your service wrapper (optional)

    app
      .factory('myStorageService', ['ngHTML5Storage', function(ngHTML5Storage){
        return {
          saveStuffInLocalStorage: function(key, value){
            return ngHTML5Storage.local(key, value);
          },
          saveStuffInSessionStorage: function(key, value){
            return ngHTML5Storage.session(key, value);
          }
        };
      }]);

    //in your controller (be sure to inject your service)
    myStorageService.saveStuffInLocalStorage(key, value)
        .then(function(data){
            //it is saved in local storage
        });
        

using ngHTML5Storage directly (without a service wrapper)

    app
        .controller('MyController', ['ngHTML5Storage', function(ngHTML5Storage){
          ngHTML5Storage.session(key, value)
            .then(function(data){
                //it is saved in session storage
            });
        });

## Methods

* `ngHTML5Storage.local(key, value)`
* `ngHTML5Storage.session(key, value)`


## Run tests

    gulp test




MIT License
