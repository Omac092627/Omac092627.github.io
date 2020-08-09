# Claim Based Authorization 


The difference between Authentication and Authorisation
First of all, we should clarify the difference between these two dependent facets of security. The simple answer is that Authentication is the process of determining who you are, while Authorisation revolves around what you are allowed to do, i.e. permissions. Obviously before you can determine what a user is allowed to do, you need to know who they are, so when authorisation is required, you must also first authenticate the user in some way.

Claims-based authentication
The concept of claims-based authentication can be a little confusing when you first come to it, but in practice it is probably very similar to approaches you are already using. You can think of claims as being a statement about, or a property of, a particular identity. That statement consists of a name and a value. For example you could have a DateOfBirth claim, FirstName claim, EmailAddress claim or IsVIP claim. Note that these statements are about what or who the identity is, not what they can do.

The identity itself represents a single declaration that may have many claims associated with it. For example, consider a driving license. This is a single identity which contains a number of claims - FirstName, LastName, DateOfBirth, Address and which vehicles you are allowed to drive. Your passport would be a different identity with a different set of claims.

When an identity is created it may be assigned one or more claims issued by a trusted party. A claim is a name value pair that represents what the subject is, not what the subject can do. For example, you may have a driver's license, issued by a local driving license authority. Your driver's license has your date of birth on it. In this case the claim name would be DateOfBirth, the claim value would be your date of birth, for example 8th June 1970 and the issuer would be the driving license authority. Claims based authorization, at its simplest, checks the value of a claim and allows access to a resource based upon that value. For example if you want access to a night club the authorization process might be:

The door security officer would evaluate the value of your date of birth claim and whether they trust the issuer (the driving license authority) before granting you access.

An identity can contain multiple claims with multiple values and can contain multiple claims of the same type.

JWT:
JSON Web Token (JWT) is a means of representing claims to be transferred between two parties. The claims in a JWT are encoded as a JSON object that is digitally signed using JSON Web Signature (JWS) and/or encrypted using JSON Web Encryption (JWE).

In simple terms, it is just another way of encoding JSON object and use that encoded object as access tokens for authentication from the server.
-----------------------------------------------------------------------------------------------------------
Adding claims checks
Claim based authorization checks are declarative - the developer embeds them within their code, against a controller or an action within a controller, specifying claims which the current user must possess, and optionally the value the claim must hold to access the requested resource. Claims requirements are policy based, the developer must build and register a policy expressing the claims requirements.

The simplest type of claim policy looks for the presence of a claim and doesn't check the value.

First you need to build and register the policy. This takes place as part of the Authorization service configuration, which normally takes part in ConfigureServices() in your Startup.cs file.

public void ConfigureServices(IServiceCollection services)
{
    services.AddMvc();

    services.AddAuthorization(options =>
    {
        options.AddPolicy("EmployeeOnly", policy => policy.RequireClaim("EmployeeNumber"));
    });
}


In this case the EmployeeOnly policy checks for the presence of an EmployeeNumber claim on the current identity.

You then apply the policy using the Policy property on the AuthorizeAttribute attribute to specify the policy name;


[Authorize(Policy = "EmployeeOnly")]
public IActionResult VacationBalance()
{
    return View();
}


The AuthorizeAttribute attribute can be applied to an entire controller, in this instance only identities matching the policy will be allowed access to any Action on the controller.

[Authorize(Policy = "EmployeeOnly")]
public class VacationController : Controller
{
    public ActionResult VacationBalance()
    {
    }
}

If you have a controller that's protected by the AuthorizeAttribute attribute, but want to allow anonymous access to particular actions you apply the AllowAnonymousAttribute attribute.

[Authorize(Policy = "EmployeeOnly")]
public class VacationController : Controller
{
    public ActionResult VacationBalance()
    {
    }

    [AllowAnonymous]
    public ActionResult VacationPolicy()
    {
    }
}

Most claims come with a value. You can specify a list of allowed values when creating the policy. The following example would only succeed for employees whose employee number was 1, 2, 3, 4 or 5.


public void ConfigureServices(IServiceCollection services)
{
    services.AddMvc();

    services.AddAuthorization(options =>
    {
        options.AddPolicy("Founders", policy =>
                          policy.RequireClaim("EmployeeNumber", "1", "2", "3", "4", "5"));
    });
}