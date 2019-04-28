---
title: <customCookieHandler>
ms.date: 03/30/2017
ms.assetid: a03b153d-5ec6-4915-9031-6f0c3fd348be
author: BrucePerlerMS
ms.openlocfilehash: 0129c63fe17b63889a77ea1a56c0d7e657def859
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61791730"
---
# <a name="customcookiehandler"></a><span data-ttu-id="091b2-101">\<customCookieHandler></span><span class="sxs-lookup"><span data-stu-id="091b2-101">\<customCookieHandler></span></span>
<span data-ttu-id="091b2-102">カスタム クッキー ハンドラーの型を設定します。</span><span class="sxs-lookup"><span data-stu-id="091b2-102">Sets the custom cookie handler type.</span></span> <span data-ttu-id="091b2-103">この要素が存在するのみ場合、`mode`の属性、`<cookieHandler>`要素が"Custom"。</span><span class="sxs-lookup"><span data-stu-id="091b2-103">This element may only be present if the `mode` attribute of the `<cookieHandler>` element is "Custom".</span></span> <span data-ttu-id="091b2-104">カスタム型から派生する必要があります、<xref:System.IdentityModel.Services.CookieHandler>クラス。</span><span class="sxs-lookup"><span data-stu-id="091b2-104">The custom type must be derived from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>  
  
 <span data-ttu-id="091b2-105">\<system.identityModel.services></span><span class="sxs-lookup"><span data-stu-id="091b2-105">\<system.identityModel.services></span></span>  
<span data-ttu-id="091b2-106">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="091b2-106">\<federationConfiguration></span></span>  
<span data-ttu-id="091b2-107">\<cookieHandler></span><span class="sxs-lookup"><span data-stu-id="091b2-107">\<cookieHandler></span></span>  
<span data-ttu-id="091b2-108">\<customCookieHandler></span><span class="sxs-lookup"><span data-stu-id="091b2-108">\<customCookieHandler></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="091b2-109">構文</span><span class="sxs-lookup"><span data-stu-id="091b2-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="091b2-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="091b2-110">Attributes and Elements</span></span>  
 <span data-ttu-id="091b2-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="091b2-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="091b2-112">属性</span><span class="sxs-lookup"><span data-stu-id="091b2-112">Attributes</span></span>  
  
|<span data-ttu-id="091b2-113">属性</span><span class="sxs-lookup"><span data-stu-id="091b2-113">Attribute</span></span>|<span data-ttu-id="091b2-114">説明</span><span class="sxs-lookup"><span data-stu-id="091b2-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="091b2-115">種類</span><span class="sxs-lookup"><span data-stu-id="091b2-115">type</span></span>|<span data-ttu-id="091b2-116">派生したカスタム型を指定します、<xref:System.IdentityModel.Services.CookieHandler>クラス。</span><span class="sxs-lookup"><span data-stu-id="091b2-116">Specifies a custom type that derives from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span> <span data-ttu-id="091b2-117">詳細を指定する方法については、`type`属性は、「[カスタム型の参照](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md)します。</span><span class="sxs-lookup"><span data-stu-id="091b2-117">For more information about how to specify the `type` attribute, see [Custom Type References](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="091b2-118">子要素</span><span class="sxs-lookup"><span data-stu-id="091b2-118">Child Elements</span></span>  
 <span data-ttu-id="091b2-119">なし</span><span class="sxs-lookup"><span data-stu-id="091b2-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="091b2-120">親要素</span><span class="sxs-lookup"><span data-stu-id="091b2-120">Parent Elements</span></span>  
  
|<span data-ttu-id="091b2-121">要素</span><span class="sxs-lookup"><span data-stu-id="091b2-121">Element</span></span>|<span data-ttu-id="091b2-122">説明</span><span class="sxs-lookup"><span data-stu-id="091b2-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="091b2-123">\<cookieHandler></span><span class="sxs-lookup"><span data-stu-id="091b2-123">\<cookieHandler></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md)|<span data-ttu-id="091b2-124">構成、<xref:System.IdentityModel.Services.CookieHandler>を<xref:System.IdentityModel.Services.SessionAuthenticationModule>読み取りと書き込みの cookie を使用します。</span><span class="sxs-lookup"><span data-stu-id="091b2-124">Configures the <xref:System.IdentityModel.Services.CookieHandler> that the <xref:System.IdentityModel.Services.SessionAuthenticationModule> uses to read and write cookies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="091b2-125">Remarks</span><span class="sxs-lookup"><span data-stu-id="091b2-125">Remarks</span></span>  
 <span data-ttu-id="091b2-126">設定して、カスタム クッキー ハンドラーを指定する場合、`mode`の属性、`<cookieHandler>`要素"Custom"を含めることによって、カスタム クッキー ハンドラーの種類を指定する必要があります、`<customCookieHandler>`クッキー ハンドラーの型を参照する子要素。</span><span class="sxs-lookup"><span data-stu-id="091b2-126">When you specify a custom cookie handler by setting the `mode` attribute of the `<cookieHandler>` element to "Custom", you must specify the type of the custom cookie handler by including a `<customCookieHandler>` child element that references the cookie handler type.</span></span> <span data-ttu-id="091b2-127">この要素にすることはできないときに指定された、`mode`属性が"Chunked"または"Default"に設定します。</span><span class="sxs-lookup"><span data-stu-id="091b2-127">This element cannot be specified when the `mode` attribute is set to "Chunked" or "Default".</span></span> <span data-ttu-id="091b2-128">カスタム クッキー ハンドラーはから派生する必要があります、<xref:System.IdentityModel.Services.CookieHandler>クラス。</span><span class="sxs-lookup"><span data-stu-id="091b2-128">Custom cookie handlers must derive from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>  
  
 <span data-ttu-id="091b2-129">`<customCookieHandler>`要素が表される、<xref:System.IdentityModel.Configuration.CustomTypeElement>クラス。</span><span class="sxs-lookup"><span data-stu-id="091b2-129">The `<customCookieHandler>` element is represented by the <xref:System.IdentityModel.Configuration.CustomTypeElement> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="091b2-130">例</span><span class="sxs-lookup"><span data-stu-id="091b2-130">Example</span></span>  
 <span data-ttu-id="091b2-131">次の例では型のカスタム cookie ハンドラーを使用して SAM`MyNamespace.MyCustomCookieHandler`します。</span><span class="sxs-lookup"><span data-stu-id="091b2-131">The following example configures the SAM to use a custom cookie handler of type `MyNamespace.MyCustomCookieHandler`.</span></span>  
  
```xml  
<cookieHandler mode="Custom">  
    <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" />  
</cookieHandler>  
```  
  
## <a name="see-also"></a><span data-ttu-id="091b2-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="091b2-132">See also</span></span>

- <xref:System.IdentityModel.Services.CookieHandler>
