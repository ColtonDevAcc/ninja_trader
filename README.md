# Usage
Usage
<br /> Run the app on your emulator or device with ```flutter run```.

# File Structure
The file structure of the app is organized by feature, with each feature having its own module. Within each feature module, we have the following subfolders based on Atomic design principles:

- Atoms: Contains the smallest UI components that are often reusable across the app.
- Molecules: Contains small UI components that are composed of one or more atoms.
- Organisms: Contains larger UI components that are composed of molecules and atoms.

<br /> The file structure looks like this example application 


```
|-- lib
|   |-- blocs
|   |   |-- authentication
|   |   |   |-- authentication_bloc.dart
|   |   |   |-- authentication_event.dart
|   |   |   |-- authentication_state.dart
|   |-- data
|   |   |-- models
|   |   |   |-- product.dart
|   |   |-- repositories
|   |   |   |-- product_repository.dart
|   |-- features
|   |   |-- authentication
|   |   |   |-- pages
|   |   |   |   |-- login_page.dart
|   |   |   |   |-- register_page.dart
|   |   |   |-- authentication_module.dart
|   |   |   |-- widgets
|   |   |   |   |-- atoms
|   |   |   |   |   |-- email_text_field.dart
|   |   |   |   |   |-- password_text_field.dart
|   |   |   |   |-- molecules
|   |   |   |   |   |-- login_form.dart
|   |   |   |   |-- organisms
|   |   |   |   |   |-- authentication_form.dart
|   |   |-- cart
|   |   |   |-- pages
|   |   |   |   |-- cart_page.dart
|   |   |   |-- cart_module.dart
|   |   |   |-- widgets
|   |   |   |   |-- atoms
|   |   |   |   |   |-- cart_item.dart
|   |   |   |   |   |-- cart_total.dart
|   |   |   |   |-- molecules
|   |   |   |   |   |-- cart_list.dart
|   |   |   |   |-- organisms
|   |   |   |   |   |-- cart_view.dart
|   |   |-- home
|   |   |   |-- pages
|   |   |   |   |-- home_page.dart
|   |   |   |-- home_module.dart
|   |   |   |-- widgets
|   |   |   |   |-- atoms
|   |   |   |   |   |-- product_card.dart
|   |   |   |   |-- molecules
|   |   |   |   |   |-- product_list.dart
|   |   |   |   |-- organisms
|   |   |   |   |   |-- product_grid.dart
|   |-- services
|   |   |-- authentication_service.dart
|   |-- utils
|   |   |-- app_constants.dart
|   |   |-- error_handler.dart
|-- main.dart
```
- `blocs`: Contains all the BLoC related files. Each BLoC has its own directory that contains the BLoC class, the events, and the states it uses.
- `data`: Contains data-related files such as models and repositories.
-  `features`: Contains all the feature-related files. Each feature has its own directory that contains the module file, the pages, and any other related files.
-  `services`: Contains all the service files, such as API clients or database services.
-  `utils`: Contains utility files, such as constants or error handlers.
-  `Within` each feature directory, there is also a widgets directory that contains atomic widgets related to that feature. These atomic widgets

# TESTS 
tests will follow the same structure as the lib folder. The tests will be located in the test folder.

# Proposal

## Proposal: Migration from auto_route to go_router

As we continue to develop complex applications in Flutter, navigation becomes a critical aspect that requires careful consideration. It is essential to choose a navigation library that provides a good user experience, is easy to maintain, and helps to increase developer productivity. In this proposal, I suggest using GoRouter over AutoRoute in Flutter applications.

- Lightweight and Fast: GoRouter is a lightweight routing library that provides fast and efficient navigation between screens. It is designed to be simple and easy to use, with minimal overhead.

- More Flexible Routing Configuration: GoRouter provides more flexibility in terms of routing configuration compared to AutoRoute. It supports dynamic routing and allows you to define multiple route patterns for a single widget.

- Better Type-Safety: GoRouter provides better type-safety compared to AutoRoute. It ensures that the type of the arguments passed to the route matches the expected type, which helps to catch errors at compile-time.

- Dependency Injection Support: GoRouter supports dependency injection, which makes it easier to pass dependencies to the screens. This helps to keep the code more organized and maintainable.

- Good Community Support: GoRouter has an active community of developers who contribute to the library and provide support to others. This ensures that the library is up-to-date and any issues are resolved quickly.

Disadvantages of AutoRoute:

- More Complex Configuration: AutoRoute has a more complex configuration compared to GoRouter. It requires more boilerplate code to set up and configure the routing, which can be time-consuming.

- Fewer Configuration Options: AutoRoute has fewer configuration options compared to GoRouter. It doesn't support dynamic routing and only allows you to define one route pattern for a widget.

- Limited Type-Safety: AutoRoute has limited type-safety compared to GoRouter. It relies on runtime checks to ensure that the type of the arguments passed to the route matches the expected type, which can lead to runtime errors.

In conclusion while both GoRouter and AutoRoute are excellent routing libraries for Flutter, GoRouter offers several advantages that make it a better choice in certain situations. It is lightweight, fast, provides more flexible routing configuration, better type-safety, and has good community support. On the other hand, AutoRoute has a more complex configuration, fewer configuration options, and limited type-safety. Therefore, I propose using GoRouter over AutoRoute for better performance, flexibility, and maintainability.

## Proposal: Migrating from SetState to BLoC for reactive app design


As developers, we all strive to create applications that are responsive, fast and scalable. One of the key aspects of achieving this is by adopting a reactive design pattern in our application. One such popular pattern is BLoC (Business Logic Component). In this proposal, I aim to outline the advantages of using BLoC over the traditional SetState reactive design pattern, and propose the migration of our application to BLoC.

Advantages of BLoC:

- Separation of concerns: BLoC allows us to separate the business logic of our application from the UI, making it easier to maintain and scale the codebase. This helps in improving the overall architecture of the application.

- Testability: Since the business logic is decoupled from the UI, it becomes easier to test the application. We can write unit tests for the BLoC components separately, ensuring that the logic is working as expected.

- Scalability: As the application grows, the number of stateful widgets increases, which can result in spaghetti code. BLoC helps in keeping the codebase organized and manageable.

- Reusability: BLoC components can be easily reused across multiple screens, making it easier to maintain the codebase.

Migrating from SetState to BLoC:

- Identify stateful widgets: The first step in migrating to BLoC is to identify the stateful widgets in our application. These widgets will have to be replaced with StreamBuilders that listen to changes in the state.

- Create BLoC classes: Next, we need to create BLoC classes for each stateful widget. These classes will contain the business logic of the widget and will be responsible for emitting streams of state changes.

- Connect UI to BLoC: Finally, we need to connect the UI to the BLoC classes using a provider. This will ensure that the UI receives the state changes from the BLoC and updates accordingly.


In conclusion, BLoC offers several advantages over the traditional SetState reactive design pattern. It helps in separating the concerns, improving testability, scalability, and reusability of our codebase. The migration to BLoC involves identifying stateful widgets, creating BLoC classes and connecting the UI to the BLoC using a provider. By adopting BLoC, we can ensure that our application is reactive, fast and scalable.

citations https://www.researchgate.net/publication/355476480_Performance_Analysis_of_BLoC_and_Provider_State_Management_Library_on_Flutte

## Proposal: Using Firebase for Feature Flagging

Feature flagging is a powerful technique used in software development to control the release of new features to a subset of users, and is an essential part of any Continuous Integration/Continuous Delivery (CI/CD) pipeline. It allows developers to easily turn features on or off, gradually roll out features, test new features with beta users, and more. In this proposal, I suggest using Firebase for feature flagging.

Benefits of using Firebase for Feature Flagging:

- Easy Integration: Firebase has a dedicated feature flagging service called Firebase Remote Config, which makes it easy to integrate feature flagging into your app.
- Real-time updates: Firebase Remote Config provides real-time updates to feature flags, which means that you can make changes on the fly without requiring users to update the app.
- Audience targeting: Firebase Remote Config allows you to target specific audiences for features, such as beta testers or specific user segments.
- Analytics Integration: Firebase Remote Config integrates seamlessly with Firebase Analytics, which allows you to measure the impact of your feature flagging on user behavior and engagement.
- Secure: Firebase Remote Config provides secure storage for your feature flags, ensuring that they cannot be tampered with by malicious actors.
- Comparison with other Feature Flagging solutions:
- There are several other feature flagging solutions available, such as LaunchDarkly and Split.io. While these solutions provide similar functionality, Firebase Remote Config offers several advantages:

Firebase Remote Config is part of the Firebase suite of products, which means that it integrates seamlessly with other Firebase products, such as Firebase Analytics and Firebase Crashlytics.
Firebase Remote Config is a cloud-hosted service, which means that you don't need to worry about maintaining your own infrastructure.
Firebase Remote Config offers a generous free tier, which allows small teams to use the service without incurring significant costs.

Using Firebase for feature flagging provides a simple, powerful, and cost-effective way to manage the release of new features in your app. Firebase Remote Config provides an easy-to-use feature flagging service with real-time updates, audience targeting, analytics integration, and secure storage. By using Firebase Remote Config, you can quickly and easily test new features with beta users, gradually roll out features, and measure the impact of your feature flagging on user behavior and engagement.

## Proposal: Using Equatable for Simplified Object Comparison in Dart and Flutter

Introduction:
When building applications in Dart and Flutter, it's common to have objects that need to be compared for equality. This process can be complicated, especially if the object contains a large number of fields. One solution to this problem is to use the Equatable library, which simplifies object comparison and reduces the likelihood of errors.

Benefits of Using Equatable:

- Simplified object comparison: Equatable allows you to compare objects by their properties rather than their references, which simplifies the comparison process and makes it less error-prone.

- Increased performance: The Equatable library uses optimized code to improve the performance of object comparison.

- Easy to implement: Equatable is easy to implement and integrate into existing codebases, with minimal changes required to existing code.

- Improved code readability: Equatable can help make your code more readable and maintainable by providing a clear and concise way to compare objects.

- Reactive in nature: Equatable is reactive in nature, which means it can be easily integrated with other reactive frameworks like BLoC, Redux, and Provider to provide a seamless user experience.

Using Equatable in your Dart and Flutter applications can simplify object comparison, improve performance, and make your code more readable and maintainable. Its reactive nature also makes it easy to integrate with other reactive frameworks. By implementing Equatable, you can save time and reduce errors in your application development process.

## Proposal: Using Theme.of Contexts versus Statically Typed Colors in Very Large Applications

In large applications, having a consistent and cohesive design system is critical to maintain a polished and professional user experience. One aspect of a design system is the color palette. There are two primary ways of managing colors in Flutter: using Theme.of contexts and statically typed colors. In this proposal, we will explore the advantages and disadvantages of each approach and recommend a best practice for managing colors in very large applications.

Background:
Flutter's Theme class provides a way to define a set of colors that can be used throughout the application. These colors can be accessed through a BuildContext using Theme.of(context). Alternatively, colors can be defined as static variables with a type, such as const Color primaryColor = Colors.blue.

Advantages of using Theme.of contexts:

- Consistency: Theme.of contexts provide a centralized location for defining a consistent color palette throughout the application. This ensures that all elements use the same colors, creating a cohesive and polished user experience.
- Scalability: As the application grows and new features are added, it can be challenging to maintain a consistent color palette with statically typed colors. Theme.of contexts make it easier to update the color palette in a single location, which saves time and reduces the risk of introducing errors.
- Flexibility: Theme.of contexts allow for dynamic theming, where the user can select a theme that changes the entire color palette of the application. This provides a high degree of flexibility and personalization, which can improve the user experience.

Disadvantages of using Theme.of contexts:

- Complexity: Theme.of contexts can be more complex to set up and manage than statically typed colors. It requires creating and maintaining a Theme object and passing it down through the widget tree using MaterialApp or Theme widgets.
- Performance: Theme.of contexts can potentially impact performance, as it requires looking up the color from a context object. This can be especially problematic if the color is used frequently throughout the application.

Advantages of using statically typed colors:

- Simplicity: Statically typed colors are easy to set up and manage. It's a simple matter of defining a variable with a type and value, and then using it throughout the application.
- Performance: Statically typed colors are faster than using Theme.of contexts because they don't require a lookup from a context object.

Disadvantages of using statically typed colors:

- Inconsistency: Statically typed colors can result in inconsistencies in the color palette if different developers use different colors or if the color values are changed without updating all instances.
- Scalability: Statically typed colors can be challenging to maintain as the application grows, especially if there are many colors to manage.
- Limited flexibility: Statically typed colors do not allow for dynamic theming or customization, which can limit the user experience.

In very large applications, I recommend using Theme.of contexts to manage colors. While it requires more setup and can potentially impact performance, the benefits of consistency, scalability, and flexibility outweigh the disadvantages. Additionally, there are techniques available to mitigate the performance impact, such as caching the theme color in a variable or using a const constructor for frequently used widgets. By using Theme.of contexts, we can ensure a consistent and cohesive design system that scales with the application and provides a high degree of flexibility for dynamic theming and customization.

## Proposal: Feature-Driven Commits in GitHub


The proposal suggests adopting feature-driven commits in GitHub. Feature-driven commits will provide a more organized and transparent approach to the development process, allowing for easier tracking of features, debugging, and code reviews. This proposal will outline the benefits of feature-driven commits and provide guidelines for implementing them in the GitHub workflow.

Benefits of Feature-Driven Commits:

- Easier to track features: With feature-driven commits, developers can track which features have been implemented and which are still in progress. This allows for better coordination between team members and project managers.

- Faster debugging: In the case of a bug, feature-driven commits allow developers to quickly identify which feature introduced the bug. This saves time and effort in identifying and resolving issues.

- Better code reviews: With feature-driven commits, code reviews become more manageable. Reviewers can focus on reviewing code for a specific feature instead of reviewing a large block of code. This makes the code review process more efficient and effective.

Guidelines for Implementing Feature-Driven Commits:

- Identify features: The first step in implementing feature-driven commits is to identify the features that will be developed. This can be done during project planning, and the features should be listed in a feature backlog or a project management tool.

- Create feature branches: For each feature, create a separate feature branch. This allows developers to work on different features in parallel without interfering with each other's work.

- Commit to feature branches: All commits related to a feature should be made to the corresponding feature branch. This ensures that all code changes related to a feature are in one place, making it easier to track and review.

- Use descriptive commit messages: Commit messages should be descriptive and include the feature name or ID. This makes it easier to identify which feature the commit belongs to.

- Merge feature branches: Once a feature is complete, merge the feature branch into the main branch. This ensures that the code changes related to a feature are incorporated into the main codebase.


Feature-driven commits can provide numerous benefits to the development process. By implementing feature-driven commits, developers can easily track features, debug issues, and conduct more effective code reviews. The guidelines outlined above can help ensure that feature-driven commits are implemented in a structured and organized manner.

## Proposal: Automating Build Process using CircleCI with QA Testing

In any software development cycle, one of the most important aspects is the build process. Building a project can take a lot of time, especially if there are multiple platforms to support. An automated build process is the best way to improve efficiency and ensure consistency in the development process. CircleCI is a continuous integration and delivery platform that can automate the build process, run tests, and deploy code to different environments.

Our development team has been manually building and testing our application, which can be time-consuming and can lead to errors. In order to improve our development process and ensure consistent builds, I propose to automate our build process using CircleCI.

Here are the steps I will take to implement this:

- Setup CircleCI:
We will start by setting up CircleCI for our project. This involves configuring CircleCI to automatically build our project when new code is pushed to our repository on Github.

- Configure Tests:
Once CircleCI is set up, we will configure our tests to run automatically when a build is triggered. We will use CircleCI’s configuration file to specify the test suite to run and how to run them.

- QA Testing:
In order to ensure our builds are of high quality, we will implement a QA process to run in CircleCI. This process will include running automated tests, manual tests, and verifying code coverage.

- Deployment:
Finally, we will configure CircleCI to deploy our application to different environments such as staging and production. We will use CircleCI’s deployment feature to automate this process.

Benefits:
By automating the build process using CircleCI, we will be able to:

- Save time: Manually building and testing applications can take hours, if not days. By automating the process, we can significantly reduce the time it takes to build and test our applications.

- Ensure Consistency: Automated builds ensure that the same steps are followed every time, reducing the risk of human error.

- Improve Quality: By adding a QA process to our builds, we can ensure that our application is of high quality before it is released.

- Faster Deployment: With CircleCI’s deployment feature, we can deploy our application faster and more efficiently.

In conclusion, automating our build process using CircleCI with QA testing will significantly improve our development process. By automating builds and tests, we can save time, ensure consistency, and improve the quality of our application. The benefits of this proposal outweigh the costs, and we believe it will result in a more efficient and effective development process.

## Proposal: Segregating Multiple Apps in the Same Repository and Reducing Overhead

As a team of 3 developers, I have encountered challenges with maintaining multiple applications in the same repository. The problem arises when we need to make changes to one application, but it affects the other applications as well. This not only creates confusion but also increases the overhead for maintaining the applications.

To solve this problem, I propose segregating the multiple applications into their own respective repositories. This will not only reduce confusion but also provide a more organized structure for development. However, segregating the applications can also create additional overhead in terms of managing multiple repositories.

To mitigate this, I propose automating the build process using CircleCI. With CircleCI, we can set up automated builds and tests for each application separately. This will reduce the manual effort required for testing and ensure that each application is independently tested and deployed.

Implementation:

- Repository Segregation:
We will start by segregating each application into their own respective repositories. This will involve creating new repositories for each application and moving the application-specific code and configurations to the respective repository.

- CircleCI Setup:
Once the repositories are created, we will set up CircleCI for each application. This will involve creating a CircleCI configuration file for each application and configuring the build and test steps. We will also configure CircleCI to automatically deploy the application after it has passed all the tests.

- Automated Testing:
With CircleCI in place, we can automate the testing process for each application. This will involve setting up unit tests, integration tests, and end-to-end tests for each application. The tests will be run automatically after every code change, ensuring that any bugs or issues are caught early in the development process.

- QA Integration:
We will integrate our QA team into the automated build process by configuring CircleCI to notify them when a build has passed all tests and is ready for QA testing. The QA team can then test the application and report any issues or bugs back to the development team.

- Deployment:
Finally, we will configure CircleCI to automatically deploy the application to the respective environments (e.g. staging, production) after it has passed all tests and QA has signed off on the build. This will ensure that the deployment process is automated and that each application is deployed to the correct environment.

Segregating multiple applications from the same repository and automating the build process using CircleCI will not only reduce confusion but also reduce the overhead for maintaining the applications. By automating the build process, we can catch bugs early in the development process and ensure that each application is independently tested and deployed. This will ultimately lead to a more organized and efficient development process.

# Lint

<br />``unawaited_futures``: Warns if a future returned by an expression is not awaited or assigned to a variable. This can lead to unexpected behavior and bugs.
<br />
<br />``always_declare_return_types``: Requires functions to have a return type specified explicitly. This makes code more readable and easier to understand.
<br />
<br />``always_require_non_null_named_parameters``: Requires named parameters that are not optional to be non-null, preventing potential null reference errors.
<br />
<br />```annotate_overrides```: Requires that methods overriding superclass methods be annotated with @override. This ensures that the intent to override a method is clear.
<br />
<br />``avoid_bool_literals_in_conditional_expressions``: Discourages the use of boolean literals in conditional expressions, such as if (condition == true) or if (condition == false), and encourages using the condition directly.
<br />
<br />``avoid_catching_errors``: Encourages catching more specific types of exceptions instead of the generic Error type. This helps catch errors more specific to the code being executed.
<br />
<br />```avoid_classes_with_only_static_members```: Discourages the creation of classes that only have static members. This is because classes with only static members are more appropriate as collections of functions, rather than as classes.
<br />
<br />```avoid_empty_else```: Discourages using empty else blocks after if statements. This can lead to confusing and hard-to-read code.
<br />
<br />```avoid_escaping_inner_quotes```: Encourages using double quotes instead of single quotes for string literals to avoid having to escape inner quotes.
<br />
<br />```avoid_field_initializers_in_const_classes```: Disallows field initializers in const classes. This is because const classes should have all of their members declared as final.
<br />
<br />```avoid_function_literals_in_foreach_calls```: Discourages using function literals in forEach calls, and instead encourages using named functions or methods.
<br />
<br />```avoid_implementing_value_types```: Discourages implementing value types, such as num or String, as they are already implemented by the language and cannot be extended or modified.
<br />
<br />```avoid_init_to_null```: Disallows initializing variables or fields to null. This is because it is often unnecessary and can be inferred by the type system.
<br />
<br />```avoid_multiple_declarations_per_line```: Discourages declaring multiple variables on the same line. This can lead to harder-to-read code and make it harder to understand which variables are being declared.
<br />
<br />```avoid_null_checks_in_equality_operators```: Discourages using null checks in equality operators, such as == or !=. This is because these operators already handle null values correctly.
<br />
<br />```avoid_positional_boolean_parameters```: Discourages using positional parameters for boolean values, and encourages using named parameters instead.
<br />
<br />```avoid_print```: Discourages using print() statements for debugging, and instead encourages using a logging framework.
<br />
<br />```avoid_private_typedef_functions```: Disallows typedefs that refer to private functions or classes. This is to ensure that typedefs are used only for public APIs.
<br />
<br />```avoid_redundant_argument_values```: Discourages using redundant values as arguments in function or method calls.
<br />
<br />```avoid_relative_lib_imports```: Discourages using relative imports for libraries in the lib directory, and instead encourages using absolute imports.
<br />
<br />```avoid_return_types_on_setters```: Disallows specifying return types for setters, as they always return void.
<br />
<br />```avoid_returning_null_for_future```: Discourages returning null for Future functions or methods, as it can lead to null reference errors.
<br />
<br />```avoid_returning_null_for_void```: Disallows returning null from a function
