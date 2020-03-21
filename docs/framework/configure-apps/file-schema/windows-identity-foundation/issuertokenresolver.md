---
title: <issuerTokenResolver>
ms.date: 03/30/2017
ms.assetid: f74392f6-3f5b-4880-bd8a-3a9130d31e65
author: BrucePerlerMS
ms.openlocfilehash: 67d7e0aa5b6b05bfe8b17a1b1efebb1fbddbb0eb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152672"
---
# <a name="issuertokenresolver"></a><span data-ttu-id="f5f1f-101">\<></span><span class="sxs-lookup"><span data-stu-id="f5f1f-101">\<issuerTokenResolver></span></span>
<span data-ttu-id="f5f1f-102">トークン ハンドラー コレクション内のハンドラーによって使用される発行者トークン リゾルバーを登録します。</span><span class="sxs-lookup"><span data-stu-id="f5f1f-102">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="f5f1f-103">発行者トークン リゾルバーは、受信トークンとメッセージの署名トークンを解決するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="f5f1f-103">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span>  
  
<span data-ttu-id="f5f1f-104">[**\<構成>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f5f1f-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f5f1f-105">&nbsp;&nbsp;[**\<>**](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="f5f1f-105">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="f5f1f-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<id構成>**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="f5f1f-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="f5f1f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>**](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="f5f1f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="f5f1f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>**](securitytokenhandlerconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="f5f1f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)</span></span>\
<span data-ttu-id="f5f1f-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>**</span><span class="sxs-lookup"><span data-stu-id="f5f1f-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuerTokenResolver>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5f1f-110">構文</span><span class="sxs-lookup"><span data-stu-id="f5f1f-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f5f1f-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="f5f1f-111">Attributes and Elements</span></span>  
 <span data-ttu-id="f5f1f-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="f5f1f-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f5f1f-113">属性</span><span class="sxs-lookup"><span data-stu-id="f5f1f-113">Attributes</span></span>  
  
|<span data-ttu-id="f5f1f-114">属性</span><span class="sxs-lookup"><span data-stu-id="f5f1f-114">Attribute</span></span>|<span data-ttu-id="f5f1f-115">説明</span><span class="sxs-lookup"><span data-stu-id="f5f1f-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f5f1f-116">type</span><span class="sxs-lookup"><span data-stu-id="f5f1f-116">type</span></span>|<span data-ttu-id="f5f1f-117">発行者トークン リゾルバーの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="f5f1f-117">Specifies the type of the issuer token resolver.</span></span> <span data-ttu-id="f5f1f-118"><xref:System.IdentityModel.Tokens.IssuerTokenResolver>クラスまたはクラスから<xref:System.IdentityModel.Tokens.IssuerTokenResolver>派生する型である必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5f1f-118">Must be either the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class or a type that derives from the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class.</span></span> <span data-ttu-id="f5f1f-119">必須。</span><span class="sxs-lookup"><span data-stu-id="f5f1f-119">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f5f1f-120">子要素</span><span class="sxs-lookup"><span data-stu-id="f5f1f-120">Child Elements</span></span>  
 <span data-ttu-id="f5f1f-121">なし</span><span class="sxs-lookup"><span data-stu-id="f5f1f-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f5f1f-122">親要素</span><span class="sxs-lookup"><span data-stu-id="f5f1f-122">Parent Elements</span></span>  
  
|<span data-ttu-id="f5f1f-123">要素</span><span class="sxs-lookup"><span data-stu-id="f5f1f-123">Element</span></span>|<span data-ttu-id="f5f1f-124">説明</span><span class="sxs-lookup"><span data-stu-id="f5f1f-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f5f1f-125">\<></span><span class="sxs-lookup"><span data-stu-id="f5f1f-125">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="f5f1f-126">セキュリティ トークン ハンドラーのコレクションの構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="f5f1f-126">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f5f1f-127">解説</span><span class="sxs-lookup"><span data-stu-id="f5f1f-127">Remarks</span></span>  
 <span data-ttu-id="f5f1f-128">発行者トークン リゾルバーは、受信トークンとメッセージの署名トークンを解決するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="f5f1f-128">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="f5f1f-129">署名のチェックに使用される暗号資料を取得するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="f5f1f-129">It is used to retrieve the cryptographic material that is used for checking the signature.</span></span> <span data-ttu-id="f5f1f-130">属性を指定する`type`必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5f1f-130">You must specify the `type` attribute.</span></span> <span data-ttu-id="f5f1f-131">指定する型は、<xref:System.IdentityModel.Tokens.IssuerTokenResolver><xref:System.IdentityModel.Tokens.IssuerTokenResolver>クラスから派生するカスタム型のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="f5f1f-131">The type specified can be either <xref:System.IdentityModel.Tokens.IssuerTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class.</span></span>  
  
 <span data-ttu-id="f5f1f-132">トークン ハンドラーによっては、構成で発行者トークン リゾルバーの設定を指定できるものもあります。</span><span class="sxs-lookup"><span data-stu-id="f5f1f-132">Some token handlers allow you to specify issuer token resolver settings in configuration.</span></span> <span data-ttu-id="f5f1f-133">個々のトークン ハンドラーの設定は、セキュリティ トークン ハンドラーコレクションで指定された設定をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="f5f1f-133">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f5f1f-134">要素を`<issuerTokenResolver>` [ \<identityConfiguration>](identityconfiguration.md)要素の子要素として指定することは非推奨になりましたが、下位互換性のために引き続きサポートされています。</span><span class="sxs-lookup"><span data-stu-id="f5f1f-134">Specifying the `<issuerTokenResolver>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="f5f1f-135">要素の設定`<securityTokenHandlerConfiguration>`は、要素上の`<identityConfiguration>`設定よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="f5f1f-135">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f5f1f-136">例</span><span class="sxs-lookup"><span data-stu-id="f5f1f-136">Example</span></span>  
 <span data-ttu-id="f5f1f-137">次の XML は、 から<xref:System.IdentityModel.Tokens.IssuerTokenResolver>派生したカスタム クラスに基づく発行者トークン リゾルバーの構成を示しています。</span><span class="sxs-lookup"><span data-stu-id="f5f1f-137">The following XML shows configuration for an issuer token resolver that is based on a custom class that derives from <xref:System.IdentityModel.Tokens.IssuerTokenResolver>.</span></span> <span data-ttu-id="f5f1f-138">トークン リゾルバーは、クラスに対して定義されたカスタム構成要素 (`<AddAudienceKeyPair>`) から初期化された対象ユーザーとキーのペアのディクショナリを保持します。</span><span class="sxs-lookup"><span data-stu-id="f5f1f-138">The token resolver maintains a dictionary of audience-key pairs that is initialized from a custom configuration element (`<AddAudienceKeyPair>`) defined for the class.</span></span> <span data-ttu-id="f5f1f-139">このクラスは、この<xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A>要素を処理するメソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="f5f1f-139">The class overrides the <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> method to process this element.</span></span> <span data-ttu-id="f5f1f-140">オーバーライドは次の例に示します。ただし、簡潔にするために、呼び出すメソッドは表示されません。</span><span class="sxs-lookup"><span data-stu-id="f5f1f-140">The override is shown in the following example; however, the methods it calls are not shown for brevity.</span></span> <span data-ttu-id="f5f1f-141">完全な例については、サンプルを`CustomToken`参照してください。</span><span class="sxs-lookup"><span data-stu-id="f5f1f-141">For the complete example, see the `CustomToken` sample.</span></span>  
  
```xml  
<issuerTokenResolver type="SimpleWebToken.CustomIssuerTokenResolver, SimpleWebToken">  
  <AddAudienceKeyPair  symmetricKey="wAVkldQiFypTQ+kdNdGWCYCHRcee8XmXxOvgmak8vSY=" audience="http://localhost:19851/" />  
</issuerTokenResolver>  
```  
  
## <a name="example"></a><span data-ttu-id="f5f1f-142">例</span><span class="sxs-lookup"><span data-stu-id="f5f1f-142">Example</span></span>
  
```csharp
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
  
## <a name="see-also"></a><span data-ttu-id="f5f1f-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="f5f1f-143">See also</span></span>

- <xref:System.IdentityModel.Tokens.IssuerTokenResolver>
