---
title: <customCookieHandler>
ms.date: 03/30/2017
ms.assetid: a03b153d-5ec6-4915-9031-6f0c3fd348be
author: BrucePerlerMS
ms.openlocfilehash: ebf1f7f3de1b44dba63977bf524dea9af2690fb1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942792"
---
# <a name="customcookiehandler"></a><span data-ttu-id="a474c-101">\<customCookieHandler ></span><span class="sxs-lookup"><span data-stu-id="a474c-101">\<customCookieHandler></span></span>
<span data-ttu-id="a474c-102">カスタムクッキーハンドラーの種類を設定します。</span><span class="sxs-lookup"><span data-stu-id="a474c-102">Sets the custom cookie handler type.</span></span> <span data-ttu-id="a474c-103">この要素は、 `mode` `<cookieHandler>`要素の属性が "Custom" の場合にのみ存在する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a474c-103">This element may only be present if the `mode` attribute of the `<cookieHandler>` element is "Custom".</span></span> <span data-ttu-id="a474c-104">カスタム型は、 <xref:System.IdentityModel.Services.CookieHandler>クラスから派生する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a474c-104">The custom type must be derived from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>  
  
 <span data-ttu-id="a474c-105">\<system.identityModel.services></span><span class="sxs-lookup"><span data-stu-id="a474c-105">\<system.identityModel.services></span></span>  
<span data-ttu-id="a474c-106">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="a474c-106">\<federationConfiguration></span></span>  
<span data-ttu-id="a474c-107">\<cookieHandler ></span><span class="sxs-lookup"><span data-stu-id="a474c-107">\<cookieHandler></span></span>  
<span data-ttu-id="a474c-108">\<customCookieHandler ></span><span class="sxs-lookup"><span data-stu-id="a474c-108">\<customCookieHandler></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a474c-109">構文</span><span class="sxs-lookup"><span data-stu-id="a474c-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a474c-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="a474c-110">Attributes and Elements</span></span>  
 <span data-ttu-id="a474c-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="a474c-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a474c-112">属性</span><span class="sxs-lookup"><span data-stu-id="a474c-112">Attributes</span></span>  
  
|<span data-ttu-id="a474c-113">属性</span><span class="sxs-lookup"><span data-stu-id="a474c-113">Attribute</span></span>|<span data-ttu-id="a474c-114">説明</span><span class="sxs-lookup"><span data-stu-id="a474c-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a474c-115">型</span><span class="sxs-lookup"><span data-stu-id="a474c-115">type</span></span>|<span data-ttu-id="a474c-116"><xref:System.IdentityModel.Services.CookieHandler>クラスから派生するカスタム型を指定します。</span><span class="sxs-lookup"><span data-stu-id="a474c-116">Specifies a custom type that derives from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span> <span data-ttu-id="a474c-117">`type`属性を指定する方法の詳細については、「[カスタム型参照](../windows-workflow-foundation/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a474c-117">For more information about how to specify the `type` attribute, see [Custom Type References](../windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a474c-118">子要素</span><span class="sxs-lookup"><span data-stu-id="a474c-118">Child Elements</span></span>  
 <span data-ttu-id="a474c-119">なし</span><span class="sxs-lookup"><span data-stu-id="a474c-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a474c-120">親要素</span><span class="sxs-lookup"><span data-stu-id="a474c-120">Parent Elements</span></span>  
  
|<span data-ttu-id="a474c-121">要素</span><span class="sxs-lookup"><span data-stu-id="a474c-121">Element</span></span>|<span data-ttu-id="a474c-122">説明</span><span class="sxs-lookup"><span data-stu-id="a474c-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a474c-123">\<cookieHandler ></span><span class="sxs-lookup"><span data-stu-id="a474c-123">\<cookieHandler></span></span>](cookiehandler.md)|<span data-ttu-id="a474c-124"><xref:System.IdentityModel.Services.CookieHandler> が<xref:System.IdentityModel.Services.SessionAuthenticationModule> cookie の読み取りと書き込みに使用するを構成します。</span><span class="sxs-lookup"><span data-stu-id="a474c-124">Configures the <xref:System.IdentityModel.Services.CookieHandler> that the <xref:System.IdentityModel.Services.SessionAuthenticationModule> uses to read and write cookies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a474c-125">Remarks</span><span class="sxs-lookup"><span data-stu-id="a474c-125">Remarks</span></span>  
 <span data-ttu-id="a474c-126">要素の属性を "custom" に設定`<customCookieHandler>`してカスタム cookie ハンドラーを指定する場合は、クッキーハンドラーの型を参照する子要素を含めることによって、カスタム cookie ハンドラーの型を指定する必要があります。 `mode` `<cookieHandler>`</span><span class="sxs-lookup"><span data-stu-id="a474c-126">When you specify a custom cookie handler by setting the `mode` attribute of the `<cookieHandler>` element to "Custom", you must specify the type of the custom cookie handler by including a `<customCookieHandler>` child element that references the cookie handler type.</span></span> <span data-ttu-id="a474c-127">属性が "Chunked" または`mode` "Default" に設定されている場合、この要素を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="a474c-127">This element cannot be specified when the `mode` attribute is set to "Chunked" or "Default".</span></span> <span data-ttu-id="a474c-128">カスタムクッキーハンドラーは、 <xref:System.IdentityModel.Services.CookieHandler>クラスから派生する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a474c-128">Custom cookie handlers must derive from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>  
  
 <span data-ttu-id="a474c-129">要素は、 <xref:System.IdentityModel.Configuration.CustomTypeElement>クラスによって表されます。 `<customCookieHandler>`</span><span class="sxs-lookup"><span data-stu-id="a474c-129">The `<customCookieHandler>` element is represented by the <xref:System.IdentityModel.Configuration.CustomTypeElement> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a474c-130">例</span><span class="sxs-lookup"><span data-stu-id="a474c-130">Example</span></span>  
 <span data-ttu-id="a474c-131">次の例では、型`MyNamespace.MyCustomCookieHandler`のカスタム cookie ハンドラーを使用するように SAM を構成します。</span><span class="sxs-lookup"><span data-stu-id="a474c-131">The following example configures the SAM to use a custom cookie handler of type `MyNamespace.MyCustomCookieHandler`.</span></span>  
  
```xml  
<cookieHandler mode="Custom">  
    <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" />  
</cookieHandler>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a474c-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="a474c-132">See also</span></span>

- <xref:System.IdentityModel.Services.CookieHandler>
