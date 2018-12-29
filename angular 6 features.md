---


---

<h1 id="features-of-angular-6.0">Features of Angular 6.0</h1>
<ol>
<li>Angular Elements</li>
<li>Service Worker Support</li>
<li>Bye, Bye Template Element</li>
<li>Ivy: New Rendering Engine</li>
<li>ngModelChange</li>
<li>ElementRef</li>
<li>Bazel Compiler</li>
<li>RxJS 6.0</li>
<li>Tree Shaking</li>
</ol>
<h2 id="angular-elements"><strong>1. Angular Elements</strong></h2>
<p>Angular is a perfect framework for developing Single Page Applications. To create a widget or component that can be included in any existing web page, was not a simple task in earlier versions of Angular. But in Angular 6, it can be done with the help of Angular Elements. Actually, Angular 6 is the first Angular release which completely supports Angular Elements. Angular Elements is the brainchild of Angular’s Rob Wormald. The Angular Elements package will give us the ability to create an Angular component and then publish that component as a web component which can be used in any HTML page (even if that page is not using the Angular framework) in other environments. It actually takes an Angular component and then wraps it within a custom element, such as a DOM element, so that we can use our favorite Angular component in other projects which do not use Angular.</p>
<h2 id="service-worker-support"><strong>2. Service Worker Support</strong></h2>
<p>Service workers are basically scripts which run in the web browser and manage to cache an application. Service workers were first introduced in Angular 5. In Angular 6, service workers come with some bug fixes, including some new functionalities. So when we deploy the latest version of the application, we may need to deactivate or uninstall the existing service worker(s). In Angular 5, there is no straightforward option for doing this, but Angular 6 brings this functionality with the new script file named  safety-worker.js**, which is actually a part of the production bundle which helps us to unregister the existing service worker(s).</p>
<p>Angular 6 now supports the configuration of navigation URLs within the Service Workers. The service worker will redirect navigation requests that don’t match any source or data group to the specified index file. Now, we can mention an optional navigationUrls list in ngsw-config.json files which contain the desired URLs. If, for example, a request’s URLs match any of the positive patterns and none of the navigate patterns, then it will be considered a navigation request and handled the right way by the service worker. In Angular 6, the service worker remains in the current mode unless the server is reconnected and updates the work.</p>
<h2 id="bye-bye-template-element"><strong>3. Bye, Bye Template Element</strong></h2>
<p>The <code>&lt;template&gt;</code> element was depreciated one year ago when Angular 4 was launched. Now it’s time to say goodbye to <code>&lt;template&gt;</code> because it is now removed from Angular 6 framework. Instead of using <code>&lt;template&gt;,</code> we now need to use <code>&lt;ng-tempalate&gt;.</code></p>
<h2 id="ivy-new-rendering-engine"><strong>5. Ivy: New Rendering Engine</strong></h2>
<p>In Angular 6, the Angular team introduced their third rendering engine called Ivy. Ivy is the next generation Angular rendering engine. In some of the previous versions of Angular (i.e. Angular 2 to Angular 4), Angular used a view engine for rendering purposes. The introduction of this rendering engine experience increases the speed and decreases the size of the application. The Angular team expects the same type of experience with the new rendering engine.</p>
<p>Angular compiles our templates into equivalent TypeScript code and then that TypeScript code is compiled to JavaScript and then the result is shipped to our users. So Ivy renderer is the new rendering engine which is basically designed to support backward compatibility with existing renderers and then also focused to improve the speed of rendering and it also optimized the size of the final package. In Angular, it will not be the default renderer but we can manually enable it using the compiler options. This important feature is not completely released in Angular 6 since it is in experimental mode; except the complete version in Angular’s next release.</p>
<h2 id="ngmodelchange"><strong>6. ngModelChange</strong></h2>
<p>Before Angular 6, the <code>ngModelChange</code>  event was emitted before the said form control updating. If we have an event handler for the <code>ngModelChange</code> event that checked the value through the control, the old value will be returned instead of the changed value. Now, in Angular 6, <code>ngModelChange</code> has emitted the value after the value is updated in the form control.</p>
<h2 id="elementreft"><strong>7. ElementRef</strong></h2>
<p>In previous versions of Angular, when we want to create the reference of an element in the template, we can use <code>@ViewChild</code> or <code>@ViewChildren</code>  or inject the host using ElementRef directly. But, the problem is that ElementRef had its <code>nativeElement</code>  property typed like any other element. But now in Angular 6, we can use type ElementRef more strictly if we want.</p>
<pre><code>@ViewChild('login') login: ElementRef&lt;HTMLInputElement&gt;;

ngAfterViewInit() {

 this.loginInput.nativeElement.focus();

}
</code></pre>
<h2 id="bazel-compiler"><strong>8. Bazel Compiler</strong></h2>
<p>Bazel Compiler is actually a build system or mechanism which is used to build nearly all software at Google. This compiler only rebuilds what is necessary to build. Since source code changes very often, it does not make any sense to rebuild the entire application for every little change. Instead of rebuilding the entire application, we build only the code which actually changes and also that code that depends on those changes. So with the help of advanced local and distributed caching, optimized dependency analysis and parallel execution, we can achieve fast and incremental builds. With Angular 6, we will have this compiler support.</p>
<h2 id="rxjs-6.0"><strong>9. RxJS 6.0</strong></h2>
<p>Angular 6 now used RxJS 6 internally. So we need to update our application accordingly. These changes provide developers an increase in performance and are easier to debug AJAX call stacks and improve modularity also, making it as backward compatible as possible. But RxJS changed the way we import things.</p>
<p>In RxJS 5, you were probably writing:</p>
<pre><code>import { Observable } from 'rxjs/Observable';

import 'rxjs/add/observable/of';

import 'rxjs/add/operator/map';

const squares$: Observable&lt;number&gt; = Observable.of(1, 2).map(n =&gt; n * n);
</code></pre>
<p>RxJS 5.5 introduced the pipeable operators:</p>
<pre><code>import { Observable } from 'rxjs/Observable';

import { of } from 'rxjs/observable/of';

import { map } from 'rxjs/operators';

const squares$: Observable&lt;number&gt; = of(1, 2).pipe( map(n =&gt; n * n));
</code></pre>
<p>And RxJS 6.0 changed the imports to:</p>
<pre><code>import { Observable, of } from 'rxjs';

import { map } from 'rxjs/operators';

const squares$: Observable&lt;number&gt; = of(1, 2).pipe(map(n =&gt; n * n));
</code></pre>
<h2 id="tree-shaking"><strong>10. Tree Shaking</strong></h2>
<p>Angular 6 moved from modules referencing services to services referencing modules to make the Angular app smaller. Tree shaking is a build optimization step which tries to ensure any unused code does not get used in our final bundle. Instead of rendering template data and passing that directly into the interpreter which knows how to do everything, the new renderer is going to generate the template instructions directly. This results in much smaller bundles and a faster startup time.</p>
<p>There is a new way to define an injectable service in Angular 6. With this new way, we can register a provider directly inside the <code>@Injectable()</code> decorator, using the new <code>providedIn</code>  attribute. It accepts ‘root’ as a value or any module name from our application. When we use ‘root,’ it means this injectable will be registered as a singleton object in the application and we don’t need to add it to the providers of the root modules. In the same way, if we use <code>provideIdIn:LoginModule</code>, then injectable is registered as a provider of the <code>LoginModules</code>  without adding it to the providers of the modules.</p>
<pre><code>@Injectable({

 providedIn: 'root'

})

export class UserService {}
</code></pre>
<p>So, in the above section, we discuss most important features of the Angular 6. Apart for these, there are also several features, like:</p>
<ol>
<li>The router sometimes hits a race condition while a route is being instantiated and a new navigation request arrives. This issue has been solved in Angular 6.</li>
<li>Avoid overriding <code>ngInjectableDef</code> in the decorator is present on the type.</li>
<li>Angular Material Library uses Component Dev Kit (CDK) which provided 30+ UI components. CDK also allows us to build our own library of UI components using Angular Material.</li>
<li>Angular CLI generates Angular artifacts using the technology called Schematics. If you decide to create your own template, then the Angular team has added the <code>ng-add</code>  command in Angular-CLI which let’s users download and install new packages in an Angular app.</li>
<li>If the user wants to upgrade their Angular app from Angular 5 to Angular 6, Angular team added support for <code>ng-update</code>  to its Angular-CLI which let the user update and upgrade packages.</li>
<li>The 2.6 version of Typescript’s “<code>resolveModuleName</code>” started to require passed-in paths to be separated by ‘<code>/</code>’ instead of being able to handle ‘<code>\</code>’.</li>
<li>Improved decorator error messages.</li>
<li>Enable size tracking of a minimal CLI render3 application.</li>
<li>The Angular team has decided to extend the long-term support (LTE) to all major releases starting with v4.</li>
<li>Web pack module bundlers have been updated to version 4 and have Angular CLI support.</li>
</ol>

