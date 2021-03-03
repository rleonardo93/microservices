# Microservices

## Definition
- Exposed by a, well defined, REST API
- Self-contained services
- Has its own database (if needed)
- No need to use a centralized Application Server
- Cloud enable (Gives the possibility to have multiple instance of each service without a lot of configuration)

## Benefits
- Possibility to use different technologies (As long as they expose a REST API)

- Dynamic Scaling
  - We may increase/reduce the number of the replicas of each service freely
  - Companies usually scale up on holiday seasons and revert it on the rest of the year

- Fast Release Scale
  - Possibility to split each service in different development teams/projects
  - Reduce the number of conflicts with each other
  
- Easier to test
  - Since each unit is in an independent deployment, we can test them with more ease
  - This includes the usage of automatic testing tools
 
## Drawbacks
- Complexity
  - Requires a good planning for new features
 
- Potentially slowe
  - More hops between services using HTTP
  - REST protocol with JSON format is higly recommended to reduce the overhead
 
- ACID pattern is lost
  - Each service runs its own transactions
  - There is a need of more compensation processes

## Motivations
- Faster developments
- Easier scalability
- Continuous delivery
- Automatic tests
- Less conflict between development teams

## Components required
- API Gateway
- Auth Service
- Service Discovery
- Config Server
- Circuit Breaker

### API Gateway
- Single entry point for communication between services and applications
- Grants security and throttling

### Auth Service
- Provides authentication and authorization of our services
  - Combined with the API Gateway
- Can be used with JWT and JWK
  - Common used on Single Page Applications
  - Can be used by other applications and between services
  - OAuth 2.0 flows wrks well with a centralized Login Gateway

### Service Discovery
- Provides the location of each srvice replicas when required
- Each service registers itself in this component when deployed

### Config Server
- Provides dynamic configuration to each service
- Can be distinct between different environments

### Circuit Breaker

