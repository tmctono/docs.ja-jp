---
title: <chunkedCookieHandler>
ms.date: 03/30/2017
ms.assetid: 7220de45-1d14-4aec-a29e-4a2ea8ac861f
author: BrucePerlerMS
ms.openlocfilehash: d9c81d5de7bea343f0d67fa00037763fbae7b8c5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59120784"
---
# <a name="chunkedcookiehandler"></a><span data-ttu-id="7cbe5-101">\<chunkedCookieHandler></span><span class="sxs-lookup"><span data-stu-id="7cbe5-101">\<chunkedCookieHandler></span></span>
<span data-ttu-id="7cbe5-102">構成、<xref:System.IdentityModel.Services.ChunkedCookieHandler>します。</span><span class="sxs-lookup"><span data-stu-id="7cbe5-102">Configures the <xref:System.IdentityModel.Services.ChunkedCookieHandler>.</span></span> <span data-ttu-id="7cbe5-103">この要素は存在のみ可能な場合、`mode`の属性、`<cookieHandler>`要素が"Default"または「チャンク」。</span><span class="sxs-lookup"><span data-stu-id="7cbe5-103">This element may only be present if the `mode` attribute of the `<cookieHandler>` element is "Default" or "Chunked".</span></span>  
  
 <span data-ttu-id="7cbe5-104">\<system.identityModel.services></span><span class="sxs-lookup"><span data-stu-id="7cbe5-104">\<system.identityModel.services></span></span>  
<span data-ttu-id="7cbe5-105">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="7cbe5-105">\<federationConfiguration></span></span>  
<span data-ttu-id="7cbe5-106">\<cookieHandler></span><span class="sxs-lookup"><span data-stu-id="7cbe5-106">\<cookieHandler></span></span>  
<span data-ttu-id="7cbe5-107">\<chunkedCookieHandler></span><span class="sxs-lookup"><span data-stu-id="7cbe5-107">\<chunkedCookieHandler></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7cbe5-108">構文</span><span class="sxs-lookup"><span data-stu-id="7cbe5-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7cbe5-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="7cbe5-109">Attributes and Elements</span></span>  
 <span data-ttu-id="7cbe5-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="7cbe5-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7cbe5-111">属性</span><span class="sxs-lookup"><span data-stu-id="7cbe5-111">Attributes</span></span>  
  
|<span data-ttu-id="7cbe5-112">属性</span><span class="sxs-lookup"><span data-stu-id="7cbe5-112">Attribute</span></span>|<span data-ttu-id="7cbe5-113">説明</span><span class="sxs-lookup"><span data-stu-id="7cbe5-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7cbe5-114">ChunkSize</span><span class="sxs-lookup"><span data-stu-id="7cbe5-114">chunkSize</span></span>|<span data-ttu-id="7cbe5-115">任意の 1 つの HTTP クッキーを HTTP cookie のデータの文字の最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="7cbe5-115">The maximum size, in characters, of the HTTP cookie data for any one HTTP cookie.</span></span> <span data-ttu-id="7cbe5-116">チャンク サイズを調整する場合は注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7cbe5-116">You must be careful when adjusting the chunk size.</span></span> <span data-ttu-id="7cbe5-117">Web ブラウザーでは、cookie とドメインごとに許可される数のサイズにさまざまな制限があります。</span><span class="sxs-lookup"><span data-stu-id="7cbe5-117">Web browsers have different limits on the size of cookies and number allowed per domain.</span></span> <span data-ttu-id="7cbe5-118">たとえば、元の Netscape 仕様では、これらの制限が規定されて。(cookie の値だけでなく、メタデータを含む)、[cookie] ヘッダーあたり 4,096 バイトと 20 の cookie ドメインごと、300 cookie の合計します。</span><span class="sxs-lookup"><span data-stu-id="7cbe5-118">For example, the original Netscape specification stipulated these limits: 300 cookies total, 4096 bytes per cookie header (including metadata, not just the cookie value), and 20 cookies per domain.</span></span> <span data-ttu-id="7cbe5-119">既定値は 2000 です。</span><span class="sxs-lookup"><span data-stu-id="7cbe5-119">The default is 2000.</span></span> <span data-ttu-id="7cbe5-120">必須。</span><span class="sxs-lookup"><span data-stu-id="7cbe5-120">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7cbe5-121">子要素</span><span class="sxs-lookup"><span data-stu-id="7cbe5-121">Child Elements</span></span>  
 <span data-ttu-id="7cbe5-122">なし</span><span class="sxs-lookup"><span data-stu-id="7cbe5-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7cbe5-123">親要素</span><span class="sxs-lookup"><span data-stu-id="7cbe5-123">Parent Elements</span></span>  
  
|<span data-ttu-id="7cbe5-124">要素</span><span class="sxs-lookup"><span data-stu-id="7cbe5-124">Element</span></span>|<span data-ttu-id="7cbe5-125">説明</span><span class="sxs-lookup"><span data-stu-id="7cbe5-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7cbe5-126">\<cookieHandler></span><span class="sxs-lookup"><span data-stu-id="7cbe5-126">\<cookieHandler></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md)|<span data-ttu-id="7cbe5-127">構成、<xref:System.IdentityModel.Services.CookieHandler>を<xref:System.IdentityModel.Services.SessionAuthenticationModule>(SAM) を使用して cookie を読み書きします。</span><span class="sxs-lookup"><span data-stu-id="7cbe5-127">Configures the <xref:System.IdentityModel.Services.CookieHandler> that the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) uses to read and write cookies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7cbe5-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="7cbe5-128">Remarks</span></span>  
 <span data-ttu-id="7cbe5-129">指定した場合、<xref:System.IdentityModel.Services.ChunkedCookieHandler>を設定して、`mode`の属性、`<cookieHandler>`を"Default"または"Chunked"要素を含めることで cookie を読み書きするクッキー ハンドラーを使用するチャンクのサイズを指定できます、`<chunkedCookieHandler>`子要素と設定の`chunkSize`属性。</span><span class="sxs-lookup"><span data-stu-id="7cbe5-129">When you specify a <xref:System.IdentityModel.Services.ChunkedCookieHandler> by setting the `mode` attribute of the `<cookieHandler>` element to "Default" or "Chunked", you can specify the chunk size that the cookie handler uses to read and write cookies by including a `<chunkedCookieHandler>` child element and setting its `chunkSize` attribute.</span></span> <span data-ttu-id="7cbe5-130">場合、`<chunkedCookieHandler>`要素が存在しない、2000 バイトの既定のチャンク サイズが使用されます。</span><span class="sxs-lookup"><span data-stu-id="7cbe5-130">If the `<chunkedCookieHandler>` element is not present, the default chunk size of 2000 bytes is used.</span></span> <span data-ttu-id="7cbe5-131">この要素にすることはできないときに指定された、`mode`属性が"Custom"に設定します。</span><span class="sxs-lookup"><span data-stu-id="7cbe5-131">This element cannot be specified when the `mode` attribute is set to "Custom".</span></span>  
  
 <span data-ttu-id="7cbe5-132">`<chunkedCookieHandler>`要素が表される、<xref:System.IdentityModel.Services.ChunkedCookieHandlerElement>クラス。</span><span class="sxs-lookup"><span data-stu-id="7cbe5-132">The `<chunkedCookieHandler>` element is represented by the <xref:System.IdentityModel.Services.ChunkedCookieHandlerElement> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7cbe5-133">例</span><span class="sxs-lookup"><span data-stu-id="7cbe5-133">Example</span></span>  
 <span data-ttu-id="7cbe5-134">次の例では、3000 バイトのチャンク単位で cookie を書き込むチャンクされたクッキー ハンドラーを構成します。</span><span class="sxs-lookup"><span data-stu-id="7cbe5-134">The following example configures a chunked cookie handler that writes cookies in chunks of 3000 bytes.</span></span>  
  
```xml  
<cookieHandler mode="Chunked">  
    <chunkedCookieHandler chunkSize=3000/>  
</cookieHandler>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7cbe5-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="7cbe5-135">See also</span></span>

- <xref:System.IdentityModel.Services.ChunkedCookieHandler>
