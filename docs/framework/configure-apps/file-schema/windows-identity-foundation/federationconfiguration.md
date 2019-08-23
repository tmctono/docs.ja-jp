---
title: <federationConfiguration>
ms.date: 03/30/2017
ms.assetid: 8b14054c-6d07-46ab-ab58-03f14beac0f2
author: BrucePerlerMS
ms.openlocfilehash: 53d6bdb34ded52e49fcc8c5de98fcd45ddabadaa
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942775"
---
# <a name="federationconfiguration"></a><span data-ttu-id="ce2eb-101">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="ce2eb-101">\<federationConfiguration></span></span>
<span data-ttu-id="ce2eb-102">Ws-federation プロトコル<xref:System.IdentityModel.Services.WSFederationAuthenticationModule>を介してフェデレーション認証を<xref:System.IdentityModel.Services.SessionAuthenticationModule>使用する場合、(wsfam) と (SAM) を構成します。</span><span class="sxs-lookup"><span data-stu-id="ce2eb-102">Configures the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) when using federated authentication through the WS-Federation protocol.</span></span> <span data-ttu-id="ce2eb-103"><xref:System.IdentityModel.Services.ClaimsPrincipalPermission>また<xref:System.Security.Claims.ClaimsAuthorizationManager> は<xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute>クラスを使用してクレームベースのアクセス制御を提供するときに、を構成します。</span><span class="sxs-lookup"><span data-stu-id="ce2eb-103">Configures the <xref:System.Security.Claims.ClaimsAuthorizationManager> when using the <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> or the <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> class to provide claims-based access control.</span></span>  
  
 <span data-ttu-id="ce2eb-104">\<system.identityModel.services></span><span class="sxs-lookup"><span data-stu-id="ce2eb-104">\<system.identityModel.services></span></span>  
<span data-ttu-id="ce2eb-105">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="ce2eb-105">\<federationConfiguration></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce2eb-106">構文</span><span class="sxs-lookup"><span data-stu-id="ce2eb-106">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration name=xs:string identityConfigurationName=xs:string>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ce2eb-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="ce2eb-107">Attributes and Elements</span></span>  
 <span data-ttu-id="ce2eb-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="ce2eb-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ce2eb-109">属性</span><span class="sxs-lookup"><span data-stu-id="ce2eb-109">Attributes</span></span>  
  
|<span data-ttu-id="ce2eb-110">属性</span><span class="sxs-lookup"><span data-stu-id="ce2eb-110">Attribute</span></span>|<span data-ttu-id="ce2eb-111">説明</span><span class="sxs-lookup"><span data-stu-id="ce2eb-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ce2eb-112">name</span><span class="sxs-lookup"><span data-stu-id="ce2eb-112">name</span></span>|<span data-ttu-id="ce2eb-113">このフェデレーション構成要素の名前。</span><span class="sxs-lookup"><span data-stu-id="ce2eb-113">The name of this federation configuration element.</span></span> <span data-ttu-id="ce2eb-114">この属性は、主に将来のプロトコルの機能拡張ポイントを提供します。</span><span class="sxs-lookup"><span data-stu-id="ce2eb-114">This attribute primarily provides an extensibility point for future protocols.</span></span> <span data-ttu-id="ce2eb-115">任意。</span><span class="sxs-lookup"><span data-stu-id="ce2eb-115">Optional.</span></span>|  
|<span data-ttu-id="ce2eb-116">identity Configurationname</span><span class="sxs-lookup"><span data-stu-id="ce2eb-116">identityConfigurationName</span></span>|<span data-ttu-id="ce2eb-117">使用するユーザー [ \<構成 >](identityconfiguration.md)要素で指定されている id 構成セクションの名前。</span><span class="sxs-lookup"><span data-stu-id="ce2eb-117">The name of the identity configuration section as specified in an [\<identityConfiguration>](identityconfiguration.md) element to use.</span></span> <span data-ttu-id="ce2eb-118">この属性が指定されていない場合は、既定の id 構成セクションが使用されます。</span><span class="sxs-lookup"><span data-stu-id="ce2eb-118">If this attribute is not specified, the default identity configuration section is used.</span></span> <span data-ttu-id="ce2eb-119">任意。</span><span class="sxs-lookup"><span data-stu-id="ce2eb-119">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ce2eb-120">子要素</span><span class="sxs-lookup"><span data-stu-id="ce2eb-120">Child Elements</span></span>  
  
|<span data-ttu-id="ce2eb-121">要素</span><span class="sxs-lookup"><span data-stu-id="ce2eb-121">Element</span></span>|<span data-ttu-id="ce2eb-122">説明</span><span class="sxs-lookup"><span data-stu-id="ce2eb-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ce2eb-123">\<cookieHandler ></span><span class="sxs-lookup"><span data-stu-id="ce2eb-123">\<cookieHandler></span></span>](cookiehandler.md)|<span data-ttu-id="ce2eb-124">SAM によって使用されるクッキーハンドラーを構成します。</span><span class="sxs-lookup"><span data-stu-id="ce2eb-124">Configures the cookie handler used by the SAM.</span></span> <span data-ttu-id="ce2eb-125">任意。</span><span class="sxs-lookup"><span data-stu-id="ce2eb-125">Optional.</span></span>|  
|[<span data-ttu-id="ce2eb-126">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="ce2eb-126">\<serviceCertificate></span></span>](servicecertificate.md)|<span data-ttu-id="ce2eb-127">トークンの暗号化と復号化に使用される証明書を構成します。</span><span class="sxs-lookup"><span data-stu-id="ce2eb-127">Configures the certificate that is used to encrypt and decrypt tokens.</span></span> <span data-ttu-id="ce2eb-128">任意。</span><span class="sxs-lookup"><span data-stu-id="ce2eb-128">Optional.</span></span>|  
|[<span data-ttu-id="ce2eb-129">\<wsFederation ></span><span class="sxs-lookup"><span data-stu-id="ce2eb-129">\<wsFederation></span></span>](wsfederation.md)|<span data-ttu-id="ce2eb-130">WS-FEDERATION 認証モジュール (WSFAM) を構成します。</span><span class="sxs-lookup"><span data-stu-id="ce2eb-130">Configures the WS-Federation Authentication Module (WSFAM).</span></span> <span data-ttu-id="ce2eb-131">任意。</span><span class="sxs-lookup"><span data-stu-id="ce2eb-131">Optional.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ce2eb-132">親要素</span><span class="sxs-lookup"><span data-stu-id="ce2eb-132">Parent Elements</span></span>  
  
|<span data-ttu-id="ce2eb-133">要素</span><span class="sxs-lookup"><span data-stu-id="ce2eb-133">Element</span></span>|<span data-ttu-id="ce2eb-134">説明</span><span class="sxs-lookup"><span data-stu-id="ce2eb-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ce2eb-135">\<system.identityModel.services></span><span class="sxs-lookup"><span data-stu-id="ce2eb-135">\<system.identityModel.services></span></span>](system-identitymodel-services.md)|<span data-ttu-id="ce2eb-136">WS-FEDERATION プロトコルを使用した認証の構成セクション。</span><span class="sxs-lookup"><span data-stu-id="ce2eb-136">Configuration section for authentication using the WS-Federation protocol.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ce2eb-137">Remarks</span><span class="sxs-lookup"><span data-stu-id="ce2eb-137">Remarks</span></span>  
 <span data-ttu-id="ce2eb-138">FederationConfiguration \<> 要素は、次の2つの異なるシナリオで設定を提供します。</span><span class="sxs-lookup"><span data-stu-id="ce2eb-138">The \<federationConfiguration> element provides settings in two different scenarios:</span></span>  
  
- <span data-ttu-id="ce2eb-139">パッシブ Web アプリケーションで ws-federation を使用する場合、要素には、 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (wsfam) <xref:System.IdentityModel.Services.SessionAuthenticationModule>と (SAM) を構成する設定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="ce2eb-139">When using WS-Federation in a passive Web application, the element contains settings that configure the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).</span></span> <span data-ttu-id="ce2eb-140">また、セキュリティトークンハンドラーと証明書の構成に使用される id 構成と、要求承認マネージャーや要求認証マネージャーなどのコンポーネントも参照しています。</span><span class="sxs-lookup"><span data-stu-id="ce2eb-140">It also references the identity configuration to be used to configure security token handlers and certificates, and components like the claims authorization manager and the claims authentication manager.</span></span>  
  
- <span data-ttu-id="ce2eb-141"><xref:System.IdentityModel.Services.ClaimsPrincipalPermission>クラスまたはクラスを使用して、コード内にクレームベースのアクセス制御を提供する場合、要素は、承認を行うために使用される要求承認マネージャーとポリシーを構成する id 構成を参照します。 <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute>行う.</span><span class="sxs-lookup"><span data-stu-id="ce2eb-141">When using the <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> or the <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> class to provide claims-based access control in your code, the element references the identity configuration that configures the claims authorization manager and policy that is used to make authorization decisions.</span></span> <span data-ttu-id="ce2eb-142">これは、パッシブな Web シナリオではないシナリオでも当てはまります。たとえば、Windows Communication Foundation (WCF) アプリケーションや、Web ベースではないアプリケーションなどです。</span><span class="sxs-lookup"><span data-stu-id="ce2eb-142">This is true, even in scenarios that are not passive Web scenarios; for example, Windows Communication Foundation (WCF) applications or an application that is not Web-based.</span></span> <span data-ttu-id="ce2eb-143">アプリケーションがパッシブな Web アプリケーション`<federationConfiguration>` [ \<](claimsauthorizationmanager.md)でない場合は、要素によって参照される id 構成の claimsAuthorizationManager > 要素とその子ポリシー要素 (存在する場合) が唯一の設定になります。適用.</span><span class="sxs-lookup"><span data-stu-id="ce2eb-143">If the application is not a passive Web application, the [\<claimsAuthorizationManager>](claimsauthorizationmanager.md) element (and its child policy elements, if present) of the identity configuration referenced by the `<federationConfiguration>` element are the only settings applied.</span></span> <span data-ttu-id="ce2eb-144">他の属性はすべて無視されます。</span><span class="sxs-lookup"><span data-stu-id="ce2eb-144">All others are ignored.</span></span>  
  
 <span data-ttu-id="ce2eb-145">シナリオに関係なく、ランタイムは既定のフェデレーション構成を読み込みます。</span><span class="sxs-lookup"><span data-stu-id="ce2eb-145">Regardless of the scenario, the runtime loads the default federation configuration.</span></span> <span data-ttu-id="ce2eb-146">動作は次のように定義されています。</span><span class="sxs-lookup"><span data-stu-id="ce2eb-146">The behavior is defined as follows:</span></span>  
  
1. <span data-ttu-id="ce2eb-147">`<federationConfiguration>`要素が存在しない場合、ランタイムはフェデレーション構成を作成し、既定値を設定します。</span><span class="sxs-lookup"><span data-stu-id="ce2eb-147">If there is no `<federationConfiguration>` element present, the runtime creates a federation configuration and populates it with default values.</span></span> <span data-ttu-id="ce2eb-148">この既定のフェデレーション構成では、既定の id 構成が参照されます。</span><span class="sxs-lookup"><span data-stu-id="ce2eb-148">This default federation configuration will reference the default identity configuration.</span></span>  
  
2. <span data-ttu-id="ce2eb-149">1つ`<federationConfiguration>`の要素が存在する場合は、名前が付けられているか名前が付いていないかに関係なく、既定のフェデレーション構成になります。</span><span class="sxs-lookup"><span data-stu-id="ce2eb-149">If a single `<federationConfiguration>` element is present, it is the default federation configuration regardless of whether it is named or unnamed.</span></span> <span data-ttu-id="ce2eb-150">`identityConfiguration`属性が指定されている場合は、名前付き id 構成が参照されます。それ以外の場合は、既定の id 構成が参照されます。</span><span class="sxs-lookup"><span data-stu-id="ce2eb-150">If its `identityConfiguration` attribute is specified, the named identity configuration is referenced; otherwise, the default identity configuration is referenced.</span></span>  
  
3. <span data-ttu-id="ce2eb-151">名前`<federationConfiguration>`のない要素が存在する場合は、既定のフェデレーション構成になります。</span><span class="sxs-lookup"><span data-stu-id="ce2eb-151">If an unnamed `<federationConfiguration>` element is present, it is the default federation configuration.</span></span> <span data-ttu-id="ce2eb-152">`identityConfiguration`属性が指定されている場合は、名前付き id 構成が参照されます。それ以外の場合は、既定の id 構成が参照されます。</span><span class="sxs-lookup"><span data-stu-id="ce2eb-152">If its `identityConfiguration` attribute is specified, the named identity configuration is referenced; otherwise, the default identity configuration is referenced.</span></span>  
  
4. <span data-ttu-id="ce2eb-153">複数の名前`<federationConfiguration>`付き要素が存在し、 `<federationConfiguration>`名前のない要素が存在しない場合は、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="ce2eb-153">If multiple named `<federationConfiguration>` elements are present and no unnamed `<federationConfiguration>` element is present, an exception is thrown.</span></span>  
  
 <span data-ttu-id="ce2eb-154">通常、1つ`<federationConfiguration>`のセクションのみが定義されます。</span><span class="sxs-lookup"><span data-stu-id="ce2eb-154">Typically, only a single `<federationConfiguration>` section is defined.</span></span> <span data-ttu-id="ce2eb-155">このセクションは、既定のフェデレーション構成です。</span><span class="sxs-lookup"><span data-stu-id="ce2eb-155">This section is the default federation configuration.</span></span> <span data-ttu-id="ce2eb-156">一意の名前`<federationConfiguration>`を持つ複数の要素を指定することもできます。ただし、この場合は、名前のないフェデレーション構成を読み込む場合は、のハンドラーを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ce2eb-156">You may specify multiple, uniquely-named `<federationConfiguration>` elements; however, in this case, if you want to load a federation configuration other than the unnamed one, you must provide a handler for the.</span></span> <span data-ttu-id="ce2eb-157"><xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfigurationCreated>イベントを発生さ<xref:System.IdentityModel.Services.Configuration.FederationConfigurationCreatedEventArgs.FederationConfiguration%2A?displayProperty=nameWithType> <xref:System.IdentityModel.Services.Configuration.FederationConfiguration>せると共に、ハンドラー内のプロパティを、構成ファイル`<federationConfiguration>`内の適切な要素の値で初期化されたオブジェクトに設定します。</span><span class="sxs-lookup"><span data-stu-id="ce2eb-157"><xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfigurationCreated> event and set the <xref:System.IdentityModel.Services.Configuration.FederationConfigurationCreatedEventArgs.FederationConfiguration%2A?displayProperty=nameWithType> property inside the handler to a <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> object initialized with values from the appropriate `<federationConfiguration>` element in the configuration file.</span></span>  
  
 <span data-ttu-id="ce2eb-158">要素は、 <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElement>クラスによって表されます。 `<federationConfiguration>`</span><span class="sxs-lookup"><span data-stu-id="ce2eb-158">The `<federationConfiguration>` element is represented by the <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElement> class.</span></span> <span data-ttu-id="ce2eb-159">構成オブジェクト自体は、 <xref:System.IdentityModel.Services.Configuration.FederationConfiguration>クラスによって表されます。</span><span class="sxs-lookup"><span data-stu-id="ce2eb-159">The configuration object itself is represented by the <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> class.</span></span> <span data-ttu-id="ce2eb-160">1つ<xref:System.IdentityModel.Services.Configuration.FederationConfiguration>のインスタンスが<xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType>プロパティに設定され、アプリケーションのフェデレーション構成が提供されます。</span><span class="sxs-lookup"><span data-stu-id="ce2eb-160">A single <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> instance is set on the <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType> property and provides federated configuration for the application.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ce2eb-161">例</span><span class="sxs-lookup"><span data-stu-id="ce2eb-161">Example</span></span>  
 <span data-ttu-id="ce2eb-162">次の XML は、 `<federationConfiguration>` wsfam の設定を指定する要素を示し、既定の cookie ハンドラー ( <xref:System.IdentityModel.Services.ChunkedCookieHandler>クラスのインスタンス) が SAM によって使用されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="ce2eb-162">The following XML shows a `<federationConfiguration>` element that specifies settings for the WSFAM and specifies that the default cookie handler (an instance of the <xref:System.IdentityModel.Services.ChunkedCookieHandler> class) be used by the SAM.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="ce2eb-163">この例では、cookie ハンドラーも WSFAM も HTTPS を使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ce2eb-163">In this example, neither the cookie handler nor WSFAM are required to use HTTPS.</span></span> <span data-ttu-id="ce2eb-164">これは、 `<wsFederation>`要素`requireHttps`の属性と`requireSsl`の`<cookieHandlerElement>`属性が`false`であるためです。</span><span class="sxs-lookup"><span data-stu-id="ce2eb-164">This is because the `requireHttps` attribute on the `<wsFederation>` element and the `requireSsl` attribute on the `<cookieHandlerElement>` are `false`.</span></span> <span data-ttu-id="ce2eb-165">ほとんどの運用環境では、セキュリティ上のリスクが生じる可能性があるため、これらの設定は推奨されません。</span><span class="sxs-lookup"><span data-stu-id="ce2eb-165">These settings are not recommended for most production environments as they may present a security risk.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ce2eb-166">関連項目</span><span class="sxs-lookup"><span data-stu-id="ce2eb-166">See also</span></span>

- <xref:System.IdentityModel.Services.WSFederationAuthenticationModule>
- <xref:System.IdentityModel.Services.SessionAuthenticationModule>
- <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType>
- [<span data-ttu-id="ce2eb-167">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="ce2eb-167">\<identityConfiguration></span></span>](identityconfiguration.md)
