---
title: <securityTokenHandlerConfiguration>
ms.date: 03/30/2017
ms.assetid: 28724cc6-020c-4a06-9a1f-d7594f315019
author: BrucePerlerMS
ms.openlocfilehash: 0aefaa808dfc32085a208420fcd582b1671acc64
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942452"
---
# <a name="securitytokenhandlerconfiguration"></a><span data-ttu-id="b0766-101">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="b0766-101">\<securityTokenHandlerConfiguration></span></span>
<span data-ttu-id="b0766-102">トークンハンドラーのコレクションの構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="b0766-102">Provides configuration for the collection of token handlers.</span></span>  
  
 <span data-ttu-id="b0766-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="b0766-103">\<system.identityModel></span></span>  
<span data-ttu-id="b0766-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="b0766-104">\<identityConfiguration></span></span>  
<span data-ttu-id="b0766-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="b0766-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="b0766-106">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="b0766-106">\<securityTokenHandlerConfiguration></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0766-107">構文</span><span class="sxs-lookup"><span data-stu-id="b0766-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b0766-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="b0766-108">Attributes and Elements</span></span>  
 <span data-ttu-id="b0766-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="b0766-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b0766-110">属性</span><span class="sxs-lookup"><span data-stu-id="b0766-110">Attributes</span></span>  
  
|<span data-ttu-id="b0766-111">属性</span><span class="sxs-lookup"><span data-stu-id="b0766-111">Attribute</span></span>|<span data-ttu-id="b0766-112">説明</span><span class="sxs-lookup"><span data-stu-id="b0766-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b0766-113">saveBootstrapContext</span><span class="sxs-lookup"><span data-stu-id="b0766-113">saveBootstrapContext</span></span>|<span data-ttu-id="b0766-114">ブートストラップトークンをセッショントークンに含める必要があるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="b0766-114">Specifies whether bootstrap tokens should be included in the session token.</span></span> <span data-ttu-id="b0766-115">また、値は、トークンハンドラーコレクションに対して設定すること`saveBootstrapContext`もできます。これを行うには、identity [ \<configuration >](identityconfiguration.md)要素の属性を設定します。</span><span class="sxs-lookup"><span data-stu-id="b0766-115">The value may also be set on a token handler collection by setting the `saveBootstrapContext` attribute on the [\<identityConfiguration>](identityconfiguration.md) element.</span></span> <span data-ttu-id="b0766-116">トークンハンドラーコレクションに設定された値は、サービスで設定された値よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="b0766-116">A value set on the token handler collection overrides the value set on the service.</span></span>|  
|<span data-ttu-id="b0766-117">maximumClockSkew</span><span class="sxs-lookup"><span data-stu-id="b0766-117">maximumClockSkew</span></span>|<span data-ttu-id="b0766-118">許容される最大のクロックスキューを指定する。<xref:System.TimeSpan></span><span class="sxs-lookup"><span data-stu-id="b0766-118">A <xref:System.TimeSpan> that specifies the maximum allowed clock skew.</span></span> <span data-ttu-id="b0766-119">サインインセッションの有効期限の検証など、時間を区別する操作を実行するときに許容される最大のクロックスキューを制御します。</span><span class="sxs-lookup"><span data-stu-id="b0766-119">Controls the maximum allowed clock skew when performing time-sensitive operations, such as validating the expiration time of a sign-in session.</span></span> <span data-ttu-id="b0766-120">既定値は5分 "00:05:00" です。</span><span class="sxs-lookup"><span data-stu-id="b0766-120">The default is 5 minutes, "00:05:00".</span></span> <span data-ttu-id="b0766-121">値を指定<xref:System.TimeSpan>する方法の詳細については、「 [Timespan values](../windows-workflow-foundation/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0766-121">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="b0766-122">また、サービスレベルでは、 `maximumClockSkew` [ \<identity configuration >](identityconfiguration.md)要素の属性を設定することによって、時刻のずれの最大値を設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="b0766-122">The maximum clock skew may also be set at the service level by setting the `maximumClockSkew` attribute on the [\<identityConfiguration>](identityconfiguration.md) element.</span></span> <span data-ttu-id="b0766-123">トークンハンドラーコレクションに設定された値は、サービスで設定された値よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="b0766-123">A value set on the token handler collection overrides the value set on the service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b0766-124">子要素</span><span class="sxs-lookup"><span data-stu-id="b0766-124">Child Elements</span></span>  
  
|<span data-ttu-id="b0766-125">要素</span><span class="sxs-lookup"><span data-stu-id="b0766-125">Element</span></span>|<span data-ttu-id="b0766-126">説明</span><span class="sxs-lookup"><span data-stu-id="b0766-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b0766-127">\<audienceUris></span><span class="sxs-lookup"><span data-stu-id="b0766-127">\<audienceUris></span></span>](audienceuris.md)|<span data-ttu-id="b0766-128">この証明書利用者の許容される識別子である Uri のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="b0766-128">Specifies the set of URIs that are acceptable identifiers of this relying party.</span></span> <span data-ttu-id="b0766-129">任意。</span><span class="sxs-lookup"><span data-stu-id="b0766-129">Optional.</span></span>|  
|[<span data-ttu-id="b0766-130">\<キャッシュ ></span><span class="sxs-lookup"><span data-stu-id="b0766-130">\<caches></span></span>](caches.md)|<span data-ttu-id="b0766-131">セッショントークンとトークンリプレイ検出に使用されるキャッシュを登録します。</span><span class="sxs-lookup"><span data-stu-id="b0766-131">Registers the caches used for session tokens and token replay detection.</span></span> <span data-ttu-id="b0766-132">は、サービスレベルまたはセキュリティトークンハンドラーコレクションで指定できます。</span><span class="sxs-lookup"><span data-stu-id="b0766-132">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="b0766-133">任意。</span><span class="sxs-lookup"><span data-stu-id="b0766-133">Optional.</span></span>|  
|[<span data-ttu-id="b0766-134">\<certificateValidation ></span><span class="sxs-lookup"><span data-stu-id="b0766-134">\<certificateValidation></span></span>](certificatevalidation.md)|<span data-ttu-id="b0766-135">トークンハンドラーが証明書を検証するために使用する設定を制御します。</span><span class="sxs-lookup"><span data-stu-id="b0766-135">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="b0766-136">は、サービスレベルまたはセキュリティトークンハンドラーコレクションで指定できます。</span><span class="sxs-lookup"><span data-stu-id="b0766-136">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="b0766-137">特定のハンドラーが独自の検証コントロールを使用して構成されている場合、これらの設定はオーバーライドされます。</span><span class="sxs-lookup"><span data-stu-id="b0766-137">These settings are overridden if a specific handler is configured with its own validator.</span></span> <span data-ttu-id="b0766-138">任意。</span><span class="sxs-lookup"><span data-stu-id="b0766-138">Optional.</span></span>|  
|[<span data-ttu-id="b0766-139">\<issuerNameRegistry ></span><span class="sxs-lookup"><span data-stu-id="b0766-139">\<issuerNameRegistry></span></span>](issuernameregistry.md)|<span data-ttu-id="b0766-140">トークンハンドラーコレクションのハンドラーによって使用される発行者名レジストリを構成します。</span><span class="sxs-lookup"><span data-stu-id="b0766-140">Configures the issuer name registry that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="b0766-141">任意。</span><span class="sxs-lookup"><span data-stu-id="b0766-141">Optional.</span></span>|  
|[<span data-ttu-id="b0766-142">\<issuerTokenResolver ></span><span class="sxs-lookup"><span data-stu-id="b0766-142">\<issuerTokenResolver></span></span>](issuertokenresolver.md)|<span data-ttu-id="b0766-143">トークンハンドラーコレクションのハンドラーによって使用される発行者トークンリゾルバーを登録します。</span><span class="sxs-lookup"><span data-stu-id="b0766-143">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="b0766-144">発行者トークンリゾルバーは、受信トークンとメッセージの署名トークンを解決するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="b0766-144">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="b0766-145">任意。</span><span class="sxs-lookup"><span data-stu-id="b0766-145">Optional.</span></span>|  
|[<span data-ttu-id="b0766-146">\<serviceTokenResolver></span><span class="sxs-lookup"><span data-stu-id="b0766-146">\<serviceTokenResolver></span></span>](servicetokenresolver.md)|<span data-ttu-id="b0766-147">トークンハンドラーコレクションのハンドラーによって使用されるサービストークンリゾルバーを登録します。</span><span class="sxs-lookup"><span data-stu-id="b0766-147">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="b0766-148">サービストークンリゾルバーは、受信トークンとメッセージの暗号化トークンを解決するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="b0766-148">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="b0766-149">任意。</span><span class="sxs-lookup"><span data-stu-id="b0766-149">Optional.</span></span>|  
|[<span data-ttu-id="b0766-150">\<tokenReplayDetection></span><span class="sxs-lookup"><span data-stu-id="b0766-150">\<tokenReplayDetection></span></span>](tokenreplaydetection.md)|<span data-ttu-id="b0766-151">トークンリプレイ検出を有効にし、トークンの有効期限を指定します。</span><span class="sxs-lookup"><span data-stu-id="b0766-151">Enables token replay detection and specifies the expiration time for tokens.</span></span> <span data-ttu-id="b0766-152">は、サービスレベルまたはセキュリティトークンハンドラーコレクションで指定できます。</span><span class="sxs-lookup"><span data-stu-id="b0766-152">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="b0766-153">任意。</span><span class="sxs-lookup"><span data-stu-id="b0766-153">Optional.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b0766-154">親要素</span><span class="sxs-lookup"><span data-stu-id="b0766-154">Parent Elements</span></span>  
  
|<span data-ttu-id="b0766-155">要素</span><span class="sxs-lookup"><span data-stu-id="b0766-155">Element</span></span>|<span data-ttu-id="b0766-156">説明</span><span class="sxs-lookup"><span data-stu-id="b0766-156">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b0766-157">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="b0766-157">\<securityTokenHandlers></span></span>](securitytokenhandlers.md)|<span data-ttu-id="b0766-158">エンドポイントに登録されているセキュリティトークンハンドラーのコレクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="b0766-158">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b0766-159">Remarks</span><span class="sxs-lookup"><span data-stu-id="b0766-159">Remarks</span></span>  
 <span data-ttu-id="b0766-160">このセクションでは、 <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration>オブジェクトのプロパティ値を提供します。</span><span class="sxs-lookup"><span data-stu-id="b0766-160">This section provides property values for a <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> object.</span></span> <span data-ttu-id="b0766-161">このセクションで構成した設定は、サービスで構成されている設定よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="b0766-161">Settings configured in this section override those configured on the service.</span></span> <span data-ttu-id="b0766-162">これらの設定の一部は、ハンドラーがセキュリティトークンハンドラーコレクションに追加されたときに指定される設定によってオーバーライドされることがあります。</span><span class="sxs-lookup"><span data-stu-id="b0766-162">Some of these settings can, in turn, be overridden by settings that are specified when a handler is added to the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b0766-163">例</span><span class="sxs-lookup"><span data-stu-id="b0766-163">Example</span></span>  
  
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
