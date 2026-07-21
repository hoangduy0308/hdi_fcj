---
title: "Blog 2"
weight: 2
chapter: false
pre: " <b> 3.2. </b> "
---

# Ways to Control Web Application Access on AWS with Amazon Cognito

While integrating authentication into the TrustBite internship project, I found that signing users in is only one part of the security problem. The system must also ensure that unauthenticated requests cannot reach protected pages, APIs, or backend services.

Amazon Cognito provides managed user directories and supports OAuth 2.0 and OpenID Connect. Depending on where authentication is enforced, it can be combined with an Application Load Balancer, Amazon API Gateway, or Amazon CloudFront and AWS Lambda. Each pattern fits a different application architecture.

---

## 1. Common OAuth 2.0 Flow

The three patterns share the same basic authentication flow:

1. A user opens the application.
2. The application redirects the user to the Cognito managed sign-in page.
3. Cognito authenticates the user and returns an authorization result.
4. The client receives a session or token, depending on the architecture.
5. The service protecting the backend validates that session or token before forwarding the request.

This approach lets Cognito manage identities while the application focuses on business logic.

---

## 2. Pattern 1: Application Load Balancer with Amazon Cognito

An Application Load Balancer can authenticate users before requests reach a web application. When an unauthenticated request arrives, the ALB redirects the browser to Cognito. After sign-in, the ALB establishes a session and forwards authenticated requests to the target group.

### Advantages

* Authentication is handled before traffic reaches the application.
* The backend does not need to implement the complete sign-in flow.
* It is straightforward for server-rendered or traditional browser applications behind an ALB.

### Limitations

* The pattern relies on browser sessions and cookies.
* It is less suitable for native mobile clients and API-first systems.
* Authentication is closely tied to traffic passing through that load balancer.

---

## 3. Pattern 2: Amazon API Gateway with Amazon Cognito

For REST or HTTP APIs, the client signs in through Cognito and sends a JWT in the `Authorization` header. API Gateway validates the token before invoking the backend integration. Invalid or expired tokens are rejected at the gateway.

### Advantages

* It fits web, mobile, and machine-to-machine API architectures.
* Unauthorized traffic is blocked before it reaches the backend.
* Backend services can remain focused on authorization rules and business logic.
* The pattern scales naturally when an application is divided into multiple APIs or services.

### Limitations

* The client must securely store and refresh tokens.
* Scopes, claims, CORS, and authorizer settings require careful configuration.
* API Gateway introduces an additional managed-service cost.

---

## 4. Pattern 3: CloudFront with AWS Lambda

For globally distributed applications, CloudFront can receive requests at the edge while a Lambda@Edge function checks authentication before protected content is returned. Valid requests continue to the origin, such as an ALB or an S3-backed web application. The origin can also require a secret header so users cannot bypass CloudFront and access it directly.

### Advantages

* Authentication can be enforced close to users at the edge.
* It combines access control with caching and global content delivery.
* The origin can be isolated from direct public access.

### Limitations

* The implementation and troubleshooting process are more complex.
* Lambda@Edge functions must follow regional and runtime restrictions.
* Token validation, cookie handling, cache behavior, and redirects must be designed together.

---

## 5. Comparing the Patterns

| Pattern | Best suited for | Authentication state | Main trade-off |
| --- | --- | --- | --- |
| **ALB + Cognito** | Traditional web applications | ALB-managed browser session | Simple, but coupled to the ALB and cookies |
| **API Gateway + Cognito** | Web/mobile clients calling APIs | OAuth access token or JWT | Flexible and scalable, but clients manage tokens |
| **CloudFront + Lambda** | Global applications and protected edge content | Token or secure cookie validated at the edge | Strong control, with higher implementation complexity |

For TrustBite, the mobile application and admin portal primarily communicate with APIs. Therefore, JWT validation through API Gateway or the backend middleware is the most natural starting point. ALB authentication remains useful for a browser-only internal portal, while the CloudFront pattern becomes attractive when global delivery and origin protection are higher priorities.

---

## Conclusion

Amazon Cognito can support several access-control architectures rather than forcing every application into one model. The right choice depends on the client type, backend design, session strategy, scale, and operational complexity the team is prepared to manage.

For an API-first system, API Gateway with Cognito provides a clean separation between authentication and business services. For a traditional website, ALB authentication can reduce backend work. For a global platform, CloudFront with edge validation offers stronger origin protection and distribution capabilities.

---

## Further Reading

Published post on AWS Study Group:
[Ways to Control Web Application Access on AWS with Amazon Cognito](https://www.facebook.com/groups/awsstudygroupfcj/permalink/2208350789929881/)
