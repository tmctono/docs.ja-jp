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
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154544"
---
# <a name="webrequestmodules-element-network-settings"></a><span data-ttu-id="cd130-102">\<webRequestModules> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="cd130-102">\<webRequestModules> Element (Network Settings)</span></span>
<span data-ttu-id="cd130-103">ネットワーク ホストから情報を要求するために使用するモジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="cd130-103">Specifies modules to use to request information from network hosts.</span></span>  
  
[<span data-ttu-id="cd130-104">**\<構成>**</span><span class="sxs-lookup"><span data-stu-id="cd130-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="cd130-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="cd130-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="cd130-106">&nbsp;&nbsp;&nbsp;&nbsp;\<></span><span class="sxs-lookup"><span data-stu-id="cd130-106">&nbsp;&nbsp;&nbsp;&nbsp;\<webRequestModules></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd130-107">構文</span><span class="sxs-lookup"><span data-stu-id="cd130-107">Syntax</span></span>  
  
```xml  
<webRequestModules>
</webRequestModules>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cd130-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="cd130-108">Attributes and Elements</span></span>  
 <span data-ttu-id="cd130-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="cd130-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cd130-110">属性</span><span class="sxs-lookup"><span data-stu-id="cd130-110">Attributes</span></span>  
 <span data-ttu-id="cd130-111">[なし] :</span><span class="sxs-lookup"><span data-stu-id="cd130-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="cd130-112">子要素</span><span class="sxs-lookup"><span data-stu-id="cd130-112">Child Elements</span></span>  
  
|<span data-ttu-id="cd130-113">**Element**</span><span class="sxs-lookup"><span data-stu-id="cd130-113">**Element**</span></span>|<span data-ttu-id="cd130-114">**説明**</span><span class="sxs-lookup"><span data-stu-id="cd130-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="cd130-115">追加</span><span class="sxs-lookup"><span data-stu-id="cd130-115">add</span></span>](add-element-for-webrequestmodules-network-settings.md)|<span data-ttu-id="cd130-116">カスタム Web 要求モジュールをアプリケーションに追加します。</span><span class="sxs-lookup"><span data-stu-id="cd130-116">Adds a custom Web request module to the application.</span></span>|  
|[<span data-ttu-id="cd130-117">クリア</span><span class="sxs-lookup"><span data-stu-id="cd130-117">clear</span></span>](clear-element-for-webrequestmodules-network-settings.md)|<span data-ttu-id="cd130-118">登録されているすべての Web 要求モジュールをアプリケーションから削除します。</span><span class="sxs-lookup"><span data-stu-id="cd130-118">Removes all registered Web request modules from the application.</span></span>|  
|[<span data-ttu-id="cd130-119">削除</span><span class="sxs-lookup"><span data-stu-id="cd130-119">remove</span></span>](remove-element-for-webrequestmodules-network-settings.md)|<span data-ttu-id="cd130-120">カスタム Web 要求モジュールをアプリケーションから削除します。</span><span class="sxs-lookup"><span data-stu-id="cd130-120">Removes a custom Web request module from the application.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cd130-121">親要素</span><span class="sxs-lookup"><span data-stu-id="cd130-121">Parent Elements</span></span>  
  
|<span data-ttu-id="cd130-122">**Element**</span><span class="sxs-lookup"><span data-stu-id="cd130-122">**Element**</span></span>|<span data-ttu-id="cd130-123">**説明**</span><span class="sxs-lookup"><span data-stu-id="cd130-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="cd130-124">system.net</span><span class="sxs-lookup"><span data-stu-id="cd130-124">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="cd130-125">.NET Framework がネットワークに接続する方法を指定するための設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="cd130-125">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cd130-126">解説</span><span class="sxs-lookup"><span data-stu-id="cd130-126">Remarks</span></span>  
 <span data-ttu-id="cd130-127">要素`webRequestModules`は、ネットワーク ホストへの情報<xref:System.Net.WebRequest>要求を処理するクラスの子孫を登録します。</span><span class="sxs-lookup"><span data-stu-id="cd130-127">The `webRequestModules` element registers descendants of the <xref:System.Net.WebRequest> class to handle information requests to network hosts.</span></span> <span data-ttu-id="cd130-128">Web 要求モジュールは、<xref:System.Net.IWebRequestCreate>インターフェイスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd130-128">Web request modules must implement the <xref:System.Net.IWebRequestCreate> interface.</span></span>  
  
 <span data-ttu-id="cd130-129">.NET Framework には`http://`、 で`https://`始まる URI の Web`file://`要求モジュールが含まれています。</span><span class="sxs-lookup"><span data-stu-id="cd130-129">The .NET Framework includes Web request modules for URIs that begin with `http://`, `https://`, and `file://`.</span></span> <span data-ttu-id="cd130-130">デフォルトのモジュールをオーバーライドするには、構成ファイルにカスタム モジュールを登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd130-130">You can override the default modules only by registering a custom module in the configuration file.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="cd130-131">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="cd130-131">Configuration Files</span></span>  
 <span data-ttu-id="cd130-132">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="cd130-132">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="cd130-133">例</span><span class="sxs-lookup"><span data-stu-id="cd130-133">Example</span></span>  
 <span data-ttu-id="cd130-134">次の例では、既定の HTTP モジュールを登録します。</span><span class="sxs-lookup"><span data-stu-id="cd130-134">The following example registers the default HTTP module.</span></span> <span data-ttu-id="cd130-135">バージョンと公開キートークンの値を、指定したモジュールの正しい値に置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd130-135">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="cd130-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="cd130-136">See also</span></span>

- <xref:System.Net.WebRequest>
- <xref:System.Net.IWebRequestCreate>
- [<span data-ttu-id="cd130-137">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="cd130-137">Network Settings Schema</span></span>](index.md)
