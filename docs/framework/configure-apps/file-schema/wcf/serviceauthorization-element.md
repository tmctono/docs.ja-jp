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
# <a name="serviceauthorization-element"></a><span data-ttu-id="44ff6-102">\<serviceAuthorization > 要素</span><span class="sxs-lookup"><span data-stu-id="44ff6-102">\<serviceAuthorization> element</span></span>

<span data-ttu-id="44ff6-103">サービス操作へのアクセスを許可する設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="44ff6-103">Specifies settings that authorize access to service operations</span></span>

<span data-ttu-id="44ff6-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="44ff6-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="44ff6-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="44ff6-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="44ff6-106">&nbsp; @ no__t @ no__t @no__t @ no__t-3[ **-6 動作 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="44ff6-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="44ff6-107">&nbsp; @ no__t-1 @ no__t @ no__t @ no__t-3[ **\<serviceBehaviors >** ](servicebehaviors.md)\.-9</span><span class="sxs-lookup"><span data-stu-id="44ff6-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\</span></span>
<span data-ttu-id="44ff6-108">&nbsp; @ no__t-1 @ no__t @ no__t @ no__t-5 @ no__t-6 @ no__t-7[ **&nbsp;0behavior >** ](behavior-of-servicebehaviors.md)1 のようになります。</span><span class="sxs-lookup"><span data-stu-id="44ff6-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\</span></span>
<span data-ttu-id="44ff6-109">&nbsp; @ no__t @ no__t @ no__t @ no__t @ no__t @ no__t @ no__t-7 @ no__t-8 @-9 **&nbsp;1serviceAuthorization > を**登録してください。</span><span class="sxs-lookup"><span data-stu-id="44ff6-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceAuthorization>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="44ff6-110">構文</span><span class="sxs-lookup"><span data-stu-id="44ff6-110">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="44ff6-111">属性と要素</span><span class="sxs-lookup"><span data-stu-id="44ff6-111">Attributes and elements</span></span>

<span data-ttu-id="44ff6-112">次のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="44ff6-112">The following sections describe attributes, child elements, and parent elements:</span></span>

### <a name="attributes"></a><span data-ttu-id="44ff6-113">属性</span><span class="sxs-lookup"><span data-stu-id="44ff6-113">Attributes</span></span>

|<span data-ttu-id="44ff6-114">属性</span><span class="sxs-lookup"><span data-stu-id="44ff6-114">Attribute</span></span>|<span data-ttu-id="44ff6-115">説明</span><span class="sxs-lookup"><span data-stu-id="44ff6-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="44ff6-116">impersonateCallerForAllOperations</span><span class="sxs-lookup"><span data-stu-id="44ff6-116">impersonateCallerForAllOperations</span></span>|<span data-ttu-id="44ff6-117">サービスのすべての操作が呼び出し元を偽装するかどうかを指定するブール値。</span><span class="sxs-lookup"><span data-stu-id="44ff6-117">A Boolean value that specifies if all the operations in the service impersonate the caller.</span></span> <span data-ttu-id="44ff6-118">既定値は `false` です。</span><span class="sxs-lookup"><span data-stu-id="44ff6-118">The default is `false`.</span></span><br /><br /> <span data-ttu-id="44ff6-119">特定のサービス操作が呼び出し元を偽装する場合、スレッド コンテキストは、指定されたサービスを実行する前に呼び出し元のコンテキストに切り替えられます。</span><span class="sxs-lookup"><span data-stu-id="44ff6-119">When a specific service operation impersonates the caller, the thread context is switched to the caller context before executing the specified service.</span></span>|  
|<span data-ttu-id="44ff6-120">principalPermissionMode</span><span class="sxs-lookup"><span data-stu-id="44ff6-120">principalPermissionMode</span></span>|<span data-ttu-id="44ff6-121">サーバーでの操作を実行するために使用されるプリンシパルを設定します。</span><span class="sxs-lookup"><span data-stu-id="44ff6-121">Sets the principal used to carry out operations on the server.</span></span> <span data-ttu-id="44ff6-122">次の値があります。</span><span class="sxs-lookup"><span data-stu-id="44ff6-122">Values include the following:</span></span><br /><br /> <span data-ttu-id="44ff6-123">-なし</span><span class="sxs-lookup"><span data-stu-id="44ff6-123">-   None</span></span><br /><span data-ttu-id="44ff6-124">-UseWindowsGroups</span><span class="sxs-lookup"><span data-stu-id="44ff6-124">-   UseWindowsGroups</span></span><br /><span data-ttu-id="44ff6-125">-UseAspNetRoles</span><span class="sxs-lookup"><span data-stu-id="44ff6-125">-   UseAspNetRoles</span></span><br /><span data-ttu-id="44ff6-126">-カスタム</span><span class="sxs-lookup"><span data-stu-id="44ff6-126">-   Custom</span></span><br /><br /> <span data-ttu-id="44ff6-127">既定値は UseWindowsGroups です。</span><span class="sxs-lookup"><span data-stu-id="44ff6-127">The default value is UseWindowsGroups.</span></span> <span data-ttu-id="44ff6-128">値は、<xref:System.ServiceModel.Description.PrincipalPermissionMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="44ff6-128">The value is of type <xref:System.ServiceModel.Description.PrincipalPermissionMode>.</span></span> <span data-ttu-id="44ff6-129">この属性の使用方法の詳細については、@no__t を参照してください。PrincipalPermissionAttribute クラス @ no__t を使用してアクセスを制限します。</span><span class="sxs-lookup"><span data-stu-id="44ff6-129">For more information on using this attribute, see [How to: Restrict Access with the PrincipalPermissionAttribute Class](../../../wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md).</span></span>|  
|<span data-ttu-id="44ff6-130">roleProviderName</span><span class="sxs-lookup"><span data-stu-id="44ff6-130">roleProviderName</span></span>|<span data-ttu-id="44ff6-131">Windows Communication Foundation (WCF) アプリケーションにロール情報を提供するロール プロバイダーの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="44ff6-131">A string that specifies the name of the role provider, which provides role information for a Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="44ff6-132">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="44ff6-132">The default is an empty string.</span></span>|  
|<span data-ttu-id="44ff6-133">ServiceAuthorizationManagerType</span><span class="sxs-lookup"><span data-stu-id="44ff6-133">ServiceAuthorizationManagerType</span></span>|<span data-ttu-id="44ff6-134">サービス承認マネージャーの型を含む文字列。</span><span class="sxs-lookup"><span data-stu-id="44ff6-134">A string containing the type of the service authorization manager.</span></span> <span data-ttu-id="44ff6-135">詳細については、「 <xref:System.ServiceModel.ServiceAuthorizationManager> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="44ff6-135">For more information, see <xref:System.ServiceModel.ServiceAuthorizationManager>.</span></span>|  

### <a name="child-elements"></a><span data-ttu-id="44ff6-136">子要素</span><span class="sxs-lookup"><span data-stu-id="44ff6-136">Child elements</span></span>

|<span data-ttu-id="44ff6-137">要素</span><span class="sxs-lookup"><span data-stu-id="44ff6-137">Element</span></span>|<span data-ttu-id="44ff6-138">説明</span><span class="sxs-lookup"><span data-stu-id="44ff6-138">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="44ff6-139">authorizationPolicies</span><span class="sxs-lookup"><span data-stu-id="44ff6-139">authorizationPolicies</span></span>|<span data-ttu-id="44ff6-140">`add` キーワードを使用して追加できる承認ポリシーの種類のコレクションを含みます。</span><span class="sxs-lookup"><span data-stu-id="44ff6-140">Contains a collection of authorization policy types, which can be added using the `add` keyword.</span></span> <span data-ttu-id="44ff6-141">各承認ポリシーは、文字列の単一の必須属性 `policyType` を含みます。</span><span class="sxs-lookup"><span data-stu-id="44ff6-141">Each authorization policy contains a single required `policyType` attribute that is a string.</span></span> <span data-ttu-id="44ff6-142">この属性は、入力クレームのセットをクレームの別のセットに変換することを可能にする承認ポリシーを指定します。</span><span class="sxs-lookup"><span data-stu-id="44ff6-142">The attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="44ff6-143">アクセス制御は、それに基づいて許可または拒否されます。</span><span class="sxs-lookup"><span data-stu-id="44ff6-143">Access control can be granted or denied based on that.</span></span> <span data-ttu-id="44ff6-144">詳細については、「 <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="44ff6-144">For more information, see <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>.</span></span>|  

### <a name="parent-elements"></a><span data-ttu-id="44ff6-145">親要素</span><span class="sxs-lookup"><span data-stu-id="44ff6-145">Parent elements</span></span>

|<span data-ttu-id="44ff6-146">要素</span><span class="sxs-lookup"><span data-stu-id="44ff6-146">Element</span></span>|<span data-ttu-id="44ff6-147">説明</span><span class="sxs-lookup"><span data-stu-id="44ff6-147">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="44ff6-148">\<behavior></span><span class="sxs-lookup"><span data-stu-id="44ff6-148">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="44ff6-149">サービスの動作設定のコレクションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="44ff6-149">Contains a collection of settings for the behavior of a service.</span></span>|  

## <a name="remarks"></a><span data-ttu-id="44ff6-150">コメント</span><span class="sxs-lookup"><span data-stu-id="44ff6-150">Remarks</span></span>

<span data-ttu-id="44ff6-151">このセクションには、承認、カスタム ロール プロバイダー、および偽装に影響する要素が含まれています。</span><span class="sxs-lookup"><span data-stu-id="44ff6-151">This section contains elements affecting authorization, custom role providers, and impersonation.</span></span>  
  
<span data-ttu-id="44ff6-152">`principalPermissionMode` 属性は、保護メソッドの使用を承認するときに使用するユーザー グループを指定します。</span><span class="sxs-lookup"><span data-stu-id="44ff6-152">The `principalPermissionMode` attribute specifies the groups of users to use when authorizing use of a protected method.</span></span> <span data-ttu-id="44ff6-153">既定値は `UseWindowsGroups` で、リソースにアクセスしようとしている ID を、"Administrators" や "Users" などの Windows グループから検索するように指定します。</span><span class="sxs-lookup"><span data-stu-id="44ff6-153">The default value is `UseWindowsGroups` and specifies that Windows groups, such as "Administrators" or "Users," are searched for an identity trying to access a resource.</span></span> <span data-ttu-id="44ff6-154">次のコードに示すように、`UseAspNetRoles` を指定して、@no__t 1system.web > 要素で構成されたカスタムロールプロバイダーを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="44ff6-154">You can also specify `UseAspNetRoles` to use a custom role provider that is configured under the \<system.web> element, as shown in the following code:</span></span>

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
  
<span data-ttu-id="44ff6-155">次のコードは、`principalPermissionMode` 属性で使用される @no__t 0 を示しています。</span><span class="sxs-lookup"><span data-stu-id="44ff6-155">The following code shows the `roleProviderName` used with the `principalPermissionMode` attribute:</span></span>
  
```xml
<behaviors>
  <behavior name="ServiceBehaviour">
    <serviceAuthorization principalPermissionMode ="UseAspNetRoles"
                          roleProviderName ="SqlProvider" />
  </behavior>
  <!-- Other configuration code not shown. -->
</behaviors>
```

<span data-ttu-id="44ff6-156">この構成要素の使用例については、「[サービス操作](../../../wcf/samples/authorizing-access-to-service-operations.md)と[承認ポリシー](../../../wcf/samples/authorization-policy.md)へのアクセスの承認」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="44ff6-156">For a detailed example of using this configuration element, see [Authorizing Access to Service Operations](../../../wcf/samples/authorizing-access-to-service-operations.md) and [Authorization Policy](../../../wcf/samples/authorization-policy.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="44ff6-157">関連項目</span><span class="sxs-lookup"><span data-stu-id="44ff6-157">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
- [<span data-ttu-id="44ff6-158">セキュリティ動作</span><span class="sxs-lookup"><span data-stu-id="44ff6-158">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="44ff6-159">サービス操作へのアクセスの承認</span><span class="sxs-lookup"><span data-stu-id="44ff6-159">Authorizing Access to Service Operations</span></span>](../../../wcf/samples/authorizing-access-to-service-operations.md)
- <span data-ttu-id="44ff6-160">[2 つのオブジェクトが等しいかどうかをテストする方法サービスのカスタム承認マネージャーを作成する @ no__t-0</span><span class="sxs-lookup"><span data-stu-id="44ff6-160">[How to: Create a Custom Authorization Manager for a Service](../../../wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)</span></span>
- <span data-ttu-id="44ff6-161">[2 つのオブジェクトが等しいかどうかをテストする方法PrincipalPermissionAttribute クラスを使用してアクセスを制限する @ no__t-0</span><span class="sxs-lookup"><span data-stu-id="44ff6-161">[How to: Restrict Access with the PrincipalPermissionAttribute Class](../../../wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)</span></span>
- [<span data-ttu-id="44ff6-162">承認ポリシー</span><span class="sxs-lookup"><span data-stu-id="44ff6-162">Authorization Policy</span></span>](../../../wcf/samples/authorization-policy.md)
