# laravel-ajax-login
laravel ajax login row javascript

#installtion
add this command to terminal in linux or mac & cmd on windows

```
composer require 5dmatweblogin/ajaxlogin:dev-master
```

#Add provider
open config/app.php  add this line on providers array
```
AjaxLogin\AjaxLoginProvider\AjaxLoginProvider::class,
```

#Authentication scaffolding
add this line to terminal 
```
php artisan make:auth
```

#Publish Vendors
not last step to add this line
we write on login.blade.php & app.blade.php & logincontroller.php & add new file on public path 
/public/AjaxLogin/AjaxLogin.js
```
php artisan vendor:publish --tag=5dmatweb --force
```

#How to use
we set for you every thing on login file and app layout file 
this is the basic 

```
  AL = new Login({
            email:"email",
            password:"password",
            btn:"btn",
            url:"/login",
            successUrl:"/",
            mode:"toast" ///alert or toast
});

```

email => set the email id  field
password => set the password id  field
btn => set the submit button id  field
url => the login post url it set by default to /login
successUrl => the url we will redirect user after success login By default we rediret to home page
mode => the error way to show we have to mode on sample alert Or toast alert

#Methods

#Done login
we have method call doneLogin this method process after user is login you can 
add your custom logic here if you want the default action to rediret to home or if you set 
successUrl property the lib will redirect user to this url
```
AL.doneLogin = function(){
            alert('login');
        };
```
#Error login
we have method call doneLogin this method process if user have error in login like wrong login info
add your custom logic here if you want , the default action to show user error in depend on user mode
select you can run your custom error show if you want the function will return with error that laravel pass
```
  AL.errorLogin = function (error) {
            console.log(error)
        };
```




