SwiftBites App
-----

# Project Instructions

## What am I building?

Embark on the exciting journey of building "SwiftBites", a SwiftUI-based application that harnesses the power of SwiftData to manage and organize food recipes. This project serves as a practical exploration of advanced database operations, including CRUD (Create, Read, Update, Delete) operations, model creation, queries, and establishing relationships between SwiftData models.

Imagine SwiftBites as your digital cookbook, where you can:

* Add and manage ingredients, forming the building blocks of your recipes.
* Seamlessly construct and categorize diverse food recipes into categories.
* Employ search and sorting functionalities to navigate through your recipes collection.
* Reuse ingredients across multiple recipes, showcasing the power of relational database concepts.

At the core of SwiftBites is SwiftData, Apple's latest persistence framework, ensuring that all your creations and modifications are reliably stored and accessible on your device.

By the end of this project, you'll not only have a functional and personalized recipe app at your fingertips but also a profound understanding of how to implement database operations in SwiftData. This experience will significantly enhance your skills in handling data models, queries, sorting mechanisms, and relationships, all in a robust, fun, and practical SwiftData project!

## Why am I building this?

Understanding database concepts and operations is crucial for any iOS developer. Databases are the backbone of most modern applications, offering a structured way to store, retrieve, and manipulate data.

In the world of iOS development, mastering database skills enables developers to create applications that are not only functional but also efficient and user-friendly.

Knowledge of databases, particularly in handling data persistence and ensuring seamless data flow within an app, is essential for developing robust applications. By learning SwiftData, you will  gain the ability to store data, implement search and sorting functionalities, and maintain data integrity, all of which are fundamental to creating high-quality, scalable, and reliable applications for the Apple ecosystem.

* **Model Container**: Delve into the intricacies of managing schemas and configuring model storage options. This knowledge is pivotal in understanding how data models are structured and stored within SwiftData.

* **Understanding `@Model` Macro**: Learn to define and use Swift classes as models managed by SwiftData. Master the usage of the `@Model` macro, including implementing property attributes for ensuring uniqueness and incorporating validation through the `@Attribute` macro.

* **Exploring `@Relationship` Macro**: Gain practical experience with how SwiftData models interact and relate to each other. Understand the implications of model relationships, such as the cascading effects when a model is deleted, and how to manage these relationships effectively.

* **Leveraging `@Query` Macro**: Acquire skills in crafting queries for SwiftData and integrating them seamlessly with SwiftUI. Learn about using predicates and sort descriptors to filter and organize data, enhancing the app’s data retrieval and display capabilities.

In conclusion, mastering SwiftData is a crucial skill. This project provides a hands-on approach to understanding database management, ensuring you're well-equipped to create data-centric, efficient iOS applications. It's an essential step in your journey to becoming a proficient and versatile iOS developer.

## How should I build this?

### Using the Starter Project

To jumpstart your journey with SwiftBites, we've provided a fully operational starter project. This includes mock models and a simulated storage class. Your first task is to run this starter project, familiarize yourself with its functionality, and briefly review the source code to understand the role of each view.

### Key Components of the Starter Project:

* **MainView**: Features a `TabView` hosting the various tabs of the application.
* **Recipes**:
    * `RecipesView`: Displays a list of recipes, offering navigation to the `RecipeForm` for adding or editing recipes. Includes a search bar and a sort button for searching and sorting recipes.
    * `RecipeCell`: A view representing each recipe in the list, also used in the `CategoriesView`.
    * `RecipeForm`: A versatile form used for adding, editing, or deleting a recipe.
* **Categories**:
    * `CategoriesView`: Shows categorized recipes in sections, with navigation to `RecipeForm` for recipe management.
    * `CategorySection`: A horizontal scroll view showcasing recipes within a specific category.
    * `CategoryForm`: For adding, editing, or deleting a category.
* **Ingredients**:
    * `IngredientsView`: Lists ingredients with swipe-to-delete functionality and navigation to `IngredientForm`.
    * `IngredientForm`: Used for adding, editing, or deleting an ingredient.

Feel free to customize the UI or add new features for a more personalized touch!

### Designing Your Data Models

Begin by defining your data models. Create a new Swift file and draw inspiration from the mock models provided. The objective is to replace the mock Storage class and models with actual SwiftData models, effectively transitioning the app from simulated to real data management.

### Integrating SwiftData Models into Views

With your models defined, start replacing the mock models and Storage class usage within the app. A strategic approach would be to begin with the Ingredient and Category forms, gradually progressing to integrate SwiftData models into other screens.

### Going Beyond - Adding a Shopping List Tab (Optional but Recommended)

Enhance the app by adding a fourth tab: "Shopping List." This feature should display a list of missing ingredients, assisting users with their shopping needs. Consider adding an 'available/unavailable' property to the ingredient model to track what needs to be purchased.

### Embrace the Journey

As you delve into SwiftData and iOS development with SwiftBites, remember that encountering challenges is a crucial part of learning. Each hurdle is an opportunity to deepen your understanding and refine your skills.

Utilize the resources provided to navigate through complex concepts and remember, every step, whether straightforward or complex, is progress. Keep a curious and patient mindset, and most importantly, enjoy the learning process. Your journey through SwiftBites is not just about building an app; it's about developing a skillset that will empower your future as a developer.

Happy coding!

## What are the requirements?

### Cleanup

* The `Storage` and `Mock` models code provided in the starter project should be deleted before submitting the final project.

### Setup

* A `ModelContainer` should be injected in the *App.swift* file.

### Models

* All models should be `final classes` and use the `@Model` macro. Defining models as structs is not allowed.
* The `name` property should be unique across models of the same type.
* Deleting a category should nullify its usage in recipes (e.g., if a recipe has a category and that category is removed, the recipe’s category should become nil).
* Deleting a recipe should remove all associated `RecipeIngredient` objects but not the `Ingredient` objects used in those recipe ingredients.

### CategoriesView

* Display a `ContentUnavailableView` with a button for `CategoryForm` in add mode when no category exists.
* Include a toolbar button to show `CategoryForm` in add mode when categories exist.
* Implement a search bar using a `#Predicate` to search categories by name.
* Show a `ContentUnavailableView` for search queries with no results.
* Display a list of sections, each represented by a `CategorySection`.

### CategorySection

* Display the category’s name.
* Include a button to show `CategoryForm` in edit mode.
* Show a `ContentUnavailableView` with a button for `RecipeForm` in add mode when no recipes in the category exist.
* Have a horizontal list of `RecipeCell` views; tapping a cell should open `RecipeForm` in edit mode for the selected recipe.

### CategoryForm

* Include a save button to add a new category in add mode, or save changes in edit mode.
* Feature a delete button in edit mode for category removal.
* Implement view dismissal upon saving or deleting.

### IngredientsView

* Display a `ContentUnavailableView` with a button for `IngredientForm` in add mode when no ingredient exists.
* Include a toolbar button to show `IngredientForm` in add mode when ingredients exist.
* Implement a search bar using a `#Predicate` to search ingredients by name.
* Show a `ContentUnavailableView` for search queries with no results.
* Display a list of ingredients, with tap action leading to `IngredientForm` in edit mode for the selected ingredient.
* Implement swipe-to-delete functionality for deleting ingredients.

### IngredientForm

* Include a save button to add a new ingredient in add mode, or save changes in edit mode.
* Feature a delete button (only in edit mode) for ingredient removal.
* Implement view dismissal upon saving or deleting.

### RecipesView

* Display a `ContentUnavailableView` with a button for `RecipeForm` in add mode when no recipe exists.
* Include a toolbar button to show `RecipeForm` in add mode when recipes exist.
* Implement sorting options using `SortDescriptor` for recipes, to sort by name, serving, and time.
* Implement a search bar using a `#Predicate` to search recipes by name or summary.
* Show a `ContentUnavailableView` for search queries with no results.
* Display a list of recipes, each in a `RecipeCell` view.

### RecipeCell

* Tapping the cell should open `RecipeForm` in edit mode for the selected recipe.
* Display the recipe’s information, including name, summary, image (or placeholder), and optionally: category, serving, and time.

### RecipeForm

* Include a save button to add a new recipe in add mode, or save changes in edit mode.
* Feature a delete button (only in edit mode) for recipe removal.
* Implement view dismissal upon saving or deleting.
* Enable adding/editing of recipe details: image, name, summary, category, serving, time, recipe ingredients, and instructions.
* Allow category selection, including a “none” option.
* Enable browsing and selection of ingredients, creating `RecipeIngredient` objects with quantities.
* Display all recipe ingredients with editable quantities.
* Allow deletion of `RecipeIngredient` objects without affecting the underlying `Ingredient` object.

## Resources

|Resource Description|Link|
|---|---|
|SwiftData \| Apple documentation|[https://developer.apple.com/documentation/swiftdata](https://developer.apple.com/documentation/swiftdata)|
|Meet SwiftData \| WWDC '23|[https://developer.apple.com/videos/play/wwdc2023/10187/](https://developer.apple.com/videos/play/wwdc2023/10187/)|
|Build an app with SwiftData \| WWDC '23|[https://developer.apple.com/videos/play/wwdc2023/10154/](https://developer.apple.com/videos/play/wwdc2023/10154/)|
|Model your schema with SwiftData \| WWDC '23|[https://developer.apple.com/videos/play/wwdc2023/10195/](https://developer.apple.com/videos/play/wwdc2023/10195/)|
|Dive deeper into SwiftData \| WWDC '23|[https://developer.apple.com/videos/play/wwdc2023/10196/](https://developer.apple.com/videos/play/wwdc2023/10196/)|
|SwiftData by Example|[https://www.hackingwithswift.com/quick-start/swiftdata](https://www.hackingwithswift.com/quick-start/swiftdata)|
