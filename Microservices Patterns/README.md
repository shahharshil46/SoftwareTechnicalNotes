# Microservices Patterns by Chris Richardson.

This file summarizes my notes from the Clean Architecture book.

### Index
1. [Escaping Monolithic hell](#chapter_1)
2. [Decomposition Strategies](#chapter_2)

## <a name="chapter_1">Chapter 1 - Escaping Monolithic hell</a>
1. In the early cycles of development of the monolithic application, it is 
    1. simple to develop
    2. easy to make radical changes to the application
    3. straightforward to test
    4. straightforward to deploy
    5. easy to scale
2. As the monolithic application outgrows its architecture
    1. complexity intimidates developers
    2. development slows down
    3. Path from commit to deployment becomes long and arduous
    4. scaling becomes difficult
    5. the app gets locked into increasingly obsolete technology stack
    6. reliability reduces
3. Scale cube and Microservices
    1. Microservices
        1. MicroService is an architectural style that functionally decomposes an application into a set of services.
        1. Each service has a focused, cohesive set of responsibilities. 
        3. Here, the services communicate via API
    2. Scaling cube and Microservices

       ![scale_cube](/images/1_1_ScaleCube.png)

        1. X-Axis (a.k.a. horizontal duplication) - Scale by cloning
            1. here, you run clones of the application behind load balancer.
            2. This is a great way of improving the capacity and availability of the service.
        2. Z-Axis (a.k.a. data partitioning) - scale by splitting similar things, (such as by customer ids).
            1. Each instance in here is responsible only for a subset of the data.
            2. The router in front of the instances uses the request attribute to route it to appropriate instance.
            3. Helps to solve problems about capacity and availability.
        3. Y-Axis (a.k.a. functional decomposition) - scale by splitting things that are different.
            1. Helps to solve the problem of increasing development and application complexity.
            2. Here, we aim to divide up the service into multiple mini-services that implements narrowly focused functionality.

    3. Modularity
        1. The microservice architecture uses services as the unit of modularity.  
    4. Comparing SOA with Microservices

        | subject | SOA | Microservice |
        | :----- | :------ | :------ |
        | Inter-Service communication | smart pipes (such as Enterprise Service Bus). | Dumb pipes, REST, or gRPC etc.
        | Data | global data model and shared databases | Data model per service |
        | Typical service | Larger Monolithic application | Smaller Service |

4. Benefits and drawbacks of Microservice architecture  
    1. Benefits
        1. Enables continuous delivery, deployment for large, complex applications
            1. Reduces time to market.
            2. Improved reliability.
            3. Employee satisfaction is higher.
        2. services are small and easily maintained
        3. services are independently deployable.
        4. services are independently scalable.
        5. It enables the teams to be autonomous.
        6. It allows easy experimenting and adoption of new technologies.
        7. It has better fault isolation.
    2. Drawbacks
        1. Finding the right services is challenging.
        2. Distributed systems are complex.
        3. Deploying features spanning across multiple services requires careful coordination.
        4. Deciding when to adopt is difficult.
    
         
## <a name="chapter_2">Chapter 2 - Decomposition strategies</a>