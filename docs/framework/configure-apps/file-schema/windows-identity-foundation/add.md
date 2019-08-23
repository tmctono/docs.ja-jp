---
title: <add>
ms.date: 03/30/2017
ms.assetid: 4712a888-f154-4395-8887-ef14a88a6497
author: BrucePerlerMS
ms.openlocfilehash: 9505970c1fd7fcdfe62d3c6ef58f5d653fab4106
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69941992"
---
# <a name="add"></a><span data-ttu-id="34b63-101">\<add></span><span class="sxs-lookup"><span data-stu-id="34b63-101">\<add></span></span>
<span data-ttu-id="34b63-102">指定されたセキュリティトークンハンドラーをトークンハンドラーコレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="34b63-102">Adds the specified security token handler to the token handler collection.</span></span>  
  
 <span data-ttu-id="34b63-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="34b63-103">\<system.identityModel></span></span>  
<span data-ttu-id="34b63-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="34b63-104">\<identityConfiguration></span></span>  
<span data-ttu-id="34b63-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="34b63-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="34b63-106">\<add></span><span class="sxs-lookup"><span data-stu-id="34b63-106">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34b63-107">構文</span><span class="sxs-lookup"><span data-stu-id="34b63-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add type=xs:string>  
        <optionalConfigurationElement>  
        </optionalConfigurationElement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="34b63-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="34b63-108">Attributes and Elements</span></span>  
 <span data-ttu-id="34b63-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="34b63-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="34b63-110">属性</span><span class="sxs-lookup"><span data-stu-id="34b63-110">Attributes</span></span>  
  
|<span data-ttu-id="34b63-111">属性</span><span class="sxs-lookup"><span data-stu-id="34b63-111">Attribute</span></span>|<span data-ttu-id="34b63-112">説明</span><span class="sxs-lookup"><span data-stu-id="34b63-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="34b63-113">型</span><span class="sxs-lookup"><span data-stu-id="34b63-113">type</span></span>|<span data-ttu-id="34b63-114">追加するトークンハンドラーの CLR 型名。</span><span class="sxs-lookup"><span data-stu-id="34b63-114">The CLR type name of the token handler to be added.</span></span> <span data-ttu-id="34b63-115">`type`属性を指定する方法の詳細については、「[カスタム型参照](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="34b63-115">For more information about how to specify the `type` attribute, see [Custom Type References](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="34b63-116">子要素</span><span class="sxs-lookup"><span data-stu-id="34b63-116">Child Elements</span></span>  
  
|<span data-ttu-id="34b63-117">要素</span><span class="sxs-lookup"><span data-stu-id="34b63-117">Element</span></span>|<span data-ttu-id="34b63-118">説明</span><span class="sxs-lookup"><span data-stu-id="34b63-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="34b63-119">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="34b63-119">\<samlSecurityTokenRequirement></span></span>](samlsecuritytokenrequirement.md)|<span data-ttu-id="34b63-120">クラス、 <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>クラス、 <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>またはこれらのクラスの派生クラスの構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="34b63-120">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
|[<span data-ttu-id="34b63-121">\<sessionTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="34b63-121">\<sessionTokenRequirement></span></span>](sessiontokenrequirement.md)|<span data-ttu-id="34b63-122"><xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>クラスまたは派生クラスの構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="34b63-122">Provides configuration for the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class or derived classes.</span></span>|  
|[<span data-ttu-id="34b63-123">\<userNameSecurityTokenHandlerRequirement ></span><span class="sxs-lookup"><span data-stu-id="34b63-123">\<userNameSecurityTokenHandlerRequirement></span></span>](usernamesecuritytokenhandlerrequirement.md)|<span data-ttu-id="34b63-124"><xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>クラスまたは派生クラスの構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="34b63-124">Provides configuration for the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> class or derived classes.</span></span>|  
|[<span data-ttu-id="34b63-125">\<x509SecurityTokenHandlerRequirement ></span><span class="sxs-lookup"><span data-stu-id="34b63-125">\<x509SecurityTokenHandlerRequirement></span></span>](x509securitytokenhandlerrequirement.md)|<span data-ttu-id="34b63-126"><xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>クラスまたは派生クラスのオプションの構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="34b63-126">Provides optional configuration for the <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> class or derived classes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="34b63-127">親要素</span><span class="sxs-lookup"><span data-stu-id="34b63-127">Parent Elements</span></span>  
  
|<span data-ttu-id="34b63-128">要素</span><span class="sxs-lookup"><span data-stu-id="34b63-128">Element</span></span>|<span data-ttu-id="34b63-129">説明</span><span class="sxs-lookup"><span data-stu-id="34b63-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="34b63-130">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="34b63-130">\<securityTokenHandlers></span></span>](securitytokenhandlers.md)|<span data-ttu-id="34b63-131">エンドポイントに登録されているセキュリティトークンハンドラーのコレクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="34b63-131">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="34b63-132">Remarks</span><span class="sxs-lookup"><span data-stu-id="34b63-132">Remarks</span></span>  
 <span data-ttu-id="34b63-133">要素`<add>`は、トークンハンドラーの構成を指定する1つの子要素を受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="34b63-133">The `<add>` element can take a single child element that specifies the configuration for the token handler.</span></span> <span data-ttu-id="34b63-134">これは、 `type` `<add>`要素の属性を通じて参照されるハンドラークラスがこの機能をサポートするかどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="34b63-134">This is dependent on whether the handler class referenced through the `type` attribute of the `<add>` element provides support for this feature.</span></span> <span data-ttu-id="34b63-135">この機能を提供するトークンハンドラークラスは、 <xref:System.Xml.XmlElement>オブジェクトを受け取るコンストラクターを公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="34b63-135">Token handler classes that provide this feature must expose a constructor that takes an <xref:System.Xml.XmlElement> object.</span></span>  
  
```  
public class CustomTokenHandler : Microsoft.IdentityModel.Tokens.SecurityTokenHandler  
{  
    public CustomTokenHandler( XmlElement customConfig )  
    {  
    }  
}  
```  
  
 <span data-ttu-id="34b63-136">いくつかの組み込みセキュリティトークンハンドラークラスは、この機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="34b63-136">Several of the built-in security token handler classes do provide this functionality.</span></span> <span data-ttu-id="34b63-137">これらのクラス<xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>は<xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>、 <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>、、、 <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>、およびです。</span><span class="sxs-lookup"><span data-stu-id="34b63-137">These classes are <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, and <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="34b63-138">トークンハンドラーコレクションには、指定された任意の型の1つのハンドラーのみを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="34b63-138">The token handler collection can only contain a single handler of any given type.</span></span> <span data-ttu-id="34b63-139">これは、たとえば、 <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>クラスから派生したハンドラーをコレクションに追加する場合は、最初にコレクションから既定で存在する<xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>を削除する必要があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="34b63-139">This means, for example, that if you want to add a handler that is derived from the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class to the collection, you must first remove the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, which is present by default, from the collection.</span></span> <span data-ttu-id="34b63-140">[ \<](clear.md) Remove > 要素を使用[ \<](remove.md)して、コレクションから1つのハンドラーを削除することも、clear > 要素を使用してコレクションからすべてのハンドラーを削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="34b63-140">You can use the [\<remove>](remove.md) element to remove a single handler from the collection or use the [\<clear>](clear.md) element to remove all handlers from the collection.</span></span>  
  
 <span data-ttu-id="34b63-141">ハンドラーに対して指定された設定は、 [ \<securityTokenHandlerConfiguration >](securitytokenhandlerconfiguration.md)要素の下にあるトークンハンドラーコレクションで指定された同等の[ \<設定よりも優先されます。>](identityconfiguration.md)要素。</span><span class="sxs-lookup"><span data-stu-id="34b63-141">Settings specified on a handler override equivalent settings specified on the token handler collection under the [\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md) element and those specified at the service-level under the [\<identityConfiguration>](identityconfiguration.md) element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="34b63-142">例</span><span class="sxs-lookup"><span data-stu-id="34b63-142">Example</span></span>  
 <span data-ttu-id="34b63-143">次の XML は、 `<add>`および`<remove>`要素を使用して、既定のセッショントークンハンドラーをカスタムセッショントークンハンドラーに置き換える方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="34b63-143">The following XML shows the use of the `<add>` and `<remove>` elements to replace the default session token handler with a custom session token handler.</span></span> <span data-ttu-id="34b63-144">XML は、「」の`ClaimsAwareWebFarm`サンプルから抜粋したものです。</span><span class="sxs-lookup"><span data-stu-id="34b63-144">The XML is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```
