---
title: <issuerNameRegistry>
ms.date: 03/30/2017
ms.assetid: 58b39d12-c953-40c4-88af-d7eb3343ca28
author: BrucePerlerMS
ms.openlocfilehash: ae263a4590cc523c64306ff5d53e54b5190ca510
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61791647"
---
# <a name="issuernameregistry"></a><span data-ttu-id="f9134-101">\<issuerNameRegistry></span><span class="sxs-lookup"><span data-stu-id="f9134-101">\<issuerNameRegistry></span></span>
<span data-ttu-id="f9134-102">トークン ハンドラー コレクションのハンドラーによって使用される発行者名レジストリを構成します。</span><span class="sxs-lookup"><span data-stu-id="f9134-102">Configures the issuer name registry that is used by handlers in the token handler collection.</span></span>  
  
 <span data-ttu-id="f9134-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="f9134-103">\<system.identityModel></span></span>  
<span data-ttu-id="f9134-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="f9134-104">\<identityConfiguration></span></span>  
<span data-ttu-id="f9134-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="f9134-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="f9134-106">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="f9134-106">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="f9134-107">\<issuerNameRegistry></span><span class="sxs-lookup"><span data-stu-id="f9134-107">\<issuerNameRegistry></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9134-108">構文</span><span class="sxs-lookup"><span data-stu-id="f9134-108">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <issuerNameRegistry type=xs:string>  
          <optionalCustomConfigurationElements />  
        </issuerNameRegistry>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f9134-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="f9134-109">Attributes and Elements</span></span>  
 <span data-ttu-id="f9134-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="f9134-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f9134-111">属性</span><span class="sxs-lookup"><span data-stu-id="f9134-111">Attributes</span></span>  
  
|<span data-ttu-id="f9134-112">属性</span><span class="sxs-lookup"><span data-stu-id="f9134-112">Attribute</span></span>|<span data-ttu-id="f9134-113">説明</span><span class="sxs-lookup"><span data-stu-id="f9134-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f9134-114">型</span><span class="sxs-lookup"><span data-stu-id="f9134-114">type</span></span>|<span data-ttu-id="f9134-115">派生した型、<xref:System.IdentityModel.Tokens.IssuerNameRegistry>クラス。</span><span class="sxs-lookup"><span data-stu-id="f9134-115">A type that derives from the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class.</span></span> <span data-ttu-id="f9134-116">詳細については、ユーザー設定を指定する方法についての`type`、[カスタム型の参照] を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f9134-116">For more information about how to specify a custom `type`, see [Custom Type References].</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f9134-117">子要素</span><span class="sxs-lookup"><span data-stu-id="f9134-117">Child Elements</span></span>  
  
|<span data-ttu-id="f9134-118">要素</span><span class="sxs-lookup"><span data-stu-id="f9134-118">Element</span></span>|<span data-ttu-id="f9134-119">説明</span><span class="sxs-lookup"><span data-stu-id="f9134-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f9134-120">\<trustedIssuers></span><span class="sxs-lookup"><span data-stu-id="f9134-120">\<trustedIssuers></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md)|<span data-ttu-id="f9134-121">ときに、`type`属性が構成ベースの発行者名レジストリを指定します (、<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>クラス)、 [ \<trustedIssuers >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md)要素を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9134-121">When the `type` attribute specifies the configuration-based issuer name registry (the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class), the [\<trustedIssuers>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md) element must be specified.</span></span> <span data-ttu-id="f9134-122">[ \<TrustedIssuers >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md)要素がかかる`<add>`、 `<clear>`、または`<remove>`要素の子要素として。</span><span class="sxs-lookup"><span data-stu-id="f9134-122">The [\<trustedIssuers>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md) element can take `<add>`, `<clear>`, or `<remove>` elements as child elements.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f9134-123">親要素</span><span class="sxs-lookup"><span data-stu-id="f9134-123">Parent Elements</span></span>  
  
|<span data-ttu-id="f9134-124">要素</span><span class="sxs-lookup"><span data-stu-id="f9134-124">Element</span></span>|<span data-ttu-id="f9134-125">説明</span><span class="sxs-lookup"><span data-stu-id="f9134-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f9134-126">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="f9134-126">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="f9134-127">トークン ハンドラー コレクションのセキュリティの構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="f9134-127">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f9134-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="f9134-128">Remarks</span></span>  
 <span data-ttu-id="f9134-129">すべての発行者トークンは、発行者名レジストリを使用して検証されます。</span><span class="sxs-lookup"><span data-stu-id="f9134-129">All issuer tokens are validated using an issuer name registry.</span></span> <span data-ttu-id="f9134-130">これはオブジェクトから派生した、<xref:System.IdentityModel.Tokens.IssuerNameRegistry>クラス。</span><span class="sxs-lookup"><span data-stu-id="f9134-130">This is an object that derives from the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class.</span></span> <span data-ttu-id="f9134-131">発行者名レジストリを使用して、対応する発行者によって生成されたトークンの署名を検証するために必要な暗号化マテリアルにニーモニック名を関連付けます。</span><span class="sxs-lookup"><span data-stu-id="f9134-131">The issuer name registry is used to associate a mnemonic name to the cryptographic material that is needed to verify the signatures of tokens produced by the corresponding issuer.</span></span> <span data-ttu-id="f9134-132">発行者名レジストリは、証明書利用者 (RP) アプリケーションによって信頼されている発行者の一覧を保持します。</span><span class="sxs-lookup"><span data-stu-id="f9134-132">The issuer name registry maintains a list of issuers that are trusted by the relying party (RP) application.</span></span> <span data-ttu-id="f9134-133">使用して、発行者名レジストリの種類を指定、`type`属性。</span><span class="sxs-lookup"><span data-stu-id="f9134-133">The type of the issuer name registry is specified using the `type` attribute.</span></span> <span data-ttu-id="f9134-134">`<issuerNameRegistry>`要素は、指定した型の構成を提供する 1 つまたは複数の子要素を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="f9134-134">The `<issuerNameRegistry>` element can have one or more child elements that provide configuration for the specified type.</span></span> <span data-ttu-id="f9134-135">これらの子要素をオーバーライドすることで処理するロジックを提供する、<xref:System.IdentityModel.Tokens.IssuerNameRegistry.LoadCustomConfiguration%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="f9134-135">You provide the logic that processes these child elements by overriding the <xref:System.IdentityModel.Tokens.IssuerNameRegistry.LoadCustomConfiguration%2A> method.</span></span>  
  
 <span data-ttu-id="f9134-136">WIF には単一の発行者名レジストリの種類をすぐに使える、<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>クラス。</span><span class="sxs-lookup"><span data-stu-id="f9134-136">WIF provides a single issuer name registry type out of the box, the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class.</span></span> <span data-ttu-id="f9134-137">このクラスは、一連の構成で指定されている信頼された発行者の証明書を使用します。</span><span class="sxs-lookup"><span data-stu-id="f9134-137">This class uses a set of trusted issuer certificates that are specified in configuration.</span></span> <span data-ttu-id="f9134-138">構成の子要素に要する`<trustedIssuers>`、信頼された発行者の証明書のコレクションが構成されています。</span><span class="sxs-lookup"><span data-stu-id="f9134-138">It requires a child configuration element, `<trustedIssuers>`, under which the collection of trusted issuer certificates is configured.</span></span> <span data-ttu-id="f9134-139">証明書が指定の ASN.1 を使用してエンコードされた証明書の拇印の形式とが追加または削除、コレクションからを使用して信頼された`<add>`、 `<clear>`、または`<remove>`要素。</span><span class="sxs-lookup"><span data-stu-id="f9134-139">Trusted certificates are specified using the ASN.1 encoded form of the certificate thumbprint and are added or removed from the collection by using `<add>`, `<clear>`, or `<remove>` elements.</span></span>  
  
 <span data-ttu-id="f9134-140">`<issuerNameRegistry>`要素が表される、<xref:System.IdentityModel.Configuration.IssuerNameRegistryElement>クラス。</span><span class="sxs-lookup"><span data-stu-id="f9134-140">The `<issuerNameRegistry>` element is represented by the <xref:System.IdentityModel.Configuration.IssuerNameRegistryElement> class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f9134-141">指定する、`<issuerNameRegistry>`要素の子要素として、 [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)要素は非推奨とされましたが、旧バージョンとの互換性もサポートします。</span><span class="sxs-lookup"><span data-stu-id="f9134-141">Specifying the `<issuerNameRegistry>` element as a child element of the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="f9134-142">上の設定、`<securityTokenHandlerConfiguration>`要素のオーバーライド、`<identityConfiguration>`要素。</span><span class="sxs-lookup"><span data-stu-id="f9134-142">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f9134-143">例</span><span class="sxs-lookup"><span data-stu-id="f9134-143">Example</span></span>  
 <span data-ttu-id="f9134-144">次の XML では、名前のレジストリをベースの構成の発行者を指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f9134-144">The following XML shows how to specify the configuration based issuer name registry.</span></span>  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB … 1EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f9134-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="f9134-145">See also</span></span>

- <xref:System.IdentityModel.Tokens.IssuerNameRegistry>
- <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>
