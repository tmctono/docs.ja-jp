---
title: <issuerTokenResolver>
ms.date: 03/30/2017
ms.assetid: f74392f6-3f5b-4880-bd8a-3a9130d31e65
author: BrucePerlerMS
ms.openlocfilehash: 8775e3044e58886cfa53a9fd9fc8b4b8ed2105b5
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251948"
---
# <a name="issuertokenresolver"></a><span data-ttu-id="794e2-101">\<issuerTokenResolver ></span><span class="sxs-lookup"><span data-stu-id="794e2-101">\<issuerTokenResolver></span></span>
<span data-ttu-id="794e2-102">トークンハンドラーコレクションのハンドラーによって使用される発行者トークンリゾルバーを登録します。</span><span class="sxs-lookup"><span data-stu-id="794e2-102">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="794e2-103">発行者トークンリゾルバーは、受信トークンとメッセージの署名トークンを解決するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="794e2-103">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span>  
  
<span data-ttu-id="794e2-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="794e2-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="794e2-105">&nbsp;&nbsp;[ **\<システムの >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="794e2-105">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="794e2-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<構成 >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="794e2-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="794e2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlers >** ](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="794e2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="794e2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlerConfiguration >** ](securitytokenhandlerconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="794e2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)</span></span>\
<span data-ttu-id="794e2-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<issuerTokenResolver >**</span><span class="sxs-lookup"><span data-stu-id="794e2-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuerTokenResolver>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="794e2-110">構文</span><span class="sxs-lookup"><span data-stu-id="794e2-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="794e2-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="794e2-111">Attributes and Elements</span></span>  
 <span data-ttu-id="794e2-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="794e2-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="794e2-113">属性</span><span class="sxs-lookup"><span data-stu-id="794e2-113">Attributes</span></span>  
  
|<span data-ttu-id="794e2-114">属性</span><span class="sxs-lookup"><span data-stu-id="794e2-114">Attribute</span></span>|<span data-ttu-id="794e2-115">説明</span><span class="sxs-lookup"><span data-stu-id="794e2-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="794e2-116">型</span><span class="sxs-lookup"><span data-stu-id="794e2-116">type</span></span>|<span data-ttu-id="794e2-117">発行者トークンリゾルバーの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="794e2-117">Specifies the type of the issuer token resolver.</span></span> <span data-ttu-id="794e2-118">は、クラスまた<xref:System.IdentityModel.Tokens.IssuerTokenResolver>は<xref:System.IdentityModel.Tokens.IssuerTokenResolver>クラスから派生した型のいずれかである必要があります。</span><span class="sxs-lookup"><span data-stu-id="794e2-118">Must be either the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class or a type that derives from the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class.</span></span> <span data-ttu-id="794e2-119">必須。</span><span class="sxs-lookup"><span data-stu-id="794e2-119">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="794e2-120">子要素</span><span class="sxs-lookup"><span data-stu-id="794e2-120">Child Elements</span></span>  
 <span data-ttu-id="794e2-121">なし</span><span class="sxs-lookup"><span data-stu-id="794e2-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="794e2-122">親要素</span><span class="sxs-lookup"><span data-stu-id="794e2-122">Parent Elements</span></span>  
  
|<span data-ttu-id="794e2-123">要素</span><span class="sxs-lookup"><span data-stu-id="794e2-123">Element</span></span>|<span data-ttu-id="794e2-124">説明</span><span class="sxs-lookup"><span data-stu-id="794e2-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="794e2-125">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="794e2-125">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="794e2-126">セキュリティトークンハンドラーのコレクションの構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="794e2-126">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="794e2-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="794e2-127">Remarks</span></span>  
 <span data-ttu-id="794e2-128">発行者トークンリゾルバーは、受信トークンとメッセージの署名トークンを解決するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="794e2-128">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="794e2-129">署名の確認に使用される暗号化マテリアルを取得するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="794e2-129">It is used to retrieve the cryptographic material that is used for checking the signature.</span></span> <span data-ttu-id="794e2-130">`type`属性を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="794e2-130">You must specify the `type` attribute.</span></span> <span data-ttu-id="794e2-131">指定できる型は、また<xref:System.IdentityModel.Tokens.IssuerTokenResolver>は<xref:System.IdentityModel.Tokens.IssuerTokenResolver>クラスから派生したカスタム型のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="794e2-131">The type specified can be either <xref:System.IdentityModel.Tokens.IssuerTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class.</span></span>  
  
 <span data-ttu-id="794e2-132">一部のトークンハンドラーでは、構成で発行者トークンリゾルバーの設定を指定できます。</span><span class="sxs-lookup"><span data-stu-id="794e2-132">Some token handlers allow you to specify issuer token resolver settings in configuration.</span></span> <span data-ttu-id="794e2-133">個々のトークンハンドラーの設定は、セキュリティトークンハンドラーコレクションで指定された設定よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="794e2-133">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="794e2-134">要素を、指定した[ \<>](identityconfiguration.md)要素の子要素として指定することは推奨されていませんが、旧バージョンとの互換性のためにサポートされています。 `<issuerTokenResolver>`</span><span class="sxs-lookup"><span data-stu-id="794e2-134">Specifying the `<issuerTokenResolver>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="794e2-135">要素の設定`<securityTokenHandlerConfiguration>`は、要素の設定`<identityConfiguration>`よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="794e2-135">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="794e2-136">例</span><span class="sxs-lookup"><span data-stu-id="794e2-136">Example</span></span>  
 <span data-ttu-id="794e2-137">次の XML は、から<xref:System.IdentityModel.Tokens.IssuerTokenResolver>派生したカスタムクラスに基づく発行者トークンリゾルバーの構成を示しています。</span><span class="sxs-lookup"><span data-stu-id="794e2-137">The following XML shows configuration for an issuer token resolver that is based on a custom class that derives from <xref:System.IdentityModel.Tokens.IssuerTokenResolver>.</span></span> <span data-ttu-id="794e2-138">トークンリゾルバーは、クラスに対して定義されているカスタム構成要素 (`<AddAudienceKeyPair>`) から初期化される、ユーザーとキーのペアのディクショナリを保持します。</span><span class="sxs-lookup"><span data-stu-id="794e2-138">The token resolver maintains a dictionary of audience-key pairs that is initialized from a custom configuration element (`<AddAudienceKeyPair>`) defined for the class.</span></span> <span data-ttu-id="794e2-139">クラスは、 <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A>メソッドをオーバーライドしてこの要素を処理します。</span><span class="sxs-lookup"><span data-stu-id="794e2-139">The class overrides the <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> method to process this element.</span></span> <span data-ttu-id="794e2-140">オーバーライドを次の例に示します。ただし、簡潔にするために呼び出すメソッドは表示されません。</span><span class="sxs-lookup"><span data-stu-id="794e2-140">The override is shown in the following example; however, the methods it calls are not shown for brevity.</span></span> <span data-ttu-id="794e2-141">完全な例については`CustomToken` 、「」のサンプルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="794e2-141">For the complete example, see the `CustomToken` sample.</span></span>  
  
```xml  
<issuerTokenResolver type="SimpleWebToken.CustomIssuerTokenResolver, SimpleWebToken">  
  <AddAudienceKeyPair  symmetricKey="wAVkldQiFypTQ+kdNdGWCYCHRcee8XmXxOvgmak8vSY=" audience="http://localhost:19851/" />  
</issuerTokenResolver>  
```  
  
## <a name="example"></a><span data-ttu-id="794e2-142">例</span><span class="sxs-lookup"><span data-stu-id="794e2-142">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="794e2-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="794e2-143">See also</span></span>

- <xref:System.IdentityModel.Tokens.IssuerTokenResolver>
