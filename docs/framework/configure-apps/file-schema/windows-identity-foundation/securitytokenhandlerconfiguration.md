---
title: <securityTokenHandlerConfiguration>
ms.date: 03/30/2017
ms.assetid: 28724cc6-020c-4a06-9a1f-d7594f315019
author: BrucePerlerMS
ms.openlocfilehash: e3e65820fa4dc341371d4f67689a288cd3f63951
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152568"
---
# <a name="securitytokenhandlerconfiguration"></a><span data-ttu-id="65f97-101">\<>を構成します。</span><span class="sxs-lookup"><span data-stu-id="65f97-101">\<securityTokenHandlerConfiguration></span></span>
<span data-ttu-id="65f97-102">トークン ハンドラーのコレクションの構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="65f97-102">Provides configuration for the collection of token handlers.</span></span>  
  
<span data-ttu-id="65f97-103">[**\<構成>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="65f97-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="65f97-104">&nbsp;&nbsp;[**\<>**](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="65f97-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="65f97-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<id構成>**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="65f97-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="65f97-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>**](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="65f97-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="65f97-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>**</span><span class="sxs-lookup"><span data-stu-id="65f97-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<securityTokenHandlerConfiguration>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65f97-108">構文</span><span class="sxs-lookup"><span data-stu-id="65f97-108">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration saveBootstrapContext=xs:boolean  
          maximumClockSkew=TimeSpan>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="65f97-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="65f97-109">Attributes and Elements</span></span>  
 <span data-ttu-id="65f97-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="65f97-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="65f97-111">属性</span><span class="sxs-lookup"><span data-stu-id="65f97-111">Attributes</span></span>  
  
|<span data-ttu-id="65f97-112">属性</span><span class="sxs-lookup"><span data-stu-id="65f97-112">Attribute</span></span>|<span data-ttu-id="65f97-113">説明</span><span class="sxs-lookup"><span data-stu-id="65f97-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="65f97-114">ブートストラップコンテキストを保存します。</span><span class="sxs-lookup"><span data-stu-id="65f97-114">saveBootstrapContext</span></span>|<span data-ttu-id="65f97-115">ブートストラップ トークンをセッション トークンに含めるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="65f97-115">Specifies whether bootstrap tokens should be included in the session token.</span></span> <span data-ttu-id="65f97-116">この値は`saveBootstrapContext`[\<、idConfiguration>](identityconfiguration.md)要素の属性を設定することで、トークン ハンドラー コレクションに設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="65f97-116">The value may also be set on a token handler collection by setting the `saveBootstrapContext` attribute on the [\<identityConfiguration>](identityconfiguration.md) element.</span></span> <span data-ttu-id="65f97-117">トークン ハンドラー コレクションに設定された値は、サービスに設定されている値をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="65f97-117">A value set on the token handler collection overrides the value set on the service.</span></span>|  
|<span data-ttu-id="65f97-118">最大時計の傾斜</span><span class="sxs-lookup"><span data-stu-id="65f97-118">maximumClockSkew</span></span>|<span data-ttu-id="65f97-119">許容<xref:System.TimeSpan>される最大クロック スキューを指定する A。</span><span class="sxs-lookup"><span data-stu-id="65f97-119">A <xref:System.TimeSpan> that specifies the maximum allowed clock skew.</span></span> <span data-ttu-id="65f97-120">サインイン セッションの有効期限を検証するなど、時間を区別する操作を実行する際に許容される最大クロック スキューを制御します。</span><span class="sxs-lookup"><span data-stu-id="65f97-120">Controls the maximum allowed clock skew when performing time-sensitive operations, such as validating the expiration time of a sign-in session.</span></span> <span data-ttu-id="65f97-121">デフォルトは 5 分の "00:05:00" です。</span><span class="sxs-lookup"><span data-stu-id="65f97-121">The default is 5 minutes, "00:05:00".</span></span> <span data-ttu-id="65f97-122">値の指定<xref:System.TimeSpan>方法の詳細については、「[タイムスパン値](../windows-workflow-foundation/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65f97-122">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="65f97-123">最大クロック スキューは[\<、identityConfiguration>](identityconfiguration.md)要素の属性を`maximumClockSkew`設定することによって、サービス レベルで設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="65f97-123">The maximum clock skew may also be set at the service level by setting the `maximumClockSkew` attribute on the [\<identityConfiguration>](identityconfiguration.md) element.</span></span> <span data-ttu-id="65f97-124">トークン ハンドラー コレクションに設定された値は、サービスに設定されている値をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="65f97-124">A value set on the token handler collection overrides the value set on the service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="65f97-125">子要素</span><span class="sxs-lookup"><span data-stu-id="65f97-125">Child Elements</span></span>  
  
|<span data-ttu-id="65f97-126">要素</span><span class="sxs-lookup"><span data-stu-id="65f97-126">Element</span></span>|<span data-ttu-id="65f97-127">説明</span><span class="sxs-lookup"><span data-stu-id="65f97-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="65f97-128">\<聴衆>を尿</span><span class="sxs-lookup"><span data-stu-id="65f97-128">\<audienceUris></span></span>](audienceuris.md)|<span data-ttu-id="65f97-129">この証明書利用者の受け入れ可能な識別子である URI のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="65f97-129">Specifies the set of URIs that are acceptable identifiers of this relying party.</span></span> <span data-ttu-id="65f97-130">省略可能。</span><span class="sxs-lookup"><span data-stu-id="65f97-130">Optional.</span></span>|  
|[<span data-ttu-id="65f97-131">\<キャッシュ></span><span class="sxs-lookup"><span data-stu-id="65f97-131">\<caches></span></span>](caches.md)|<span data-ttu-id="65f97-132">セッション トークンおよびトークンの再生検出に使用されるキャッシュを登録します。</span><span class="sxs-lookup"><span data-stu-id="65f97-132">Registers the caches used for session tokens and token replay detection.</span></span> <span data-ttu-id="65f97-133">サービス レベルまたはセキュリティ トークン ハンドラーコレクションで指定できます。</span><span class="sxs-lookup"><span data-stu-id="65f97-133">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="65f97-134">省略可能。</span><span class="sxs-lookup"><span data-stu-id="65f97-134">Optional.</span></span>|  
|[<span data-ttu-id="65f97-135">\<証明書検証></span><span class="sxs-lookup"><span data-stu-id="65f97-135">\<certificateValidation></span></span>](certificatevalidation.md)|<span data-ttu-id="65f97-136">トークン ハンドラーが証明書の検証に使用する設定を制御します。</span><span class="sxs-lookup"><span data-stu-id="65f97-136">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="65f97-137">サービス レベルまたはセキュリティ トークン ハンドラーコレクションで指定できます。</span><span class="sxs-lookup"><span data-stu-id="65f97-137">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="65f97-138">特定のハンドラーが独自の検証コントロールで構成されている場合、これらの設定はオーバーライドされます。</span><span class="sxs-lookup"><span data-stu-id="65f97-138">These settings are overridden if a specific handler is configured with its own validator.</span></span> <span data-ttu-id="65f97-139">省略可能。</span><span class="sxs-lookup"><span data-stu-id="65f97-139">Optional.</span></span>|  
|[<span data-ttu-id="65f97-140">\<レジストリ></span><span class="sxs-lookup"><span data-stu-id="65f97-140">\<issuerNameRegistry></span></span>](issuernameregistry.md)|<span data-ttu-id="65f97-141">トークン ハンドラーコレクション内のハンドラーによって使用される発行者名レジストリを構成します。</span><span class="sxs-lookup"><span data-stu-id="65f97-141">Configures the issuer name registry that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="65f97-142">省略可能。</span><span class="sxs-lookup"><span data-stu-id="65f97-142">Optional.</span></span>|  
|[<span data-ttu-id="65f97-143">\<></span><span class="sxs-lookup"><span data-stu-id="65f97-143">\<issuerTokenResolver></span></span>](issuertokenresolver.md)|<span data-ttu-id="65f97-144">トークン ハンドラー コレクション内のハンドラーによって使用される発行者トークン リゾルバーを登録します。</span><span class="sxs-lookup"><span data-stu-id="65f97-144">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="65f97-145">発行者トークン リゾルバーは、受信トークンとメッセージの署名トークンを解決するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="65f97-145">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="65f97-146">省略可能。</span><span class="sxs-lookup"><span data-stu-id="65f97-146">Optional.</span></span>|  
|[<span data-ttu-id="65f97-147">\<></span><span class="sxs-lookup"><span data-stu-id="65f97-147">\<serviceTokenResolver></span></span>](servicetokenresolver.md)|<span data-ttu-id="65f97-148">トークン ハンドラー コレクション内のハンドラーによって使用されるサービス トークン リゾルバーを登録します。</span><span class="sxs-lookup"><span data-stu-id="65f97-148">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="65f97-149">サービス トークン リゾルバーは、受信トークンとメッセージの暗号化トークンを解決するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="65f97-149">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="65f97-150">省略可能。</span><span class="sxs-lookup"><span data-stu-id="65f97-150">Optional.</span></span>|  
|[<span data-ttu-id="65f97-151">\<トークンリプレイ検出></span><span class="sxs-lookup"><span data-stu-id="65f97-151">\<tokenReplayDetection></span></span>](tokenreplaydetection.md)|<span data-ttu-id="65f97-152">トークン再生検出を有効にし、トークンの有効期限を指定します。</span><span class="sxs-lookup"><span data-stu-id="65f97-152">Enables token replay detection and specifies the expiration time for tokens.</span></span> <span data-ttu-id="65f97-153">サービス レベルまたはセキュリティ トークン ハンドラーコレクションで指定できます。</span><span class="sxs-lookup"><span data-stu-id="65f97-153">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="65f97-154">省略可能。</span><span class="sxs-lookup"><span data-stu-id="65f97-154">Optional.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="65f97-155">親要素</span><span class="sxs-lookup"><span data-stu-id="65f97-155">Parent Elements</span></span>  
  
|<span data-ttu-id="65f97-156">要素</span><span class="sxs-lookup"><span data-stu-id="65f97-156">Element</span></span>|<span data-ttu-id="65f97-157">説明</span><span class="sxs-lookup"><span data-stu-id="65f97-157">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="65f97-158">\<></span><span class="sxs-lookup"><span data-stu-id="65f97-158">\<securityTokenHandlers></span></span>](securitytokenhandlers.md)|<span data-ttu-id="65f97-159">エンドポイントに登録されているセキュリティ トークン ハンドラーのコレクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="65f97-159">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="65f97-160">解説</span><span class="sxs-lookup"><span data-stu-id="65f97-160">Remarks</span></span>  
 <span data-ttu-id="65f97-161">このセクションでは、オブジェクトのプロパティ<xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration>値を提供します。</span><span class="sxs-lookup"><span data-stu-id="65f97-161">This section provides property values for a <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> object.</span></span> <span data-ttu-id="65f97-162">このセクションで構成した設定は、サービスで構成された設定よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="65f97-162">Settings configured in this section override those configured on the service.</span></span> <span data-ttu-id="65f97-163">これらの設定の一部は、セキュリティ トークン ハンドラーのコレクションにハンドラーが追加されるときに指定された設定によってオーバーライドされる場合があります。</span><span class="sxs-lookup"><span data-stu-id="65f97-163">Some of these settings can, in turn, be overridden by settings that are specified when a handler is added to the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="65f97-164">例</span><span class="sxs-lookup"><span data-stu-id="65f97-164">Example</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>
      <securityTokenHandlerConfiguration>  
  
        <audienceUris>  
          <clear/>  
          <add value="http://www.example.com/myapp/" />  
        </audienceUris>  
  
        <issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel">  
          <trustedIssuers>  
            <add thumbprint="97249e1a … 4c9158de" name="contoso.com" />  
          </trustedIssuers>  
        </issuerNameRegistry>  
  
        <issuerTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
  
        <serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```
