---
title: <federationConfiguration>
ms.date: 03/30/2017
ms.assetid: 8b14054c-6d07-46ab-ab58-03f14beac0f2
author: BrucePerlerMS
ms.openlocfilehash: 148b2f3e12fbfbf85b800f0ca7f5dc7dc1845d24
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252001"
---
# <a name="federationconfiguration"></a><span data-ttu-id="24e4e-101">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="24e4e-101">\<federationConfiguration></span></span>
<span data-ttu-id="24e4e-102">Ws-federation プロトコル<xref:System.IdentityModel.Services.WSFederationAuthenticationModule>を介してフェデレーション認証を<xref:System.IdentityModel.Services.SessionAuthenticationModule>使用する場合、(wsfam) と (SAM) を構成します。</span><span class="sxs-lookup"><span data-stu-id="24e4e-102">Configures the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) when using federated authentication through the WS-Federation protocol.</span></span> <span data-ttu-id="24e4e-103"><xref:System.IdentityModel.Services.ClaimsPrincipalPermission>また<xref:System.Security.Claims.ClaimsAuthorizationManager> は<xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute>クラスを使用してクレームベースのアクセス制御を提供するときに、を構成します。</span><span class="sxs-lookup"><span data-stu-id="24e4e-103">Configures the <xref:System.Security.Claims.ClaimsAuthorizationManager> when using the <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> or the <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> class to provide claims-based access control.</span></span>  
  
<span data-ttu-id="24e4e-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="24e4e-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="24e4e-105">&nbsp;&nbsp;[ **\<> のシステム**](system-identitymodel-services.md)</span><span class="sxs-lookup"><span data-stu-id="24e4e-105">&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)</span></span>\
<span data-ttu-id="24e4e-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<federationConfiguration >**</span><span class="sxs-lookup"><span data-stu-id="24e4e-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<federationConfiguration>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24e4e-107">構文</span><span class="sxs-lookup"><span data-stu-id="24e4e-107">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration name=xs:string identityConfigurationName=xs:string>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="24e4e-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="24e4e-108">Attributes and Elements</span></span>  
 <span data-ttu-id="24e4e-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="24e4e-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="24e4e-110">属性</span><span class="sxs-lookup"><span data-stu-id="24e4e-110">Attributes</span></span>  
  
|<span data-ttu-id="24e4e-111">属性</span><span class="sxs-lookup"><span data-stu-id="24e4e-111">Attribute</span></span>|<span data-ttu-id="24e4e-112">説明</span><span class="sxs-lookup"><span data-stu-id="24e4e-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="24e4e-113">name</span><span class="sxs-lookup"><span data-stu-id="24e4e-113">name</span></span>|<span data-ttu-id="24e4e-114">このフェデレーション構成要素の名前。</span><span class="sxs-lookup"><span data-stu-id="24e4e-114">The name of this federation configuration element.</span></span> <span data-ttu-id="24e4e-115">この属性は、主に将来のプロトコルの機能拡張ポイントを提供します。</span><span class="sxs-lookup"><span data-stu-id="24e4e-115">This attribute primarily provides an extensibility point for future protocols.</span></span> <span data-ttu-id="24e4e-116">任意。</span><span class="sxs-lookup"><span data-stu-id="24e4e-116">Optional.</span></span>|  
|<span data-ttu-id="24e4e-117">identity Configurationname</span><span class="sxs-lookup"><span data-stu-id="24e4e-117">identityConfigurationName</span></span>|<span data-ttu-id="24e4e-118">使用するユーザー [ \<構成 >](identityconfiguration.md)要素で指定されている id 構成セクションの名前。</span><span class="sxs-lookup"><span data-stu-id="24e4e-118">The name of the identity configuration section as specified in an [\<identityConfiguration>](identityconfiguration.md) element to use.</span></span> <span data-ttu-id="24e4e-119">この属性が指定されていない場合は、既定の id 構成セクションが使用されます。</span><span class="sxs-lookup"><span data-stu-id="24e4e-119">If this attribute is not specified, the default identity configuration section is used.</span></span> <span data-ttu-id="24e4e-120">任意。</span><span class="sxs-lookup"><span data-stu-id="24e4e-120">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="24e4e-121">子要素</span><span class="sxs-lookup"><span data-stu-id="24e4e-121">Child Elements</span></span>  
  
|<span data-ttu-id="24e4e-122">要素</span><span class="sxs-lookup"><span data-stu-id="24e4e-122">Element</span></span>|<span data-ttu-id="24e4e-123">説明</span><span class="sxs-lookup"><span data-stu-id="24e4e-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="24e4e-124">\<cookieHandler ></span><span class="sxs-lookup"><span data-stu-id="24e4e-124">\<cookieHandler></span></span>](cookiehandler.md)|<span data-ttu-id="24e4e-125">SAM によって使用されるクッキーハンドラーを構成します。</span><span class="sxs-lookup"><span data-stu-id="24e4e-125">Configures the cookie handler used by the SAM.</span></span> <span data-ttu-id="24e4e-126">任意。</span><span class="sxs-lookup"><span data-stu-id="24e4e-126">Optional.</span></span>|  
|[<span data-ttu-id="24e4e-127">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="24e4e-127">\<serviceCertificate></span></span>](servicecertificate.md)|<span data-ttu-id="24e4e-128">トークンの暗号化と復号化に使用される証明書を構成します。</span><span class="sxs-lookup"><span data-stu-id="24e4e-128">Configures the certificate that is used to encrypt and decrypt tokens.</span></span> <span data-ttu-id="24e4e-129">任意。</span><span class="sxs-lookup"><span data-stu-id="24e4e-129">Optional.</span></span>|  
|[<span data-ttu-id="24e4e-130">\<wsFederation ></span><span class="sxs-lookup"><span data-stu-id="24e4e-130">\<wsFederation></span></span>](wsfederation.md)|<span data-ttu-id="24e4e-131">WS-FEDERATION 認証モジュール (WSFAM) を構成します。</span><span class="sxs-lookup"><span data-stu-id="24e4e-131">Configures the WS-Federation Authentication Module (WSFAM).</span></span> <span data-ttu-id="24e4e-132">任意。</span><span class="sxs-lookup"><span data-stu-id="24e4e-132">Optional.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="24e4e-133">親要素</span><span class="sxs-lookup"><span data-stu-id="24e4e-133">Parent Elements</span></span>  
  
|<span data-ttu-id="24e4e-134">要素</span><span class="sxs-lookup"><span data-stu-id="24e4e-134">Element</span></span>|<span data-ttu-id="24e4e-135">説明</span><span class="sxs-lookup"><span data-stu-id="24e4e-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="24e4e-136">\<system.identityModel.services></span><span class="sxs-lookup"><span data-stu-id="24e4e-136">\<system.identityModel.services></span></span>](system-identitymodel-services.md)|<span data-ttu-id="24e4e-137">WS-FEDERATION プロトコルを使用した認証の構成セクション。</span><span class="sxs-lookup"><span data-stu-id="24e4e-137">Configuration section for authentication using the WS-Federation protocol.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="24e4e-138">Remarks</span><span class="sxs-lookup"><span data-stu-id="24e4e-138">Remarks</span></span>  
 <span data-ttu-id="24e4e-139">FederationConfiguration \<> 要素は、次の2つの異なるシナリオで設定を提供します。</span><span class="sxs-lookup"><span data-stu-id="24e4e-139">The \<federationConfiguration> element provides settings in two different scenarios:</span></span>  
  
- <span data-ttu-id="24e4e-140">パッシブ Web アプリケーションで ws-federation を使用する場合、要素には、 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (wsfam) <xref:System.IdentityModel.Services.SessionAuthenticationModule>と (SAM) を構成する設定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="24e4e-140">When using WS-Federation in a passive Web application, the element contains settings that configure the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).</span></span> <span data-ttu-id="24e4e-141">また、セキュリティトークンハンドラーと証明書の構成に使用される id 構成と、要求承認マネージャーや要求認証マネージャーなどのコンポーネントも参照しています。</span><span class="sxs-lookup"><span data-stu-id="24e4e-141">It also references the identity configuration to be used to configure security token handlers and certificates, and components like the claims authorization manager and the claims authentication manager.</span></span>  
  
- <span data-ttu-id="24e4e-142"><xref:System.IdentityModel.Services.ClaimsPrincipalPermission>クラスまたはクラスを使用して、コード内にクレームベースのアクセス制御を提供する場合、要素は、承認を行うために使用される要求承認マネージャーとポリシーを構成する id 構成を参照します。 <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute>行う.</span><span class="sxs-lookup"><span data-stu-id="24e4e-142">When using the <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> or the <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> class to provide claims-based access control in your code, the element references the identity configuration that configures the claims authorization manager and policy that is used to make authorization decisions.</span></span> <span data-ttu-id="24e4e-143">これは、パッシブな Web シナリオではないシナリオでも当てはまります。たとえば、Windows Communication Foundation (WCF) アプリケーションや、Web ベースではないアプリケーションなどです。</span><span class="sxs-lookup"><span data-stu-id="24e4e-143">This is true, even in scenarios that are not passive Web scenarios; for example, Windows Communication Foundation (WCF) applications or an application that is not Web-based.</span></span> <span data-ttu-id="24e4e-144">アプリケーションがパッシブな Web アプリケーション`<federationConfiguration>` [ \<](claimsauthorizationmanager.md)でない場合は、要素によって参照される id 構成の claimsAuthorizationManager > 要素とその子ポリシー要素 (存在する場合) が唯一の設定になります。適用.</span><span class="sxs-lookup"><span data-stu-id="24e4e-144">If the application is not a passive Web application, the [\<claimsAuthorizationManager>](claimsauthorizationmanager.md) element (and its child policy elements, if present) of the identity configuration referenced by the `<federationConfiguration>` element are the only settings applied.</span></span> <span data-ttu-id="24e4e-145">他の属性はすべて無視されます。</span><span class="sxs-lookup"><span data-stu-id="24e4e-145">All others are ignored.</span></span>  
  
 <span data-ttu-id="24e4e-146">シナリオに関係なく、ランタイムは既定のフェデレーション構成を読み込みます。</span><span class="sxs-lookup"><span data-stu-id="24e4e-146">Regardless of the scenario, the runtime loads the default federation configuration.</span></span> <span data-ttu-id="24e4e-147">動作は次のように定義されています。</span><span class="sxs-lookup"><span data-stu-id="24e4e-147">The behavior is defined as follows:</span></span>  
  
1. <span data-ttu-id="24e4e-148">`<federationConfiguration>`要素が存在しない場合、ランタイムはフェデレーション構成を作成し、既定値を設定します。</span><span class="sxs-lookup"><span data-stu-id="24e4e-148">If there is no `<federationConfiguration>` element present, the runtime creates a federation configuration and populates it with default values.</span></span> <span data-ttu-id="24e4e-149">この既定のフェデレーション構成では、既定の id 構成が参照されます。</span><span class="sxs-lookup"><span data-stu-id="24e4e-149">This default federation configuration will reference the default identity configuration.</span></span>  
  
2. <span data-ttu-id="24e4e-150">1つ`<federationConfiguration>`の要素が存在する場合は、名前が付けられているか名前が付いていないかに関係なく、既定のフェデレーション構成になります。</span><span class="sxs-lookup"><span data-stu-id="24e4e-150">If a single `<federationConfiguration>` element is present, it is the default federation configuration regardless of whether it is named or unnamed.</span></span> <span data-ttu-id="24e4e-151">`identityConfiguration`属性が指定されている場合は、名前付き id 構成が参照されます。それ以外の場合は、既定の id 構成が参照されます。</span><span class="sxs-lookup"><span data-stu-id="24e4e-151">If its `identityConfiguration` attribute is specified, the named identity configuration is referenced; otherwise, the default identity configuration is referenced.</span></span>  
  
3. <span data-ttu-id="24e4e-152">名前`<federationConfiguration>`のない要素が存在する場合は、既定のフェデレーション構成になります。</span><span class="sxs-lookup"><span data-stu-id="24e4e-152">If an unnamed `<federationConfiguration>` element is present, it is the default federation configuration.</span></span> <span data-ttu-id="24e4e-153">`identityConfiguration`属性が指定されている場合は、名前付き id 構成が参照されます。それ以外の場合は、既定の id 構成が参照されます。</span><span class="sxs-lookup"><span data-stu-id="24e4e-153">If its `identityConfiguration` attribute is specified, the named identity configuration is referenced; otherwise, the default identity configuration is referenced.</span></span>  
  
4. <span data-ttu-id="24e4e-154">複数の名前`<federationConfiguration>`付き要素が存在し、 `<federationConfiguration>`名前のない要素が存在しない場合は、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="24e4e-154">If multiple named `<federationConfiguration>` elements are present and no unnamed `<federationConfiguration>` element is present, an exception is thrown.</span></span>  
  
 <span data-ttu-id="24e4e-155">通常、1つ`<federationConfiguration>`のセクションのみが定義されます。</span><span class="sxs-lookup"><span data-stu-id="24e4e-155">Typically, only a single `<federationConfiguration>` section is defined.</span></span> <span data-ttu-id="24e4e-156">このセクションは、既定のフェデレーション構成です。</span><span class="sxs-lookup"><span data-stu-id="24e4e-156">This section is the default federation configuration.</span></span> <span data-ttu-id="24e4e-157">一意の名前`<federationConfiguration>`を持つ複数の要素を指定することもできます。ただし、この場合は、名前のないフェデレーション構成を読み込む場合は、のハンドラーを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="24e4e-157">You may specify multiple, uniquely-named `<federationConfiguration>` elements; however, in this case, if you want to load a federation configuration other than the unnamed one, you must provide a handler for the.</span></span> <span data-ttu-id="24e4e-158"><xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfigurationCreated>イベントを発生さ<xref:System.IdentityModel.Services.Configuration.FederationConfigurationCreatedEventArgs.FederationConfiguration%2A?displayProperty=nameWithType> <xref:System.IdentityModel.Services.Configuration.FederationConfiguration>せると共に、ハンドラー内のプロパティを、構成ファイル`<federationConfiguration>`内の適切な要素の値で初期化されたオブジェクトに設定します。</span><span class="sxs-lookup"><span data-stu-id="24e4e-158"><xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfigurationCreated> event and set the <xref:System.IdentityModel.Services.Configuration.FederationConfigurationCreatedEventArgs.FederationConfiguration%2A?displayProperty=nameWithType> property inside the handler to a <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> object initialized with values from the appropriate `<federationConfiguration>` element in the configuration file.</span></span>  
  
 <span data-ttu-id="24e4e-159">要素は、 <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElement>クラスによって表されます。 `<federationConfiguration>`</span><span class="sxs-lookup"><span data-stu-id="24e4e-159">The `<federationConfiguration>` element is represented by the <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElement> class.</span></span> <span data-ttu-id="24e4e-160">構成オブジェクト自体は、 <xref:System.IdentityModel.Services.Configuration.FederationConfiguration>クラスによって表されます。</span><span class="sxs-lookup"><span data-stu-id="24e4e-160">The configuration object itself is represented by the <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> class.</span></span> <span data-ttu-id="24e4e-161">1つ<xref:System.IdentityModel.Services.Configuration.FederationConfiguration>のインスタンスが<xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType>プロパティに設定され、アプリケーションのフェデレーション構成が提供されます。</span><span class="sxs-lookup"><span data-stu-id="24e4e-161">A single <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> instance is set on the <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType> property and provides federated configuration for the application.</span></span>  
  
## <a name="example"></a><span data-ttu-id="24e4e-162">例</span><span class="sxs-lookup"><span data-stu-id="24e4e-162">Example</span></span>  
 <span data-ttu-id="24e4e-163">次の XML は、 `<federationConfiguration>` wsfam の設定を指定する要素を示し、既定の cookie ハンドラー ( <xref:System.IdentityModel.Services.ChunkedCookieHandler>クラスのインスタンス) が SAM によって使用されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="24e4e-163">The following XML shows a `<federationConfiguration>` element that specifies settings for the WSFAM and specifies that the default cookie handler (an instance of the <xref:System.IdentityModel.Services.ChunkedCookieHandler> class) be used by the SAM.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="24e4e-164">この例では、cookie ハンドラーも WSFAM も HTTPS を使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="24e4e-164">In this example, neither the cookie handler nor WSFAM are required to use HTTPS.</span></span> <span data-ttu-id="24e4e-165">これは、 `<wsFederation>`要素`requireHttps`の属性と`requireSsl`の`<cookieHandlerElement>`属性が`false`であるためです。</span><span class="sxs-lookup"><span data-stu-id="24e4e-165">This is because the `requireHttps` attribute on the `<wsFederation>` element and the `requireSsl` attribute on the `<cookieHandlerElement>` are `false`.</span></span> <span data-ttu-id="24e4e-166">ほとんどの運用環境では、セキュリティ上のリスクが生じる可能性があるため、これらの設定は推奨されません。</span><span class="sxs-lookup"><span data-stu-id="24e4e-166">These settings are not recommended for most production environments as they may present a security risk.</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <wsFederation passiveRedirectEnabled="true"   
      issuer="http://localhost:15839/wsFederationSTS/Issue"   
      realm="http://localhost:50969/" reply="http://localhost:50969/"   
      requireHttps="false"   
      signOutReply="http://localhost:50969/SignedOutPage.html"   
      signOutQueryString="Param1=value2&Param2=value2"   
      persistentCookiesOnPassiveRedirects="true" />  
    <cookieHandler requireSsl="false" />  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="see-also"></a><span data-ttu-id="24e4e-167">関連項目</span><span class="sxs-lookup"><span data-stu-id="24e4e-167">See also</span></span>

- <xref:System.IdentityModel.Services.WSFederationAuthenticationModule>
- <xref:System.IdentityModel.Services.SessionAuthenticationModule>
- <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType>
- [<span data-ttu-id="24e4e-168">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="24e4e-168">\<identityConfiguration></span></span>](identityconfiguration.md)
