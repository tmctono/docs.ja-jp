---
title: <issuerTokenResolver>
ms.date: 03/30/2017
ms.assetid: f74392f6-3f5b-4880-bd8a-3a9130d31e65
author: BrucePerlerMS
ms.openlocfilehash: da591940910b16d42ef8ab1a05c4b244dbe543f4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942628"
---
# <a name="issuertokenresolver"></a><span data-ttu-id="b53f9-101">\<issuerTokenResolver ></span><span class="sxs-lookup"><span data-stu-id="b53f9-101">\<issuerTokenResolver></span></span>
<span data-ttu-id="b53f9-102">トークンハンドラーコレクションのハンドラーによって使用される発行者トークンリゾルバーを登録します。</span><span class="sxs-lookup"><span data-stu-id="b53f9-102">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="b53f9-103">発行者トークンリゾルバーは、受信トークンとメッセージの署名トークンを解決するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="b53f9-103">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span>  
  
 <span data-ttu-id="b53f9-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="b53f9-104">\<system.identityModel></span></span>  
<span data-ttu-id="b53f9-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="b53f9-105">\<identityConfiguration></span></span>  
<span data-ttu-id="b53f9-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="b53f9-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="b53f9-107">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="b53f9-107">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="b53f9-108">\<issuerTokenResolver ></span><span class="sxs-lookup"><span data-stu-id="b53f9-108">\<issuerTokenResolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b53f9-109">構文</span><span class="sxs-lookup"><span data-stu-id="b53f9-109">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <issuerTokenResolver type=xs:string>  
        </issuerTokenResolver>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b53f9-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="b53f9-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b53f9-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="b53f9-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b53f9-112">属性</span><span class="sxs-lookup"><span data-stu-id="b53f9-112">Attributes</span></span>  
  
|<span data-ttu-id="b53f9-113">属性</span><span class="sxs-lookup"><span data-stu-id="b53f9-113">Attribute</span></span>|<span data-ttu-id="b53f9-114">説明</span><span class="sxs-lookup"><span data-stu-id="b53f9-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b53f9-115">種類</span><span class="sxs-lookup"><span data-stu-id="b53f9-115">type</span></span>|<span data-ttu-id="b53f9-116">発行者トークンリゾルバーの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="b53f9-116">Specifies the type of the issuer token resolver.</span></span> <span data-ttu-id="b53f9-117">は、クラスまた<xref:System.IdentityModel.Tokens.IssuerTokenResolver>は<xref:System.IdentityModel.Tokens.IssuerTokenResolver>クラスから派生した型のいずれかである必要があります。</span><span class="sxs-lookup"><span data-stu-id="b53f9-117">Must be either the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class or a type that derives from the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class.</span></span> <span data-ttu-id="b53f9-118">必須。</span><span class="sxs-lookup"><span data-stu-id="b53f9-118">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b53f9-119">子要素</span><span class="sxs-lookup"><span data-stu-id="b53f9-119">Child Elements</span></span>  
 <span data-ttu-id="b53f9-120">なし</span><span class="sxs-lookup"><span data-stu-id="b53f9-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b53f9-121">親要素</span><span class="sxs-lookup"><span data-stu-id="b53f9-121">Parent Elements</span></span>  
  
|<span data-ttu-id="b53f9-122">要素</span><span class="sxs-lookup"><span data-stu-id="b53f9-122">Element</span></span>|<span data-ttu-id="b53f9-123">説明</span><span class="sxs-lookup"><span data-stu-id="b53f9-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b53f9-124">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="b53f9-124">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="b53f9-125">セキュリティトークンハンドラーのコレクションの構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="b53f9-125">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b53f9-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="b53f9-126">Remarks</span></span>  
 <span data-ttu-id="b53f9-127">発行者トークンリゾルバーは、受信トークンとメッセージの署名トークンを解決するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="b53f9-127">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="b53f9-128">署名の確認に使用される暗号化マテリアルを取得するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="b53f9-128">It is used to retrieve the cryptographic material that is used for checking the signature.</span></span> <span data-ttu-id="b53f9-129">`type`属性を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b53f9-129">You must specify the `type` attribute.</span></span> <span data-ttu-id="b53f9-130">指定できる型は、また<xref:System.IdentityModel.Tokens.IssuerTokenResolver>は<xref:System.IdentityModel.Tokens.IssuerTokenResolver>クラスから派生したカスタム型のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="b53f9-130">The type specified can be either <xref:System.IdentityModel.Tokens.IssuerTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class.</span></span>  
  
 <span data-ttu-id="b53f9-131">一部のトークンハンドラーでは、構成で発行者トークンリゾルバーの設定を指定できます。</span><span class="sxs-lookup"><span data-stu-id="b53f9-131">Some token handlers allow you to specify issuer token resolver settings in configuration.</span></span> <span data-ttu-id="b53f9-132">個々のトークンハンドラーの設定は、セキュリティトークンハンドラーコレクションで指定された設定よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="b53f9-132">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b53f9-133">要素を、指定した[ \<>](identityconfiguration.md)要素の子要素として指定することは推奨されていませんが、旧バージョンとの互換性のためにサポートされています。 `<issuerTokenResolver>`</span><span class="sxs-lookup"><span data-stu-id="b53f9-133">Specifying the `<issuerTokenResolver>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="b53f9-134">要素の設定`<securityTokenHandlerConfiguration>`は、要素の設定`<identityConfiguration>`よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="b53f9-134">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b53f9-135">例</span><span class="sxs-lookup"><span data-stu-id="b53f9-135">Example</span></span>  
 <span data-ttu-id="b53f9-136">次の XML は、から<xref:System.IdentityModel.Tokens.IssuerTokenResolver>派生したカスタムクラスに基づく発行者トークンリゾルバーの構成を示しています。</span><span class="sxs-lookup"><span data-stu-id="b53f9-136">The following XML shows configuration for an issuer token resolver that is based on a custom class that derives from <xref:System.IdentityModel.Tokens.IssuerTokenResolver>.</span></span> <span data-ttu-id="b53f9-137">トークンリゾルバーは、クラスに対して定義されているカスタム構成要素 (`<AddAudienceKeyPair>`) から初期化される、ユーザーとキーのペアのディクショナリを保持します。</span><span class="sxs-lookup"><span data-stu-id="b53f9-137">The token resolver maintains a dictionary of audience-key pairs that is initialized from a custom configuration element (`<AddAudienceKeyPair>`) defined for the class.</span></span> <span data-ttu-id="b53f9-138">クラスは、 <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A>メソッドをオーバーライドしてこの要素を処理します。</span><span class="sxs-lookup"><span data-stu-id="b53f9-138">The class overrides the <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> method to process this element.</span></span> <span data-ttu-id="b53f9-139">オーバーライドを次の例に示します。ただし、簡潔にするために呼び出すメソッドは表示されません。</span><span class="sxs-lookup"><span data-stu-id="b53f9-139">The override is shown in the following example; however, the methods it calls are not shown for brevity.</span></span> <span data-ttu-id="b53f9-140">完全な例については`CustomToken` 、「」のサンプルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b53f9-140">For the complete example, see the `CustomToken` sample.</span></span>  
  
```xml  
<issuerTokenResolver type="SimpleWebToken.CustomIssuerTokenResolver, SimpleWebToken">  
  <AddAudienceKeyPair  symmetricKey="wAVkldQiFypTQ+kdNdGWCYCHRcee8XmXxOvgmak8vSY=" audience="http://localhost:19851/" />  
</issuerTokenResolver>  
```  
  
## <a name="example"></a><span data-ttu-id="b53f9-141">例</span><span class="sxs-lookup"><span data-stu-id="b53f9-141">Example</span></span>  
  
```  
public override void LoadCustomConfiguration(System.Xml.XmlNodeList nodelist)  
{  
    foreach (XmlNode node in nodelist)  
    {  
        XmlDictionaryReader rdr = XmlDictionaryReader.CreateDictionaryReader(new XmlTextReader(new StringReader(node.OuterXml)));  
        rdr.MoveToContent();  
  
        string symmetricKey = rdr.GetAttribute("symmetricKey");  
        string audience = rdr.GetAttribute("audience");  
  
        this.AddAudienceKeyPair(audience, symmetricKey);  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="b53f9-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="b53f9-142">See also</span></span>

- <xref:System.IdentityModel.Tokens.IssuerTokenResolver>
