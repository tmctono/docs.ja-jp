---
title: <claimsAuthorizationManager>
ms.date: 03/30/2017
ms.assetid: 9354eee3-f692-4ad6-8427-3169686b8bcc
author: BrucePerlerMS
ms.openlocfilehash: 74ca031f7017d51adaa7a71593f537b64abbeae6
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942889"
---
# <a name="claimsauthorizationmanager"></a><span data-ttu-id="6afa5-101">\<claimsAuthorizationManager ></span><span class="sxs-lookup"><span data-stu-id="6afa5-101">\<claimsAuthorizationManager></span></span>
<span data-ttu-id="6afa5-102">入力方向の要求に対して要求承認マネージャーを登録します。</span><span class="sxs-lookup"><span data-stu-id="6afa5-102">Registers a claims authorization manager for the incoming claims.</span></span>  
  
 <span data-ttu-id="6afa5-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="6afa5-103">\<system.identityModel></span></span>  
<span data-ttu-id="6afa5-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="6afa5-104">\<identityConfiguration></span></span>  
<span data-ttu-id="6afa5-105">\<claimsAuthorizationManager ></span><span class="sxs-lookup"><span data-stu-id="6afa5-105">\<claimsAuthorizationManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6afa5-106">構文</span><span class="sxs-lookup"><span data-stu-id="6afa5-106">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthorizationManager type = xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthorizationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6afa5-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="6afa5-107">Attributes and Elements</span></span>  
 <span data-ttu-id="6afa5-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="6afa5-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6afa5-109">属性</span><span class="sxs-lookup"><span data-stu-id="6afa5-109">Attributes</span></span>  
  
|<span data-ttu-id="6afa5-110">属性</span><span class="sxs-lookup"><span data-stu-id="6afa5-110">Attribute</span></span>|<span data-ttu-id="6afa5-111">説明</span><span class="sxs-lookup"><span data-stu-id="6afa5-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6afa5-112">種類</span><span class="sxs-lookup"><span data-stu-id="6afa5-112">type</span></span>|<span data-ttu-id="6afa5-113"><xref:System.Security.Claims.ClaimsAuthorizationManager>クラスから派生するカスタム型。</span><span class="sxs-lookup"><span data-stu-id="6afa5-113">A custom type that derives from the <xref:System.Security.Claims.ClaimsAuthorizationManager> class.</span></span> <span data-ttu-id="6afa5-114">`type`属性を指定する方法の詳細については、「[カスタム型参照](../windows-workflow-foundation/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6afa5-114">For more information about how to specify the `type` attribute, see [Custom Type References](../windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6afa5-115">子要素</span><span class="sxs-lookup"><span data-stu-id="6afa5-115">Child Elements</span></span>  
 <span data-ttu-id="6afa5-116">`type`属性が存在しない場合、または`type`属性が<xref:System.Security.Claims.ClaimsAuthenticationManager>クラスを`<claimsAuthorizationManager>`参照している場合、要素は子要素を受け取りません<xref:System.Security.Claims.ClaimsAuthorizationManager> 。ただし、から派生したクラスは子構成要素を定義できます。</span><span class="sxs-lookup"><span data-stu-id="6afa5-116">If there is no `type` attribute, or if the `type` attribute references the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthorizationManager>` element does not take child elements; however, classes derived from <xref:System.Security.Claims.ClaimsAuthorizationManager> can define child configuration elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6afa5-117">親要素</span><span class="sxs-lookup"><span data-stu-id="6afa5-117">Parent Elements</span></span>  
  
|<span data-ttu-id="6afa5-118">要素</span><span class="sxs-lookup"><span data-stu-id="6afa5-118">Element</span></span>|<span data-ttu-id="6afa5-119">説明</span><span class="sxs-lookup"><span data-stu-id="6afa5-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6afa5-120">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="6afa5-120">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="6afa5-121">サービスレベルの id 設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="6afa5-121">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6afa5-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="6afa5-122">Remarks</span></span>  
 <span data-ttu-id="6afa5-123">クラスに<xref:System.Security.Claims.ClaimsAuthorizationManager>よって提供される既定の動作では、常に入力方向の要求が承認されます。</span><span class="sxs-lookup"><span data-stu-id="6afa5-123">The default behavior provided through the <xref:System.Security.Claims.ClaimsAuthorizationManager> class always authorizes the incoming claims.</span></span> <span data-ttu-id="6afa5-124">属性が指定されていない`type`場合、また<xref:System.Security.Claims.ClaimsAuthorizationManager>は属性で`<claimsAuthorizationManager>`クラスが指定されている場合、要素は子要素を受け取りません。 `type`</span><span class="sxs-lookup"><span data-stu-id="6afa5-124">If no `type` attribute is specified or if the `type` attribute specifies the <xref:System.Security.Claims.ClaimsAuthorizationManager> class, the `<claimsAuthorizationManager>` element does not take child elements.</span></span> <span data-ttu-id="6afa5-125">`type`属性を指定して、 <xref:System.Security.Claims.ClaimsAuthorizationManager>クラスから派生した型を登録し、カスタム動作を実装することができます。</span><span class="sxs-lookup"><span data-stu-id="6afa5-125">You can specify the `type` attribute to register a type derived from the <xref:System.Security.Claims.ClaimsAuthorizationManager> class to implement custom behavior.</span></span> <span data-ttu-id="6afa5-126">派生クラスでは、 `<claimsAuthorizationManager>`要素の子要素を使用した構成をサポートできます。これを行うには、 <xref:System.Security.Claims.ClaimsAuthorizationManager.LoadCustomConfiguration%2A>メソッドをオーバーライドしてこれらの要素を処理します。</span><span class="sxs-lookup"><span data-stu-id="6afa5-126">Derived classes can support configuration through child elements of the `<claimsAuthorizationManager>` element by overriding the <xref:System.Security.Claims.ClaimsAuthorizationManager.LoadCustomConfiguration%2A> method to handle these elements.</span></span> <span data-ttu-id="6afa5-127">子要素に対して定義されているスキーマは、クラスのデザイナーによって作成されます。</span><span class="sxs-lookup"><span data-stu-id="6afa5-127">The schema defined for the child elements is up to the designer of the class.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="6afa5-128">クラスまたは<xref:System.IdentityModel.Services.ClaimsPrincipalPermission>クラスを使用して、コードにクレームベースのアクセス制御を提供する場合、 `<federationConfiguration>`要素によって参照される id 構成によって、要求承認マネージャーと、 <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute>承認の決定。</span><span class="sxs-lookup"><span data-stu-id="6afa5-128">When using the <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> or the <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> class to provide claims-based access control in your code, the identity configuration that is referenced by the `<federationConfiguration>` element configures the claims authorization manager and policy that is used to make authorization decisions.</span></span> <span data-ttu-id="6afa5-129">これは、Windows Communication Foundation (WCF) アプリケーションや Web ベースではないアプリケーションなど、パッシブな Web シナリオではないシナリオでも当てはまります。</span><span class="sxs-lookup"><span data-stu-id="6afa5-129">This is true, even in scenarios that are not passive Web scenarios, for example Windows Communication Foundation (WCF) applications or an application that is not Web-based.</span></span> <span data-ttu-id="6afa5-130">アプリケーションがパッシブな Web アプリケーション`<claimsAuthorizationManager>`でない場合は、参照される id 構成の要素 (およびその子ポリシー要素が存在する場合) が適用される唯一の設定です。</span><span class="sxs-lookup"><span data-stu-id="6afa5-130">If the application is not a passive Web application, the `<claimsAuthorizationManager>` element (and its child policy elements, if present) of the referenced identity configuration are the only settings applied.</span></span> <span data-ttu-id="6afa5-131">その他の設定はすべて無視されます。</span><span class="sxs-lookup"><span data-stu-id="6afa5-131">All other settings are ignored.</span></span> <span data-ttu-id="6afa5-132">詳細については、「 [ \<federationConfiguration >](federationconfiguration.md)要素」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6afa5-132">For more information, see the [\<federationConfiguration>](federationconfiguration.md) element.</span></span>  
  
 <span data-ttu-id="6afa5-133">この要素は、 <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthorizationManager%2A?displayProperty=nameWithType>プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="6afa5-133">This element sets the <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthorizationManager%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6afa5-134">例</span><span class="sxs-lookup"><span data-stu-id="6afa5-134">Example</span></span>  
 <span data-ttu-id="6afa5-135">次の XML は、リソースアクションのペアで構成されるポリシーを実装するクレーム承認マネージャーの構成を示しています。これらのポリシーは、要求元がリソースに対してアクションを実行するために必要なクレームのブール値の組み合わせを指定します。</span><span class="sxs-lookup"><span data-stu-id="6afa5-135">The following XML shows the configuration for a claims authorization manager that implements policy composed of resource-action pairs each of which specifies boolean combinations of the claims that a requestor must possess to perform the action on the resource.</span></span> <span data-ttu-id="6afa5-136">このポリシーを使用できる要求承認マネージャーを実装するコードについては、「 `ClaimsBasedAuthorization` 」のサンプルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6afa5-136">The code that implements the claims authorization manager capable of using this policy can be found in the `ClaimsBasedAuthorization` sample.</span></span>  
  
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
