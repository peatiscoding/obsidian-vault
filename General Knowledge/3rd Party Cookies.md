Author: Kittiphat S
Date: 16 Jan 2024

Possible Solutions
1. Using StorageAccess API [ref](https://developer.mozilla.org/en-US/docs/Web/API/Storage_Access_API)
2. Using Sender's constraint, specifically, DPoP or Demonstration Proof of Possession. [ref](https://cloudentity.com/developers/blog/mtls_vs_dpop/) and also [ref](https://www.ietf.org/proceedings/93/slides/slides-93-oauth-5.pdf)

## Using StorageAccess API

in short. The Storage access api will grant access to the 3rd party cookie just like in iOS/Android when it need permission from user. These API basically ask the user to access these 3rd party cookie via the Agents (Browser) APIs. However by the nature of this it means to access such cookie you will need:
1. Target URL (url that host store this cookie information)
2. The asynchronous UX that ensure that user accept the requirement to access the cookie first.

To implement this feature we will need:
1. Update SDK to incorporate the use of cookies.

This is (from my point of view) a standardized way to fix the problem. However the drawback of this method are:
1. increased complexity of UX which means all user must click accept the allowance to use such storage access.
2. And risk of the unsupported browsers.
3. A lot harder to support.
4. A risk of complication; `requestStorageAccess` method "REQUIRED" user interaction (human gesture of Click or Tap) Otherwise the method will be denied. This will surely post a challenge when we need a certain UX flow to be "seamless".

For better understanding and how it works for 3 major browsers please visit [document](https://developer.mozilla.org/en-US/docs/Web/API/Storage_Access_API#how_it_works)
## DPoP - Demonstration Proof of Possession

On the contrary side, we can implement the system without relying on 3rd party cookie. This will need a bit of more modification and a bit of implementation on the SDK and Service end.

1. DPoP is another layer of token that -- when the client is asking for token e.g. (silent_sso) client must send over the Client's public key. So that the access_token, and id_token that would be issued from the IdP -- is to be bound by such Client's public & private key.
2. By doing so; Server will now validate Access Token and the DPoP everytime the request coming in.
3. Even with the leak of both tokens (Access Token and DPoP) it won't be able to call with modified payload. Or even replay it as DPoP is extremely short-lived.

To implement this feature we will need:
1. Update SDK to incorporate the DPoP token upon requesting AccessToken/ID Token
2. Update SDK to incorporate a way to store the secret effectively and securely. 
3. Update SDK's invocation to add DPoP into the mix when the API need to be called. Such as Refresh, Get Source Token APIs
4. Update Backend service to validate DPoP. (Introduce new Middleware, and TokenValidator to authorizer layer.)

This method is very clean way to fix the issue as the UX will basically the same; However it need a lot of implementation as mentioned above.

Drawback is that now every API call to our IdP system will need this DPoP to be recalculated. Hence it is no longer a standard interfaces. Please see [DPoP](https://cloudentity.com/developers/blog/mtls_vs_dpop/#dpop) for details on how it works.