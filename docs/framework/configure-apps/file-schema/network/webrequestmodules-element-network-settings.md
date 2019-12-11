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
ms.openlocfilehash: e119d9ce1f8bb6f07f8050612550db459a2f065c
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697461"
---
# <a name="webrequestmodules-element-network-settings"></a><span data-ttu-id="7964f-102">\<webRequestModules> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="7964f-102">\<webRequestModules> Element (Network Settings)</span></span>
<span data-ttu-id="7964f-103">ネットワークホストから情報を要求するために使用するモジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="7964f-103">Specifies modules to use to request information from network hosts.</span></span>  
  
[<span data-ttu-id="7964f-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="7964f-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="7964f-105">&nbsp;&nbsp;[ **\<system.net>** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="7964f-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="7964f-106">&nbsp; @ no__t-1 @ no__t @ no__t @ no__t-4webRequestModules ></span><span class="sxs-lookup"><span data-stu-id="7964f-106">&nbsp;&nbsp;&nbsp;&nbsp;\<webRequestModules></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7964f-107">構文</span><span class="sxs-lookup"><span data-stu-id="7964f-107">Syntax</span></span>  
  
```xml  
<webRequestModules>   
</webRequestModules>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7964f-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="7964f-108">Attributes and Elements</span></span>  
 <span data-ttu-id="7964f-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="7964f-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7964f-110">属性</span><span class="sxs-lookup"><span data-stu-id="7964f-110">Attributes</span></span>  
 <span data-ttu-id="7964f-111">[なし] :</span><span class="sxs-lookup"><span data-stu-id="7964f-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7964f-112">子要素</span><span class="sxs-lookup"><span data-stu-id="7964f-112">Child Elements</span></span>  
  
|<span data-ttu-id="7964f-113">**要素**</span><span class="sxs-lookup"><span data-stu-id="7964f-113">**Element**</span></span>|<span data-ttu-id="7964f-114">**[説明]**</span><span class="sxs-lookup"><span data-stu-id="7964f-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="7964f-115">add</span><span class="sxs-lookup"><span data-stu-id="7964f-115">add</span></span>](add-element-for-webrequestmodules-network-settings.md)|<span data-ttu-id="7964f-116">アプリケーションにカスタム Web 要求モジュールを追加します。</span><span class="sxs-lookup"><span data-stu-id="7964f-116">Adds a custom Web request module to the application.</span></span>|  
|[<span data-ttu-id="7964f-117">clear</span><span class="sxs-lookup"><span data-stu-id="7964f-117">clear</span></span>](clear-element-for-webrequestmodules-network-settings.md)|<span data-ttu-id="7964f-118">アプリケーションから、登録されているすべての Web 要求モジュールを削除します。</span><span class="sxs-lookup"><span data-stu-id="7964f-118">Removes all registered Web request modules from the application.</span></span>|  
|[<span data-ttu-id="7964f-119">remove</span><span class="sxs-lookup"><span data-stu-id="7964f-119">remove</span></span>](remove-element-for-webrequestmodules-network-settings.md)|<span data-ttu-id="7964f-120">アプリケーションからカスタム Web 要求モジュールを削除します。</span><span class="sxs-lookup"><span data-stu-id="7964f-120">Removes a custom Web request module from the application.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7964f-121">親要素</span><span class="sxs-lookup"><span data-stu-id="7964f-121">Parent Elements</span></span>  
  
|<span data-ttu-id="7964f-122">**要素**</span><span class="sxs-lookup"><span data-stu-id="7964f-122">**Element**</span></span>|<span data-ttu-id="7964f-123">**[説明]**</span><span class="sxs-lookup"><span data-stu-id="7964f-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="7964f-124">system.net</span><span class="sxs-lookup"><span data-stu-id="7964f-124">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="7964f-125">.NET Framework がネットワークに接続する方法を指定するための設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="7964f-125">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7964f-126">コメント</span><span class="sxs-lookup"><span data-stu-id="7964f-126">Remarks</span></span>  
 <span data-ttu-id="7964f-127">@No__t-0 要素は、ネットワークホストへの情報要求を処理するために、<xref:System.Net.WebRequest> クラスの子孫を登録します。</span><span class="sxs-lookup"><span data-stu-id="7964f-127">The `webRequestModules` element registers descendants of the <xref:System.Net.WebRequest> class to handle information requests to network hosts.</span></span> <span data-ttu-id="7964f-128">Web 要求モジュールは @no__t 0 インターフェイスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7964f-128">Web request modules must implement the <xref:System.Net.IWebRequestCreate> interface.</span></span>  
  
 <span data-ttu-id="7964f-129">.NET Framework には、`http://`、`https://`、および `file://` で始まる Uri の Web 要求モジュールが含まれています。</span><span class="sxs-lookup"><span data-stu-id="7964f-129">The .NET Framework includes Web request modules for URIs that begin with `http://`, `https://`, and `file://`.</span></span> <span data-ttu-id="7964f-130">既定のモジュールをオーバーライドするには、構成ファイルにカスタムモジュールを登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7964f-130">You can override the default modules only by registering a custom module in the configuration file.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="7964f-131">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="7964f-131">Configuration Files</span></span>  
 <span data-ttu-id="7964f-132">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="7964f-132">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7964f-133">例</span><span class="sxs-lookup"><span data-stu-id="7964f-133">Example</span></span>  
 <span data-ttu-id="7964f-134">次の例では、既定の HTTP モジュールを登録します。</span><span class="sxs-lookup"><span data-stu-id="7964f-134">The following example registers the default HTTP module.</span></span> <span data-ttu-id="7964f-135">Version および PublicKeyToken の値は、指定されたモジュールの正しい値に置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="7964f-135">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7964f-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="7964f-136">See also</span></span>

- <xref:System.Net.WebRequest>
- <xref:System.Net.IWebRequestCreate>
- [<span data-ttu-id="7964f-137">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="7964f-137">Network Settings Schema</span></span>](index.md)
