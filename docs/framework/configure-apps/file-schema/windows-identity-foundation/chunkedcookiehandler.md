---
title: <chunkedCookieHandler>
ms.date: 03/30/2017
ms.assetid: 7220de45-1d14-4aec-a29e-4a2ea8ac861f
author: BrucePerlerMS
ms.openlocfilehash: b3b4cf0d7c2748079af7a94534622b1dbadd3ab5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69941891"
---
# <a name="chunkedcookiehandler"></a><span data-ttu-id="1be05-101">\<chunkedCookieHandler></span><span class="sxs-lookup"><span data-stu-id="1be05-101">\<chunkedCookieHandler></span></span>
<span data-ttu-id="1be05-102">を<xref:System.IdentityModel.Services.ChunkedCookieHandler>構成します。</span><span class="sxs-lookup"><span data-stu-id="1be05-102">Configures the <xref:System.IdentityModel.Services.ChunkedCookieHandler>.</span></span> <span data-ttu-id="1be05-103">この要素は、 `mode` `<cookieHandler>`要素の属性が "Default" または "Chunked" の場合にのみ存在する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1be05-103">This element may only be present if the `mode` attribute of the `<cookieHandler>` element is "Default" or "Chunked".</span></span>  
  
 <span data-ttu-id="1be05-104">\<system.identityModel.services></span><span class="sxs-lookup"><span data-stu-id="1be05-104">\<system.identityModel.services></span></span>  
<span data-ttu-id="1be05-105">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="1be05-105">\<federationConfiguration></span></span>  
<span data-ttu-id="1be05-106">\<cookieHandler ></span><span class="sxs-lookup"><span data-stu-id="1be05-106">\<cookieHandler></span></span>  
<span data-ttu-id="1be05-107">\<chunkedCookieHandler></span><span class="sxs-lookup"><span data-stu-id="1be05-107">\<chunkedCookieHandler></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1be05-108">構文</span><span class="sxs-lookup"><span data-stu-id="1be05-108">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <cookieHandler mode="Chunked||Default" >  
      <chunkedCookieHandler size=xs:int >  
      </chunkedCookieHandler>  
    </cookieHandler>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1be05-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="1be05-109">Attributes and Elements</span></span>  
 <span data-ttu-id="1be05-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="1be05-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1be05-111">属性</span><span class="sxs-lookup"><span data-stu-id="1be05-111">Attributes</span></span>  
  
|<span data-ttu-id="1be05-112">属性</span><span class="sxs-lookup"><span data-stu-id="1be05-112">Attribute</span></span>|<span data-ttu-id="1be05-113">説明</span><span class="sxs-lookup"><span data-stu-id="1be05-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1be05-114">chunkSize</span><span class="sxs-lookup"><span data-stu-id="1be05-114">chunkSize</span></span>|<span data-ttu-id="1be05-115">1つの HTTP クッキーの HTTP クッキーデータの最大サイズ (文字数)。</span><span class="sxs-lookup"><span data-stu-id="1be05-115">The maximum size, in characters, of the HTTP cookie data for any one HTTP cookie.</span></span> <span data-ttu-id="1be05-116">チャンクサイズを調整する場合は注意が必要です。</span><span class="sxs-lookup"><span data-stu-id="1be05-116">You must be careful when adjusting the chunk size.</span></span> <span data-ttu-id="1be05-117">Web ブラウザーでは、cookie のサイズとドメインごとに許可される数の制限が異なります。</span><span class="sxs-lookup"><span data-stu-id="1be05-117">Web browsers have different limits on the size of cookies and number allowed per domain.</span></span> <span data-ttu-id="1be05-118">たとえば、Netscape の元の仕様では、次の制限が規定されています。300クッキーの合計、cookie ヘッダーあたりの4096バイト (cookie 値だけでなく、メタデータを含む)、ドメインごとに20の cookie。</span><span class="sxs-lookup"><span data-stu-id="1be05-118">For example, the original Netscape specification stipulated these limits: 300 cookies total, 4096 bytes per cookie header (including metadata, not just the cookie value), and 20 cookies per domain.</span></span> <span data-ttu-id="1be05-119">既定値は2000です。</span><span class="sxs-lookup"><span data-stu-id="1be05-119">The default is 2000.</span></span> <span data-ttu-id="1be05-120">必須。</span><span class="sxs-lookup"><span data-stu-id="1be05-120">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1be05-121">子要素</span><span class="sxs-lookup"><span data-stu-id="1be05-121">Child Elements</span></span>  
 <span data-ttu-id="1be05-122">なし</span><span class="sxs-lookup"><span data-stu-id="1be05-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1be05-123">親要素</span><span class="sxs-lookup"><span data-stu-id="1be05-123">Parent Elements</span></span>  
  
|<span data-ttu-id="1be05-124">要素</span><span class="sxs-lookup"><span data-stu-id="1be05-124">Element</span></span>|<span data-ttu-id="1be05-125">説明</span><span class="sxs-lookup"><span data-stu-id="1be05-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1be05-126">\<cookieHandler ></span><span class="sxs-lookup"><span data-stu-id="1be05-126">\<cookieHandler></span></span>](cookiehandler.md)|<span data-ttu-id="1be05-127">(SAM) が<xref:System.IdentityModel.Services.SessionAuthenticationModule> cookie の読み取りと書き込みに使用するを構成します。<xref:System.IdentityModel.Services.CookieHandler></span><span class="sxs-lookup"><span data-stu-id="1be05-127">Configures the <xref:System.IdentityModel.Services.CookieHandler> that the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) uses to read and write cookies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1be05-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="1be05-128">Remarks</span></span>  
 <span data-ttu-id="1be05-129">要素の<xref:System.IdentityModel.Services.ChunkedCookieHandler> `mode`属性を "Default" または "Chunked" に設定してを指定した場合、 `<chunkedCookieHandler>`子要素を含めることによって cookie ハンドラーが cookie の読み取りと書き込みに使用するチャンクサイズを指定できます。 `<cookieHandler>``chunkSize`属性を設定しています。</span><span class="sxs-lookup"><span data-stu-id="1be05-129">When you specify a <xref:System.IdentityModel.Services.ChunkedCookieHandler> by setting the `mode` attribute of the `<cookieHandler>` element to "Default" or "Chunked", you can specify the chunk size that the cookie handler uses to read and write cookies by including a `<chunkedCookieHandler>` child element and setting its `chunkSize` attribute.</span></span> <span data-ttu-id="1be05-130">`<chunkedCookieHandler>`要素が存在しない場合は、既定のチャンクサイズである2000バイトが使用されます。</span><span class="sxs-lookup"><span data-stu-id="1be05-130">If the `<chunkedCookieHandler>` element is not present, the default chunk size of 2000 bytes is used.</span></span> <span data-ttu-id="1be05-131">属性が "Custom" に設定`mode`されている場合、この要素を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="1be05-131">This element cannot be specified when the `mode` attribute is set to "Custom".</span></span>  
  
 <span data-ttu-id="1be05-132">要素は、 <xref:System.IdentityModel.Services.ChunkedCookieHandlerElement>クラスによって表されます。 `<chunkedCookieHandler>`</span><span class="sxs-lookup"><span data-stu-id="1be05-132">The `<chunkedCookieHandler>` element is represented by the <xref:System.IdentityModel.Services.ChunkedCookieHandlerElement> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1be05-133">例</span><span class="sxs-lookup"><span data-stu-id="1be05-133">Example</span></span>  
 <span data-ttu-id="1be05-134">次の例では、3000バイトのチャンク単位でクッキーを書き込むチャンク cookie ハンドラーを構成します。</span><span class="sxs-lookup"><span data-stu-id="1be05-134">The following example configures a chunked cookie handler that writes cookies in chunks of 3000 bytes.</span></span>  
  
```xml  
<cookieHandler mode="Chunked">  
    <chunkedCookieHandler chunkSize=3000/>  
</cookieHandler>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1be05-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="1be05-135">See also</span></span>

- <xref:System.IdentityModel.Services.ChunkedCookieHandler>
