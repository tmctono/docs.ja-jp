---
title: <customCookieHandler>
ms.date: 03/30/2017
ms.assetid: a03b153d-5ec6-4915-9031-6f0c3fd348be
author: BrucePerlerMS
ms.openlocfilehash: e1f32e17cf0da5e948d778e8b61aca6053eff4ef
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252019"
---
# <a name="customcookiehandler"></a><span data-ttu-id="9dc85-101">\<customCookieHandler ></span><span class="sxs-lookup"><span data-stu-id="9dc85-101">\<customCookieHandler></span></span>
<span data-ttu-id="9dc85-102">カスタムクッキーハンドラーの種類を設定します。</span><span class="sxs-lookup"><span data-stu-id="9dc85-102">Sets the custom cookie handler type.</span></span> <span data-ttu-id="9dc85-103">この要素は、 `mode` `<cookieHandler>`要素の属性が "Custom" の場合にのみ存在する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9dc85-103">This element may only be present if the `mode` attribute of the `<cookieHandler>` element is "Custom".</span></span> <span data-ttu-id="9dc85-104">カスタム型は、 <xref:System.IdentityModel.Services.CookieHandler>クラスから派生する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9dc85-104">The custom type must be derived from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>  
  
<span data-ttu-id="9dc85-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9dc85-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="9dc85-106">&nbsp;&nbsp;[ **\<> のシステム**](system-identitymodel-services.md)</span><span class="sxs-lookup"><span data-stu-id="9dc85-106">&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)</span></span>\
<span data-ttu-id="9dc85-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<federationConfiguration >** ](federationconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="9dc85-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)</span></span>\
<span data-ttu-id="9dc85-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<cookieHandler >** ](cookiehandler.md)</span><span class="sxs-lookup"><span data-stu-id="9dc85-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cookieHandler>**](cookiehandler.md)</span></span>\
<span data-ttu-id="9dc85-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<customCookieHandler >**</span><span class="sxs-lookup"><span data-stu-id="9dc85-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customCookieHandler>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9dc85-110">構文</span><span class="sxs-lookup"><span data-stu-id="9dc85-110">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <cookieHandler mode="Custom">  
      <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" >  
      </customCookieHandler>  
    </cookieHandler>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9dc85-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="9dc85-111">Attributes and Elements</span></span>  
 <span data-ttu-id="9dc85-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="9dc85-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9dc85-113">属性</span><span class="sxs-lookup"><span data-stu-id="9dc85-113">Attributes</span></span>  
  
|<span data-ttu-id="9dc85-114">属性</span><span class="sxs-lookup"><span data-stu-id="9dc85-114">Attribute</span></span>|<span data-ttu-id="9dc85-115">説明</span><span class="sxs-lookup"><span data-stu-id="9dc85-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9dc85-116">型</span><span class="sxs-lookup"><span data-stu-id="9dc85-116">type</span></span>|<span data-ttu-id="9dc85-117"><xref:System.IdentityModel.Services.CookieHandler>クラスから派生するカスタム型を指定します。</span><span class="sxs-lookup"><span data-stu-id="9dc85-117">Specifies a custom type that derives from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span> <span data-ttu-id="9dc85-118">`type`属性を指定する方法の詳細については、「[カスタム型参照](../windows-workflow-foundation/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9dc85-118">For more information about how to specify the `type` attribute, see [Custom Type References](../windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9dc85-119">子要素</span><span class="sxs-lookup"><span data-stu-id="9dc85-119">Child Elements</span></span>  
 <span data-ttu-id="9dc85-120">なし</span><span class="sxs-lookup"><span data-stu-id="9dc85-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9dc85-121">親要素</span><span class="sxs-lookup"><span data-stu-id="9dc85-121">Parent Elements</span></span>  
  
|<span data-ttu-id="9dc85-122">要素</span><span class="sxs-lookup"><span data-stu-id="9dc85-122">Element</span></span>|<span data-ttu-id="9dc85-123">説明</span><span class="sxs-lookup"><span data-stu-id="9dc85-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9dc85-124">\<cookieHandler ></span><span class="sxs-lookup"><span data-stu-id="9dc85-124">\<cookieHandler></span></span>](cookiehandler.md)|<span data-ttu-id="9dc85-125"><xref:System.IdentityModel.Services.CookieHandler> が<xref:System.IdentityModel.Services.SessionAuthenticationModule> cookie の読み取りと書き込みに使用するを構成します。</span><span class="sxs-lookup"><span data-stu-id="9dc85-125">Configures the <xref:System.IdentityModel.Services.CookieHandler> that the <xref:System.IdentityModel.Services.SessionAuthenticationModule> uses to read and write cookies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9dc85-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="9dc85-126">Remarks</span></span>  
 <span data-ttu-id="9dc85-127">要素の属性を "custom" に設定`<customCookieHandler>`してカスタム cookie ハンドラーを指定する場合は、クッキーハンドラーの型を参照する子要素を含めることによって、カスタム cookie ハンドラーの型を指定する必要があります。 `mode` `<cookieHandler>`</span><span class="sxs-lookup"><span data-stu-id="9dc85-127">When you specify a custom cookie handler by setting the `mode` attribute of the `<cookieHandler>` element to "Custom", you must specify the type of the custom cookie handler by including a `<customCookieHandler>` child element that references the cookie handler type.</span></span> <span data-ttu-id="9dc85-128">属性が "Chunked" または`mode` "Default" に設定されている場合、この要素を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="9dc85-128">This element cannot be specified when the `mode` attribute is set to "Chunked" or "Default".</span></span> <span data-ttu-id="9dc85-129">カスタムクッキーハンドラーは、 <xref:System.IdentityModel.Services.CookieHandler>クラスから派生する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9dc85-129">Custom cookie handlers must derive from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>  
  
 <span data-ttu-id="9dc85-130">要素は、 <xref:System.IdentityModel.Configuration.CustomTypeElement>クラスによって表されます。 `<customCookieHandler>`</span><span class="sxs-lookup"><span data-stu-id="9dc85-130">The `<customCookieHandler>` element is represented by the <xref:System.IdentityModel.Configuration.CustomTypeElement> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9dc85-131">例</span><span class="sxs-lookup"><span data-stu-id="9dc85-131">Example</span></span>  
 <span data-ttu-id="9dc85-132">次の例では、型`MyNamespace.MyCustomCookieHandler`のカスタム cookie ハンドラーを使用するように SAM を構成します。</span><span class="sxs-lookup"><span data-stu-id="9dc85-132">The following example configures the SAM to use a custom cookie handler of type `MyNamespace.MyCustomCookieHandler`.</span></span>  
  
```xml  
<cookieHandler mode="Custom">  
    <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" />  
</cookieHandler>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9dc85-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="9dc85-133">See also</span></span>

- <xref:System.IdentityModel.Services.CookieHandler>
