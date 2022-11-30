
# 1. Micro-Services
Microservice architecture is a design pattern that separates an application into independently deployable services. Each independent service communicates with the others through lightweight APIs or a Data layer. This service can use different programming languages different than PHP and are free from the Magento 2 best practices.

Magento 2 microservices, such as orders, product catalog, and checkout, provide an API through service. Font-end interacts with these microservice through GraphQL or REST or direct database communication and server-side rendering with HTML response.

![Micro Services](https://i.imgur.com/jmj2i81.png)

In this image, we can see Magento has
micro-services requirements as they divided the services in many micro ones which has its own responsibilities
but communicate with others to form a unified system.