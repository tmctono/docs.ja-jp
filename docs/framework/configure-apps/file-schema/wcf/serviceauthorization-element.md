---
title: <serviceAuthorization> 要素
ms.date: 03/30/2017
ms.assetid: 18cddad5-ddcb-4839-a0ac-1d6f6ab783ca
ms.openlocfilehash: b636b7006900ecff1be553cf32105df7cea7e800
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399689"
---
# <a name="serviceauthorization-element"></a><span data-ttu-id="22103-102">\<serviceAuthorization > 要素</span><span class="sxs-lookup"><span data-stu-id="22103-102">\<serviceAuthorization> element</span></span>
<span data-ttu-id="22103-103">サービス操作へのアクセスを許可する設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="22103-103">Specifies settings that authorize access to service operations</span></span>  
  
<span data-ttu-id="22103-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="22103-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="22103-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="22103-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="22103-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="22103-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="22103-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="22103-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="22103-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="22103-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="22103-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<serviceAuthorization >**</span><span class="sxs-lookup"><span data-stu-id="22103-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceAuthorization>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22103-110">構文</span><span class="sxs-lookup"><span data-stu-id="22103-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="22103-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="22103-111">Attributes and Elements</span></span>  
 <span data-ttu-id="22103-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="22103-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="22103-113">属性</span><span class="sxs-lookup"><span data-stu-id="22103-113">Attributes</span></span>  
  
|<span data-ttu-id="22103-114">属性</span><span class="sxs-lookup"><span data-stu-id="22103-114">Attribute</span></span>|<span data-ttu-id="22103-115">説明</span><span class="sxs-lookup"><span data-stu-id="22103-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="22103-116">impersonateCallerForAllOperations</span><span class="sxs-lookup"><span data-stu-id="22103-116">impersonateCallerForAllOperations</span></span>|<span data-ttu-id="22103-117">サービスのすべての操作が呼び出し元を偽装するかどうかを指定するブール値。</span><span class="sxs-lookup"><span data-stu-id="22103-117">A Boolean value that specifies if all the operations in the service impersonate the caller.</span></span> <span data-ttu-id="22103-118">既定値は `false` です。</span><span class="sxs-lookup"><span data-stu-id="22103-118">The default is `false`.</span></span><br /><br /> <span data-ttu-id="22103-119">特定のサービス操作が呼び出し元を偽装する場合、スレッド コンテキストは、指定されたサービスを実行する前に呼び出し元のコンテキストに切り替えられます。</span><span class="sxs-lookup"><span data-stu-id="22103-119">When a specific service operation impersonates the caller, the thread context is switched to the caller context before executing the specified service.</span></span>|  
|<span data-ttu-id="22103-120">principalPermissionMode</span><span class="sxs-lookup"><span data-stu-id="22103-120">principalPermissionMode</span></span>|<span data-ttu-id="22103-121">サーバーでの操作を実行するために使用されるプリンシパルを設定します。</span><span class="sxs-lookup"><span data-stu-id="22103-121">Sets the principal used to carry out operations on the server.</span></span> <span data-ttu-id="22103-122">次の値があります。</span><span class="sxs-lookup"><span data-stu-id="22103-122">Values include the following:</span></span><br /><br /> <span data-ttu-id="22103-123">-なし</span><span class="sxs-lookup"><span data-stu-id="22103-123">-   None</span></span><br /><span data-ttu-id="22103-124">-UseWindowsGroups</span><span class="sxs-lookup"><span data-stu-id="22103-124">-   UseWindowsGroups</span></span><br /><span data-ttu-id="22103-125">-UseAspNetRoles</span><span class="sxs-lookup"><span data-stu-id="22103-125">-   UseAspNetRoles</span></span><br /><span data-ttu-id="22103-126">-カスタム</span><span class="sxs-lookup"><span data-stu-id="22103-126">-   Custom</span></span><br /><br /> <span data-ttu-id="22103-127">既定値は UseWindowsGroups です。</span><span class="sxs-lookup"><span data-stu-id="22103-127">The default value is UseWindowsGroups.</span></span> <span data-ttu-id="22103-128">値は、<xref:System.ServiceModel.Description.PrincipalPermissionMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="22103-128">The value is of type <xref:System.ServiceModel.Description.PrincipalPermissionMode>.</span></span> <span data-ttu-id="22103-129">この属性の使用方法の詳細につい[ては、「方法:PrincipalPermissionAttribute クラス](../../../wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)を使用してアクセスを制限します。</span><span class="sxs-lookup"><span data-stu-id="22103-129">For more information on using this attribute, see [How to: Restrict Access with the PrincipalPermissionAttribute Class](../../../wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md).</span></span>|  
|<span data-ttu-id="22103-130">roleProviderName</span><span class="sxs-lookup"><span data-stu-id="22103-130">roleProviderName</span></span>|<span data-ttu-id="22103-131">Windows Communication Foundation (WCF) アプリケーションにロール情報を提供するロール プロバイダーの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="22103-131">A string that specifies the name of the role provider, which provides role information for a Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="22103-132">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="22103-132">The default is an empty string.</span></span>|  
|<span data-ttu-id="22103-133">ServiceAuthorizationManagerType</span><span class="sxs-lookup"><span data-stu-id="22103-133">ServiceAuthorizationManagerType</span></span>|<span data-ttu-id="22103-134">サービス承認マネージャーの型を含む文字列。</span><span class="sxs-lookup"><span data-stu-id="22103-134">A string containing the type of the service authorization manager.</span></span> <span data-ttu-id="22103-135">詳細については、「 <xref:System.ServiceModel.ServiceAuthorizationManager> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="22103-135">For more information, see <xref:System.ServiceModel.ServiceAuthorizationManager>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="22103-136">子要素</span><span class="sxs-lookup"><span data-stu-id="22103-136">Child Elements</span></span>  
  
|<span data-ttu-id="22103-137">要素</span><span class="sxs-lookup"><span data-stu-id="22103-137">Element</span></span>|<span data-ttu-id="22103-138">説明</span><span class="sxs-lookup"><span data-stu-id="22103-138">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="22103-139">authorizationPolicies</span><span class="sxs-lookup"><span data-stu-id="22103-139">authorizationPolicies</span></span>|<span data-ttu-id="22103-140">`add` キーワードを使用して追加できる承認ポリシーの種類のコレクションを含みます。</span><span class="sxs-lookup"><span data-stu-id="22103-140">Contains a collection of authorization policy types, which can be added using the `add` keyword.</span></span> <span data-ttu-id="22103-141">各承認ポリシーは、文字列の単一の必須属性 `policyType` を含みます。</span><span class="sxs-lookup"><span data-stu-id="22103-141">Each authorization policy contains a single required `policyType` attribute that is a string.</span></span> <span data-ttu-id="22103-142">この属性は、入力クレームのセットをクレームの別のセットに変換することを可能にする承認ポリシーを指定します。</span><span class="sxs-lookup"><span data-stu-id="22103-142">The attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="22103-143">アクセス制御は、それに基づいて許可または拒否されます。</span><span class="sxs-lookup"><span data-stu-id="22103-143">Access control can be granted or denied based on that.</span></span> <span data-ttu-id="22103-144">詳細については、「 <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="22103-144">For more information, see <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="22103-145">親要素</span><span class="sxs-lookup"><span data-stu-id="22103-145">Parent Elements</span></span>  
  
|<span data-ttu-id="22103-146">要素</span><span class="sxs-lookup"><span data-stu-id="22103-146">Element</span></span>|<span data-ttu-id="22103-147">説明</span><span class="sxs-lookup"><span data-stu-id="22103-147">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="22103-148">\<behavior></span><span class="sxs-lookup"><span data-stu-id="22103-148">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="22103-149">サービスの動作設定のコレクションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="22103-149">Contains a collection of settings for the behavior of a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="22103-150">Remarks</span><span class="sxs-lookup"><span data-stu-id="22103-150">Remarks</span></span>  
 <span data-ttu-id="22103-151">このセクションには、承認、カスタム ロール プロバイダー、および偽装に影響する要素が含まれています。</span><span class="sxs-lookup"><span data-stu-id="22103-151">This section contains elements affecting authorization, custom role providers, and impersonation.</span></span>  
  
 <span data-ttu-id="22103-152">`principalPermissionMode` 属性は、保護メソッドの使用を承認するときに使用するユーザー グループを指定します。</span><span class="sxs-lookup"><span data-stu-id="22103-152">The `principalPermissionMode` attribute specifies the groups of users to use when authorizing use of a protected method.</span></span> <span data-ttu-id="22103-153">既定値は `UseWindowsGroups` で、リソースにアクセスしようとしている ID を、"Administrators" や "Users" などの Windows グループから検索するように指定します。</span><span class="sxs-lookup"><span data-stu-id="22103-153">The default value is `UseWindowsGroups` and specifies that Windows groups, such as "Administrators" or "Users," are searched for an identity trying to access a resource.</span></span> <span data-ttu-id="22103-154">次のコードに`UseAspNetRoles`示すように、system.web > 要素の\<下に構成されているカスタムロールプロバイダーを使用するように指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="22103-154">You can also specify `UseAspNetRoles` to use a custom role provider that is configured under the \<system.web> element, as shown in the following code.</span></span>  
  
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
  
 <span data-ttu-id="22103-155">`roleProviderName` 属性で `principalPermissionMode` を使用する方法を次のコードに示します。</span><span class="sxs-lookup"><span data-stu-id="22103-155">The following code shows the `roleProviderName` used with the `principalPermissionMode` attribute.</span></span>  
  
```xml  
<behaviors>
  <behavior name="ServiceBehaviour">
    <serviceAuthorization principalPermissionMode ="UseAspNetRoles"
                          roleProviderName ="SqlProvider" />
  </behavior>
  <!-- Other configuration code not shown. -->
</behaviors>
```  
  
 <span data-ttu-id="22103-156">この構成要素の使用例については、「[サービス操作](../../../wcf/samples/authorizing-access-to-service-operations.md)と[承認ポリシー](../../../wcf/samples/authorization-policy.md)へのアクセスの承認」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="22103-156">For a detailed example of using this configuration element, see [Authorizing Access to Service Operations](../../../wcf/samples/authorizing-access-to-service-operations.md) and [Authorization Policy](../../../wcf/samples/authorization-policy.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22103-157">関連項目</span><span class="sxs-lookup"><span data-stu-id="22103-157">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
- [<span data-ttu-id="22103-158">セキュリティ動作</span><span class="sxs-lookup"><span data-stu-id="22103-158">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="22103-159">サービス操作へのアクセスの承認</span><span class="sxs-lookup"><span data-stu-id="22103-159">Authorizing Access to Service Operations</span></span>](../../../wcf/samples/authorizing-access-to-service-operations.md)
- [<span data-ttu-id="22103-160">方法: サービスのカスタム承認マネージャーを作成する</span><span class="sxs-lookup"><span data-stu-id="22103-160">How to: Create a Custom Authorization Manager for a Service</span></span>](../../../wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)
- [<span data-ttu-id="22103-161">方法: PrincipalPermissionAttribute クラスを使用してアクセスを制限する</span><span class="sxs-lookup"><span data-stu-id="22103-161">How to: Restrict Access with the PrincipalPermissionAttribute Class</span></span>](../../../wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)
- [<span data-ttu-id="22103-162">承認ポリシー</span><span class="sxs-lookup"><span data-stu-id="22103-162">Authorization Policy</span></span>](../../../wcf/samples/authorization-policy.md)
