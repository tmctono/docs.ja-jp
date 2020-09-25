---
title: <trustedIssuers>
ms.date: 03/30/2017
ms.assetid: d818c917-07b4-40db-9801-8676561859fd
author: BrucePerlerMS
ms.openlocfilehash: 08cddd19f40f039f86e100cc7ee6a78633502eb2
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185562"
---
# \<trustedIssuers>

<span data-ttu-id="72bbd-101">構成ベースの発行者名レジストリ () によって使用される、信頼された発行者の証明書の一覧を構成し <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> ます。</span><span class="sxs-lookup"><span data-stu-id="72bbd-101">Configures the list of trusted issuer certificates used by the configuration-based issuer name registry (<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuerNameRegistry>**](issuernameregistry.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<trustedIssuers>**  
  
## <a name="syntax"></a><span data-ttu-id="72bbd-102">構文</span><span class="sxs-lookup"><span data-stu-id="72bbd-102">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <issuerNameRegistry>  
          <trustedIssuers>  
            <add thumbprint=xs:string name=xs:string>  
            <clear>  
            <remove thumbprint=xs:string>  
          </trustedIssuers>  
        </issuerNameRegistry>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="72bbd-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="72bbd-103">Attributes and Elements</span></span>  

 <span data-ttu-id="72bbd-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="72bbd-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="72bbd-105">属性</span><span class="sxs-lookup"><span data-stu-id="72bbd-105">Attributes</span></span>  

 <span data-ttu-id="72bbd-106">None</span><span class="sxs-lookup"><span data-stu-id="72bbd-106">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="72bbd-107">子要素</span><span class="sxs-lookup"><span data-stu-id="72bbd-107">Child Elements</span></span>  
  
|<span data-ttu-id="72bbd-108">要素</span><span class="sxs-lookup"><span data-stu-id="72bbd-108">Element</span></span>|<span data-ttu-id="72bbd-109">説明</span><span class="sxs-lookup"><span data-stu-id="72bbd-109">Description</span></span>|  
|-------------|-----------------|  
|`<add thumbprint=xs:string name=xs:string>`|<span data-ttu-id="72bbd-110">信頼された発行者のコレクションに証明書を追加します。</span><span class="sxs-lookup"><span data-stu-id="72bbd-110">Adds a certificate to the collection of trusted issuers.</span></span> <span data-ttu-id="72bbd-111">証明書は属性で指定され `thumbprint` ます。</span><span class="sxs-lookup"><span data-stu-id="72bbd-111">The certificate is specified with the `thumbprint` attribute.</span></span> <span data-ttu-id="72bbd-112">この属性は必須であり、証明書の拇印の asn.1 エンコード形式を含んでいる必要があります。</span><span class="sxs-lookup"><span data-stu-id="72bbd-112">This attribute is required and should contain the ASN.1 encoded form of the certificate thumbprint.</span></span> <span data-ttu-id="72bbd-113">`name`属性は省略可能で、証明書のフレンドリ名を指定するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="72bbd-113">The `name` attribute is optional and can be used to specify a friendly name for the certificate.</span></span>|  
|`<clear>`|<span data-ttu-id="72bbd-114">信頼された発行者のコレクションからすべての証明書を削除します。</span><span class="sxs-lookup"><span data-stu-id="72bbd-114">Clears all certificates from the collection of trusted issuers.</span></span>|  
|`<remove thumbprint=xs:string>`|<span data-ttu-id="72bbd-115">信頼された発行者のコレクションから証明書を削除します。</span><span class="sxs-lookup"><span data-stu-id="72bbd-115">Removes a certificate from the collection of trusted issuers.</span></span> <span data-ttu-id="72bbd-116">証明書は属性で指定され `thumbprint` ます。</span><span class="sxs-lookup"><span data-stu-id="72bbd-116">The certificate is specified with the `thumbprint` attribute.</span></span> <span data-ttu-id="72bbd-117">この属性は必須です。</span><span class="sxs-lookup"><span data-stu-id="72bbd-117">This attribute is required.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="72bbd-118">親要素</span><span class="sxs-lookup"><span data-stu-id="72bbd-118">Parent Elements</span></span>  
  
|<span data-ttu-id="72bbd-119">要素</span><span class="sxs-lookup"><span data-stu-id="72bbd-119">Element</span></span>|<span data-ttu-id="72bbd-120">説明</span><span class="sxs-lookup"><span data-stu-id="72bbd-120">Description</span></span>|  
|-------------|-----------------|  
|[\<issuerNameRegistry>](issuernameregistry.md)|<span data-ttu-id="72bbd-121">発行者名レジストリを構成します。</span><span class="sxs-lookup"><span data-stu-id="72bbd-121">Configures the issuer name registry.</span></span> <span data-ttu-id="72bbd-122">**重要:**  要素 `type` の属性は、 `<issuerNameRegistry>` 要素を有効にするためにクラスを参照する必要があり <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> `<trustedIssuers>` ます。</span><span class="sxs-lookup"><span data-stu-id="72bbd-122">**Important:**  The `type` attribute of the `<issuerNameRegistry>` element must reference the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class for the `<trustedIssuers>` element to be valid.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="72bbd-123">解説</span><span class="sxs-lookup"><span data-stu-id="72bbd-123">Remarks</span></span>  

 <span data-ttu-id="72bbd-124">Windows Identity Foundation (WIF) は、クラスの1つの実装を、クラスのすぐに使用できるようにし <xref:System.IdentityModel.Tokens.IssuerNameRegistry> <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> ます。</span><span class="sxs-lookup"><span data-stu-id="72bbd-124">Windows Identity Foundation (WIF) provides a single implementation of the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class out of the box, the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class.</span></span> <span data-ttu-id="72bbd-125">構成発行者名レジストリは、構成から読み込まれる信頼された発行者の一覧を保持します。</span><span class="sxs-lookup"><span data-stu-id="72bbd-125">The configuration issuer name registry maintains a list of trusted issuers that is loaded from configuration.</span></span> <span data-ttu-id="72bbd-126">リストでは、発行者によって生成されたトークンの署名を検証するために必要な x.509 証明書に各発行者名が関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="72bbd-126">The list associates each issuer name with the X.509 certificate that is needed to verify the signature of tokens produced by the issuer.</span></span> <span data-ttu-id="72bbd-127">信頼された発行者の証明書の一覧は、要素の下で指定され `<trustedIssuers>` ます。</span><span class="sxs-lookup"><span data-stu-id="72bbd-127">The list of trusted issuer certificates is specified under the `<trustedIssuers>` element.</span></span> <span data-ttu-id="72bbd-128">リスト内の各要素は、ニーモニック発行者名と、その発行者によって生成されるトークンの署名を検証するために必要な x.509 証明書を関連付けます。</span><span class="sxs-lookup"><span data-stu-id="72bbd-128">Each element in the list associates a mnemonic issuer name with the X.509 certificate that is needed to verify the signature of tokens produced by that issuer.</span></span> <span data-ttu-id="72bbd-129">信頼された証明書は、asn.1 エンコード形式の証明書の拇印を使用して指定され、要素を使用してコレクションに追加され `<add>` ます。</span><span class="sxs-lookup"><span data-stu-id="72bbd-129">Trusted certificates are specified using the ASN.1 encoded form of the certificate thumbprint and are added the collection by using `<add>` element.</span></span> <span data-ttu-id="72bbd-130">要素と要素を使用して、一覧から発行者 (証明書) を消去または削除でき `<clear>` `<remove>` ます。</span><span class="sxs-lookup"><span data-stu-id="72bbd-130">You can clear or remove issuers (certificates) from the list by using the `<clear>` and `<remove>` elements.</span></span>  
  
 <span data-ttu-id="72bbd-131">要素 `type` の属性は、 `<issuerNameRegistry>` 要素を有効にするためにクラスを参照する必要があり <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> `<trustedIssuers>` ます。</span><span class="sxs-lookup"><span data-stu-id="72bbd-131">The `type` attribute of the `<issuerNameRegistry>` element must reference the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class for the `<trustedIssuers>` element to be valid.</span></span>  
  
## <a name="example"></a><span data-ttu-id="72bbd-132">例</span><span class="sxs-lookup"><span data-stu-id="72bbd-132">Example</span></span>  

 <span data-ttu-id="72bbd-133">次の XML は、構成ベースの発行者名レジストリを指定する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="72bbd-133">The following XML shows how to specify the configuration based issuer name registry.</span></span>  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB2F32 … B1DC01EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a><span data-ttu-id="72bbd-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="72bbd-134">See also</span></span>

- <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>
- <xref:System.IdentityModel.Tokens.IssuerNameRegistry>
