---
title: <securityTokenHandlerConfiguration>
ms.date: 03/30/2017
ms.assetid: 28724cc6-020c-4a06-9a1f-d7594f315019
author: BrucePerlerMS
ms.openlocfilehash: 330e52bd73a8032e4073fe434c852e5bdf8e1d47
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251887"
---
# <a name="securitytokenhandlerconfiguration"></a><span data-ttu-id="9aa39-101">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="9aa39-101">\<securityTokenHandlerConfiguration></span></span>
<span data-ttu-id="9aa39-102">トークンハンドラーのコレクションの構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="9aa39-102">Provides configuration for the collection of token handlers.</span></span>  
  
<span data-ttu-id="9aa39-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9aa39-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="9aa39-104">&nbsp;&nbsp;[ **\<システムの >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="9aa39-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="9aa39-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<構成 >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="9aa39-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="9aa39-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlers >** ](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="9aa39-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="9aa39-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<securityTokenHandlerConfiguration >**</span><span class="sxs-lookup"><span data-stu-id="9aa39-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<securityTokenHandlerConfiguration>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9aa39-108">構文</span><span class="sxs-lookup"><span data-stu-id="9aa39-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9aa39-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="9aa39-109">Attributes and Elements</span></span>  
 <span data-ttu-id="9aa39-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="9aa39-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9aa39-111">属性</span><span class="sxs-lookup"><span data-stu-id="9aa39-111">Attributes</span></span>  
  
|<span data-ttu-id="9aa39-112">属性</span><span class="sxs-lookup"><span data-stu-id="9aa39-112">Attribute</span></span>|<span data-ttu-id="9aa39-113">説明</span><span class="sxs-lookup"><span data-stu-id="9aa39-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9aa39-114">saveBootstrapContext</span><span class="sxs-lookup"><span data-stu-id="9aa39-114">saveBootstrapContext</span></span>|<span data-ttu-id="9aa39-115">ブートストラップトークンをセッショントークンに含める必要があるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="9aa39-115">Specifies whether bootstrap tokens should be included in the session token.</span></span> <span data-ttu-id="9aa39-116">また、値は、トークンハンドラーコレクションに対して設定すること`saveBootstrapContext`もできます。これを行うには、identity [ \<configuration >](identityconfiguration.md)要素の属性を設定します。</span><span class="sxs-lookup"><span data-stu-id="9aa39-116">The value may also be set on a token handler collection by setting the `saveBootstrapContext` attribute on the [\<identityConfiguration>](identityconfiguration.md) element.</span></span> <span data-ttu-id="9aa39-117">トークンハンドラーコレクションに設定された値は、サービスで設定された値よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="9aa39-117">A value set on the token handler collection overrides the value set on the service.</span></span>|  
|<span data-ttu-id="9aa39-118">maximumClockSkew</span><span class="sxs-lookup"><span data-stu-id="9aa39-118">maximumClockSkew</span></span>|<span data-ttu-id="9aa39-119">許容される最大のクロックスキューを指定する。<xref:System.TimeSpan></span><span class="sxs-lookup"><span data-stu-id="9aa39-119">A <xref:System.TimeSpan> that specifies the maximum allowed clock skew.</span></span> <span data-ttu-id="9aa39-120">サインインセッションの有効期限の検証など、時間を区別する操作を実行するときに許容される最大のクロックスキューを制御します。</span><span class="sxs-lookup"><span data-stu-id="9aa39-120">Controls the maximum allowed clock skew when performing time-sensitive operations, such as validating the expiration time of a sign-in session.</span></span> <span data-ttu-id="9aa39-121">既定値は5分 "00:05:00" です。</span><span class="sxs-lookup"><span data-stu-id="9aa39-121">The default is 5 minutes, "00:05:00".</span></span> <span data-ttu-id="9aa39-122">値を指定<xref:System.TimeSpan>する方法の詳細については、「 [Timespan values](../windows-workflow-foundation/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9aa39-122">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="9aa39-123">また、サービスレベルでは、 `maximumClockSkew` [ \<identity configuration >](identityconfiguration.md)要素の属性を設定することによって、時刻のずれの最大値を設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="9aa39-123">The maximum clock skew may also be set at the service level by setting the `maximumClockSkew` attribute on the [\<identityConfiguration>](identityconfiguration.md) element.</span></span> <span data-ttu-id="9aa39-124">トークンハンドラーコレクションに設定された値は、サービスで設定された値よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="9aa39-124">A value set on the token handler collection overrides the value set on the service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9aa39-125">子要素</span><span class="sxs-lookup"><span data-stu-id="9aa39-125">Child Elements</span></span>  
  
|<span data-ttu-id="9aa39-126">要素</span><span class="sxs-lookup"><span data-stu-id="9aa39-126">Element</span></span>|<span data-ttu-id="9aa39-127">説明</span><span class="sxs-lookup"><span data-stu-id="9aa39-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9aa39-128">\<audienceUris></span><span class="sxs-lookup"><span data-stu-id="9aa39-128">\<audienceUris></span></span>](audienceuris.md)|<span data-ttu-id="9aa39-129">この証明書利用者の許容される識別子である Uri のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="9aa39-129">Specifies the set of URIs that are acceptable identifiers of this relying party.</span></span> <span data-ttu-id="9aa39-130">任意。</span><span class="sxs-lookup"><span data-stu-id="9aa39-130">Optional.</span></span>|  
|[<span data-ttu-id="9aa39-131">\<キャッシュ ></span><span class="sxs-lookup"><span data-stu-id="9aa39-131">\<caches></span></span>](caches.md)|<span data-ttu-id="9aa39-132">セッショントークンとトークンリプレイ検出に使用されるキャッシュを登録します。</span><span class="sxs-lookup"><span data-stu-id="9aa39-132">Registers the caches used for session tokens and token replay detection.</span></span> <span data-ttu-id="9aa39-133">は、サービスレベルまたはセキュリティトークンハンドラーコレクションで指定できます。</span><span class="sxs-lookup"><span data-stu-id="9aa39-133">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="9aa39-134">任意。</span><span class="sxs-lookup"><span data-stu-id="9aa39-134">Optional.</span></span>|  
|[<span data-ttu-id="9aa39-135">\<certificateValidation ></span><span class="sxs-lookup"><span data-stu-id="9aa39-135">\<certificateValidation></span></span>](certificatevalidation.md)|<span data-ttu-id="9aa39-136">トークンハンドラーが証明書を検証するために使用する設定を制御します。</span><span class="sxs-lookup"><span data-stu-id="9aa39-136">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="9aa39-137">は、サービスレベルまたはセキュリティトークンハンドラーコレクションで指定できます。</span><span class="sxs-lookup"><span data-stu-id="9aa39-137">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="9aa39-138">特定のハンドラーが独自の検証コントロールを使用して構成されている場合、これらの設定はオーバーライドされます。</span><span class="sxs-lookup"><span data-stu-id="9aa39-138">These settings are overridden if a specific handler is configured with its own validator.</span></span> <span data-ttu-id="9aa39-139">任意。</span><span class="sxs-lookup"><span data-stu-id="9aa39-139">Optional.</span></span>|  
|[<span data-ttu-id="9aa39-140">\<issuerNameRegistry ></span><span class="sxs-lookup"><span data-stu-id="9aa39-140">\<issuerNameRegistry></span></span>](issuernameregistry.md)|<span data-ttu-id="9aa39-141">トークンハンドラーコレクションのハンドラーによって使用される発行者名レジストリを構成します。</span><span class="sxs-lookup"><span data-stu-id="9aa39-141">Configures the issuer name registry that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="9aa39-142">任意。</span><span class="sxs-lookup"><span data-stu-id="9aa39-142">Optional.</span></span>|  
|[<span data-ttu-id="9aa39-143">\<issuerTokenResolver ></span><span class="sxs-lookup"><span data-stu-id="9aa39-143">\<issuerTokenResolver></span></span>](issuertokenresolver.md)|<span data-ttu-id="9aa39-144">トークンハンドラーコレクションのハンドラーによって使用される発行者トークンリゾルバーを登録します。</span><span class="sxs-lookup"><span data-stu-id="9aa39-144">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="9aa39-145">発行者トークンリゾルバーは、受信トークンとメッセージの署名トークンを解決するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="9aa39-145">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="9aa39-146">任意。</span><span class="sxs-lookup"><span data-stu-id="9aa39-146">Optional.</span></span>|  
|[<span data-ttu-id="9aa39-147">\<serviceTokenResolver></span><span class="sxs-lookup"><span data-stu-id="9aa39-147">\<serviceTokenResolver></span></span>](servicetokenresolver.md)|<span data-ttu-id="9aa39-148">トークンハンドラーコレクションのハンドラーによって使用されるサービストークンリゾルバーを登録します。</span><span class="sxs-lookup"><span data-stu-id="9aa39-148">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="9aa39-149">サービストークンリゾルバーは、受信トークンとメッセージの暗号化トークンを解決するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="9aa39-149">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="9aa39-150">任意。</span><span class="sxs-lookup"><span data-stu-id="9aa39-150">Optional.</span></span>|  
|[<span data-ttu-id="9aa39-151">\<tokenReplayDetection></span><span class="sxs-lookup"><span data-stu-id="9aa39-151">\<tokenReplayDetection></span></span>](tokenreplaydetection.md)|<span data-ttu-id="9aa39-152">トークンリプレイ検出を有効にし、トークンの有効期限を指定します。</span><span class="sxs-lookup"><span data-stu-id="9aa39-152">Enables token replay detection and specifies the expiration time for tokens.</span></span> <span data-ttu-id="9aa39-153">は、サービスレベルまたはセキュリティトークンハンドラーコレクションで指定できます。</span><span class="sxs-lookup"><span data-stu-id="9aa39-153">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="9aa39-154">任意。</span><span class="sxs-lookup"><span data-stu-id="9aa39-154">Optional.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9aa39-155">親要素</span><span class="sxs-lookup"><span data-stu-id="9aa39-155">Parent Elements</span></span>  
  
|<span data-ttu-id="9aa39-156">要素</span><span class="sxs-lookup"><span data-stu-id="9aa39-156">Element</span></span>|<span data-ttu-id="9aa39-157">説明</span><span class="sxs-lookup"><span data-stu-id="9aa39-157">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9aa39-158">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="9aa39-158">\<securityTokenHandlers></span></span>](securitytokenhandlers.md)|<span data-ttu-id="9aa39-159">エンドポイントに登録されているセキュリティトークンハンドラーのコレクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="9aa39-159">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9aa39-160">Remarks</span><span class="sxs-lookup"><span data-stu-id="9aa39-160">Remarks</span></span>  
 <span data-ttu-id="9aa39-161">このセクションでは、 <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration>オブジェクトのプロパティ値を提供します。</span><span class="sxs-lookup"><span data-stu-id="9aa39-161">This section provides property values for a <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> object.</span></span> <span data-ttu-id="9aa39-162">このセクションで構成した設定は、サービスで構成されている設定よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="9aa39-162">Settings configured in this section override those configured on the service.</span></span> <span data-ttu-id="9aa39-163">これらの設定の一部は、ハンドラーがセキュリティトークンハンドラーコレクションに追加されたときに指定される設定によってオーバーライドされることがあります。</span><span class="sxs-lookup"><span data-stu-id="9aa39-163">Some of these settings can, in turn, be overridden by settings that are specified when a handler is added to the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9aa39-164">例</span><span class="sxs-lookup"><span data-stu-id="9aa39-164">Example</span></span>  
  
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
