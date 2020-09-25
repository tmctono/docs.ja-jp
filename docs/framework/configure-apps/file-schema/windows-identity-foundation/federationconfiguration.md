---
title: <federationConfiguration>
ms.date: 03/30/2017
ms.assetid: 8b14054c-6d07-46ab-ab58-03f14beac0f2
author: BrucePerlerMS
ms.openlocfilehash: 39e96a161a2e75d5f00b73f6b08b1e4a0c109aee
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201357"
---
# \<federationConfiguration>

<span data-ttu-id="a0c9d-101"><xref:System.IdentityModel.Services.WSFederationAuthenticationModule> <xref:System.IdentityModel.Services.SessionAuthenticationModule> Ws-federation プロトコルを介してフェデレーション認証を使用する場合、(wsfam) と (SAM) を構成します。</span><span class="sxs-lookup"><span data-stu-id="a0c9d-101">Configures the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) when using federated authentication through the WS-Federation protocol.</span></span> <span data-ttu-id="a0c9d-102"><xref:System.Security.Claims.ClaimsAuthorizationManager> <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> またはクラスを使用して <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> クレームベースのアクセス制御を提供するときに、を構成します。</span><span class="sxs-lookup"><span data-stu-id="a0c9d-102">Configures the <xref:System.Security.Claims.ClaimsAuthorizationManager> when using the <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> or the <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> class to provide claims-based access control.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<federationConfiguration>**  
  
## <a name="syntax"></a><span data-ttu-id="a0c9d-103">構文</span><span class="sxs-lookup"><span data-stu-id="a0c9d-103">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration name=xs:string identityConfigurationName=xs:string>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a0c9d-104">属性および要素</span><span class="sxs-lookup"><span data-stu-id="a0c9d-104">Attributes and Elements</span></span>  

 <span data-ttu-id="a0c9d-105">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="a0c9d-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a0c9d-106">属性</span><span class="sxs-lookup"><span data-stu-id="a0c9d-106">Attributes</span></span>  
  
|<span data-ttu-id="a0c9d-107">属性</span><span class="sxs-lookup"><span data-stu-id="a0c9d-107">Attribute</span></span>|<span data-ttu-id="a0c9d-108">説明</span><span class="sxs-lookup"><span data-stu-id="a0c9d-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a0c9d-109">name</span><span class="sxs-lookup"><span data-stu-id="a0c9d-109">name</span></span>|<span data-ttu-id="a0c9d-110">フェデレーション構成要素の名前。</span><span class="sxs-lookup"><span data-stu-id="a0c9d-110">The name of this federation configuration element.</span></span> <span data-ttu-id="a0c9d-111">この属性は、主に将来のプロトコルの機能拡張ポイントを提供します。</span><span class="sxs-lookup"><span data-stu-id="a0c9d-111">This attribute primarily provides an extensibility point for future protocols.</span></span> <span data-ttu-id="a0c9d-112">省略可能。</span><span class="sxs-lookup"><span data-stu-id="a0c9d-112">Optional.</span></span>|  
|<span data-ttu-id="a0c9d-113">identity Configurationname</span><span class="sxs-lookup"><span data-stu-id="a0c9d-113">identityConfigurationName</span></span>|<span data-ttu-id="a0c9d-114">使用する要素で指定されている id 構成セクションの名前 [\<identityConfiguration>](identityconfiguration.md) 。</span><span class="sxs-lookup"><span data-stu-id="a0c9d-114">The name of the identity configuration section as specified in an [\<identityConfiguration>](identityconfiguration.md) element to use.</span></span> <span data-ttu-id="a0c9d-115">この属性が指定されていない場合は、既定の id 構成セクションが使用されます。</span><span class="sxs-lookup"><span data-stu-id="a0c9d-115">If this attribute is not specified, the default identity configuration section is used.</span></span> <span data-ttu-id="a0c9d-116">省略可能。</span><span class="sxs-lookup"><span data-stu-id="a0c9d-116">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a0c9d-117">子要素</span><span class="sxs-lookup"><span data-stu-id="a0c9d-117">Child Elements</span></span>  
  
|<span data-ttu-id="a0c9d-118">要素</span><span class="sxs-lookup"><span data-stu-id="a0c9d-118">Element</span></span>|<span data-ttu-id="a0c9d-119">説明</span><span class="sxs-lookup"><span data-stu-id="a0c9d-119">Description</span></span>|  
|-------------|-----------------|  
|[\<cookieHandler>](cookiehandler.md)|<span data-ttu-id="a0c9d-120">SAM によって使用されるクッキーハンドラーを構成します。</span><span class="sxs-lookup"><span data-stu-id="a0c9d-120">Configures the cookie handler used by the SAM.</span></span> <span data-ttu-id="a0c9d-121">省略可能。</span><span class="sxs-lookup"><span data-stu-id="a0c9d-121">Optional.</span></span>|  
|[\<serviceCertificate>](servicecertificate.md)|<span data-ttu-id="a0c9d-122">トークンの暗号化と復号化に使用される証明書を構成します。</span><span class="sxs-lookup"><span data-stu-id="a0c9d-122">Configures the certificate that is used to encrypt and decrypt tokens.</span></span> <span data-ttu-id="a0c9d-123">省略可能。</span><span class="sxs-lookup"><span data-stu-id="a0c9d-123">Optional.</span></span>|  
|[\<wsFederation>](wsfederation.md)|<span data-ttu-id="a0c9d-124">WS-FEDERATION 認証モジュール (WSFAM) を構成します。</span><span class="sxs-lookup"><span data-stu-id="a0c9d-124">Configures the WS-Federation Authentication Module (WSFAM).</span></span> <span data-ttu-id="a0c9d-125">省略可能。</span><span class="sxs-lookup"><span data-stu-id="a0c9d-125">Optional.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a0c9d-126">親要素</span><span class="sxs-lookup"><span data-stu-id="a0c9d-126">Parent Elements</span></span>  
  
|<span data-ttu-id="a0c9d-127">要素</span><span class="sxs-lookup"><span data-stu-id="a0c9d-127">Element</span></span>|<span data-ttu-id="a0c9d-128">説明</span><span class="sxs-lookup"><span data-stu-id="a0c9d-128">Description</span></span>|  
|-------------|-----------------|  
|[\<system.identityModel.services>](system-identitymodel-services.md)|<span data-ttu-id="a0c9d-129">WS-FEDERATION プロトコルを使用した認証の構成セクション。</span><span class="sxs-lookup"><span data-stu-id="a0c9d-129">Configuration section for authentication using the WS-Federation protocol.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a0c9d-130">解説</span><span class="sxs-lookup"><span data-stu-id="a0c9d-130">Remarks</span></span>  

 <span data-ttu-id="a0c9d-131">要素は、 \<federationConfiguration> 2 つの異なるシナリオで設定を提供します。</span><span class="sxs-lookup"><span data-stu-id="a0c9d-131">The \<federationConfiguration> element provides settings in two different scenarios:</span></span>  
  
- <span data-ttu-id="a0c9d-132">パッシブ Web アプリケーションで WS-FEDERATION を使用する場合、要素には、 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (wsfam) と (SAM) を構成する設定が含まれ <xref:System.IdentityModel.Services.SessionAuthenticationModule> ます。</span><span class="sxs-lookup"><span data-stu-id="a0c9d-132">When using WS-Federation in a passive Web application, the element contains settings that configure the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).</span></span> <span data-ttu-id="a0c9d-133">また、セキュリティトークンハンドラーと証明書の構成に使用される id 構成と、要求承認マネージャーや要求認証マネージャーなどのコンポーネントも参照しています。</span><span class="sxs-lookup"><span data-stu-id="a0c9d-133">It also references the identity configuration to be used to configure security token handlers and certificates, and components like the claims authorization manager and the claims authentication manager.</span></span>  
  
- <span data-ttu-id="a0c9d-134">クラスまたはクラスを使用して、 <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> コード内にクレームベースのアクセス制御を提供する場合、要素は、承認の決定に使用されるクレーム承認マネージャーとポリシーを構成する id 構成を参照します。</span><span class="sxs-lookup"><span data-stu-id="a0c9d-134">When using the <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> or the <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> class to provide claims-based access control in your code, the element references the identity configuration that configures the claims authorization manager and policy that is used to make authorization decisions.</span></span> <span data-ttu-id="a0c9d-135">これは、パッシブな Web シナリオではないシナリオでも当てはまります。たとえば、Windows Communication Foundation (WCF) アプリケーションや、Web ベースではないアプリケーションなどです。</span><span class="sxs-lookup"><span data-stu-id="a0c9d-135">This is true, even in scenarios that are not passive Web scenarios; for example, Windows Communication Foundation (WCF) applications or an application that is not Web-based.</span></span> <span data-ttu-id="a0c9d-136">アプリケーションがパッシブな Web アプリケーションでない場合は、要素 [\<claimsAuthorizationManager>](claimsauthorizationmanager.md) (およびその子ポリシー要素が存在する場合) は、要素によって参照される id 構成に適用される `<federationConfiguration>` 唯一の設定です。</span><span class="sxs-lookup"><span data-stu-id="a0c9d-136">If the application is not a passive Web application, the [\<claimsAuthorizationManager>](claimsauthorizationmanager.md) element (and its child policy elements, if present) of the identity configuration referenced by the `<federationConfiguration>` element are the only settings applied.</span></span> <span data-ttu-id="a0c9d-137">他の属性はすべて無視されます。</span><span class="sxs-lookup"><span data-stu-id="a0c9d-137">All others are ignored.</span></span>  
  
 <span data-ttu-id="a0c9d-138">シナリオに関係なく、ランタイムは既定のフェデレーション構成を読み込みます。</span><span class="sxs-lookup"><span data-stu-id="a0c9d-138">Regardless of the scenario, the runtime loads the default federation configuration.</span></span> <span data-ttu-id="a0c9d-139">動作は次のように定義されています。</span><span class="sxs-lookup"><span data-stu-id="a0c9d-139">The behavior is defined as follows:</span></span>  
  
1. <span data-ttu-id="a0c9d-140">要素が存在しない場合 `<federationConfiguration>` 、ランタイムはフェデレーション構成を作成し、既定値を設定します。</span><span class="sxs-lookup"><span data-stu-id="a0c9d-140">If there is no `<federationConfiguration>` element present, the runtime creates a federation configuration and populates it with default values.</span></span> <span data-ttu-id="a0c9d-141">この既定のフェデレーション構成では、既定の id 構成が参照されます。</span><span class="sxs-lookup"><span data-stu-id="a0c9d-141">This default federation configuration will reference the default identity configuration.</span></span>  
  
2. <span data-ttu-id="a0c9d-142">1つの `<federationConfiguration>` 要素が存在する場合は、名前が付けられているか名前が付いていないかに関係なく、既定のフェデレーション構成になります。</span><span class="sxs-lookup"><span data-stu-id="a0c9d-142">If a single `<federationConfiguration>` element is present, it is the default federation configuration regardless of whether it is named or unnamed.</span></span> <span data-ttu-id="a0c9d-143">`identityConfiguration`属性が指定されている場合は、名前付き id 構成が参照されます。それ以外の場合は、既定の id 構成が参照されます。</span><span class="sxs-lookup"><span data-stu-id="a0c9d-143">If its `identityConfiguration` attribute is specified, the named identity configuration is referenced; otherwise, the default identity configuration is referenced.</span></span>  
  
3. <span data-ttu-id="a0c9d-144">名前のない `<federationConfiguration>` 要素が存在する場合は、既定のフェデレーション構成になります。</span><span class="sxs-lookup"><span data-stu-id="a0c9d-144">If an unnamed `<federationConfiguration>` element is present, it is the default federation configuration.</span></span> <span data-ttu-id="a0c9d-145">`identityConfiguration`属性が指定されている場合は、名前付き id 構成が参照されます。それ以外の場合は、既定の id 構成が参照されます。</span><span class="sxs-lookup"><span data-stu-id="a0c9d-145">If its `identityConfiguration` attribute is specified, the named identity configuration is referenced; otherwise, the default identity configuration is referenced.</span></span>  
  
4. <span data-ttu-id="a0c9d-146">複数の名前付き `<federationConfiguration>` 要素が存在し、名前のない要素が存在しない場合は `<federationConfiguration>` 、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="a0c9d-146">If multiple named `<federationConfiguration>` elements are present and no unnamed `<federationConfiguration>` element is present, an exception is thrown.</span></span>  
  
 <span data-ttu-id="a0c9d-147">通常、1つの `<federationConfiguration>` セクションのみが定義されます。</span><span class="sxs-lookup"><span data-stu-id="a0c9d-147">Typically, only a single `<federationConfiguration>` section is defined.</span></span> <span data-ttu-id="a0c9d-148">このセクションは、既定のフェデレーション構成です。</span><span class="sxs-lookup"><span data-stu-id="a0c9d-148">This section is the default federation configuration.</span></span> <span data-ttu-id="a0c9d-149">一意の名前を持つ複数の要素を指定することもできます `<federationConfiguration>` 。ただし、この場合は、名前のないフェデレーション構成を読み込む場合は、のハンドラーを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a0c9d-149">You may specify multiple, uniquely-named `<federationConfiguration>` elements; however, in this case, if you want to load a federation configuration other than the unnamed one, you must provide a handler for the.</span></span> <span data-ttu-id="a0c9d-150"><xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfigurationCreated> イベントを発生さ <xref:System.IdentityModel.Services.Configuration.FederationConfigurationCreatedEventArgs.FederationConfiguration%2A?displayProperty=nameWithType> せると共に、ハンドラー内のプロパティを、 <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> 構成ファイル内の適切な要素の値で初期化されたオブジェクトに設定し `<federationConfiguration>` ます。</span><span class="sxs-lookup"><span data-stu-id="a0c9d-150"><xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfigurationCreated> event and set the <xref:System.IdentityModel.Services.Configuration.FederationConfigurationCreatedEventArgs.FederationConfiguration%2A?displayProperty=nameWithType> property inside the handler to a <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> object initialized with values from the appropriate `<federationConfiguration>` element in the configuration file.</span></span>  
  
 <span data-ttu-id="a0c9d-151">`<federationConfiguration>`要素は、クラスによって表され <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElement> ます。</span><span class="sxs-lookup"><span data-stu-id="a0c9d-151">The `<federationConfiguration>` element is represented by the <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElement> class.</span></span> <span data-ttu-id="a0c9d-152">構成オブジェクト自体は、クラスによって表され <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> ます。</span><span class="sxs-lookup"><span data-stu-id="a0c9d-152">The configuration object itself is represented by the <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> class.</span></span> <span data-ttu-id="a0c9d-153">1つの <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> インスタンスがプロパティに設定され、 <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType> アプリケーションのフェデレーション構成が提供されます。</span><span class="sxs-lookup"><span data-stu-id="a0c9d-153">A single <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> instance is set on the <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType> property and provides federated configuration for the application.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a0c9d-154">例</span><span class="sxs-lookup"><span data-stu-id="a0c9d-154">Example</span></span>  

 <span data-ttu-id="a0c9d-155">次の XML は、 `<federationConfiguration>` WSFAM の設定を指定する要素を示し、既定の cookie ハンドラー (クラスのインスタンス <xref:System.IdentityModel.Services.ChunkedCookieHandler> ) が SAM によって使用されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="a0c9d-155">The following XML shows a `<federationConfiguration>` element that specifies settings for the WSFAM and specifies that the default cookie handler (an instance of the <xref:System.IdentityModel.Services.ChunkedCookieHandler> class) be used by the SAM.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="a0c9d-156">この例では、cookie ハンドラーも WSFAM も HTTPS を使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="a0c9d-156">In this example, neither the cookie handler nor WSFAM are required to use HTTPS.</span></span> <span data-ttu-id="a0c9d-157">これは、 `requireHttps` 要素の属性 `<wsFederation>` と `requireSsl` の属性 `<cookieHandlerElement>` が `false` であるためです。</span><span class="sxs-lookup"><span data-stu-id="a0c9d-157">This is because the `requireHttps` attribute on the `<wsFederation>` element and the `requireSsl` attribute on the `<cookieHandlerElement>` are `false`.</span></span> <span data-ttu-id="a0c9d-158">ほとんどの運用環境では、セキュリティ上のリスクが生じる可能性があるため、これらの設定は推奨されません。</span><span class="sxs-lookup"><span data-stu-id="a0c9d-158">These settings are not recommended for most production environments as they may present a security risk.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a0c9d-159">関連項目</span><span class="sxs-lookup"><span data-stu-id="a0c9d-159">See also</span></span>

- <xref:System.IdentityModel.Services.WSFederationAuthenticationModule>
- <xref:System.IdentityModel.Services.SessionAuthenticationModule>
- <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType>
- [\<identityConfiguration>](identityconfiguration.md)
