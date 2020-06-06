---
title: <webRequestModules> 要素 (ネットワーク設定)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules
- http://schemas.microsoft.com/.NetConfiguration/v2.0#webRequestModules
helpviewer_keywords:
- webRequestModules element
- <webRequestModules> element
ms.assetid: 1263de11-3e0a-4f94-97c9-710b2ae53817
ms.openlocfilehash: 7f2805283f89e6165d336b3e593d34054e02115d
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154544"
---
# <a name="webrequestmodules-element-network-settings"></a><span data-ttu-id="0aeee-102">\<webRequestModules> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="0aeee-102">\<webRequestModules> Element (Network Settings)</span></span>
<span data-ttu-id="0aeee-103">ネットワークホストから情報を要求するために使用するモジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="0aeee-103">Specifies modules to use to request information from network hosts.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;\<webRequestModules>  
  
## <a name="syntax"></a><span data-ttu-id="0aeee-104">構文</span><span class="sxs-lookup"><span data-stu-id="0aeee-104">Syntax</span></span>  
  
```xml  
<webRequestModules>
</webRequestModules>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0aeee-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="0aeee-105">Attributes and Elements</span></span>  
 <span data-ttu-id="0aeee-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="0aeee-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0aeee-107">属性</span><span class="sxs-lookup"><span data-stu-id="0aeee-107">Attributes</span></span>  
 <span data-ttu-id="0aeee-108">なし。</span><span class="sxs-lookup"><span data-stu-id="0aeee-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0aeee-109">子要素</span><span class="sxs-lookup"><span data-stu-id="0aeee-109">Child Elements</span></span>  
  
|<span data-ttu-id="0aeee-110">**要素**</span><span class="sxs-lookup"><span data-stu-id="0aeee-110">**Element**</span></span>|<span data-ttu-id="0aeee-111">**説明**</span><span class="sxs-lookup"><span data-stu-id="0aeee-111">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="0aeee-112">add</span><span class="sxs-lookup"><span data-stu-id="0aeee-112">add</span></span>](add-element-for-webrequestmodules-network-settings.md)|<span data-ttu-id="0aeee-113">アプリケーションにカスタム Web 要求モジュールを追加します。</span><span class="sxs-lookup"><span data-stu-id="0aeee-113">Adds a custom Web request module to the application.</span></span>|  
|[<span data-ttu-id="0aeee-114">オフ</span><span class="sxs-lookup"><span data-stu-id="0aeee-114">clear</span></span>](clear-element-for-webrequestmodules-network-settings.md)|<span data-ttu-id="0aeee-115">アプリケーションから、登録されているすべての Web 要求モジュールを削除します。</span><span class="sxs-lookup"><span data-stu-id="0aeee-115">Removes all registered Web request modules from the application.</span></span>|  
|[<span data-ttu-id="0aeee-116">remove</span><span class="sxs-lookup"><span data-stu-id="0aeee-116">remove</span></span>](remove-element-for-webrequestmodules-network-settings.md)|<span data-ttu-id="0aeee-117">アプリケーションからカスタム Web 要求モジュールを削除します。</span><span class="sxs-lookup"><span data-stu-id="0aeee-117">Removes a custom Web request module from the application.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0aeee-118">親要素</span><span class="sxs-lookup"><span data-stu-id="0aeee-118">Parent Elements</span></span>  
  
|<span data-ttu-id="0aeee-119">**要素**</span><span class="sxs-lookup"><span data-stu-id="0aeee-119">**Element**</span></span>|<span data-ttu-id="0aeee-120">**説明**</span><span class="sxs-lookup"><span data-stu-id="0aeee-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="0aeee-121">system.net</span><span class="sxs-lookup"><span data-stu-id="0aeee-121">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="0aeee-122">.NET Framework がネットワークに接続する方法を指定するための設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="0aeee-122">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0aeee-123">解説</span><span class="sxs-lookup"><span data-stu-id="0aeee-123">Remarks</span></span>  
 <span data-ttu-id="0aeee-124">要素は、 `webRequestModules` <xref:System.Net.WebRequest> ネットワークホストに対する情報要求を処理するために、クラスの子孫を登録します。</span><span class="sxs-lookup"><span data-stu-id="0aeee-124">The `webRequestModules` element registers descendants of the <xref:System.Net.WebRequest> class to handle information requests to network hosts.</span></span> <span data-ttu-id="0aeee-125">Web 要求モジュールは、インターフェイスを実装する必要があり <xref:System.Net.IWebRequestCreate> ます。</span><span class="sxs-lookup"><span data-stu-id="0aeee-125">Web request modules must implement the <xref:System.Net.IWebRequestCreate> interface.</span></span>  
  
 <span data-ttu-id="0aeee-126">.NET Framework には、、、およびで始まる Uri の Web 要求モジュールが含まれてい `http://` `https://` `file://` ます。</span><span class="sxs-lookup"><span data-stu-id="0aeee-126">The .NET Framework includes Web request modules for URIs that begin with `http://`, `https://`, and `file://`.</span></span> <span data-ttu-id="0aeee-127">既定のモジュールをオーバーライドするには、構成ファイルにカスタムモジュールを登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0aeee-127">You can override the default modules only by registering a custom module in the configuration file.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="0aeee-128">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="0aeee-128">Configuration Files</span></span>  
 <span data-ttu-id="0aeee-129">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="0aeee-129">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0aeee-130">例</span><span class="sxs-lookup"><span data-stu-id="0aeee-130">Example</span></span>  
 <span data-ttu-id="0aeee-131">次の例では、既定の HTTP モジュールを登録します。</span><span class="sxs-lookup"><span data-stu-id="0aeee-131">The following example registers the default HTTP module.</span></span> <span data-ttu-id="0aeee-132">Version および PublicKeyToken の値は、指定されたモジュールの正しい値に置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="0aeee-132">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <webRequestModules>  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator, System, Version=2.0.3600.0,  
           Culture=neutral, PublicKeyToken=b77a5c561934e089"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0aeee-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="0aeee-133">See also</span></span>

- <xref:System.Net.WebRequest>
- <xref:System.Net.IWebRequestCreate>
- [<span data-ttu-id="0aeee-134">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="0aeee-134">Network Settings Schema</span></span>](index.md)
