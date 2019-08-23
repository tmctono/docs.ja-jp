---
title: <serviceAuthorization> 要素
ms.date: 03/30/2017
ms.assetid: 18cddad5-ddcb-4839-a0ac-1d6f6ab783ca
ms.openlocfilehash: b73e2049afb460bf9be8b76ee272ba0547b61453
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936400"
---
# <a name="serviceauthorization-element"></a><span data-ttu-id="15477-102">\<serviceAuthorization > 要素</span><span class="sxs-lookup"><span data-stu-id="15477-102">\<serviceAuthorization> element</span></span>
<span data-ttu-id="15477-103">サービス操作へのアクセスを許可する設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="15477-103">Specifies settings that authorize access to service operations</span></span>  
  
 <span data-ttu-id="15477-104">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="15477-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="15477-105">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="15477-105">\<behaviors></span></span>  
<span data-ttu-id="15477-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="15477-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="15477-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="15477-107">\<behavior></span></span>  
<span data-ttu-id="15477-108">\<serviceAuthorization ></span><span class="sxs-lookup"><span data-stu-id="15477-108">\<serviceAuthorization></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15477-109">構文</span><span class="sxs-lookup"><span data-stu-id="15477-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="15477-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="15477-110">Attributes and Elements</span></span>  
 <span data-ttu-id="15477-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="15477-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="15477-112">属性</span><span class="sxs-lookup"><span data-stu-id="15477-112">Attributes</span></span>  
  
|<span data-ttu-id="15477-113">属性</span><span class="sxs-lookup"><span data-stu-id="15477-113">Attribute</span></span>|<span data-ttu-id="15477-114">説明</span><span class="sxs-lookup"><span data-stu-id="15477-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="15477-115">impersonateCallerForAllOperations</span><span class="sxs-lookup"><span data-stu-id="15477-115">impersonateCallerForAllOperations</span></span>|<span data-ttu-id="15477-116">サービスのすべての操作が呼び出し元を偽装するかどうかを指定するブール値。</span><span class="sxs-lookup"><span data-stu-id="15477-116">A Boolean value that specifies if all the operations in the service impersonate the caller.</span></span> <span data-ttu-id="15477-117">既定値は `false` です。</span><span class="sxs-lookup"><span data-stu-id="15477-117">The default is `false`.</span></span><br /><br /> <span data-ttu-id="15477-118">特定のサービス操作が呼び出し元を偽装する場合、スレッド コンテキストは、指定されたサービスを実行する前に呼び出し元のコンテキストに切り替えられます。</span><span class="sxs-lookup"><span data-stu-id="15477-118">When a specific service operation impersonates the caller, the thread context is switched to the caller context before executing the specified service.</span></span>|  
|<span data-ttu-id="15477-119">principalPermissionMode</span><span class="sxs-lookup"><span data-stu-id="15477-119">principalPermissionMode</span></span>|<span data-ttu-id="15477-120">サーバーでの操作を実行するために使用されるプリンシパルを設定します。</span><span class="sxs-lookup"><span data-stu-id="15477-120">Sets the principal used to carry out operations on the server.</span></span> <span data-ttu-id="15477-121">次の値があります。</span><span class="sxs-lookup"><span data-stu-id="15477-121">Values include the following:</span></span><br /><br /> <span data-ttu-id="15477-122">-なし</span><span class="sxs-lookup"><span data-stu-id="15477-122">-   None</span></span><br /><span data-ttu-id="15477-123">-UseWindowsGroups</span><span class="sxs-lookup"><span data-stu-id="15477-123">-   UseWindowsGroups</span></span><br /><span data-ttu-id="15477-124">-UseAspNetRoles</span><span class="sxs-lookup"><span data-stu-id="15477-124">-   UseAspNetRoles</span></span><br /><span data-ttu-id="15477-125">-カスタム</span><span class="sxs-lookup"><span data-stu-id="15477-125">-   Custom</span></span><br /><br /> <span data-ttu-id="15477-126">既定値は UseWindowsGroups です。</span><span class="sxs-lookup"><span data-stu-id="15477-126">The default value is UseWindowsGroups.</span></span> <span data-ttu-id="15477-127">値は、<xref:System.ServiceModel.Description.PrincipalPermissionMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="15477-127">The value is of type <xref:System.ServiceModel.Description.PrincipalPermissionMode>.</span></span> <span data-ttu-id="15477-128">この属性の使用方法の詳細につい[ては、「方法:PrincipalPermissionAttribute クラス](../../../wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)を使用してアクセスを制限します。</span><span class="sxs-lookup"><span data-stu-id="15477-128">For more information on using this attribute, see [How to: Restrict Access with the PrincipalPermissionAttribute Class](../../../wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md).</span></span>|  
|<span data-ttu-id="15477-129">roleProviderName</span><span class="sxs-lookup"><span data-stu-id="15477-129">roleProviderName</span></span>|<span data-ttu-id="15477-130">Windows Communication Foundation (WCF) アプリケーションにロール情報を提供するロール プロバイダーの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="15477-130">A string that specifies the name of the role provider, which provides role information for a Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="15477-131">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="15477-131">The default is an empty string.</span></span>|  
|<span data-ttu-id="15477-132">ServiceAuthorizationManagerType</span><span class="sxs-lookup"><span data-stu-id="15477-132">ServiceAuthorizationManagerType</span></span>|<span data-ttu-id="15477-133">サービス承認マネージャーの型を含む文字列。</span><span class="sxs-lookup"><span data-stu-id="15477-133">A string containing the type of the service authorization manager.</span></span> <span data-ttu-id="15477-134">詳細については、「 <xref:System.ServiceModel.ServiceAuthorizationManager> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="15477-134">For more information, see <xref:System.ServiceModel.ServiceAuthorizationManager>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="15477-135">子要素</span><span class="sxs-lookup"><span data-stu-id="15477-135">Child Elements</span></span>  
  
|<span data-ttu-id="15477-136">要素</span><span class="sxs-lookup"><span data-stu-id="15477-136">Element</span></span>|<span data-ttu-id="15477-137">説明</span><span class="sxs-lookup"><span data-stu-id="15477-137">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="15477-138">authorizationPolicies</span><span class="sxs-lookup"><span data-stu-id="15477-138">authorizationPolicies</span></span>|<span data-ttu-id="15477-139">`add` キーワードを使用して追加できる承認ポリシーの種類のコレクションを含みます。</span><span class="sxs-lookup"><span data-stu-id="15477-139">Contains a collection of authorization policy types, which can be added using the `add` keyword.</span></span> <span data-ttu-id="15477-140">各承認ポリシーは、文字列の単一の必須属性 `policyType` を含みます。</span><span class="sxs-lookup"><span data-stu-id="15477-140">Each authorization policy contains a single required `policyType` attribute that is a string.</span></span> <span data-ttu-id="15477-141">この属性は、入力クレームのセットをクレームの別のセットに変換することを可能にする承認ポリシーを指定します。</span><span class="sxs-lookup"><span data-stu-id="15477-141">The attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="15477-142">アクセス制御は、それに基づいて許可または拒否されます。</span><span class="sxs-lookup"><span data-stu-id="15477-142">Access control can be granted or denied based on that.</span></span> <span data-ttu-id="15477-143">詳細については、「 <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="15477-143">For more information, see <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="15477-144">親要素</span><span class="sxs-lookup"><span data-stu-id="15477-144">Parent Elements</span></span>  
  
|<span data-ttu-id="15477-145">要素</span><span class="sxs-lookup"><span data-stu-id="15477-145">Element</span></span>|<span data-ttu-id="15477-146">説明</span><span class="sxs-lookup"><span data-stu-id="15477-146">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="15477-147">\<behavior></span><span class="sxs-lookup"><span data-stu-id="15477-147">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="15477-148">サービスの動作設定のコレクションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="15477-148">Contains a collection of settings for the behavior of a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="15477-149">Remarks</span><span class="sxs-lookup"><span data-stu-id="15477-149">Remarks</span></span>  
 <span data-ttu-id="15477-150">このセクションには、承認、カスタム ロール プロバイダー、および偽装に影響する要素が含まれています。</span><span class="sxs-lookup"><span data-stu-id="15477-150">This section contains elements affecting authorization, custom role providers, and impersonation.</span></span>  
  
 <span data-ttu-id="15477-151">`principalPermissionMode` 属性は、保護メソッドの使用を承認するときに使用するユーザー グループを指定します。</span><span class="sxs-lookup"><span data-stu-id="15477-151">The `principalPermissionMode` attribute specifies the groups of users to use when authorizing use of a protected method.</span></span> <span data-ttu-id="15477-152">既定値は `UseWindowsGroups` で、リソースにアクセスしようとしている ID を、"Administrators" や "Users" などの Windows グループから検索するように指定します。</span><span class="sxs-lookup"><span data-stu-id="15477-152">The default value is `UseWindowsGroups` and specifies that Windows groups, such as "Administrators" or "Users," are searched for an identity trying to access a resource.</span></span> <span data-ttu-id="15477-153">次のコードに`UseAspNetRoles`示すように、system.web > 要素の\<下に構成されているカスタムロールプロバイダーを使用するように指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="15477-153">You can also specify `UseAspNetRoles` to use a custom role provider that is configured under the \<system.web> element, as shown in the following code.</span></span>  
  
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
  
 <span data-ttu-id="15477-154">`roleProviderName` 属性で `principalPermissionMode` を使用する方法を次のコードに示します。</span><span class="sxs-lookup"><span data-stu-id="15477-154">The following code shows the `roleProviderName` used with the `principalPermissionMode` attribute.</span></span>  
  
```xml  
<behaviors>
  <behavior name="ServiceBehaviour">
    <serviceAuthorization principalPermissionMode ="UseAspNetRoles"
                          roleProviderName ="SqlProvider" />
  </behavior>
  <!-- Other configuration code not shown. -->
</behaviors>
```  
  
 <span data-ttu-id="15477-155">この構成要素の使用例については、「[サービス操作](../../../wcf/samples/authorizing-access-to-service-operations.md)と[承認ポリシー](../../../wcf/samples/authorization-policy.md)へのアクセスの承認」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="15477-155">For a detailed example of using this configuration element, see [Authorizing Access to Service Operations](../../../wcf/samples/authorizing-access-to-service-operations.md) and [Authorization Policy](../../../wcf/samples/authorization-policy.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15477-156">関連項目</span><span class="sxs-lookup"><span data-stu-id="15477-156">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
- [<span data-ttu-id="15477-157">セキュリティ動作</span><span class="sxs-lookup"><span data-stu-id="15477-157">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="15477-158">サービス操作へのアクセスの承認</span><span class="sxs-lookup"><span data-stu-id="15477-158">Authorizing Access to Service Operations</span></span>](../../../wcf/samples/authorizing-access-to-service-operations.md)
- [<span data-ttu-id="15477-159">方法: サービスのカスタム承認マネージャーを作成する</span><span class="sxs-lookup"><span data-stu-id="15477-159">How to: Create a Custom Authorization Manager for a Service</span></span>](../../../wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)
- [<span data-ttu-id="15477-160">方法: PrincipalPermissionAttribute クラスを使用してアクセスを制限する</span><span class="sxs-lookup"><span data-stu-id="15477-160">How to: Restrict Access with the PrincipalPermissionAttribute Class</span></span>](../../../wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)
- [<span data-ttu-id="15477-161">承認ポリシー</span><span class="sxs-lookup"><span data-stu-id="15477-161">Authorization Policy</span></span>](../../../wcf/samples/authorization-policy.md)
