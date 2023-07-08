# UploadFile



<ol>

<li><h2>What is the ASP.NET Core?</h2> 
<p><a href="https://www.dotnettricks.com/training/masters-program/aspnet-core">ASP.NET Core</a> is not an upgraded version of ASP.NET. ASP.NET Core is completely rewriting that work with the .net Core framework. It is much faster, configurable, modular, scalable, extensible, and has cross-platform support. It can work with both .NET Core and .net framework via the .NET standard framework. It is best suitable for developing cloud-based such as web applications, mobile applications, and IoT applications.</p><p>ASP.NET Core was primarily designed to make the most important part of the ASP.NET components under the concept learn and the compose framework where the previous ASP.NET&nbsp; components were released under a variety of different licenses periodically, The ASP.NET Core framework is a completely open-sourced framework. Apart from the other parts of the framework of the .NET framework libraries, the ASP.NET Core is primarily designed from scratch to be the platform-agnostic that performs seamlessly. It will allow the ASP.NET Core apps to be deployed on the various platforms or the o/s such as the macOS or Linux-based servers or certain devices.</p>
</li><li>
<h2>What are the features provided by ASP.NET Core?</h2>
<p>Following are the core features that are provided by the ASP.NET Core</p>
<ul class="unorderlist">
<li><p>Built-in supports for <a href="https://www.dotnettricks.com/learn/dependencyinjection">Dependency Injection</a></p>
</li><li><p>Built-in supports for the logging framework and it can be extensible</p>
</li><li><p>Introduced a new, fast and cross-platform web server - Kestrel. So, a web application can run without IIS, Apache, and Nginx.</p>
</li><li><p>Multiple hosting ways are supported</p>
</li><li><p>It supports modularity, so the developer needs to include the module required by the application. However, the&nbsp;<a href="https://www.dotnettricks.com/learn/netcore" target="_blank" style="background-color: rgb(255, 255, 255); display: inline !important;">.NET Core&nbsp;<span style="text-align: justify; color: rgb(0, 0, 0);">framework is also providing the meta package that includes the libraries</span></a></p>
</li><li><p>Command-line supports to creating, building, and running of the application</p>
</li><li><p>There is no web.config file. We can store the custom configuration into an appsettings.json file</p>
</li><li><p>There is no Global.asax file. We can now register and use the services in the startup class</p>
</li><li><p>It has good support for asynchronous programming</p>
</li><li><p>Support WebSocket and SignalR</p>
</li><li><p>Provide protection against CSRF (Cross-Site Request Forgery)</p>
</li></ul>
</li><li>

<h2>What are the advantages of ASP.NET Core over ASP.NET?</h2>
<p>There are the following advantages of ASP.NET Core over ASP.NET :</p>
<ul class="unorderlist">
<li><p>It is cross-platform, so it can be run on Windows, Linux, and Mac.</p> 
</li><li><p>There is no dependency on framework installation because all the required dependencies are shipped with our application</p>
</li><li><p>ASP.NET Core can handle more requests than the ASP.NET</p>
</li><li><p>Multiple deployment options available withASP.NET Core</p>
</li></ul>
</li><li>

<h2>What are Metapackages?</h2>
<p>The framework .NET Core 2.0 introduced Metapackage which includes all the supported packages by ASP.NET code with their dependencies into one package. It helps us to do fast development as we don't require to include the individual ASP.NET Core packages. The assembly Microsoft.AspNetCore.All is a meta package provided by ASP.NET core.</p><p>In other words, the Metapackages of .NET Core describes the set of packages that are used together and acts as a parent of the child grouping structure. The Metapackages are referenced just like any other NuGet package naming convention such as "NETStandard.Library". An by referencing the meta-package, you have, then all its child packages will be having the reference of its dependent packages accordingly.</p>
</li><li>
<h2>Can ASP.NET Core application work with full .NET 4.x Framework?</h2>
<p>Yes. ASP.NET core application works with full .NET framework via the .NET standard library.</p>
</li> <li> 
<h2>What is the startup class in ASP.NET core?</h2>
<p>The startup class is the entry point of the ASP.NET Core application. Every .NET Core application must have this class. This class contains the application configuration related items. It is not necessary that the class name must be "Startup", it can be anything, we can configure the startup class in the Program class.</p>
<pre class="prettyprint lang-c linenums"> 
 public class Program
 {
 public static void Main(string[] args)
 {
 CreateWebHostBuilder(args).Build().Run();
 }
 
 public static IWebHostBuilder CreateWebHostBuilder(string[] args) =&gt;
 WebHost.CreateDefaultBuilder(args)
 .UseStartup&lt;TestClass&gt;();
 }
</pre>
</li><li>
<h2>What is the use of the ConfigureServices method of the startup class?</h2>
<p>This is an optional method of startup class. It can be used to configure the services that are used by the application. This method calls first when the application is requested for the first time. Using this method, we can add the services to the DI container, so services are available as a dependency in the controller constructor.</p>
</li><li>
<h2>What is the use of the Configure method of the startup class?</h2>
<p>It defines how the application will respond to each HTTP request. We can configure the request pipeline by configuring the middleware. It accepts IApplicationBuilder as a parameter and also it has two optional parameters: IHostingEnvironment and ILoggerFactory. Using this method, we can configure built-in <a href="https://www.dotnettricks.com/learn/aspnetcore/middleware-custom-pipeline" target="_blank">middleware</a> such as routing, authentication, session, etc. as well as third-party middleware.</p>
</li><li>
<h2>What is middleware?</h2>
<p>It is software that is injected into the application pipeline to handle requests and responses. They are just like chained to each other and form as a pipeline. The incoming requests are passed through this pipeline where all middleware is configured, and middleware can perform some action on the request before passing it to the next middleware. Same as for the responses, they are also passing through the middleware but in reverse order.</p>
<div class="center">
 <img src="https://dotnettrickscloud.blob.core.windows.net/img/aspnetcore/aspnet-middleware.png" alt="middleware example"></div><div class="center">While working with the ASP.NET Core framework, there are tons of built-in Middleware components available that are already made available that we can use directly that act as a plug and play components. If we don't want to use any of the in-built middleware, then we can also create our own Middleware components in asp.net core applications whenever we want. The most important point that you need to keep in mind is, that in ASP.NET Core a given Middleware component should only have a specific purpose which means it should be used for a single responsibility.</div><div class="center">
 </div>
</li><li>
<h2>What is the difference between IApplicationBuilder.Use() and IApplicationBuilder.Run()?</h2>
<p>We can use both the methods in Configure methods of the startup class. Both are used to add middleware delegates to the application request pipeline. The middleware adds using IApplicationBuilder.Use may call the next middleware in the pipeline whereas the middleware adds using IApplicationBuilder.The run method never calls the subsequent middleware. After IApplicationBuilder.Run method, system stop adding middleware in the request pipeline.</p>
</li><li>
<h2>What is the use of the "Map" extension while adding middleware to the ASP.NET Core pipeline?</h2>
<p>It is used for branching the pipeline. It branches the ASP.NET Core pipeline based on request path matching. If the request path starts with the given path, middleware on to that branch will execute.</p>
<pre class="prettyprint lang-c linenums"> 
 public void Configure(IApplicationBuilder app)
 {
 app.Map("/path1", Middleware1);
 app.Map("/path2", Middleware2);
 }
</pre>
</li><li>
<h2>What is routing in ASP.NET Core?</h2> 
<p>Routing is functionality that map incoming request to the route handler. The route can have values (extract them from the URL) that are used to process the request. Using the route, routing can find a route handler based on the URL. All the routes are registered when the application is started. There are two types of <a href="https://www.dotnettricks.com/learn/aspnetcore/routing" target="_blank">routing</a> supported by ASP.NET Core</p>
<ul class="unorderlist">
<li><p>The conventional routing</p>
</li><li><p>Attribute routing</p>
</li></ul>
<p>The Routing uses routes to map incoming requests with the route handler and Generates URL that is used in response. Mostly, the application has a single collection of routes and this collection is used for the process of the request. The RouteAsync method is used to map incoming requests (that match the URL) with available in route collection.</p>
</li><li>
<h2>How to enable Session in ASP.NET Core?</h2>
<p>The middleware for the session is provided by the package Microsoft.AspNetCore.Session. To use the session in the ASP.NET Core application, we need to add this package to the csproj file and add the Session middleware to the ASP.NET Core request pipeline.</p>
<pre class="prettyprint lang-c linenums"> 
 public class Startup
 {
 public void ConfigureServices(IServiceCollection services)
 {
 ….
 ….
 services.AddSession();
 services.AddMvc();
 }
 public void Configure(IApplicationBuilder app, IHostingEnvironment env)
 {
 ….
 ….
 app.UseSession();
 ….
 ….
 }
 }
</pre>
</li><li>
<h2>What are the various JSON files available in ASP.NET Core?</h2>
<p>There are the following JSON files in ASP.NET Core :</p>
<ul class="unorderlist">
<li><p>global.json</p>
</li><li><p>launchsettings.json</p>
</li><li><p>appsettings.json</p>
</li><li><p>bundleconfig.json</p>
</li><li><p>bower.json</p>
</li><li><p>package.json</p>
</li></ul>
</li><li>
<h2>What is tag helper in ASP.NET Core?</h2>
<p>It is a feature provided by the Razor view engine that enables us to write server-side code to create and render the HTML element in view (Razor). The tag-helper is a C# class that is used to generate the view by adding the HTML element. The functionality of the tag helper is very similar to the HTML helper of ASP.NET MVC.</p>
<pre class="prettyprint lang-html linenums"> Example:
 //HTML Helper
 @Html.TextBoxFor(model =&gt; model.FirstName, new { @class = "form-control", placeholder = "Enter Your First Name" }) 
 
 //content with tag helper
 &lt;input asp-for="FirstName" placeholder="Enter Your First Name" class="form-control" /&gt; 
 
 //Equivalent HTML
 &lt;input placeholder="Enter Your First Name" class="form-control" id="FirstName" name="FirstName" value="" type="text"&gt; 
</pre>
</li><li>
<h2>How to disable Tag Helper at the element level?</h2>
<p>We can disable Tag Helper at the element level using the opt-out character ("!"). This character must apply to open and close the Html tag.</p>
<b>Example</b> <pre class="prettyprint lang-html linenums"> &lt;!span asp-validation-for="phone" class="divPhone"&gt;&lt;/!span&gt;
</pre>
</li><li> 
<h2>What are Razor Pages in ASP.NET Core?</h2>
<p>This is a new feature introduced in ASP.NET Core 2.0. It follows a page-centric development model just like ASP.NET web forms. It supports all the features of ASP.NET Core.</p> 
<b>Example</b> <pre class="prettyprint lang-html linenums"> @page 
 &lt;h1&gt; Hello, Book Reader!&lt;/h1&gt; 
 &lt;h2&gt; This is Razor Pages &lt;/h2&gt;
</pre>
<p>The Razor pages start with the @page directive. This directive handle request directly without passing through the controller. The Razor pages may have code behind files, but it is not really a code-behind file. It is a class inherited from PageModel class.</p>
</li><li> 
<h2>How can we do the automatic model binding in Razor pages?</h2>
<p>The Razor pages provide the option to bind property automatically when posting the data using the BindProperty attribute. By default, it only binds the properties only with non-GET verbs. we need to set SupportsGet property to true to bind a property on getting a request.</p>
<b>Example</b> <pre class="prettyprint lang-c linenums"> public class Test1Model : PageModel
 {
 [BindProperty]
 public string Name { get; set; }
 }
</pre>
</li><li>
<h2>How can we inject the service dependency into the controller?</h2>
<p>There are three easy steps to add a custom service as a dependency on the controller.</p>
<p><b>Step 1:</b> Create the service</p>
<pre class="prettyprint lang-c linenums"> public interface IHelloWorldService
 {
 string SaysHello();
 }
 
 public class HelloWorldService: IHelloWorldService
 {
 public string SaysHello()
 {
 return "Hello ";
 }
 }
</pre>
<p><b>Step 2: </b>Add this service to the Service container (service can either be added by singleton, transient, or scoped)</p>
<pre class="prettyprint lang-c linenums"> public void ConfigureServices(IServiceCollection services)
 {
 ….
 …
 services.AddTransient&lt;IHelloWorldService, HelloWorldService&gt;();
 …
 …
 }
</pre>
<p><b>Step 3: </b>Use this service as a dependency in the controller</p>
<pre class="prettyprint lang-c linenums"> public class HomeController: Controller
 {
 IHelloWorldService _helloWorldService;
 public HomeController(IHelloWorldService helloWorldService)
 {
 _helloWorldService = helloWorldService;
 }
 }
</pre>
</li><li>
<h2>How to specify the service life for a registered service that is added as a dependency?</h2>
<p>ASP.NET Core allows us to specify the lifetime for registered services. The service instance gets disposed of automatically based on a specified lifetime. So, we do not care about the cleaning these dependencies, it will take care of the ASP.NET Core framework. There are three types of lifetimes.</p>
<h3>Singleton</h3>
<p>ASP.NET Core will create and share a single instance of the service through the application life. The service can be added as a singleton using the AddSingleton method of IServiceCollection. ASP.NET Core creates a service instance at the time of registration and subsequence requests use this service instance. Here, we do not require to implement the Singleton design pattern and single instance maintained by the ASP.NET Core itself.</p>
<b>Example</b> <pre class="prettyprint lang-c linenums"> services.AddSingleton&lt;IHelloWorldService, HelloWorldService&gt;();
</pre>
<h3>Transient</h3>
<p>ASP.NET Core will create and share an instance of the service every time to the application when we ask for it. The service can be added as Transient using the AddTransient method of IServiceCollection. This lifetime can be used in stateless service. It is a way to add lightweight service.</p>
<b>Example</b> <pre class="prettyprint lang-c linenums"> services.AddTransient&lt;IHelloWorldService, HelloWorldService&gt;();
</pre>
<h3>Scoped</h3>
<p>ASP.NET Core will create and share an instance of the service per request to the application. It means that a single instance of service is available per request. It will create a new instance in the new request. The service can be added as scoped using an AddScoped method of IServiceCollection. We need to take care while the service registered via Scoped in middleware and inject the service in the Invoke or InvokeAsync methods. If we inject dependency via the constructor, it behaves like a singleton object.</p>
<pre class="prettyprint lang-c linenums">services.AddScoped&lt;IHelloWorldService, HelloWorldService&gt;();
</pre>
</li> 
</ol>