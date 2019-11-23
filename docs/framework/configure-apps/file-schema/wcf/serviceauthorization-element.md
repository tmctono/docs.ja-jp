---
title: <serviceAuthorization> 要素
ms.date: 03/30/2017
ms.assetid: 18cddad5-ddcb-4839-a0ac-1d6f6ab783ca
ms.openlocfilehash: f476f754a340f52859be2986e42754cba0ef3771
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/03/2019
ms.locfileid: "71834023"
---
# <a name="serviceauthorization-element"></a><span data-ttu-id="1ae59-102">\<serviceAuthorization > 要素</span><span class="sxs-lookup"><span data-stu-id="1ae59-102">\<serviceAuthorization> element</span></span>

<span data-ttu-id="1ae59-103">サービス操作へのアクセスを許可する設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="1ae59-103">Specifies settings that authorize access to service operations</span></span>

<span data-ttu-id="1ae59-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="1ae59-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="1ae59-105">&nbsp;&nbsp;[ **\<system.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="1ae59-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="1ae59-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<の動作**](behaviors.md)></span><span class="sxs-lookup"><span data-stu-id="1ae59-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="1ae59-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="1ae59-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="1ae59-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**動作 >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="1ae59-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="1ae59-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**serviceAuthorization >**</span><span class="sxs-lookup"><span data-stu-id="1ae59-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceAuthorization>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="1ae59-110">構文</span><span class="sxs-lookup"><span data-stu-id="1ae59-110">Syntax</span></span>

```xml
<serviceAuthorization impersonateCallerForAllOperations="Boolean"
                      principalPermissionMode="None/UseWindowsGroups/UseAspNetRoles/Custom"
                      roleProviderName="String"
                      serviceAuthorizationManagerType="String">
  <authorizationPolicies>
    <add policyType="String" />
  </authorizationPolicies>
</serviceAuthorization>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="1ae59-111">属性と要素</span><span class="sxs-lookup"><span data-stu-id="1ae59-111">Attributes and elements</span></span>

<span data-ttu-id="1ae59-112">次のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="1ae59-112">The following sections describe attributes, child elements, and parent elements:</span></span>

### <a name="attributes"></a><span data-ttu-id="1ae59-113">属性</span><span class="sxs-lookup"><span data-stu-id="1ae59-113">Attributes</span></span>

|<span data-ttu-id="1ae59-114">属性</span><span class="sxs-lookup"><span data-stu-id="1ae59-114">Attribute</span></span>|<span data-ttu-id="1ae59-115">説明</span><span class="sxs-lookup"><span data-stu-id="1ae59-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1ae59-116">impersonateCallerForAllOperations</span><span class="sxs-lookup"><span data-stu-id="1ae59-116">impersonateCallerForAllOperations</span></span>|<span data-ttu-id="1ae59-117">サービスのすべての操作が呼び出し元を偽装するかどうかを指定するブール値。</span><span class="sxs-lookup"><span data-stu-id="1ae59-117">A Boolean value that specifies if all the operations in the service impersonate the caller.</span></span> <span data-ttu-id="1ae59-118">既定値は、`false` です。</span><span class="sxs-lookup"><span data-stu-id="1ae59-118">The default is `false`.</span></span><br /><br /> <span data-ttu-id="1ae59-119">特定のサービス操作が呼び出し元を偽装する場合、スレッド コンテキストは、指定されたサービスを実行する前に呼び出し元のコンテキストに切り替えられます。</span><span class="sxs-lookup"><span data-stu-id="1ae59-119">When a specific service operation impersonates the caller, the thread context is switched to the caller context before executing the specified service.</span></span>|  
|<span data-ttu-id="1ae59-120">principalPermissionMode</span><span class="sxs-lookup"><span data-stu-id="1ae59-120">principalPermissionMode</span></span>|<span data-ttu-id="1ae59-121">サーバーでの操作を実行するために使用されるプリンシパルを設定します。</span><span class="sxs-lookup"><span data-stu-id="1ae59-121">Sets the principal used to carry out operations on the server.</span></span> <span data-ttu-id="1ae59-122">次の値があります。</span><span class="sxs-lookup"><span data-stu-id="1ae59-122">Values include the following:</span></span><br /><br /> <span data-ttu-id="1ae59-123">-なし</span><span class="sxs-lookup"><span data-stu-id="1ae59-123">-   None</span></span><br /><span data-ttu-id="1ae59-124">-UseWindowsGroups</span><span class="sxs-lookup"><span data-stu-id="1ae59-124">-   UseWindowsGroups</span></span><br /><span data-ttu-id="1ae59-125">-UseAspNetRoles</span><span class="sxs-lookup"><span data-stu-id="1ae59-125">-   UseAspNetRoles</span></span><br /><span data-ttu-id="1ae59-126">-カスタム</span><span class="sxs-lookup"><span data-stu-id="1ae59-126">-   Custom</span></span><br /><br /> <span data-ttu-id="1ae59-127">既定値は UseWindowsGroups です。</span><span class="sxs-lookup"><span data-stu-id="1ae59-127">The default value is UseWindowsGroups.</span></span> <span data-ttu-id="1ae59-128">値は、<xref:System.ServiceModel.Description.PrincipalPermissionMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="1ae59-128">The value is of type <xref:System.ServiceModel.Description.PrincipalPermissionMode>.</span></span> <span data-ttu-id="1ae59-129">この属性の使用方法の詳細については、「[方法: PrincipalPermissionAttribute クラスを使用してアクセスを制限する](../../../wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1ae59-129">For more information on using this attribute, see [How to: Restrict Access with the PrincipalPermissionAttribute Class](../../../wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md).</span></span>|  
|<span data-ttu-id="1ae59-130">roleProviderName</span><span class="sxs-lookup"><span data-stu-id="1ae59-130">roleProviderName</span></span>|<span data-ttu-id="1ae59-131">Windows Communication Foundation (WCF) アプリケーションにロール情報を提供するロール プロバイダーの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="1ae59-131">A string that specifies the name of the role provider, which provides role information for a Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="1ae59-132">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="1ae59-132">The default is an empty string.</span></span>|  
|<span data-ttu-id="1ae59-133">ServiceAuthorizationManagerType</span><span class="sxs-lookup"><span data-stu-id="1ae59-133">ServiceAuthorizationManagerType</span></span>|<span data-ttu-id="1ae59-134">サービス承認マネージャーの型を含む文字列。</span><span class="sxs-lookup"><span data-stu-id="1ae59-134">A string containing the type of the service authorization manager.</span></span> <span data-ttu-id="1ae59-135">詳細については、「 <xref:System.ServiceModel.ServiceAuthorizationManager>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1ae59-135">For more information, see <xref:System.ServiceModel.ServiceAuthorizationManager>.</span></span>|  

### <a name="child-elements"></a><span data-ttu-id="1ae59-136">子要素</span><span class="sxs-lookup"><span data-stu-id="1ae59-136">Child elements</span></span>

|<span data-ttu-id="1ae59-137">要素</span><span class="sxs-lookup"><span data-stu-id="1ae59-137">Element</span></span>|<span data-ttu-id="1ae59-138">説明</span><span class="sxs-lookup"><span data-stu-id="1ae59-138">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1ae59-139">authorizationPolicies</span><span class="sxs-lookup"><span data-stu-id="1ae59-139">authorizationPolicies</span></span>|<span data-ttu-id="1ae59-140">`add` キーワードを使用して追加できる承認ポリシーの種類のコレクションを含みます。</span><span class="sxs-lookup"><span data-stu-id="1ae59-140">Contains a collection of authorization policy types, which can be added using the `add` keyword.</span></span> <span data-ttu-id="1ae59-141">各承認ポリシーは、文字列の単一の必須属性 `policyType` を含みます。</span><span class="sxs-lookup"><span data-stu-id="1ae59-141">Each authorization policy contains a single required `policyType` attribute that is a string.</span></span> <span data-ttu-id="1ae59-142">この属性は、入力クレームのセットをクレームの別のセットに変換することを可能にする承認ポリシーを指定します。</span><span class="sxs-lookup"><span data-stu-id="1ae59-142">The attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="1ae59-143">アクセス制御は、それに基づいて許可または拒否されます。</span><span class="sxs-lookup"><span data-stu-id="1ae59-143">Access control can be granted or denied based on that.</span></span> <span data-ttu-id="1ae59-144">詳細については、「 <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1ae59-144">For more information, see <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>.</span></span>|  

### <a name="parent-elements"></a><span data-ttu-id="1ae59-145">親要素</span><span class="sxs-lookup"><span data-stu-id="1ae59-145">Parent elements</span></span>

|<span data-ttu-id="1ae59-146">要素</span><span class="sxs-lookup"><span data-stu-id="1ae59-146">Element</span></span>|<span data-ttu-id="1ae59-147">説明</span><span class="sxs-lookup"><span data-stu-id="1ae59-147">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1ae59-148">\<behavior></span><span class="sxs-lookup"><span data-stu-id="1ae59-148">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="1ae59-149">サービスの動作設定のコレクションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="1ae59-149">Contains a collection of settings for the behavior of a service.</span></span>|  

## <a name="remarks"></a><span data-ttu-id="1ae59-150">コメント</span><span class="sxs-lookup"><span data-stu-id="1ae59-150">Remarks</span></span>

<span data-ttu-id="1ae59-151">このセクションには、承認、カスタム ロール プロバイダー、および偽装に影響する要素が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1ae59-151">This section contains elements affecting authorization, custom role providers, and impersonation.</span></span>  
  
<span data-ttu-id="1ae59-152">`principalPermissionMode` 属性は、保護メソッドの使用を承認するときに使用するユーザー グループを指定します。</span><span class="sxs-lookup"><span data-stu-id="1ae59-152">The `principalPermissionMode` attribute specifies the groups of users to use when authorizing use of a protected method.</span></span> <span data-ttu-id="1ae59-153">既定値は `UseWindowsGroups` で、リソースにアクセスしようとしている ID を、"Administrators" や "Users" などの Windows グループから検索するように指定します。</span><span class="sxs-lookup"><span data-stu-id="1ae59-153">The default value is `UseWindowsGroups` and specifies that Windows groups, such as "Administrators" or "Users," are searched for an identity trying to access a resource.</span></span> <span data-ttu-id="1ae59-154">次のコードに示すように、\<system.web > 要素の下に構成されているカスタムロールプロバイダーを使用するように `UseAspNetRoles` を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="1ae59-154">You can also specify `UseAspNetRoles` to use a custom role provider that is configured under the \<system.web> element, as shown in the following code:</span></span>

```xml
<system.web>
  <membership defaultProvider="SqlProvider"
              userIsOnlineTimeWindow="15">
    <providers>
      <clear />
      <add name="SqlProvider"
           type="System.Web.Security.SqlMembershipProvider"
           connectionStringName="SqlConn"
           applicationName="MembershipProvider"
           enablePasswordRetrieval="false"
           enablePasswordReset="false"
           requiresQuestionAndAnswer="false"
           requiresUniqueEmail="true"
           passwordFormat="Hashed" />
    </providers>
  </membership>
  <!-- Other configuration code not shown. -->
</system.web>
```
  
<span data-ttu-id="1ae59-155">次のコードは、`principalPermissionMode` 属性で使用される `roleProviderName` を示しています。</span><span class="sxs-lookup"><span data-stu-id="1ae59-155">The following code shows the `roleProviderName` used with the `principalPermissionMode` attribute:</span></span>
  
```xml
<behaviors>
  <behavior name="ServiceBehaviour">
    <serviceAuthorization principalPermissionMode ="UseAspNetRoles"
                          roleProviderName ="SqlProvider" />
  </behavior>
  <!-- Other configuration code not shown. -->
</behaviors>
```

<span data-ttu-id="1ae59-156">この構成要素の使用例については、「[サービス操作](../../../wcf/samples/authorizing-access-to-service-operations.md)と[承認ポリシー](../../../wcf/samples/authorization-policy.md)へのアクセスの承認」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1ae59-156">For a detailed example of using this configuration element, see [Authorizing Access to Service Operations](../../../wcf/samples/authorizing-access-to-service-operations.md) and [Authorization Policy](../../../wcf/samples/authorization-policy.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1ae59-157">参照</span><span class="sxs-lookup"><span data-stu-id="1ae59-157">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
- [<span data-ttu-id="1ae59-158">セキュリティ動作</span><span class="sxs-lookup"><span data-stu-id="1ae59-158">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="1ae59-159">サービス操作へのアクセスの承認</span><span class="sxs-lookup"><span data-stu-id="1ae59-159">Authorizing Access to Service Operations</span></span>](../../../wcf/samples/authorizing-access-to-service-operations.md)
- [<span data-ttu-id="1ae59-160">方法 : サービスで使用するカスタム承認マネージャーを作成する</span><span class="sxs-lookup"><span data-stu-id="1ae59-160">How to: Create a Custom Authorization Manager for a Service</span></span>](../../../wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)
- [<span data-ttu-id="1ae59-161">方法: PrincipalPermissionAttribute クラスでアクセスを制限する</span><span class="sxs-lookup"><span data-stu-id="1ae59-161">How to: Restrict Access with the PrincipalPermissionAttribute Class</span></span>](../../../wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)
- [<span data-ttu-id="1ae59-162">承認ポリシー</span><span class="sxs-lookup"><span data-stu-id="1ae59-162">Authorization Policy</span></span>](../../../wcf/samples/authorization-policy.md)
