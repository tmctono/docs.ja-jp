---
title: <issuerNameRegistry>
ms.date: 03/30/2017
ms.assetid: 58b39d12-c953-40c4-88af-d7eb3343ca28
author: BrucePerlerMS
ms.openlocfilehash: d0a1f8dd0c29aaee56c2ca1162cc70cc1e5ed106
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942664"
---
# <a name="issuernameregistry"></a><span data-ttu-id="a12d0-101">\<issuerNameRegistry ></span><span class="sxs-lookup"><span data-stu-id="a12d0-101">\<issuerNameRegistry></span></span>
<span data-ttu-id="a12d0-102">トークンハンドラーコレクションのハンドラーによって使用される発行者名レジストリを構成します。</span><span class="sxs-lookup"><span data-stu-id="a12d0-102">Configures the issuer name registry that is used by handlers in the token handler collection.</span></span>  
  
 <span data-ttu-id="a12d0-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="a12d0-103">\<system.identityModel></span></span>  
<span data-ttu-id="a12d0-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="a12d0-104">\<identityConfiguration></span></span>  
<span data-ttu-id="a12d0-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="a12d0-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="a12d0-106">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="a12d0-106">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="a12d0-107">\<issuerNameRegistry ></span><span class="sxs-lookup"><span data-stu-id="a12d0-107">\<issuerNameRegistry></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a12d0-108">構文</span><span class="sxs-lookup"><span data-stu-id="a12d0-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a12d0-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="a12d0-109">Attributes and Elements</span></span>  
 <span data-ttu-id="a12d0-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="a12d0-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a12d0-111">属性</span><span class="sxs-lookup"><span data-stu-id="a12d0-111">Attributes</span></span>  
  
|<span data-ttu-id="a12d0-112">属性</span><span class="sxs-lookup"><span data-stu-id="a12d0-112">Attribute</span></span>|<span data-ttu-id="a12d0-113">説明</span><span class="sxs-lookup"><span data-stu-id="a12d0-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a12d0-114">型</span><span class="sxs-lookup"><span data-stu-id="a12d0-114">type</span></span>|<span data-ttu-id="a12d0-115"><xref:System.IdentityModel.Tokens.IssuerNameRegistry>クラスから派生する型。</span><span class="sxs-lookup"><span data-stu-id="a12d0-115">A type that derives from the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class.</span></span> <span data-ttu-id="a12d0-116">カスタム`type`を指定する方法の詳細については、「[カスタム型参照]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a12d0-116">For more information about how to specify a custom `type`, see [Custom Type References].</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a12d0-117">子要素</span><span class="sxs-lookup"><span data-stu-id="a12d0-117">Child Elements</span></span>  
  
|<span data-ttu-id="a12d0-118">要素</span><span class="sxs-lookup"><span data-stu-id="a12d0-118">Element</span></span>|<span data-ttu-id="a12d0-119">説明</span><span class="sxs-lookup"><span data-stu-id="a12d0-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a12d0-120">\<trustedIssuers ></span><span class="sxs-lookup"><span data-stu-id="a12d0-120">\<trustedIssuers></span></span>](trustedissuers.md)|<span data-ttu-id="a12d0-121">属性で`type`構成ベースの発行者名レジストリ<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> (クラス) [ \<](trustedissuers.md)を指定する場合は、trustedIssuers > 要素を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a12d0-121">When the `type` attribute specifies the configuration-based issuer name registry (the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class), the [\<trustedIssuers>](trustedissuers.md) element must be specified.</span></span> <span data-ttu-id="a12d0-122">TrustedIssuers > 要素は、、 `<add>` `<clear>`、または`<remove>`要素を子要素として受け取ることができます。 [ \<](trustedissuers.md)</span><span class="sxs-lookup"><span data-stu-id="a12d0-122">The [\<trustedIssuers>](trustedissuers.md) element can take `<add>`, `<clear>`, or `<remove>` elements as child elements.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a12d0-123">親要素</span><span class="sxs-lookup"><span data-stu-id="a12d0-123">Parent Elements</span></span>  
  
|<span data-ttu-id="a12d0-124">要素</span><span class="sxs-lookup"><span data-stu-id="a12d0-124">Element</span></span>|<span data-ttu-id="a12d0-125">説明</span><span class="sxs-lookup"><span data-stu-id="a12d0-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a12d0-126">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="a12d0-126">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="a12d0-127">セキュリティトークンハンドラーのコレクションの構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="a12d0-127">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a12d0-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="a12d0-128">Remarks</span></span>  
 <span data-ttu-id="a12d0-129">発行者のトークンはすべて、発行者名レジストリを使用して検証されます。</span><span class="sxs-lookup"><span data-stu-id="a12d0-129">All issuer tokens are validated using an issuer name registry.</span></span> <span data-ttu-id="a12d0-130">これは、 <xref:System.IdentityModel.Tokens.IssuerNameRegistry>クラスから派生するオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="a12d0-130">This is an object that derives from the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class.</span></span> <span data-ttu-id="a12d0-131">発行者名レジストリは、対応する発行者によって生成されるトークンの署名を検証するために必要な暗号マテリアルにニーモニック名を関連付けるために使用されます。</span><span class="sxs-lookup"><span data-stu-id="a12d0-131">The issuer name registry is used to associate a mnemonic name to the cryptographic material that is needed to verify the signatures of tokens produced by the corresponding issuer.</span></span> <span data-ttu-id="a12d0-132">発行者名レジストリは、証明書利用者 (RP) アプリケーションによって信頼されている発行者の一覧を保持します。</span><span class="sxs-lookup"><span data-stu-id="a12d0-132">The issuer name registry maintains a list of issuers that are trusted by the relying party (RP) application.</span></span> <span data-ttu-id="a12d0-133">発行者名レジストリの種類は、 `type`属性を使用して指定されます。</span><span class="sxs-lookup"><span data-stu-id="a12d0-133">The type of the issuer name registry is specified using the `type` attribute.</span></span> <span data-ttu-id="a12d0-134">要素`<issuerNameRegistry>`は、指定された型の構成を提供する1つ以上の子要素を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="a12d0-134">The `<issuerNameRegistry>` element can have one or more child elements that provide configuration for the specified type.</span></span> <span data-ttu-id="a12d0-135">これらの子要素を処理するロジックは、 <xref:System.IdentityModel.Tokens.IssuerNameRegistry.LoadCustomConfiguration%2A>メソッドをオーバーライドすることによって指定します。</span><span class="sxs-lookup"><span data-stu-id="a12d0-135">You provide the logic that processes these child elements by overriding the <xref:System.IdentityModel.Tokens.IssuerNameRegistry.LoadCustomConfiguration%2A> method.</span></span>  
  
 <span data-ttu-id="a12d0-136">WIF では、単一の発行者名のレジストリの<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>種類が、クラスのすぐに使用できます。</span><span class="sxs-lookup"><span data-stu-id="a12d0-136">WIF provides a single issuer name registry type out of the box, the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class.</span></span> <span data-ttu-id="a12d0-137">このクラスは、構成で指定された信頼された発行者証明書のセットを使用します。</span><span class="sxs-lookup"><span data-stu-id="a12d0-137">This class uses a set of trusted issuer certificates that are specified in configuration.</span></span> <span data-ttu-id="a12d0-138">これには、信頼され`<trustedIssuers>`た発行元の証明書のコレクションを構成する子構成要素が必要です。</span><span class="sxs-lookup"><span data-stu-id="a12d0-138">It requires a child configuration element, `<trustedIssuers>`, under which the collection of trusted issuer certificates is configured.</span></span> <span data-ttu-id="a12d0-139">信頼された証明書は、asn.1 でエンコードされた証明書の拇印を使用して指定され`<add>`、 `<clear>`、、 `<remove>`または要素を使用してコレクションに追加または削除されます。</span><span class="sxs-lookup"><span data-stu-id="a12d0-139">Trusted certificates are specified using the ASN.1 encoded form of the certificate thumbprint and are added or removed from the collection by using `<add>`, `<clear>`, or `<remove>` elements.</span></span>  
  
 <span data-ttu-id="a12d0-140">要素は、 <xref:System.IdentityModel.Configuration.IssuerNameRegistryElement>クラスによって表されます。 `<issuerNameRegistry>`</span><span class="sxs-lookup"><span data-stu-id="a12d0-140">The `<issuerNameRegistry>` element is represented by the <xref:System.IdentityModel.Configuration.IssuerNameRegistryElement> class.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a12d0-141">要素を、指定した[ \<>](identityconfiguration.md)要素の子要素として指定することは推奨されていませんが、旧バージョンとの互換性のためにサポートされています。 `<issuerNameRegistry>`</span><span class="sxs-lookup"><span data-stu-id="a12d0-141">Specifying the `<issuerNameRegistry>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="a12d0-142">要素の設定`<securityTokenHandlerConfiguration>`は、要素の設定`<identityConfiguration>`よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="a12d0-142">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a12d0-143">例</span><span class="sxs-lookup"><span data-stu-id="a12d0-143">Example</span></span>  
 <span data-ttu-id="a12d0-144">次の XML は、構成ベースの発行者名レジストリを指定する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="a12d0-144">The following XML shows how to specify the configuration based issuer name registry.</span></span>  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB … 1EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a12d0-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="a12d0-145">See also</span></span>

- <xref:System.IdentityModel.Tokens.IssuerNameRegistry>
- <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>
