# Testing and Swagger


When consuming a web API, understanding its various methods can be challenging for a developer. Swagger, also known as OpenAPI, solves the problem of generating useful documentation and help pages for web APIs. It provides benefits such as interactive documentation, client SDK generation, and API discoverability.

In this article, the Swashbuckle.AspNetCore and NSwag .NET Swagger implementations are showcased:

Swashbuckle.AspNetCore is an open source project for generating Swagger documents for ASP.NET Core Web APIs.

NSwag is another open source project for generating Swagger documents and integrating Swagger UI or ReDoc into ASP.NET Core web APIs. Additionally, NSwag offers approaches to generate C# and TypeScript client code for your API.

What is Swagger / OpenAPI?
Swagger is a language-agnostic specification for describing REST APIs. The Swagger project was donated to the OpenAPI Initiative, where it's now referred to as OpenAPI. Both names are used interchangeably; however, OpenAPI is preferred. It allows both computers and humans to understand the capabilities of a service without any direct access to the implementation (source code, network access, documentation). One goal is to minimize the amount of work needed to connect disassociated services. Another goal is to reduce the amount of time needed to accurately document a service.

Swagger UI offers a web-based UI that provides information about the service, using the generated OpenAPI specification. Both Swashbuckle and NSwag include an embedded version of Swagger UI, so that it can be hosted in your ASP.NET Core app using a middleware registration call. 