---
title: <claimsAuthorizationManager>
ms.date: 03/30/2017
ms.assetid: 9354eee3-f692-4ad6-8427-3169686b8bcc
author: BrucePerlerMS
ms.openlocfilehash: 0718f789ff4d99fb4e2651a9a704da4248cd5f49
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91158436"
---
# \<claimsAuthorizationManager>

<span data-ttu-id="c0bd0-101">入力方向の要求に対して要求承認マネージャーを登録します。</span><span class="sxs-lookup"><span data-stu-id="c0bd0-101">Registers a claims authorization manager for the incoming claims.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<claimsAuthorizationManager>**  
  
## <a name="syntax"></a><span data-ttu-id="c0bd0-102">構文</span><span class="sxs-lookup"><span data-stu-id="c0bd0-102">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthorizationManager type = xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthorizationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c0bd0-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="c0bd0-103">Attributes and Elements</span></span>  

 <span data-ttu-id="c0bd0-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="c0bd0-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c0bd0-105">属性</span><span class="sxs-lookup"><span data-stu-id="c0bd0-105">Attributes</span></span>  
  
|<span data-ttu-id="c0bd0-106">属性</span><span class="sxs-lookup"><span data-stu-id="c0bd0-106">Attribute</span></span>|<span data-ttu-id="c0bd0-107">[説明]</span><span class="sxs-lookup"><span data-stu-id="c0bd0-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c0bd0-108">type</span><span class="sxs-lookup"><span data-stu-id="c0bd0-108">type</span></span>|<span data-ttu-id="c0bd0-109">クラスから派生するカスタム型 <xref:System.Security.Claims.ClaimsAuthorizationManager> 。</span><span class="sxs-lookup"><span data-stu-id="c0bd0-109">A custom type that derives from the <xref:System.Security.Claims.ClaimsAuthorizationManager> class.</span></span> <span data-ttu-id="c0bd0-110">属性を指定する方法の詳細については `type` 、「 [カスタム型参照](../windows-workflow-foundation/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0bd0-110">For more information about how to specify the `type` attribute, see [Custom Type References](../windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c0bd0-111">子要素</span><span class="sxs-lookup"><span data-stu-id="c0bd0-111">Child Elements</span></span>  

 <span data-ttu-id="c0bd0-112">属性が存在しない場合、 `type` または属性がクラスを参照している場合、 `type` 要素は <xref:System.Security.Claims.ClaimsAuthenticationManager> `<claimsAuthorizationManager>` 子要素を受け取りません。ただし、から派生したクラス <xref:System.Security.Claims.ClaimsAuthorizationManager> は子構成要素を定義できます。</span><span class="sxs-lookup"><span data-stu-id="c0bd0-112">If there is no `type` attribute, or if the `type` attribute references the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthorizationManager>` element does not take child elements; however, classes derived from <xref:System.Security.Claims.ClaimsAuthorizationManager> can define child configuration elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c0bd0-113">親要素</span><span class="sxs-lookup"><span data-stu-id="c0bd0-113">Parent Elements</span></span>  
  
|<span data-ttu-id="c0bd0-114">要素</span><span class="sxs-lookup"><span data-stu-id="c0bd0-114">Element</span></span>|<span data-ttu-id="c0bd0-115">説明</span><span class="sxs-lookup"><span data-stu-id="c0bd0-115">Description</span></span>|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|<span data-ttu-id="c0bd0-116">サービスレベルの id 設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="c0bd0-116">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c0bd0-117">解説</span><span class="sxs-lookup"><span data-stu-id="c0bd0-117">Remarks</span></span>  

 <span data-ttu-id="c0bd0-118">クラスによって提供される既定の動作では、 <xref:System.Security.Claims.ClaimsAuthorizationManager> 常に入力方向の要求が承認されます。</span><span class="sxs-lookup"><span data-stu-id="c0bd0-118">The default behavior provided through the <xref:System.Security.Claims.ClaimsAuthorizationManager> class always authorizes the incoming claims.</span></span> <span data-ttu-id="c0bd0-119">属性が指定されていない場合、 `type` または属性でクラスが指定されている場合、 `type` <xref:System.Security.Claims.ClaimsAuthorizationManager> 要素は `<claimsAuthorizationManager>` 子要素を受け取りません。</span><span class="sxs-lookup"><span data-stu-id="c0bd0-119">If no `type` attribute is specified or if the `type` attribute specifies the <xref:System.Security.Claims.ClaimsAuthorizationManager> class, the `<claimsAuthorizationManager>` element does not take child elements.</span></span> <span data-ttu-id="c0bd0-120">属性を指定して、 `type` クラスから派生した型を登録し、 <xref:System.Security.Claims.ClaimsAuthorizationManager> カスタム動作を実装することができます。</span><span class="sxs-lookup"><span data-stu-id="c0bd0-120">You can specify the `type` attribute to register a type derived from the <xref:System.Security.Claims.ClaimsAuthorizationManager> class to implement custom behavior.</span></span> <span data-ttu-id="c0bd0-121">派生クラスでは、要素の子要素を使用した構成をサポートできます。これを行う `<claimsAuthorizationManager>` には、メソッドをオーバーライドして <xref:System.Security.Claims.ClaimsAuthorizationManager.LoadCustomConfiguration%2A> これらの要素を処理します。</span><span class="sxs-lookup"><span data-stu-id="c0bd0-121">Derived classes can support configuration through child elements of the `<claimsAuthorizationManager>` element by overriding the <xref:System.Security.Claims.ClaimsAuthorizationManager.LoadCustomConfiguration%2A> method to handle these elements.</span></span> <span data-ttu-id="c0bd0-122">子要素に対して定義されているスキーマは、クラスのデザイナーによって作成されます。</span><span class="sxs-lookup"><span data-stu-id="c0bd0-122">The schema defined for the child elements is up to the designer of the class.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="c0bd0-123">クラスまたはクラスを使用して、 <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> コード内にクレームベースのアクセス制御を提供する場合、要素によって参照される id 構成によって、 `<federationConfiguration>` 承認の決定に使用される要求承認マネージャーとポリシーが構成されます。</span><span class="sxs-lookup"><span data-stu-id="c0bd0-123">When using the <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> or the <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> class to provide claims-based access control in your code, the identity configuration that is referenced by the `<federationConfiguration>` element configures the claims authorization manager and policy that is used to make authorization decisions.</span></span> <span data-ttu-id="c0bd0-124">これは、Windows Communication Foundation (WCF) アプリケーションや Web ベースではないアプリケーションなど、パッシブな Web シナリオではないシナリオでも当てはまります。</span><span class="sxs-lookup"><span data-stu-id="c0bd0-124">This is true, even in scenarios that are not passive Web scenarios, for example Windows Communication Foundation (WCF) applications or an application that is not Web-based.</span></span> <span data-ttu-id="c0bd0-125">アプリケーションがパッシブな Web アプリケーションでない場合は、 `<claimsAuthorizationManager>` 参照される id 構成の要素 (およびその子ポリシー要素が存在する場合) が適用される唯一の設定です。</span><span class="sxs-lookup"><span data-stu-id="c0bd0-125">If the application is not a passive Web application, the `<claimsAuthorizationManager>` element (and its child policy elements, if present) of the referenced identity configuration are the only settings applied.</span></span> <span data-ttu-id="c0bd0-126">その他すべての設定は無視されます。</span><span class="sxs-lookup"><span data-stu-id="c0bd0-126">All other settings are ignored.</span></span> <span data-ttu-id="c0bd0-127">詳細については、[\<federationConfiguration>](federationconfiguration.md) 要素を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0bd0-127">For more information, see the [\<federationConfiguration>](federationconfiguration.md) element.</span></span>  
  
 <span data-ttu-id="c0bd0-128">この要素は、 <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthorizationManager%2A?displayProperty=nameWithType> プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="c0bd0-128">This element sets the <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthorizationManager%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c0bd0-129">例</span><span class="sxs-lookup"><span data-stu-id="c0bd0-129">Example</span></span>  

 <span data-ttu-id="c0bd0-130">次の XML は、リソースアクションのペアで構成されるポリシーを実装するクレーム承認マネージャーの構成を示しています。これらのポリシーは、要求元がリソースに対してアクションを実行するために必要なクレームのブール値の組み合わせを指定します。</span><span class="sxs-lookup"><span data-stu-id="c0bd0-130">The following XML shows the configuration for a claims authorization manager that implements policy composed of resource-action pairs each of which specifies boolean combinations of the claims that a requestor must possess to perform the action on the resource.</span></span> <span data-ttu-id="c0bd0-131">このポリシーを使用できる要求承認マネージャーを実装するコードについては、「」のサンプルを参照して `ClaimsBasedAuthorization` ください。</span><span class="sxs-lookup"><span data-stu-id="c0bd0-131">The code that implements the claims authorization manager capable of using this policy can be found in the `ClaimsBasedAuthorization` sample.</span></span>  
  
```xml  
<system.identityModel>  
    <identityConfiguration>  
      <claimsAuthorizationManager type="ClaimsAuthorizationLibrary.MyClaimsAuthorizationManager, ClaimsAuthorizationLibrary">  
        <policy resource="http://localhost:28491/Developers.aspx" action="GET">  
          <or>  
            <claim claimType="http://schemas.microsoft.com/ws/2008/06/identity/claims/role" claimValue="developer" />  
            <claim claimType="http://schemas.xmlsoap.org/claims/Group" claimValue="Administrator" />  
          </or>  
        </policy>  
        <policy resource="http://localhost:28491/Administrators.aspx" action="GET">  
          <and>  
            <claim claimType="http://schemas.xmlsoap.org/claims/Group" claimValue="Administrator" />  
            <claim claimType="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/country" claimValue="USA" />  
          </and>  
        </policy>  
        <policy resource="http://localhost:28491/Default.aspx" action="GET">  
        </policy>  
        <policy resource="http://localhost:28491/" action="GET">  
        </policy>  
        <policy resource="http://localhost:28491/Claims.aspx" action="GET">  
        </policy>  
      </claimsAuthorizationManager>  
    <identityConfiguration>  
<system.identityModel>  
```
