---
title: <customCookieHandler>
ms.date: 03/30/2017
ms.assetid: a03b153d-5ec6-4915-9031-6f0c3fd348be
author: BrucePerlerMS
ms.openlocfilehash: a8ee23ac6facaea18cd7f1820616cb9b16afa336
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91189852"
---
# \<customCookieHandler>

<span data-ttu-id="03a71-101">カスタムクッキーハンドラーの種類を設定します。</span><span class="sxs-lookup"><span data-stu-id="03a71-101">Sets the custom cookie handler type.</span></span> <span data-ttu-id="03a71-102">この要素は `mode` 、要素の属性が "Custom" の場合にのみ存在する可能性があり `<cookieHandler>` ます。</span><span class="sxs-lookup"><span data-stu-id="03a71-102">This element may only be present if the `mode` attribute of the `<cookieHandler>` element is "Custom".</span></span> <span data-ttu-id="03a71-103">カスタム型は、クラスから派生する必要があり <xref:System.IdentityModel.Services.CookieHandler> ます。</span><span class="sxs-lookup"><span data-stu-id="03a71-103">The custom type must be derived from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cookieHandler>**](cookiehandler.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customCookieHandler>**  
  
## <a name="syntax"></a><span data-ttu-id="03a71-104">構文</span><span class="sxs-lookup"><span data-stu-id="03a71-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="03a71-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="03a71-105">Attributes and Elements</span></span>  

 <span data-ttu-id="03a71-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="03a71-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="03a71-107">属性</span><span class="sxs-lookup"><span data-stu-id="03a71-107">Attributes</span></span>  
  
|<span data-ttu-id="03a71-108">属性</span><span class="sxs-lookup"><span data-stu-id="03a71-108">Attribute</span></span>|<span data-ttu-id="03a71-109">[説明]</span><span class="sxs-lookup"><span data-stu-id="03a71-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="03a71-110">type</span><span class="sxs-lookup"><span data-stu-id="03a71-110">type</span></span>|<span data-ttu-id="03a71-111">クラスから派生するカスタム型を指定し <xref:System.IdentityModel.Services.CookieHandler> ます。</span><span class="sxs-lookup"><span data-stu-id="03a71-111">Specifies a custom type that derives from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span> <span data-ttu-id="03a71-112">属性を指定する方法の詳細については `type` 、「 [カスタム型参照](../windows-workflow-foundation/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="03a71-112">For more information about how to specify the `type` attribute, see [Custom Type References](../windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="03a71-113">子要素</span><span class="sxs-lookup"><span data-stu-id="03a71-113">Child Elements</span></span>  

 <span data-ttu-id="03a71-114">None</span><span class="sxs-lookup"><span data-stu-id="03a71-114">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="03a71-115">親要素</span><span class="sxs-lookup"><span data-stu-id="03a71-115">Parent Elements</span></span>  
  
|<span data-ttu-id="03a71-116">要素</span><span class="sxs-lookup"><span data-stu-id="03a71-116">Element</span></span>|<span data-ttu-id="03a71-117">説明</span><span class="sxs-lookup"><span data-stu-id="03a71-117">Description</span></span>|  
|-------------|-----------------|  
|[\<cookieHandler>](cookiehandler.md)|<span data-ttu-id="03a71-118"><xref:System.IdentityModel.Services.CookieHandler>が <xref:System.IdentityModel.Services.SessionAuthenticationModule> cookie の読み取りと書き込みに使用するを構成します。</span><span class="sxs-lookup"><span data-stu-id="03a71-118">Configures the <xref:System.IdentityModel.Services.CookieHandler> that the <xref:System.IdentityModel.Services.SessionAuthenticationModule> uses to read and write cookies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="03a71-119">解説</span><span class="sxs-lookup"><span data-stu-id="03a71-119">Remarks</span></span>  

 <span data-ttu-id="03a71-120">要素の属性を "Custom" に設定してカスタム cookie ハンドラーを指定する場合は、 `mode` `<cookieHandler>` `<customCookieHandler>` クッキーハンドラーの型を参照する子要素を含めることによって、カスタム cookie ハンドラーの型を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="03a71-120">When you specify a custom cookie handler by setting the `mode` attribute of the `<cookieHandler>` element to "Custom", you must specify the type of the custom cookie handler by including a `<customCookieHandler>` child element that references the cookie handler type.</span></span> <span data-ttu-id="03a71-121">`mode`属性が "Chunked" または "Default" に設定されている場合、この要素を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="03a71-121">This element cannot be specified when the `mode` attribute is set to "Chunked" or "Default".</span></span> <span data-ttu-id="03a71-122">カスタムクッキーハンドラーは、クラスから派生する必要があり <xref:System.IdentityModel.Services.CookieHandler> ます。</span><span class="sxs-lookup"><span data-stu-id="03a71-122">Custom cookie handlers must derive from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>  
  
 <span data-ttu-id="03a71-123">`<customCookieHandler>`要素は、クラスによって表され <xref:System.IdentityModel.Configuration.CustomTypeElement> ます。</span><span class="sxs-lookup"><span data-stu-id="03a71-123">The `<customCookieHandler>` element is represented by the <xref:System.IdentityModel.Configuration.CustomTypeElement> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="03a71-124">例</span><span class="sxs-lookup"><span data-stu-id="03a71-124">Example</span></span>  

 <span data-ttu-id="03a71-125">次の例では、型のカスタム cookie ハンドラーを使用するように SAM を構成し `MyNamespace.MyCustomCookieHandler` ます。</span><span class="sxs-lookup"><span data-stu-id="03a71-125">The following example configures the SAM to use a custom cookie handler of type `MyNamespace.MyCustomCookieHandler`.</span></span>  
  
```xml  
<cookieHandler mode="Custom">  
    <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" />  
</cookieHandler>  
```  
  
## <a name="see-also"></a><span data-ttu-id="03a71-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="03a71-126">See also</span></span>

- <xref:System.IdentityModel.Services.CookieHandler>
