

# Features of Angular 6.0

1. Angular Elements
2. Service Worker Support
3. Bye, Bye Template Element
4. Ivy: New Rendering Engine
5. ngModelChange
6. ElementRef<T>
7. Bazel Compiler
8. RxJS 6.0
9. Tree Shaking

## **1. Angular Elements**

Angular is a perfect framework for developing Single Page Applications. To create a widget or component that can be included in any existing web page, was not a simple task in earlier versions of Angular. But in Angular 6, it can be done with the help of Angular Elements. Actually, Angular 6 is the first Angular release which completely supports Angular Elements. Angular Elements is the brainchild of Angular’s Rob Wormald. The Angular Elements package will give us the ability to create an Angular component and then publish that component as a web component which can be used in any HTML page (even if that page is not using the Angular framework) in other environments. It actually takes an Angular component and then wraps it within a custom element, such as a DOM element, so that we can use our favorite Angular component in other projects which do not use Angular.

## **2. Service Worker Support**

Service workers are basically scripts which run in the web browser and manage to cache an application. Service workers were first introduced in Angular 5. In Angular 6, service workers come with some bug fixes, including some new functionalities. So when we deploy the latest version of the application, we may need to deactivate or uninstall the existing service worker(s). In Angular 5, there is no straightforward option for doing this, but Angular 6 brings this functionality with the new script file named  safety-worker.js**, which is actually a part of the production bundle which helps us to unregister the existing service worker(s).

Angular 6 now supports the configuration of navigation URLs within the Service Workers. The service worker will redirect navigation requests that don’t match any source or data group to the specified index file. Now, we can mention an optional navigationUrls list in ngsw-config.json files which contain the desired URLs. If, for example, a request's URLs match any of the positive patterns and none of the navigate patterns, then it will be considered a navigation request and handled the right way by the service worker. In Angular 6, the service worker remains in the current mode unless the server is reconnected and updates the work.  


## **3. Bye, Bye Template Element**

The <template> element was depreciated one year ago when Angular 4 was launched. Now it’s time to say goodbye to <template> because it is now removed from Angular 6 framework. Instead of using <template>, we now need to use <ng-tempalate>.

## **5. Ivy: New Rendering Engine**

In Angular 6, the Angular team introduced their third rendering engine called Ivy. Ivy is the next generation Angular rendering engine. In some of the previous versions of Angular (i.e. Angular 2 to Angular 4), Angular used a view engine for rendering purposes. The introduction of this rendering engine experience increases the speed and decreases the size of the application. The Angular team expects the same type of experience with the new rendering engine.

Angular compiles our templates into equivalent TypeScript code and then that TypeScript code is compiled to JavaScript and then the result is shipped to our users. So Ivy renderer is the new rendering engine which is basically designed to support backward compatibility with existing renderers and then also focused to improve the speed of rendering and it also optimized the size of the final package. In Angular, it will not be the default renderer but we can manually enable it using the compiler options. This important feature is not completely released in Angular 6 since it is in experimental mode; except the complete version in Angular's next release.

## **6. ngModelChange**

Before Angular 6, the `ngModelChange`  event was emitted before the said form control updating. If we have an event handler for the `ngModelChange` event that checked the value through the control, the old value will be returned instead of the changed value. Now, in Angular 6, `ngModelChange` has emitted the value after the value is updated in the form control.

## **7. ElementRef<T>**

In previous versions of Angular, when we want to create the reference of an element in the template, we can use `@ViewChild` or `@ViewChildren`  or inject the host using ElementRef directly. But, the problem is that ElementRef had its `nativeElement`  property typed like any other element. But now in Angular 6, we can use type ElementRef more strictly if we want.

  

    @ViewChild('login') login: ElementRef<HTMLInputElement>;
    
    ngAfterViewInit() {
    
     this.loginInput.nativeElement.focus();
    
    }
## **8. Bazel Compiler**

Bazel Compiler is actually a build system or mechanism which is used to build nearly all software at Google. This compiler only rebuilds what is necessary to build. Since source code changes very often, it does not make any sense to rebuild the entire application for every little change. Instead of rebuilding the entire application, we build only the code which actually changes and also that code that depends on those changes. So with the help of advanced local and distributed caching, optimized dependency analysis and parallel execution, we can achieve fast and incremental builds. With Angular 6, we will have this compiler support.

## **9. RxJS 6.0**

Angular 6 now used RxJS 6 internally. So we need to update our application accordingly. These changes provide developers an increase in performance and are easier to debug AJAX call stacks and improve modularity also, making it as backward compatible as possible. But RxJS changed the way we import things.

In RxJS 5, you were probably writing:

    import { Observable } from 'rxjs/Observable';
    
    import 'rxjs/add/observable/of';
    
    import 'rxjs/add/operator/map';
    
    const squares$: Observable<number> = Observable.of(1, 2).map(n => n * n);

RxJS 5.5 introduced the pipeable operators:


    import { Observable } from 'rxjs/Observable';
    
    import { of } from 'rxjs/observable/of';
    
    import { map } from 'rxjs/operators';
    
    const squares$: Observable<number> = of(1, 2).pipe( map(n => n * n));

And RxJS 6.0 changed the imports to:

    import { Observable, of } from 'rxjs';
    
    import { map } from 'rxjs/operators';
    
    const squares$: Observable<number> = of(1, 2).pipe(map(n => n * n));
## **10. Tree Shaking**

Angular 6 moved from modules referencing services to services referencing modules to make the Angular app smaller. Tree shaking is a build optimization step which tries to ensure any unused code does not get used in our final bundle. Instead of rendering template data and passing that directly into the interpreter which knows how to do everything, the new renderer is going to generate the template instructions directly. This results in much smaller bundles and a faster startup time.

There is a new way to define an injectable service in Angular 6. With this new way, we can register a provider directly inside the `@Injectable()` decorator, using the new `providedIn`  attribute. It accepts ‘root’ as a value or any module name from our application. When we use ‘root,’ it means this injectable will be registered as a singleton object in the application and we don’t need to add it to the providers of the root modules. In the same way, if we use `provideIdIn:LoginModule`, then injectable is registered as a provider of the `LoginModules`  without adding it to the providers of the modules.

@Injectable({

 providedIn: 'root'

})

export class UserService {}

So, in the above section, we discuss most important features of the Angular 6. Apart for these, there are also several features, like:

1.  The router sometimes hits a race condition while a route is being instantiated and a new navigation request arrives. This issue has been solved in Angular 6.
2.  Avoid overriding `ngInjectableDef` in the decorator is present on the type.
3.  Angular Material Library uses Component Dev Kit (CDK) which provided 30+ UI components. CDK also allows us to build our own library of UI components using Angular Material.
4.  Angular CLI generates Angular artifacts using the technology called Schematics. If you decide to create your own template, then the Angular team has added the `ng-add`  command in Angular-CLI which let's users download and install new packages in an Angular app.
5.  If the user wants to upgrade their Angular app from Angular 5 to Angular 6, Angular team added support for `ng-update`  to its Angular-CLI which let the user update and upgrade packages.
6.  The 2.6 version of Typescript’s “`resolveModuleName`” started to require passed-in paths to be separated by '`/`' instead of being able to handle '`\`'.
7.  Improved decorator error messages.
8.  Enable size tracking of a minimal CLI render3 application.
9.  The Angular team has decided to extend the long-term support (LTE) to all major releases starting with v4.
10.  Web pack module bundlers have been updated to version 4 and have Angular CLI support.
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTYzODgxMDQ1NF19
-->