---
title: <issuerNameRegistry>
ms.date: 03/30/2017
ms.assetid: 58b39d12-c953-40c4-88af-d7eb3343ca28
author: BrucePerlerMS
ms.openlocfilehash: 9991430f09cb6a63d0a3cdde24a4ff03d3dd746d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91165053"
---
# \<issuerNameRegistry>

<span data-ttu-id="88c10-101">トークンハンドラーコレクションのハンドラーによって使用される発行者名レジストリを構成します。</span><span class="sxs-lookup"><span data-stu-id="88c10-101">Configures the issuer name registry that is used by handlers in the token handler collection.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuerNameRegistry>**  
  
## <a name="syntax"></a><span data-ttu-id="88c10-102">構文</span><span class="sxs-lookup"><span data-stu-id="88c10-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="88c10-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="88c10-103">Attributes and Elements</span></span>  

 <span data-ttu-id="88c10-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="88c10-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="88c10-105">属性</span><span class="sxs-lookup"><span data-stu-id="88c10-105">Attributes</span></span>  
  
|<span data-ttu-id="88c10-106">属性</span><span class="sxs-lookup"><span data-stu-id="88c10-106">Attribute</span></span>|<span data-ttu-id="88c10-107">[説明]</span><span class="sxs-lookup"><span data-stu-id="88c10-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="88c10-108">type</span><span class="sxs-lookup"><span data-stu-id="88c10-108">type</span></span>|<span data-ttu-id="88c10-109">クラスから派生する型 <xref:System.IdentityModel.Tokens.IssuerNameRegistry> 。</span><span class="sxs-lookup"><span data-stu-id="88c10-109">A type that derives from the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class.</span></span> <span data-ttu-id="88c10-110">カスタムを指定する方法の詳細については `type` 、「[カスタム型参照]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="88c10-110">For more information about how to specify a custom `type`, see [Custom Type References].</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="88c10-111">子要素</span><span class="sxs-lookup"><span data-stu-id="88c10-111">Child Elements</span></span>  
  
|<span data-ttu-id="88c10-112">要素</span><span class="sxs-lookup"><span data-stu-id="88c10-112">Element</span></span>|<span data-ttu-id="88c10-113">説明</span><span class="sxs-lookup"><span data-stu-id="88c10-113">Description</span></span>|  
|-------------|-----------------|  
|[\<trustedIssuers>](trustedissuers.md)|<span data-ttu-id="88c10-114">属性で `type` 構成ベースの発行者名レジストリ (クラス) を指定する場合は、 <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> [\<trustedIssuers>](trustedissuers.md) 要素を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="88c10-114">When the `type` attribute specifies the configuration-based issuer name registry (the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class), the [\<trustedIssuers>](trustedissuers.md) element must be specified.</span></span> <span data-ttu-id="88c10-115">[\<trustedIssuers>](trustedissuers.md)要素は `<add>` 、 `<clear>` `<remove>` 子要素として、、またはの各要素を受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="88c10-115">The [\<trustedIssuers>](trustedissuers.md) element can take `<add>`, `<clear>`, or `<remove>` elements as child elements.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="88c10-116">親要素</span><span class="sxs-lookup"><span data-stu-id="88c10-116">Parent Elements</span></span>  
  
|<span data-ttu-id="88c10-117">要素</span><span class="sxs-lookup"><span data-stu-id="88c10-117">Element</span></span>|<span data-ttu-id="88c10-118">説明</span><span class="sxs-lookup"><span data-stu-id="88c10-118">Description</span></span>|  
|-------------|-----------------|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="88c10-119">セキュリティトークンハンドラーのコレクションの構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="88c10-119">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="88c10-120">解説</span><span class="sxs-lookup"><span data-stu-id="88c10-120">Remarks</span></span>  

 <span data-ttu-id="88c10-121">発行者のトークンはすべて、発行者名レジストリを使用して検証されます。</span><span class="sxs-lookup"><span data-stu-id="88c10-121">All issuer tokens are validated using an issuer name registry.</span></span> <span data-ttu-id="88c10-122">これは、クラスから派生するオブジェクトです <xref:System.IdentityModel.Tokens.IssuerNameRegistry> 。</span><span class="sxs-lookup"><span data-stu-id="88c10-122">This is an object that derives from the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class.</span></span> <span data-ttu-id="88c10-123">発行者名レジストリは、対応する発行者によって生成されるトークンの署名を検証するために必要な暗号マテリアルにニーモニック名を関連付けるために使用されます。</span><span class="sxs-lookup"><span data-stu-id="88c10-123">The issuer name registry is used to associate a mnemonic name to the cryptographic material that is needed to verify the signatures of tokens produced by the corresponding issuer.</span></span> <span data-ttu-id="88c10-124">発行者名レジストリは、証明書利用者 (RP) アプリケーションによって信頼されている発行者の一覧を保持します。</span><span class="sxs-lookup"><span data-stu-id="88c10-124">The issuer name registry maintains a list of issuers that are trusted by the relying party (RP) application.</span></span> <span data-ttu-id="88c10-125">発行者名レジストリの種類は、属性を使用して指定され `type` ます。</span><span class="sxs-lookup"><span data-stu-id="88c10-125">The type of the issuer name registry is specified using the `type` attribute.</span></span> <span data-ttu-id="88c10-126">要素は、 `<issuerNameRegistry>` 指定された型の構成を提供する1つ以上の子要素を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="88c10-126">The `<issuerNameRegistry>` element can have one or more child elements that provide configuration for the specified type.</span></span> <span data-ttu-id="88c10-127">これらの子要素を処理するロジックは、メソッドをオーバーライドすることによって指定し <xref:System.IdentityModel.Tokens.IssuerNameRegistry.LoadCustomConfiguration%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="88c10-127">You provide the logic that processes these child elements by overriding the <xref:System.IdentityModel.Tokens.IssuerNameRegistry.LoadCustomConfiguration%2A> method.</span></span>  
  
 <span data-ttu-id="88c10-128">WIF では、単一の発行者名のレジストリの種類が、クラスのすぐに使用 <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> できます。</span><span class="sxs-lookup"><span data-stu-id="88c10-128">WIF provides a single issuer name registry type out of the box, the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class.</span></span> <span data-ttu-id="88c10-129">このクラスは、構成で指定された信頼された発行者証明書のセットを使用します。</span><span class="sxs-lookup"><span data-stu-id="88c10-129">This class uses a set of trusted issuer certificates that are specified in configuration.</span></span> <span data-ttu-id="88c10-130">これには、 `<trustedIssuers>` 信頼された発行元の証明書のコレクションを構成する子構成要素が必要です。</span><span class="sxs-lookup"><span data-stu-id="88c10-130">It requires a child configuration element, `<trustedIssuers>`, under which the collection of trusted issuer certificates is configured.</span></span> <span data-ttu-id="88c10-131">信頼された証明書は、asn.1 でエンコードされた証明書の拇印を使用して指定され、 `<add>` 、 `<clear>` 、または要素を使用してコレクションに追加または削除され `<remove>` ます。</span><span class="sxs-lookup"><span data-stu-id="88c10-131">Trusted certificates are specified using the ASN.1 encoded form of the certificate thumbprint and are added or removed from the collection by using `<add>`, `<clear>`, or `<remove>` elements.</span></span>  
  
 <span data-ttu-id="88c10-132">`<issuerNameRegistry>`要素は、クラスによって表され <xref:System.IdentityModel.Configuration.IssuerNameRegistryElement> ます。</span><span class="sxs-lookup"><span data-stu-id="88c10-132">The `<issuerNameRegistry>` element is represented by the <xref:System.IdentityModel.Configuration.IssuerNameRegistryElement> class.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="88c10-133">要素 `<issuerNameRegistry>` の子要素としての指定 [\<identityConfiguration>](identityconfiguration.md) は非推奨とされましたが、旧バージョンとの互換性のために引き続きサポートされています。</span><span class="sxs-lookup"><span data-stu-id="88c10-133">Specifying the `<issuerNameRegistry>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="88c10-134">要素の設定は、要素の設定 `<securityTokenHandlerConfiguration>` よりも優先さ `<identityConfiguration>` れます。</span><span class="sxs-lookup"><span data-stu-id="88c10-134">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="88c10-135">例</span><span class="sxs-lookup"><span data-stu-id="88c10-135">Example</span></span>  

 <span data-ttu-id="88c10-136">次の XML は、構成ベースの発行者名レジストリを指定する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="88c10-136">The following XML shows how to specify the configuration based issuer name registry.</span></span>  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB … 1EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a><span data-ttu-id="88c10-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="88c10-137">See also</span></span>

- <xref:System.IdentityModel.Tokens.IssuerNameRegistry>
- <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>
