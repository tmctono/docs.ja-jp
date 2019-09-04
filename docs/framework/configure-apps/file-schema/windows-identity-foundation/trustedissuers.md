---
title: <trustedIssuers>
ms.date: 03/30/2017
ms.assetid: d818c917-07b4-40db-9801-8676561859fd
author: BrucePerlerMS
ms.openlocfilehash: 50fc7194823fb0c5c426fb54ffd50b17c3714ed9
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251756"
---
# <a name="trustedissuers"></a><span data-ttu-id="afb1c-101">\<trustedIssuers ></span><span class="sxs-lookup"><span data-stu-id="afb1c-101">\<trustedIssuers></span></span>
<span data-ttu-id="afb1c-102">構成ベースの発行者名レジストリ (<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>) によって使用される、信頼された発行者の証明書の一覧を構成します。</span><span class="sxs-lookup"><span data-stu-id="afb1c-102">Configures the list of trusted issuer certificates used by the configuration-based issuer name registry (<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>).</span></span>  
  
<span data-ttu-id="afb1c-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="afb1c-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="afb1c-104">&nbsp;&nbsp;[ **\<システムの >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="afb1c-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="afb1c-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<構成 >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="afb1c-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="afb1c-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlers >** ](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="afb1c-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="afb1c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlerConfiguration >** ](securitytokenhandlerconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="afb1c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)</span></span>\
<span data-ttu-id="afb1c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<issuerNameRegistry >** ](issuernameregistry.md)</span><span class="sxs-lookup"><span data-stu-id="afb1c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuerNameRegistry>**](issuernameregistry.md)</span></span>\
<span data-ttu-id="afb1c-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<trustedIssuers >**</span><span class="sxs-lookup"><span data-stu-id="afb1c-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<trustedIssuers>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="afb1c-110">構文</span><span class="sxs-lookup"><span data-stu-id="afb1c-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="afb1c-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="afb1c-111">Attributes and Elements</span></span>  
 <span data-ttu-id="afb1c-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="afb1c-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="afb1c-113">属性</span><span class="sxs-lookup"><span data-stu-id="afb1c-113">Attributes</span></span>  
 <span data-ttu-id="afb1c-114">なし</span><span class="sxs-lookup"><span data-stu-id="afb1c-114">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="afb1c-115">子要素</span><span class="sxs-lookup"><span data-stu-id="afb1c-115">Child Elements</span></span>  
  
|<span data-ttu-id="afb1c-116">要素</span><span class="sxs-lookup"><span data-stu-id="afb1c-116">Element</span></span>|<span data-ttu-id="afb1c-117">説明</span><span class="sxs-lookup"><span data-stu-id="afb1c-117">Description</span></span>|  
|-------------|-----------------|  
|`<add thumbprint=xs:string name=xs:string>`|<span data-ttu-id="afb1c-118">信頼された発行者のコレクションに証明書を追加します。</span><span class="sxs-lookup"><span data-stu-id="afb1c-118">Adds a certificate to the collection of trusted issuers.</span></span> <span data-ttu-id="afb1c-119">証明書は`thumbprint`属性で指定されます。</span><span class="sxs-lookup"><span data-stu-id="afb1c-119">The certificate is specified with the `thumbprint` attribute.</span></span> <span data-ttu-id="afb1c-120">この属性は必須であり、証明書の拇印の asn.1 エンコード形式を含んでいる必要があります。</span><span class="sxs-lookup"><span data-stu-id="afb1c-120">This attribute is required and should contain the ASN.1 encoded form of the certificate thumbprint.</span></span> <span data-ttu-id="afb1c-121">`name`属性は省略可能で、証明書のフレンドリ名を指定するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="afb1c-121">The `name` attribute is optional and can be used to specify a friendly name for the certificate.</span></span>|  
|`<clear>`|<span data-ttu-id="afb1c-122">信頼された発行者のコレクションからすべての証明書を削除します。</span><span class="sxs-lookup"><span data-stu-id="afb1c-122">Clears all certificates from the collection of trusted issuers.</span></span>|  
|`<remove thumbprint=xs:string>`|<span data-ttu-id="afb1c-123">信頼された発行者のコレクションから証明書を削除します。</span><span class="sxs-lookup"><span data-stu-id="afb1c-123">Removes a certificate from the collection of trusted issuers.</span></span> <span data-ttu-id="afb1c-124">証明書は`thumbprint`属性で指定されます。</span><span class="sxs-lookup"><span data-stu-id="afb1c-124">The certificate is specified with the `thumbprint` attribute.</span></span> <span data-ttu-id="afb1c-125">この属性は必須です。</span><span class="sxs-lookup"><span data-stu-id="afb1c-125">This attribute is required.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="afb1c-126">親要素</span><span class="sxs-lookup"><span data-stu-id="afb1c-126">Parent Elements</span></span>  
  
|<span data-ttu-id="afb1c-127">要素</span><span class="sxs-lookup"><span data-stu-id="afb1c-127">Element</span></span>|<span data-ttu-id="afb1c-128">説明</span><span class="sxs-lookup"><span data-stu-id="afb1c-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="afb1c-129">\<issuerNameRegistry ></span><span class="sxs-lookup"><span data-stu-id="afb1c-129">\<issuerNameRegistry></span></span>](issuernameregistry.md)|<span data-ttu-id="afb1c-130">発行者名レジストリを構成します。</span><span class="sxs-lookup"><span data-stu-id="afb1c-130">Configures the issuer name registry.</span></span> <span data-ttu-id="afb1c-131">**重要:** 要素`type` <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>の属性は、 `<trustedIssuers>`要素を有効にするためにクラスを参照する必要があります。 `<issuerNameRegistry>`</span><span class="sxs-lookup"><span data-stu-id="afb1c-131">**Important:**  The `type` attribute of the `<issuerNameRegistry>` element must reference the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class for the `<trustedIssuers>` element to be valid.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="afb1c-132">Remarks</span><span class="sxs-lookup"><span data-stu-id="afb1c-132">Remarks</span></span>  
 <span data-ttu-id="afb1c-133">Windows Identity Foundation (WIF) は、クラスの1つ<xref:System.IdentityModel.Tokens.IssuerNameRegistry>の実装を、 <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>クラスのすぐに使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="afb1c-133">Windows Identity Foundation (WIF) provides a single implementation of the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class out of the box, the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class.</span></span> <span data-ttu-id="afb1c-134">構成発行者名レジストリは、構成から読み込まれる信頼された発行者の一覧を保持します。</span><span class="sxs-lookup"><span data-stu-id="afb1c-134">The configuration issuer name registry maintains a list of trusted issuers that is loaded from configuration.</span></span> <span data-ttu-id="afb1c-135">リストでは、発行者によって生成されたトークンの署名を検証するために必要な x.509 証明書に各発行者名が関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="afb1c-135">The list associates each issuer name with the X.509 certificate that is needed to verify the signature of tokens produced by the issuer.</span></span> <span data-ttu-id="afb1c-136">信頼された発行者の証明書の`<trustedIssuers>`一覧は、要素の下で指定されます。</span><span class="sxs-lookup"><span data-stu-id="afb1c-136">The list of trusted issuer certificates is specified under the `<trustedIssuers>` element.</span></span> <span data-ttu-id="afb1c-137">リスト内の各要素は、ニーモニック発行者名と、その発行者によって生成されるトークンの署名を検証するために必要な x.509 証明書を関連付けます。</span><span class="sxs-lookup"><span data-stu-id="afb1c-137">Each element in the list associates a mnemonic issuer name with the X.509 certificate that is needed to verify the signature of tokens produced by that issuer.</span></span> <span data-ttu-id="afb1c-138">信頼された証明書は、asn.1 エンコード形式の証明書の拇印を使用して指定さ`<add>`れ、要素を使用してコレクションに追加されます。</span><span class="sxs-lookup"><span data-stu-id="afb1c-138">Trusted certificates are specified using the ASN.1 encoded form of the certificate thumbprint and are added the collection by using `<add>` element.</span></span> <span data-ttu-id="afb1c-139">要素`<clear>` と`<remove>`要素を使用して、一覧から発行者 (証明書) を消去または削除できます。</span><span class="sxs-lookup"><span data-stu-id="afb1c-139">You can clear or remove issuers (certificates) from the list by using the `<clear>` and `<remove>` elements.</span></span>  
  
 <span data-ttu-id="afb1c-140">要素`type` <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>の属性は、 `<trustedIssuers>`要素を有効にするためにクラスを参照する必要があります。 `<issuerNameRegistry>`</span><span class="sxs-lookup"><span data-stu-id="afb1c-140">The `type` attribute of the `<issuerNameRegistry>` element must reference the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class for the `<trustedIssuers>` element to be valid.</span></span>  
  
## <a name="example"></a><span data-ttu-id="afb1c-141">例</span><span class="sxs-lookup"><span data-stu-id="afb1c-141">Example</span></span>  
 <span data-ttu-id="afb1c-142">次の XML は、構成ベースの発行者名レジストリを指定する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="afb1c-142">The following XML shows how to specify the configuration based issuer name registry.</span></span>  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB2F32 … B1DC01EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a><span data-ttu-id="afb1c-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="afb1c-143">See also</span></span>

- <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>
- <xref:System.IdentityModel.Tokens.IssuerNameRegistry>
