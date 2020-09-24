---
title: <securityTokenHandlerConfiguration>
ms.date: 03/30/2017
ms.assetid: 28724cc6-020c-4a06-9a1f-d7594f315019
author: BrucePerlerMS
ms.openlocfilehash: 4c6affbc24a58424158e466fb732e9a3b3d6f1ed
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91157019"
---
# \<securityTokenHandlerConfiguration>

<span data-ttu-id="f7b0b-101">トークンハンドラーのコレクションの構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="f7b0b-101">Provides configuration for the collection of token handlers.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<securityTokenHandlerConfiguration>**  
  
## <a name="syntax"></a><span data-ttu-id="f7b0b-102">構文</span><span class="sxs-lookup"><span data-stu-id="f7b0b-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f7b0b-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="f7b0b-103">Attributes and Elements</span></span>  

 <span data-ttu-id="f7b0b-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="f7b0b-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f7b0b-105">属性</span><span class="sxs-lookup"><span data-stu-id="f7b0b-105">Attributes</span></span>  
  
|<span data-ttu-id="f7b0b-106">属性</span><span class="sxs-lookup"><span data-stu-id="f7b0b-106">Attribute</span></span>|<span data-ttu-id="f7b0b-107">[説明]</span><span class="sxs-lookup"><span data-stu-id="f7b0b-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f7b0b-108">saveBootstrapContext</span><span class="sxs-lookup"><span data-stu-id="f7b0b-108">saveBootstrapContext</span></span>|<span data-ttu-id="f7b0b-109">ブートストラップトークンをセッショントークンに含める必要があるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="f7b0b-109">Specifies whether bootstrap tokens should be included in the session token.</span></span> <span data-ttu-id="f7b0b-110">また、要素の属性を設定することによって、トークンハンドラーコレクションに値を設定することもでき `saveBootstrapContext` [\<identityConfiguration>](identityconfiguration.md) ます。</span><span class="sxs-lookup"><span data-stu-id="f7b0b-110">The value may also be set on a token handler collection by setting the `saveBootstrapContext` attribute on the [\<identityConfiguration>](identityconfiguration.md) element.</span></span> <span data-ttu-id="f7b0b-111">トークンハンドラーコレクションに設定された値は、サービスで設定された値よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="f7b0b-111">A value set on the token handler collection overrides the value set on the service.</span></span>|  
|<span data-ttu-id="f7b0b-112">maximumClockSkew</span><span class="sxs-lookup"><span data-stu-id="f7b0b-112">maximumClockSkew</span></span>|<span data-ttu-id="f7b0b-113"><xref:System.TimeSpan>許容される最大のクロックスキューを指定する。</span><span class="sxs-lookup"><span data-stu-id="f7b0b-113">A <xref:System.TimeSpan> that specifies the maximum allowed clock skew.</span></span> <span data-ttu-id="f7b0b-114">サインインセッションの有効期限の検証など、時間を区別する操作を実行するときに許容される最大のクロックスキューを制御します。</span><span class="sxs-lookup"><span data-stu-id="f7b0b-114">Controls the maximum allowed clock skew when performing time-sensitive operations, such as validating the expiration time of a sign-in session.</span></span> <span data-ttu-id="f7b0b-115">既定値は5分 "00:05:00" です。</span><span class="sxs-lookup"><span data-stu-id="f7b0b-115">The default is 5 minutes, "00:05:00".</span></span> <span data-ttu-id="f7b0b-116">値を指定する方法の詳細について <xref:System.TimeSpan> は、「 [Timespan values](../windows-workflow-foundation/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7b0b-116">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="f7b0b-117">また、要素の属性を設定することによって、サービスレベルで時刻のずれの最大値を設定することもでき `maximumClockSkew` [\<identityConfiguration>](identityconfiguration.md) ます。</span><span class="sxs-lookup"><span data-stu-id="f7b0b-117">The maximum clock skew may also be set at the service level by setting the `maximumClockSkew` attribute on the [\<identityConfiguration>](identityconfiguration.md) element.</span></span> <span data-ttu-id="f7b0b-118">トークンハンドラーコレクションに設定された値は、サービスで設定された値よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="f7b0b-118">A value set on the token handler collection overrides the value set on the service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f7b0b-119">子要素</span><span class="sxs-lookup"><span data-stu-id="f7b0b-119">Child Elements</span></span>  
  
|<span data-ttu-id="f7b0b-120">要素</span><span class="sxs-lookup"><span data-stu-id="f7b0b-120">Element</span></span>|<span data-ttu-id="f7b0b-121">説明</span><span class="sxs-lookup"><span data-stu-id="f7b0b-121">Description</span></span>|  
|-------------|-----------------|  
|[\<audienceUris>](audienceuris.md)|<span data-ttu-id="f7b0b-122">この証明書利用者の許容される識別子である Uri のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="f7b0b-122">Specifies the set of URIs that are acceptable identifiers of this relying party.</span></span> <span data-ttu-id="f7b0b-123">省略可能。</span><span class="sxs-lookup"><span data-stu-id="f7b0b-123">Optional.</span></span>|  
|[\<caches>](caches.md)|<span data-ttu-id="f7b0b-124">セッショントークンとトークンリプレイ検出に使用されるキャッシュを登録します。</span><span class="sxs-lookup"><span data-stu-id="f7b0b-124">Registers the caches used for session tokens and token replay detection.</span></span> <span data-ttu-id="f7b0b-125">は、サービスレベルまたはセキュリティトークンハンドラーコレクションで指定できます。</span><span class="sxs-lookup"><span data-stu-id="f7b0b-125">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="f7b0b-126">省略可能。</span><span class="sxs-lookup"><span data-stu-id="f7b0b-126">Optional.</span></span>|  
|[\<certificateValidation>](certificatevalidation.md)|<span data-ttu-id="f7b0b-127">トークンハンドラーが証明書を検証するために使用する設定を制御します。</span><span class="sxs-lookup"><span data-stu-id="f7b0b-127">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="f7b0b-128">は、サービスレベルまたはセキュリティトークンハンドラーコレクションで指定できます。</span><span class="sxs-lookup"><span data-stu-id="f7b0b-128">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="f7b0b-129">特定のハンドラーが独自の検証コントロールを使用して構成されている場合、これらの設定はオーバーライドされます。</span><span class="sxs-lookup"><span data-stu-id="f7b0b-129">These settings are overridden if a specific handler is configured with its own validator.</span></span> <span data-ttu-id="f7b0b-130">省略可能。</span><span class="sxs-lookup"><span data-stu-id="f7b0b-130">Optional.</span></span>|  
|[\<issuerNameRegistry>](issuernameregistry.md)|<span data-ttu-id="f7b0b-131">トークンハンドラーコレクションのハンドラーによって使用される発行者名レジストリを構成します。</span><span class="sxs-lookup"><span data-stu-id="f7b0b-131">Configures the issuer name registry that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="f7b0b-132">省略可能。</span><span class="sxs-lookup"><span data-stu-id="f7b0b-132">Optional.</span></span>|  
|[\<issuerTokenResolver>](issuertokenresolver.md)|<span data-ttu-id="f7b0b-133">トークンハンドラーコレクションのハンドラーによって使用される発行者トークンリゾルバーを登録します。</span><span class="sxs-lookup"><span data-stu-id="f7b0b-133">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="f7b0b-134">発行者トークンリゾルバーは、受信トークンとメッセージの署名トークンを解決するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="f7b0b-134">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="f7b0b-135">省略可能。</span><span class="sxs-lookup"><span data-stu-id="f7b0b-135">Optional.</span></span>|  
|[\<serviceTokenResolver>](servicetokenresolver.md)|<span data-ttu-id="f7b0b-136">トークンハンドラーコレクションのハンドラーによって使用されるサービストークンリゾルバーを登録します。</span><span class="sxs-lookup"><span data-stu-id="f7b0b-136">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="f7b0b-137">サービストークンリゾルバーは、受信トークンとメッセージの暗号化トークンを解決するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="f7b0b-137">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="f7b0b-138">省略可能。</span><span class="sxs-lookup"><span data-stu-id="f7b0b-138">Optional.</span></span>|  
|[\<tokenReplayDetection>](tokenreplaydetection.md)|<span data-ttu-id="f7b0b-139">トークンリプレイ検出を有効にし、トークンの有効期限を指定します。</span><span class="sxs-lookup"><span data-stu-id="f7b0b-139">Enables token replay detection and specifies the expiration time for tokens.</span></span> <span data-ttu-id="f7b0b-140">は、サービスレベルまたはセキュリティトークンハンドラーコレクションで指定できます。</span><span class="sxs-lookup"><span data-stu-id="f7b0b-140">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="f7b0b-141">省略可能。</span><span class="sxs-lookup"><span data-stu-id="f7b0b-141">Optional.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f7b0b-142">親要素</span><span class="sxs-lookup"><span data-stu-id="f7b0b-142">Parent Elements</span></span>  
  
|<span data-ttu-id="f7b0b-143">要素</span><span class="sxs-lookup"><span data-stu-id="f7b0b-143">Element</span></span>|<span data-ttu-id="f7b0b-144">説明</span><span class="sxs-lookup"><span data-stu-id="f7b0b-144">Description</span></span>|  
|-------------|-----------------|  
|[\<securityTokenHandlers>](securitytokenhandlers.md)|<span data-ttu-id="f7b0b-145">エンドポイントに登録されているセキュリティトークンハンドラーのコレクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="f7b0b-145">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f7b0b-146">解説</span><span class="sxs-lookup"><span data-stu-id="f7b0b-146">Remarks</span></span>  

 <span data-ttu-id="f7b0b-147">このセクションでは、オブジェクトのプロパティ値を提供 <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> します。</span><span class="sxs-lookup"><span data-stu-id="f7b0b-147">This section provides property values for a <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> object.</span></span> <span data-ttu-id="f7b0b-148">このセクションで構成した設定は、サービスで構成されている設定よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="f7b0b-148">Settings configured in this section override those configured on the service.</span></span> <span data-ttu-id="f7b0b-149">これらの設定の一部は、ハンドラーがセキュリティトークンハンドラーコレクションに追加されたときに指定される設定によってオーバーライドされることがあります。</span><span class="sxs-lookup"><span data-stu-id="f7b0b-149">Some of these settings can, in turn, be overridden by settings that are specified when a handler is added to the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f7b0b-150">例</span><span class="sxs-lookup"><span data-stu-id="f7b0b-150">Example</span></span>  
  
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
