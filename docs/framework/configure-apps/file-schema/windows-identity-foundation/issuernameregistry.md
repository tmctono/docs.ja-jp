---
title: <issuerNameRegistry>
ms.date: 03/30/2017
ms.assetid: 58b39d12-c953-40c4-88af-d7eb3343ca28
author: BrucePerlerMS
ms.openlocfilehash: 209e702da80f2569f2b6c068f50f1af4489157f6
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251965"
---
# <a name="issuernameregistry"></a><span data-ttu-id="5bc41-101">\<issuerNameRegistry ></span><span class="sxs-lookup"><span data-stu-id="5bc41-101">\<issuerNameRegistry></span></span>
<span data-ttu-id="5bc41-102">トークンハンドラーコレクションのハンドラーによって使用される発行者名レジストリを構成します。</span><span class="sxs-lookup"><span data-stu-id="5bc41-102">Configures the issuer name registry that is used by handlers in the token handler collection.</span></span>  
  
<span data-ttu-id="5bc41-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="5bc41-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="5bc41-104">&nbsp;&nbsp;[ **\<システムの >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="5bc41-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="5bc41-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<構成 >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="5bc41-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="5bc41-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlers >** ](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="5bc41-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="5bc41-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlerConfiguration >** ](securitytokenhandlerconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="5bc41-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)</span></span>\
<span data-ttu-id="5bc41-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<issuerNameRegistry >**</span><span class="sxs-lookup"><span data-stu-id="5bc41-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuerNameRegistry>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5bc41-109">構文</span><span class="sxs-lookup"><span data-stu-id="5bc41-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5bc41-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="5bc41-110">Attributes and Elements</span></span>  
 <span data-ttu-id="5bc41-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="5bc41-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5bc41-112">属性</span><span class="sxs-lookup"><span data-stu-id="5bc41-112">Attributes</span></span>  
  
|<span data-ttu-id="5bc41-113">属性</span><span class="sxs-lookup"><span data-stu-id="5bc41-113">Attribute</span></span>|<span data-ttu-id="5bc41-114">説明</span><span class="sxs-lookup"><span data-stu-id="5bc41-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5bc41-115">型</span><span class="sxs-lookup"><span data-stu-id="5bc41-115">type</span></span>|<span data-ttu-id="5bc41-116"><xref:System.IdentityModel.Tokens.IssuerNameRegistry>クラスから派生する型。</span><span class="sxs-lookup"><span data-stu-id="5bc41-116">A type that derives from the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class.</span></span> <span data-ttu-id="5bc41-117">カスタム`type`を指定する方法の詳細については、「[カスタム型参照]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5bc41-117">For more information about how to specify a custom `type`, see [Custom Type References].</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5bc41-118">子要素</span><span class="sxs-lookup"><span data-stu-id="5bc41-118">Child Elements</span></span>  
  
|<span data-ttu-id="5bc41-119">要素</span><span class="sxs-lookup"><span data-stu-id="5bc41-119">Element</span></span>|<span data-ttu-id="5bc41-120">説明</span><span class="sxs-lookup"><span data-stu-id="5bc41-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5bc41-121">\<trustedIssuers ></span><span class="sxs-lookup"><span data-stu-id="5bc41-121">\<trustedIssuers></span></span>](trustedissuers.md)|<span data-ttu-id="5bc41-122">属性で`type`構成ベースの発行者名レジストリ<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> (クラス) [ \<](trustedissuers.md)を指定する場合は、trustedIssuers > 要素を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5bc41-122">When the `type` attribute specifies the configuration-based issuer name registry (the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class), the [\<trustedIssuers>](trustedissuers.md) element must be specified.</span></span> <span data-ttu-id="5bc41-123">TrustedIssuers > 要素は、、 `<add>` `<clear>`、または`<remove>`要素を子要素として受け取ることができます。 [ \<](trustedissuers.md)</span><span class="sxs-lookup"><span data-stu-id="5bc41-123">The [\<trustedIssuers>](trustedissuers.md) element can take `<add>`, `<clear>`, or `<remove>` elements as child elements.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5bc41-124">親要素</span><span class="sxs-lookup"><span data-stu-id="5bc41-124">Parent Elements</span></span>  
  
|<span data-ttu-id="5bc41-125">要素</span><span class="sxs-lookup"><span data-stu-id="5bc41-125">Element</span></span>|<span data-ttu-id="5bc41-126">説明</span><span class="sxs-lookup"><span data-stu-id="5bc41-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5bc41-127">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="5bc41-127">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="5bc41-128">セキュリティトークンハンドラーのコレクションの構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="5bc41-128">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5bc41-129">Remarks</span><span class="sxs-lookup"><span data-stu-id="5bc41-129">Remarks</span></span>  
 <span data-ttu-id="5bc41-130">発行者のトークンはすべて、発行者名レジストリを使用して検証されます。</span><span class="sxs-lookup"><span data-stu-id="5bc41-130">All issuer tokens are validated using an issuer name registry.</span></span> <span data-ttu-id="5bc41-131">これは、 <xref:System.IdentityModel.Tokens.IssuerNameRegistry>クラスから派生するオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="5bc41-131">This is an object that derives from the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class.</span></span> <span data-ttu-id="5bc41-132">発行者名レジストリは、対応する発行者によって生成されるトークンの署名を検証するために必要な暗号マテリアルにニーモニック名を関連付けるために使用されます。</span><span class="sxs-lookup"><span data-stu-id="5bc41-132">The issuer name registry is used to associate a mnemonic name to the cryptographic material that is needed to verify the signatures of tokens produced by the corresponding issuer.</span></span> <span data-ttu-id="5bc41-133">発行者名レジストリは、証明書利用者 (RP) アプリケーションによって信頼されている発行者の一覧を保持します。</span><span class="sxs-lookup"><span data-stu-id="5bc41-133">The issuer name registry maintains a list of issuers that are trusted by the relying party (RP) application.</span></span> <span data-ttu-id="5bc41-134">発行者名レジストリの種類は、 `type`属性を使用して指定されます。</span><span class="sxs-lookup"><span data-stu-id="5bc41-134">The type of the issuer name registry is specified using the `type` attribute.</span></span> <span data-ttu-id="5bc41-135">要素`<issuerNameRegistry>`は、指定された型の構成を提供する1つ以上の子要素を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="5bc41-135">The `<issuerNameRegistry>` element can have one or more child elements that provide configuration for the specified type.</span></span> <span data-ttu-id="5bc41-136">これらの子要素を処理するロジックは、 <xref:System.IdentityModel.Tokens.IssuerNameRegistry.LoadCustomConfiguration%2A>メソッドをオーバーライドすることによって指定します。</span><span class="sxs-lookup"><span data-stu-id="5bc41-136">You provide the logic that processes these child elements by overriding the <xref:System.IdentityModel.Tokens.IssuerNameRegistry.LoadCustomConfiguration%2A> method.</span></span>  
  
 <span data-ttu-id="5bc41-137">WIF では、単一の発行者名のレジストリの<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>種類が、クラスのすぐに使用できます。</span><span class="sxs-lookup"><span data-stu-id="5bc41-137">WIF provides a single issuer name registry type out of the box, the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class.</span></span> <span data-ttu-id="5bc41-138">このクラスは、構成で指定された信頼された発行者証明書のセットを使用します。</span><span class="sxs-lookup"><span data-stu-id="5bc41-138">This class uses a set of trusted issuer certificates that are specified in configuration.</span></span> <span data-ttu-id="5bc41-139">これには、信頼され`<trustedIssuers>`た発行元の証明書のコレクションを構成する子構成要素が必要です。</span><span class="sxs-lookup"><span data-stu-id="5bc41-139">It requires a child configuration element, `<trustedIssuers>`, under which the collection of trusted issuer certificates is configured.</span></span> <span data-ttu-id="5bc41-140">信頼された証明書は、asn.1 でエンコードされた証明書の拇印を使用して指定され`<add>`、 `<clear>`、、 `<remove>`または要素を使用してコレクションに追加または削除されます。</span><span class="sxs-lookup"><span data-stu-id="5bc41-140">Trusted certificates are specified using the ASN.1 encoded form of the certificate thumbprint and are added or removed from the collection by using `<add>`, `<clear>`, or `<remove>` elements.</span></span>  
  
 <span data-ttu-id="5bc41-141">要素は、 <xref:System.IdentityModel.Configuration.IssuerNameRegistryElement>クラスによって表されます。 `<issuerNameRegistry>`</span><span class="sxs-lookup"><span data-stu-id="5bc41-141">The `<issuerNameRegistry>` element is represented by the <xref:System.IdentityModel.Configuration.IssuerNameRegistryElement> class.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5bc41-142">要素を、指定した[ \<>](identityconfiguration.md)要素の子要素として指定することは推奨されていませんが、旧バージョンとの互換性のためにサポートされています。 `<issuerNameRegistry>`</span><span class="sxs-lookup"><span data-stu-id="5bc41-142">Specifying the `<issuerNameRegistry>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="5bc41-143">要素の設定`<securityTokenHandlerConfiguration>`は、要素の設定`<identityConfiguration>`よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="5bc41-143">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5bc41-144">例</span><span class="sxs-lookup"><span data-stu-id="5bc41-144">Example</span></span>  
 <span data-ttu-id="5bc41-145">次の XML は、構成ベースの発行者名レジストリを指定する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="5bc41-145">The following XML shows how to specify the configuration based issuer name registry.</span></span>  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB … 1EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5bc41-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="5bc41-146">See also</span></span>

- <xref:System.IdentityModel.Tokens.IssuerNameRegistry>
- <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>
