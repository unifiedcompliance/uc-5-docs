---
description: Unified Compliance REST-based APIs
---

# API Gateway

The Unified Compliance 4.0 application is also an API Gateway, ie. a software platform where your organization can interact with the Unified Compliance library of data. API developers can make API calls to the gateway to retrieve and publish data.

The gateway supports RESTful APIs that:

* Are HTTP-based
* Enable stateless client-server communication
* Implement standard HTTP methods such as GET, POST, and PATCH
* Utilize an API Key for authentication

Visit the Workspace Settings page and select the API tab to generate API Key(s) for your workspace.  Then when calling the APIs, set an authorization header named "x-api-key" with a value of your API Key.

A subscription plan will also provide you with a starting amount of API tokens. Tokens are deducted each time your team makes an API call (depending on the type of call made and the content downloaded).  Need more tokens? No problem - visit the Plans page to add more tokens to your workspace!

Refer to the Unified Compliance 4.0 API documentation here for more details:  [https://uc4apidocs.unifiedcompliance.com/](https://uc4apidocs.unifiedcompliance.com/)
