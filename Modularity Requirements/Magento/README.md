# 1. Micro-Services
Microservice architecture is a design pattern that separates an application into independently deployable services. Each independent service communicates with the others through lightweight APIs or a Data layer. This service can use different programming languages different than PHP and are free from the Magento 2 best practices.

Magento 2 microservices, such as orders, product catalog, and checkout, provide an API through service. Font-end interacts with these microservice through GraphQL or REST or direct database communication and server-side rendering with HTML response.

![Micro Services](https://i.imgur.com/jmj2i81.png)

In this image, we can see Magento has
micro-services requirements as they divided the services in many micro ones which has its own responsibilities
but communicate with others to form a unified system.

# 2. Modular Structure
Magento 2 stores the source files in a very structured and sophisticated manner. It is essential for the users to understand the directory structure in Magento 2 before diving deep into the versatility of this eCommerce platform. It is also essential for the budding developers to clear the Magento 2 Folder Structure concept, as it will help them better understand how the backend works in Magento 2.

![Micro Services](https://i.imgur.com/qZrn6K4.png)

## Module-based, not file-based structure

When starting a project, the easiest way to go is Magento project structure, which somehow forces you to group your files by type: components, services, helpers with a few odd exceptions, such as the router and the store. This structure is not wrong — for small applications, it’s very easy to maintain, but for mid-size/large applications there are a few downsides:
- The source code navigation is not simple: imagine the amount of files inside the components folder, and knowing the purpose of each one — same for any other file type
- Debugging can be very time-consuming: you’d need to jump file-to-file and draw a mental map of how a simple process works to get to the root cause of a bug.

A better alternative is to structure your project using old-fashioned modules and to think of each module as a small vue-cli project, decreasing the downsides explained above, so you get something like this:


![Micro Services](https://i.imgur.com/tln2Yys.png)

# 3. Class/Components Reusability
Avoid using redundant or duplicate code, which can be hard to maintain. Instead of copying and pasting the same code throughout your extension, create a single class or method and reference it when needed.

As a general rule, reuse code as much as possible to prevent code duplication.

The code you write should be small, focused, and provide a generic solution. This will help you reuse code in future development.

Here is the example of code reusability in Magento:

https://github.com/magento/magento2/blob/2.4-develop/app/code/Magento/AdminNotification/Controller/Adminhtml/System/Message/ListAction.php  

# 4. Extensibility

## Introduction:
Product extensibility describes how easy it is to expand a product’s feature set. An extensible product has been designed from its earliest stages for customization and enhancement. Extensible products are designed for ease in expanding your installation’s feature set, enriching current features, and integrating with third-party software.

Maximizing extensibility has been our goal through all aspects of Magento development. Core tasks such as shipping are packaged as discrete modules, and you expand your features by installing modules that you either buy from third-party vendors or create yourself.

Here's the example of extensibility in magento:

https://github.com/magento/magento2/blob/2.4-develop/app/code/Magento/Backend/App/AbstractAction.php


# 5. Linters for better code quality

The first linters used to check the source code and find potential optimizations for compilers. But, over the years, many other checks and analysis would be included in the process of linting.

The usage of linters has also helped many developers to write better code for not compiled programming languages. As there is not compiling time errors, finding typos, syntax errors, uses of undeclared variables, calls to undefined or deprecated functions, for instance, helping developers to fix it faster and reduce bugs before execution.


## Performance improvements:

Every experienced developer knows not only the importance of performing software but many tricks that improve it. The problem is: what about newcomers? How can you pass this knowledge forward? Even senior programmers can miss a technique or two. So, why not let an automation software do it for you?

Did you know that in CSS, the universal selector (*) may slow down a page loading time? Or that unqualified attribute selectors have the same performance characteristics as the universal selector? Avoiding them is good practice.

Many linters include a performance check. They can add different kinds of performance improvements for experienced and newcomers developers. CSSLint is just an example.
