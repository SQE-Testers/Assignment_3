
# 1. Micro-Services
Microservices architecture is a concept of building an application based on breaking it into multiple modules. Each module has its own specific responsibilities but communicates with others to form a unified system. This approach provides freedom of development and choice of tools (technology language, framework) within each application.

## Vue StoreFront

![Micro Services](https://i0.wp.com/academiamag.com/wp-content/uploads/2021/12/Fast_university_Lahore_campus.jpg?resize=770%2C515&ssl=1)

## Micro-Services Example in Vue StoreFront Code

![GitHub picture of packages](https://drive.google.com/file/d/1_tgCuG4iQlOOrXFNrapmY9fmLGVmeEqL/view?usp=share_link)

In this image, we can see Vue StoreFront has
micro-services requirements as they divided the services in many micro ones which has its own responsibilities
but communicate with others to form a unified system.
## 2. Modular Structure
Every project has its own requirements and each team has its own way of working, so this is not THE guide on how to structure your Vue project; it’s more of a source of ideas and good practices that you can follow to improve your code maintainability:

- Source code navigation
- Testability
- Monitoring + Observability
- Debugging
- Collaboration

## Module-based, not file-based structure

When starting a new Vue project, the easiest way to go is vue-cli project structure, which somehow forces you to group your files by type: components, services, helpers with a few odd exceptions, such as the router and the store. This structure is not wrong — for small applications, it’s very easy to maintain, but for mid-size/large applications there are a few downsides:
- The source code navigation is not simple: imagine the amount of files inside the components folder, and knowing the purpose of each one — same for any other file type
- Debugging can be very time-consuming: you’d need to jump file-to-file and draw a mental map of how a simple process works to get to the root cause of a bug.

A better alternative is to structure your project using old-fashioned modules and to think of each module as a small vue-cli project, decreasing the downsides explained above, so you get something like this:


![Micro Services](https://drive.google.com/file/d/1_tgCuG4iQlOOrXFNrapmY9fmLGVmeEqL/view?usp=share_link)


## 3. Class/Components Reusability

Vue StoreFront is doing each functionality in a separate module and whenever they need that module to be there they just simply "import" that module.

- Example: ![Micro Services](https://drive.google.com/file/d/1_tgCuG4iQlOOrXFNrapmY9fmLGVmeEqL/view?usp=share_link)
All these imports are using the other modules which that file needed.

## 4. Extensibility
