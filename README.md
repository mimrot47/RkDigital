
### .NET Questions

#### **ASP.NET Core**

1. **What is dependency injection, and how is it used in ASP.NET Core?**
   - Dependency Injection (DI) is a design pattern used in ASP.NET Core to achieve Inversion of Control (IoC) between classes and their dependencies. ASP.NET Core has built-in support for DI. You can register services in `Startup.cs` using methods like `AddSingleton`, `AddScoped`, and `AddTransient`. For example, `services.AddScoped<IUserService, UserService>();` injects the `UserService` class wherever `IUserService` is required.

2. **How do you configure middleware in ASP.NET Core?**
   - Middleware components in ASP.NET Core are configured in the `Startup.Configure` method. They are executed in the order they’re added. Common middleware includes `UseRouting`, `UseAuthorization`, and `UseEndpoints`. For example:
     ```csharp
     public void Configure(IApplicationBuilder app, IHostingEnvironment env)
     {
         app.UseRouting();
         app.UseAuthentication();
         app.UseAuthorization();
         app.UseEndpoints(endpoints =>
         {
             endpoints.MapControllers();
         });
     }
     ```

3. **Can you explain the differences between ASP.NET Core and the traditional ASP.NET framework?**
   - ASP.NET Core is a cross-platform, cloud-optimized rewrite of the ASP.NET framework. Key differences include dependency injection by default, improved performance, modular middleware, and the ability to run on Linux and macOS in addition to Windows.

4. **How do you manage authentication and authorization in ASP.NET Core?**
   - ASP.NET Core uses policies, roles, and claims for authorization. Authentication can be managed using built-in libraries like `Identity` or third-party providers through OAuth. Policies are created in `ConfigureServices` with `services.AddAuthorization()`, and applied with attributes like `[Authorize]`.

#### **Entity Framework**

1. **How does Entity Framework handle database migrations?**
   - Entity Framework migrations help manage database schema changes over time. You can create migrations using the `Add-Migration` command and apply them using `Update-Database`. Migrations allow version control of database schema and avoid manual script management.

2. **What is lazy loading, and how does it work in Entity Framework?**
   - Lazy Loading defers the loading of related data until it's accessed. In EF Core, it’s enabled by virtual navigation properties and can be turned on by configuring `LazyLoadingEnabled = true` in the `DbContext`.

3. **How would you implement a many-to-many relationship in Entity Framework?**
   - In Entity Framework Core, many-to-many relationships can be established without needing a join entity by defining collections in both entities. In older versions, a joining table with two foreign keys was required.

#### **C# Fundamentals**

1. **Explain the difference between `abstract` classes and `interfaces`.**
   - Abstract classes can have both implemented and unimplemented members, whereas interfaces only define methods without implementations. An abstract class is a base class from which other classes can derive, but only single inheritance is allowed. Interfaces support multiple inheritance.

2. **What are delegates, and how are they used in C#?**
   - Delegates are types that represent references to methods. They’re used for defining callback methods and implementing event handling. For instance:
     ```csharp
     public delegate int MathOperation(int x, int y);
     ```

3. **Can you explain the concept of asynchronous programming in C#?**
   - Asynchronous programming in C# is handled using `async` and `await` keywords. It allows code to run tasks without blocking the main thread, improving performance. For example:
     ```csharp
     public async Task<string> GetDataAsync()
     {
         await Task.Delay(1000);
         return "Data";
     }
     ```

---

### Angular Questions

#### **Angular Basics**

1. **What are components, and how are they structured in an Angular application?**
   - Components are the building blocks of Angular applications. Each component has its own view and logic. A component is created with a TypeScript class, HTML template, and a CSS style. The structure includes a `@Component` decorator defining metadata, like selector and template.

2. **Can you explain the lifecycle hooks in Angular and their uses?**
   - Angular components have lifecycle hooks, such as `ngOnInit`, `ngOnDestroy`, and `ngAfterViewInit`. `ngOnInit` is the most commonly used, where initializations are performed. `ngOnDestroy` is used to clean up resources when the component is destroyed.

3. **How does Angular handle dependency injection?**
   - Angular provides a DI system that lets you inject services into components, pipes, and other services. Services are typically singleton instances and are provided using the `@Injectable` decorator.

#### **Angular Advanced**

1. **What is Angular CLI, and how does it help in developing Angular applications?**
   - The Angular CLI is a command-line interface that simplifies the development process. It can generate components, services, modules, and perform tasks like building, testing, and linting. For instance, `ng generate component my-component` creates a new component with boilerplate code.

2. **How would you manage state in an Angular application?**
   - Angular applications often use libraries like NgRx for state management, where state is stored centrally and managed through actions and reducers. This ensures consistency and simplifies debugging.

3. **Explain RxJS and how Observables work in Angular.**
   - RxJS is a library for reactive programming with Observables, allowing for asynchronous operations. Observables are streams of data that you can subscribe to and manage with operators like `map`, `filter`, and `mergeMap`.

#### **TypeScript**

1. **How is TypeScript different from JavaScript, and why is it beneficial for Angular?**
   - TypeScript is a superset of JavaScript that adds static typing, interfaces, and better tooling, making code more predictable and reducing runtime errors. Angular uses TypeScript for safer and more structured code.

2. **Can you explain decorators in TypeScript and how they are used in Angular?**
   - Decorators in TypeScript, such as `@Component` and `@Injectable`, are special functions that add metadata to classes. They are essential in Angular to define components, services, and modules.

---

### General Development and Project-Based Questions

1. **Describe a challenging project you worked on with Angular and .NET Core. How did you overcome difficulties?**
   - In projects like "Google RE Tax 2.0," I focused on tax compliance and user experience. This required close collaboration with stakeholders, implementing modular and scalable components in Angular, and creating APIs in .NET Core.

2. **As a UX Tech Lead, what practices did you follow to improve user experience?**
   - As a UX Tech Lead, I emphasized performance optimization, accessibility, and responsive design. We optimized by reducing DOM manipulation and using efficient Angular data-binding practices.

3. **What has been your experience with Docker and Kubernetes in the development process?**
   - With Docker, I containerized applications to ensure consistency across environments. Kubernetes was used to scale and manage deployments. Git was used for version control, while Postman was essential for testing APIs.


