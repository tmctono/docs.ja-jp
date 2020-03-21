---
title: <federationConfiguration>
ms.date: 03/30/2017
ms.assetid: 8b14054c-6d07-46ab-ab58-03f14beac0f2
author: BrucePerlerMS
ms.openlocfilehash: bcd8e00b770517e3faff011b4acee08ebdc5a0df
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152737"
---
# <a name="federationconfiguration"></a><span data-ttu-id="2995b-101">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="2995b-101">\<federationConfiguration></span></span>
<span data-ttu-id="2995b-102">WS フェデレーション<xref:System.IdentityModel.Services.WSFederationAuthenticationModule>プロトコルを使用してフェデレーション認証<xref:System.IdentityModel.Services.SessionAuthenticationModule>を使用する場合に、(WSFAM) と (SAM) を構成します。</span><span class="sxs-lookup"><span data-stu-id="2995b-102">Configures the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) when using federated authentication through the WS-Federation protocol.</span></span> <span data-ttu-id="2995b-103">または クラス<xref:System.Security.Claims.ClaimsAuthorizationManager>を使用してクレーム<xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute>ベースのアクセス制御を提供する場合に を構成します。 <xref:System.IdentityModel.Services.ClaimsPrincipalPermission></span><span class="sxs-lookup"><span data-stu-id="2995b-103">Configures the <xref:System.Security.Claims.ClaimsAuthorizationManager> when using the <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> or the <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> class to provide claims-based access control.</span></span>  
  
<span data-ttu-id="2995b-104">[**\<構成>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="2995b-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="2995b-105">&nbsp;&nbsp;[**\<サービス>**](system-identitymodel-services.md)</span><span class="sxs-lookup"><span data-stu-id="2995b-105">&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)</span></span>\
<span data-ttu-id="2995b-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<フェデレーション構成>**</span><span class="sxs-lookup"><span data-stu-id="2995b-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<federationConfiguration>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2995b-107">構文</span><span class="sxs-lookup"><span data-stu-id="2995b-107">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration name=xs:string identityConfigurationName=xs:string>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2995b-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="2995b-108">Attributes and Elements</span></span>  
 <span data-ttu-id="2995b-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="2995b-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2995b-110">属性</span><span class="sxs-lookup"><span data-stu-id="2995b-110">Attributes</span></span>  
  
|<span data-ttu-id="2995b-111">属性</span><span class="sxs-lookup"><span data-stu-id="2995b-111">Attribute</span></span>|<span data-ttu-id="2995b-112">説明</span><span class="sxs-lookup"><span data-stu-id="2995b-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2995b-113">name</span><span class="sxs-lookup"><span data-stu-id="2995b-113">name</span></span>|<span data-ttu-id="2995b-114">フェデレーション構成要素の名前。</span><span class="sxs-lookup"><span data-stu-id="2995b-114">The name of this federation configuration element.</span></span> <span data-ttu-id="2995b-115">この属性は、主に将来のプロトコルの拡張ポイントを提供します。</span><span class="sxs-lookup"><span data-stu-id="2995b-115">This attribute primarily provides an extensibility point for future protocols.</span></span> <span data-ttu-id="2995b-116">省略可能。</span><span class="sxs-lookup"><span data-stu-id="2995b-116">Optional.</span></span>|  
|<span data-ttu-id="2995b-117">構成名</span><span class="sxs-lookup"><span data-stu-id="2995b-117">identityConfigurationName</span></span>|<span data-ttu-id="2995b-118">[ \<identityConfiguration>](identityconfiguration.md)要素で指定されている ID 構成セクションの名前。</span><span class="sxs-lookup"><span data-stu-id="2995b-118">The name of the identity configuration section as specified in an [\<identityConfiguration>](identityconfiguration.md) element to use.</span></span> <span data-ttu-id="2995b-119">この属性を指定しない場合は、デフォルトの ID 構成セクションが使用されます。</span><span class="sxs-lookup"><span data-stu-id="2995b-119">If this attribute is not specified, the default identity configuration section is used.</span></span> <span data-ttu-id="2995b-120">省略可能。</span><span class="sxs-lookup"><span data-stu-id="2995b-120">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2995b-121">子要素</span><span class="sxs-lookup"><span data-stu-id="2995b-121">Child Elements</span></span>  
  
|<span data-ttu-id="2995b-122">要素</span><span class="sxs-lookup"><span data-stu-id="2995b-122">Element</span></span>|<span data-ttu-id="2995b-123">説明</span><span class="sxs-lookup"><span data-stu-id="2995b-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2995b-124">\<クッキーハンドラー></span><span class="sxs-lookup"><span data-stu-id="2995b-124">\<cookieHandler></span></span>](cookiehandler.md)|<span data-ttu-id="2995b-125">SAM によって使用されるクッキー ハンドラーを構成します。</span><span class="sxs-lookup"><span data-stu-id="2995b-125">Configures the cookie handler used by the SAM.</span></span> <span data-ttu-id="2995b-126">省略可能。</span><span class="sxs-lookup"><span data-stu-id="2995b-126">Optional.</span></span>|  
|[<span data-ttu-id="2995b-127">\<サービス証明書></span><span class="sxs-lookup"><span data-stu-id="2995b-127">\<serviceCertificate></span></span>](servicecertificate.md)|<span data-ttu-id="2995b-128">トークンの暗号化と復号化に使用される証明書を構成します。</span><span class="sxs-lookup"><span data-stu-id="2995b-128">Configures the certificate that is used to encrypt and decrypt tokens.</span></span> <span data-ttu-id="2995b-129">省略可能。</span><span class="sxs-lookup"><span data-stu-id="2995b-129">Optional.</span></span>|  
|[<span data-ttu-id="2995b-130">\<ws フェデレーション></span><span class="sxs-lookup"><span data-stu-id="2995b-130">\<wsFederation></span></span>](wsfederation.md)|<span data-ttu-id="2995b-131">WS フェデレーション認証モジュール (WSFAM) を構成します。</span><span class="sxs-lookup"><span data-stu-id="2995b-131">Configures the WS-Federation Authentication Module (WSFAM).</span></span> <span data-ttu-id="2995b-132">省略可能。</span><span class="sxs-lookup"><span data-stu-id="2995b-132">Optional.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2995b-133">親要素</span><span class="sxs-lookup"><span data-stu-id="2995b-133">Parent Elements</span></span>  
  
|<span data-ttu-id="2995b-134">要素</span><span class="sxs-lookup"><span data-stu-id="2995b-134">Element</span></span>|<span data-ttu-id="2995b-135">説明</span><span class="sxs-lookup"><span data-stu-id="2995b-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2995b-136">\<サービス></span><span class="sxs-lookup"><span data-stu-id="2995b-136">\<system.identityModel.services></span></span>](system-identitymodel-services.md)|<span data-ttu-id="2995b-137">WS フェデレーション プロトコルを使用した認証の構成セクション。</span><span class="sxs-lookup"><span data-stu-id="2995b-137">Configuration section for authentication using the WS-Federation protocol.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2995b-138">解説</span><span class="sxs-lookup"><span data-stu-id="2995b-138">Remarks</span></span>  
 <span data-ttu-id="2995b-139">フェデレーション\<構成>要素は、2 つの異なるシナリオで設定を提供します。</span><span class="sxs-lookup"><span data-stu-id="2995b-139">The \<federationConfiguration> element provides settings in two different scenarios:</span></span>  
  
- <span data-ttu-id="2995b-140">パッシブ Web アプリケーションで WS フェデレーションを使用する場合、要素には<xref:System.IdentityModel.Services.WSFederationAuthenticationModule>(WSFAM) と<xref:System.IdentityModel.Services.SessionAuthenticationModule>(SAM) を構成する設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="2995b-140">When using WS-Federation in a passive Web application, the element contains settings that configure the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).</span></span> <span data-ttu-id="2995b-141">また、セキュリティ トークン ハンドラーと証明書の構成に使用する ID 構成、およびクレーム承認マネージャーやクレーム認証マネージャーなどのコンポーネントも参照します。</span><span class="sxs-lookup"><span data-stu-id="2995b-141">It also references the identity configuration to be used to configure security token handlers and certificates, and components like the claims authorization manager and the claims authentication manager.</span></span>  
  
- <span data-ttu-id="2995b-142"><xref:System.IdentityModel.Services.ClaimsPrincipalPermission>または クラスを<xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute>使用してコードでクレーム ベースのアクセス制御を提供する場合、要素は、承認の決定に使用される要求承認マネージャーとポリシーを構成する ID 構成を参照します。</span><span class="sxs-lookup"><span data-stu-id="2995b-142">When using the <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> or the <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> class to provide claims-based access control in your code, the element references the identity configuration that configures the claims authorization manager and policy that is used to make authorization decisions.</span></span> <span data-ttu-id="2995b-143">これは、パッシブ Web シナリオではないシナリオでも同様です。たとえば、WCF (Windows 通信財団) アプリケーションや Web ベースではないアプリケーションなどです。</span><span class="sxs-lookup"><span data-stu-id="2995b-143">This is true, even in scenarios that are not passive Web scenarios; for example, Windows Communication Foundation (WCF) applications or an application that is not Web-based.</span></span> <span data-ttu-id="2995b-144">アプリケーションがパッシブ Web アプリケーションでない場合、`<federationConfiguration>`[\<要素](claimsauthorizationmanager.md)によって参照される ID 構成の claimsAuthorizationManager>要素 (およびその子ポリシー要素がある場合) だけが適用されます。</span><span class="sxs-lookup"><span data-stu-id="2995b-144">If the application is not a passive Web application, the [\<claimsAuthorizationManager>](claimsauthorizationmanager.md) element (and its child policy elements, if present) of the identity configuration referenced by the `<federationConfiguration>` element are the only settings applied.</span></span> <span data-ttu-id="2995b-145">他の属性はすべて無視されます。</span><span class="sxs-lookup"><span data-stu-id="2995b-145">All others are ignored.</span></span>  
  
 <span data-ttu-id="2995b-146">シナリオに関係なく、ランタイムは既定のフェデレーション構成を読み込みます。</span><span class="sxs-lookup"><span data-stu-id="2995b-146">Regardless of the scenario, the runtime loads the default federation configuration.</span></span> <span data-ttu-id="2995b-147">動作は次のように定義されます。</span><span class="sxs-lookup"><span data-stu-id="2995b-147">The behavior is defined as follows:</span></span>  
  
1. <span data-ttu-id="2995b-148">要素が存在しない`<federationConfiguration>`場合、ランタイムはフェデレーション構成を作成し、既定値を設定します。</span><span class="sxs-lookup"><span data-stu-id="2995b-148">If there is no `<federationConfiguration>` element present, the runtime creates a federation configuration and populates it with default values.</span></span> <span data-ttu-id="2995b-149">この既定のフェデレーション構成は、既定の ID 構成を参照します。</span><span class="sxs-lookup"><span data-stu-id="2995b-149">This default federation configuration will reference the default identity configuration.</span></span>  
  
2. <span data-ttu-id="2995b-150">1 つの`<federationConfiguration>`要素が存在する場合、名前が付いているか名前が付けられていないかにかかわらず、既定のフェデレーション構成になります。</span><span class="sxs-lookup"><span data-stu-id="2995b-150">If a single `<federationConfiguration>` element is present, it is the default federation configuration regardless of whether it is named or unnamed.</span></span> <span data-ttu-id="2995b-151">属性が`identityConfiguration`指定されている場合は、名前付き ID 構成が参照されます。それ以外の場合は、既定の ID 構成が参照されます。</span><span class="sxs-lookup"><span data-stu-id="2995b-151">If its `identityConfiguration` attribute is specified, the named identity configuration is referenced; otherwise, the default identity configuration is referenced.</span></span>  
  
3. <span data-ttu-id="2995b-152">名前`<federationConfiguration>`のない要素が存在する場合、その要素は既定のフェデレーション構成です。</span><span class="sxs-lookup"><span data-stu-id="2995b-152">If an unnamed `<federationConfiguration>` element is present, it is the default federation configuration.</span></span> <span data-ttu-id="2995b-153">属性が`identityConfiguration`指定されている場合は、名前付き ID 構成が参照されます。それ以外の場合は、既定の ID 構成が参照されます。</span><span class="sxs-lookup"><span data-stu-id="2995b-153">If its `identityConfiguration` attribute is specified, the named identity configuration is referenced; otherwise, the default identity configuration is referenced.</span></span>  
  
4. <span data-ttu-id="2995b-154">複数の名前`<federationConfiguration>`付き要素が存在し、`<federationConfiguration>`名前のない要素が存在しない場合は、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="2995b-154">If multiple named `<federationConfiguration>` elements are present and no unnamed `<federationConfiguration>` element is present, an exception is thrown.</span></span>  
  
 <span data-ttu-id="2995b-155">通常、1 つの`<federationConfiguration>`セクションのみが定義されます。</span><span class="sxs-lookup"><span data-stu-id="2995b-155">Typically, only a single `<federationConfiguration>` section is defined.</span></span> <span data-ttu-id="2995b-156">このセクションは、既定のフェデレーション構成です。</span><span class="sxs-lookup"><span data-stu-id="2995b-156">This section is the default federation configuration.</span></span> <span data-ttu-id="2995b-157">複数の一意の名前`<federationConfiguration>`の要素を指定できます。ただし、この場合、名前のない構成以外のフェデレーション構成をロードする場合は、 に対してハンドラーを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2995b-157">You may specify multiple, uniquely-named `<federationConfiguration>` elements; however, in this case, if you want to load a federation configuration other than the unnamed one, you must provide a handler for the.</span></span> <span data-ttu-id="2995b-158"><xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfigurationCreated>イベントを設定し<xref:System.IdentityModel.Services.Configuration.FederationConfigurationCreatedEventArgs.FederationConfiguration%2A?displayProperty=nameWithType>、ハンドラー内のプロパティを<xref:System.IdentityModel.Services.Configuration.FederationConfiguration>構成ファイル内の適切な`<federationConfiguration>`要素の値で初期化されたオブジェクトに設定します。</span><span class="sxs-lookup"><span data-stu-id="2995b-158"><xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfigurationCreated> event and set the <xref:System.IdentityModel.Services.Configuration.FederationConfigurationCreatedEventArgs.FederationConfiguration%2A?displayProperty=nameWithType> property inside the handler to a <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> object initialized with values from the appropriate `<federationConfiguration>` element in the configuration file.</span></span>  
  
 <span data-ttu-id="2995b-159">要素`<federationConfiguration>`は<xref:System.IdentityModel.Services.Configuration.FederationConfigurationElement>クラスによって表されます。</span><span class="sxs-lookup"><span data-stu-id="2995b-159">The `<federationConfiguration>` element is represented by the <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElement> class.</span></span> <span data-ttu-id="2995b-160">構成オブジェクト自体は<xref:System.IdentityModel.Services.Configuration.FederationConfiguration>、クラスによって表されます。</span><span class="sxs-lookup"><span data-stu-id="2995b-160">The configuration object itself is represented by the <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> class.</span></span> <span data-ttu-id="2995b-161">プロパティに<xref:System.IdentityModel.Services.Configuration.FederationConfiguration>単一のインスタンスが<xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType>設定され、アプリケーションのフェデレーション構成が提供されます。</span><span class="sxs-lookup"><span data-stu-id="2995b-161">A single <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> instance is set on the <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType> property and provides federated configuration for the application.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2995b-162">例</span><span class="sxs-lookup"><span data-stu-id="2995b-162">Example</span></span>  
 <span data-ttu-id="2995b-163">次の XML`<federationConfiguration>`は、WSFAM の設定を指定し、既定の Cookie ハンドラー (<xref:System.IdentityModel.Services.ChunkedCookieHandler>クラスのインスタンス) を SAM で使用することを指定する要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="2995b-163">The following XML shows a `<federationConfiguration>` element that specifies settings for the WSFAM and specifies that the default cookie handler (an instance of the <xref:System.IdentityModel.Services.ChunkedCookieHandler> class) be used by the SAM.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="2995b-164">この例では、HTTPS を使用するために Cookie ハンドラーも WSFAM も必要ありません。</span><span class="sxs-lookup"><span data-stu-id="2995b-164">In this example, neither the cookie handler nor WSFAM are required to use HTTPS.</span></span> <span data-ttu-id="2995b-165">これは、要素の`requireHttps`属性と`<wsFederation>`の`requireSsl`属性`<cookieHandlerElement>`が であるためです`false`。</span><span class="sxs-lookup"><span data-stu-id="2995b-165">This is because the `requireHttps` attribute on the `<wsFederation>` element and the `requireSsl` attribute on the `<cookieHandlerElement>` are `false`.</span></span> <span data-ttu-id="2995b-166">これらの設定は、セキュリティ上のリスクが生じる可能性があるため、ほとんどの運用環境では推奨されません。</span><span class="sxs-lookup"><span data-stu-id="2995b-166">These settings are not recommended for most production environments as they may present a security risk.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2995b-167">関連項目</span><span class="sxs-lookup"><span data-stu-id="2995b-167">See also</span></span>

- <xref:System.IdentityModel.Services.WSFederationAuthenticationModule>
- <xref:System.IdentityModel.Services.SessionAuthenticationModule>
- <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType>
- [<span data-ttu-id="2995b-168">\<id構成></span><span class="sxs-lookup"><span data-stu-id="2995b-168">\<identityConfiguration></span></span>](identityconfiguration.md)
