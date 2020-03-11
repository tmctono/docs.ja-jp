---
title: .NET マイクロサービスと Web アプリケーションでの承認について
description: .NET マイクロサービスと Web アプリケーションのセキュリティ - ASP.NET Core アプリケーションの主な承認オプション (ロールベースとポリシーベース) の概要について説明します。
author: mjrousos
ms.date: 01/30/2020
ms.openlocfilehash: f6b69faceac9a9b4819212cc04f89080f3ddad56
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/20/2020
ms.locfileid: "77501764"
---
# <a name="about-authorization-in-net-microservices-and-web-applications"></a><span data-ttu-id="cd94b-103">.NET マイクロサービスと Web アプリケーションでの承認について</span><span class="sxs-lookup"><span data-stu-id="cd94b-103">About authorization in .NET microservices and web applications</span></span>

<span data-ttu-id="cd94b-104">認証の後に、ASP.NET Core Web API がアクセスを承認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd94b-104">After authentication, ASP.NET Core Web APIs need to authorize access.</span></span> <span data-ttu-id="cd94b-105">このプロセスによって、サービスが一部の認証ユーザーに API を提供できますが、すべてのユーザーではありません。</span><span class="sxs-lookup"><span data-stu-id="cd94b-105">This process allows a service to make APIs available to some authenticated users, but not to all.</span></span> <span data-ttu-id="cd94b-106">[承認](/aspnet/core/security/authorization/introduction)は、ユーザーのロールまたはカスタム ポリシーに基づいて行われ、要求またはその他のヒューリスティックの調査が含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="cd94b-106">[Authorization](/aspnet/core/security/authorization/introduction) can be done based on users’ roles or based on custom policy, which might include inspecting claims or other heuristics.</span></span>

<span data-ttu-id="cd94b-107">次の例に示すように、ASP.NET Core MVC ルートへのアクセス制限は、アクション メソッド (またはすべてのコントローラーのアクションで承認が必要な場合は、コントローラーのクラス) に Authorize 属性を適用するのと同じくらい簡単です。</span><span class="sxs-lookup"><span data-stu-id="cd94b-107">Restricting access to an ASP.NET Core MVC route is as easy as applying an Authorize attribute to the action method (or to the controller’s class if all the controller’s actions require authorization), as shown in following example:</span></span>

```csharp
public class AccountController : Controller
{
    public ActionResult Login()
    {
    }

    [Authorize]
    public ActionResult Logout()
    {
    }
}
```

<span data-ttu-id="cd94b-108">既定では、パラメーターなしの Authorize 属性を追加すると、そのコントローラーまたはアクションの認証されたユーザーへのアクセスが制限されます。</span><span class="sxs-lookup"><span data-stu-id="cd94b-108">By default, adding an Authorize attribute without parameters will limit access to authenticated users for that controller or action.</span></span> <span data-ttu-id="cd94b-109">特定のユーザーだけに利用できる API をさらに制限するには、ユーザーが満たす必要がある必要なロールまたはポリシーを指定するように属性を拡張することができます。</span><span class="sxs-lookup"><span data-stu-id="cd94b-109">To further restrict an API to be available for only specific users, the attribute can be expanded to specify required roles or policies that users must satisfy.</span></span>

## <a name="implement-role-based-authorization"></a><span data-ttu-id="cd94b-110">ロールベースの承認を実装する</span><span class="sxs-lookup"><span data-stu-id="cd94b-110">Implement role-based authorization</span></span>

<span data-ttu-id="cd94b-111">ASP.NET Core ID には、ロールの概念が組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="cd94b-111">ASP.NET Core Identity has a built-in concept of roles.</span></span> <span data-ttu-id="cd94b-112">ユーザーに加えて、ASP.NET Core ID は、アプリケーションによって使用されるさまざまなロールに関する情報を格納し、どのユーザーがどのロールに割り当てられているかを追跡します。</span><span class="sxs-lookup"><span data-stu-id="cd94b-112">In addition to users, ASP.NET Core Identity stores information about different roles used by the application and keeps track of which users are assigned to which roles.</span></span> <span data-ttu-id="cd94b-113">このような割り当ては、永続化されたストレージ内のロールを更新する `RoleManager` の種類と、ユーザーのロールの付与または取り消しを行う `UserManager` の種類を使用してプログラムで変更できます。</span><span class="sxs-lookup"><span data-stu-id="cd94b-113">These assignments can be changed programmatically with the `RoleManager` type that updates roles in persisted storage, and the `UserManager` type that can grant or revoke roles from users.</span></span>

<span data-ttu-id="cd94b-114">JWT ベアラー トークンによる認証を行う場合、ASP.NET Core JWT ベアラー認証ミドルウェアは、トークンで見つかったロール要求に基づいてユーザーのロールを入力します。</span><span class="sxs-lookup"><span data-stu-id="cd94b-114">If you're authenticating with JWT bearer tokens, the ASP.NET Core JWT bearer authentication middleware will populate a user’s roles based on role claims found in the token.</span></span> <span data-ttu-id="cd94b-115">MVC アクションまたはコントローラーへのアクセスを特定のロールのユーザーに制限するために、次のコード フラグメントに示すように、Authorize 注釈 (属性) に Roles パラメーターを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="cd94b-115">To limit access to an MVC action or controller to users in specific roles, you can include a Roles parameter in the Authorize annotation (attribute), as shown in the following code fragment:</span></span>

```csharp
[Authorize(Roles = "Administrator, PowerUser")]
public class ControlPanelController : Controller
{
    public ActionResult SetTime()
    {
    }

    [Authorize(Roles = "Administrator")]
    public ActionResult ShutDown()
    {
    }
}
```

<span data-ttu-id="cd94b-116">この例では、Administrator または PowerUser ロールのユーザーのみが、ControlPanel コントローラーの API (SetTime アクションの実行など) にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="cd94b-116">In this example, only users in the Administrator or PowerUser roles can access APIs in the ControlPanel controller (such as executing the SetTime action).</span></span> <span data-ttu-id="cd94b-117">ShutDown API は、Administrator ロールのユーザーのみにアクセスを許可するようにさらに制限します。</span><span class="sxs-lookup"><span data-stu-id="cd94b-117">The ShutDown API is further restricted to allow access only to users in the Administrator role.</span></span>

<span data-ttu-id="cd94b-118">ユーザーに複数のロールが割り当てられていることを必須にするには、次の例で示すように、複数の Authorize 属性を使用します。</span><span class="sxs-lookup"><span data-stu-id="cd94b-118">To require a user be in multiple roles, you use multiple Authorize attributes, as shown in the following example:</span></span>

```csharp
[Authorize(Roles = "Administrator, PowerUser")]
[Authorize(Roles = "RemoteEmployee ")]
[Authorize(Policy = "CustomPolicy")]
public ActionResult API1 ()
{
}
```

<span data-ttu-id="cd94b-119">この例では、API1 を呼び出すために、ユーザーは次の条件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd94b-119">In this example, to call API1, a user must:</span></span>

- <span data-ttu-id="cd94b-120">Administrator "*または*" PowerUser ロールであり、"*かつ*"</span><span class="sxs-lookup"><span data-stu-id="cd94b-120">Be in the Administrator *or* PowerUser role, *and*</span></span>

- <span data-ttu-id="cd94b-121">RemoteEmployee ロールであり、*かつ*</span><span class="sxs-lookup"><span data-stu-id="cd94b-121">Be in the RemoteEmployee role, *and*</span></span>

- <span data-ttu-id="cd94b-122">CustomPolicy 承認のためのカスタム ハンドラーを満たしている。</span><span class="sxs-lookup"><span data-stu-id="cd94b-122">Satisfy a custom handler for CustomPolicy authorization.</span></span>

## <a name="implement-policy-based-authorization"></a><span data-ttu-id="cd94b-123">ポリシーベースの承認を実装する</span><span class="sxs-lookup"><span data-stu-id="cd94b-123">Implement policy-based authorization</span></span>

<span data-ttu-id="cd94b-124">カスタム承認規則も[承認ポリシー](https://docs.asp.net/en/latest/security/authorization/policies.html)を使用して記述できます。</span><span class="sxs-lookup"><span data-stu-id="cd94b-124">Custom authorization rules can also be written using [authorization policies](https://docs.asp.net/en/latest/security/authorization/policies.html).</span></span> <span data-ttu-id="cd94b-125">ここでは、概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="cd94b-125">This section provides an overview.</span></span> <span data-ttu-id="cd94b-126">詳細については、[ASP.NET Authorization Workshop](https://github.com/blowdart/AspNetAuthorizationWorkshop) に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd94b-126">For more information, see the [ASP.NET Authorization Workshop](https://github.com/blowdart/AspNetAuthorizationWorkshop).</span></span>

<span data-ttu-id="cd94b-127">カスタム承認ポリシーは、service.AddAuthorization メソッドを使用して、Startup.ConfigureServices メソッドに登録されます。</span><span class="sxs-lookup"><span data-stu-id="cd94b-127">Custom authorization policies are registered in the Startup.ConfigureServices method using the service.AddAuthorization method.</span></span> <span data-ttu-id="cd94b-128">このメソッドは、AuthorizationOptions 引数を構成するデリゲートを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="cd94b-128">This method takes a delegate that configures an AuthorizationOptions argument.</span></span>

```csharp
services.AddAuthorization(options =>
{
    options.AddPolicy("AdministratorsOnly", policy =>
        policy.RequireRole("Administrator"));

    options.AddPolicy("EmployeesOnly", policy =>
        policy.RequireClaim("EmployeeNumber"));

    options.AddPolicy("Over21", policy =>
        policy.Requirements.Add(new MinimumAgeRequirement(21)));
});
```

<span data-ttu-id="cd94b-129">例に示すように、ポリシーをさまざまな種類の要件に関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="cd94b-129">As shown in the example, policies can be associated with different types of requirements.</span></span> <span data-ttu-id="cd94b-130">ポリシーが登録された後に、ポリシーの名前を Authorize 属性の Policy 引数として渡すことで、アクションまたはコントローラーにポリシーを適用できます (たとえば、`[Authorize(Policy="EmployeesOnly")]`)。ポリシーは、これらの例に示すように 1 つだけでなく複数の要件を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="cd94b-130">After the policies are registered, they can be applied to an action or controller by passing the policy’s name as the Policy argument of the Authorize attribute (for example, `[Authorize(Policy="EmployeesOnly")]`) Policies can have multiple requirements, not just one (as shown in these examples).</span></span>

<span data-ttu-id="cd94b-131">前の例では、AddPolicy の最初の呼び出しは、ロールによる承認の代替の方法です。</span><span class="sxs-lookup"><span data-stu-id="cd94b-131">In the previous example, the first AddPolicy call is just an alternative way of authorizing by role.</span></span> <span data-ttu-id="cd94b-132">`[Authorize(Policy="AdministratorsOnly")]` が API に適用される場合、Administrator ロールのユーザーのみがアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="cd94b-132">If `[Authorize(Policy="AdministratorsOnly")]` is applied to an API, only users in the Administrator role will be able to access it.</span></span>

<span data-ttu-id="cd94b-133">2 番目の <xref:Microsoft.AspNetCore.Authorization.AuthorizationOptions.AddPolicy%2A> の呼び出しは、特定の要求をユーザーに提示することをユーザーに義務付けるための簡単な方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="cd94b-133">The second <xref:Microsoft.AspNetCore.Authorization.AuthorizationOptions.AddPolicy%2A> call demonstrates an easy way to require that a particular claim should be present for the user.</span></span> <span data-ttu-id="cd94b-134"><xref:Microsoft.AspNetCore.Authorization.AuthorizationPolicyBuilder.RequireClaim%2A> メソッドは、また、必要に応じて、要求の予期される値を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="cd94b-134">The <xref:Microsoft.AspNetCore.Authorization.AuthorizationPolicyBuilder.RequireClaim%2A> method also optionally takes expected values for the claim.</span></span> <span data-ttu-id="cd94b-135">値を指定する場合、ユーザーが正しい種類の要求と、指定された値のいずれかの両方を持っている場合にのみこの要件を満たします。</span><span class="sxs-lookup"><span data-stu-id="cd94b-135">If values are specified, the requirement is met only if the user has both a claim of the correct type and one of the specified values.</span></span> <span data-ttu-id="cd94b-136">JWT ベアラー認証ミドルウェアを使用している場合、すべての JWT プロパティはユーザーの要求として使用可能になります。</span><span class="sxs-lookup"><span data-stu-id="cd94b-136">If you're using the JWT bearer authentication middleware, all JWT properties will be available as user claims.</span></span>

<span data-ttu-id="cd94b-137">ここで示す最も注目すべきポリシーは、カスタム承認要件を使用している 3 番目の `AddPolicy` メソッドです。</span><span class="sxs-lookup"><span data-stu-id="cd94b-137">The most interesting policy shown here is in the third `AddPolicy` method, because it uses a custom authorization requirement.</span></span> <span data-ttu-id="cd94b-138">カスタム承認要件を使用すると、承認を実行する方法を細かく制御することができます。</span><span class="sxs-lookup"><span data-stu-id="cd94b-138">By using custom authorization requirements, you can have a great deal of control over how authorization is performed.</span></span> <span data-ttu-id="cd94b-139">これを機能させるには、次の種類を実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd94b-139">For this to work, you must implement these types:</span></span>

- <span data-ttu-id="cd94b-140"><xref:Microsoft.AspNetCore.Authorization.IAuthorizationRequirement> から派生し、要件の詳細を指定するフィールドを格納している要件の種類。</span><span class="sxs-lookup"><span data-stu-id="cd94b-140">A Requirements type that derives from <xref:Microsoft.AspNetCore.Authorization.IAuthorizationRequirement> and that contains fields specifying the details of the requirement.</span></span> <span data-ttu-id="cd94b-141">例では、これはサンプル `MinimumAgeRequirement` の種類の年齢フィールドです。</span><span class="sxs-lookup"><span data-stu-id="cd94b-141">In the example, this is an age field for the sample `MinimumAgeRequirement` type.</span></span>

- <span data-ttu-id="cd94b-142"><xref:Microsoft.AspNetCore.Authorization.AuthorizationHandler%601> を実装するハンドラー。T は、ハンドラーが満たすことができる <xref:Microsoft.AspNetCore.Authorization.IAuthorizationRequirement> の種類です。</span><span class="sxs-lookup"><span data-stu-id="cd94b-142">A handler that implements <xref:Microsoft.AspNetCore.Authorization.AuthorizationHandler%601>, where T is the type of <xref:Microsoft.AspNetCore.Authorization.IAuthorizationRequirement> that the handler can satisfy.</span></span> <span data-ttu-id="cd94b-143">このハンドラーは、ユーザーに関する情報を格納している指定されたコンテキストが要件を満たすかどうかをチェックする <xref:Microsoft.AspNetCore.Authorization.AuthorizationHandler%601.HandleRequirementAsync%2A> メソッドを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd94b-143">The handler must implement the <xref:Microsoft.AspNetCore.Authorization.AuthorizationHandler%601.HandleRequirementAsync%2A> method, which checks whether a specified context that contains information about the user satisfies the requirement.</span></span>

<span data-ttu-id="cd94b-144">ユーザーが要件を満たす場合、`context.Succeed` への呼び出しが、ユーザーを承認されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="cd94b-144">If the user meets the requirement, a call to `context.Succeed` will indicate that the user is authorized.</span></span> <span data-ttu-id="cd94b-145">ユーザーが承認要件を満たす方法が複数ある場合、複数のハンドラーを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="cd94b-145">If there are multiple ways that a user might satisfy an authorization requirement, multiple handlers can be created.</span></span>

<span data-ttu-id="cd94b-146">カスタム ポリシーの要件の `AddPolicy` 呼び出しへの登録に加えて、依存関係の挿入 (`services.AddTransient<IAuthorizationHandler, MinimumAgeHandler>()`) を使用してカスタム要件ハンドラーも登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd94b-146">In addition to registering custom policy requirements with `AddPolicy` calls, you also need to register custom requirement handlers via Dependency Injection (`services.AddTransient<IAuthorizationHandler, MinimumAgeHandler>()`).</span></span>

<span data-ttu-id="cd94b-147">カスタム承認要件およびユーザーの年齢 (`DateOfBirth` 要求に基づく) をチェックするハンドラーの例については、ASP.NET Core [承認ドキュメント](https://docs.asp.net/en/latest/security/authorization/policies.html)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd94b-147">An example of a custom authorization requirement and handler for checking a user’s age (based on a `DateOfBirth` claim) is available in the ASP.NET Core [authorization documentation](https://docs.asp.net/en/latest/security/authorization/policies.html).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="cd94b-148">その他の技術情報</span><span class="sxs-lookup"><span data-stu-id="cd94b-148">Additional resources</span></span>

- <span data-ttu-id="cd94b-149">**ASP.NET Core の認証** </span><span class="sxs-lookup"><span data-stu-id="cd94b-149">**ASP.NET Core Authentication** </span></span>\
  [https://docs.microsoft.com/aspnet/core/security/authentication/identity](/aspnet/core/security/authentication/identity)

- <span data-ttu-id="cd94b-150">**ASP.NET Core の承認** </span><span class="sxs-lookup"><span data-stu-id="cd94b-150">**ASP.NET Core Authorization** </span></span>\
  [https://docs.microsoft.com/aspnet/core/security/authorization/introduction](/aspnet/core/security/authorization/introduction)

- <span data-ttu-id="cd94b-151">**ロールベースの承認** </span><span class="sxs-lookup"><span data-stu-id="cd94b-151">**Role-based Authorization** </span></span>\
  [https://docs.microsoft.com/aspnet/core/security/authorization/roles](/aspnet/core/security/authorization/roles)

- <span data-ttu-id="cd94b-152">**カスタム ポリシーベースの承認** </span><span class="sxs-lookup"><span data-stu-id="cd94b-152">**Custom Policy-Based Authorization** </span></span>\
  [https://docs.microsoft.com/aspnet/core/security/authorization/policies](/aspnet/core/security/authorization/policies)

>[!div class="step-by-step"]
><span data-ttu-id="cd94b-153">[前へ](index.md)
>[次へ](developer-app-secrets-storage.md)</span><span class="sxs-lookup"><span data-stu-id="cd94b-153">[Previous](index.md)
[Next](developer-app-secrets-storage.md)</span></span>
