---
title: <webProxyScript> 要素 (ネットワーク設定)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#webProxyScript
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/webProxyScript
helpviewer_keywords:
- <webProxyScript> element
- webProxyScript element
ms.assetid: a13c26db-6218-4af3-9696-38f24b23bfac
ms.openlocfilehash: e36b470b1ec348085b13a58630b0ac6833e43946
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91178308"
---
# <a name="webproxyscript-element-network-settings"></a><span data-ttu-id="e2650-102">\<webProxyScript> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="e2650-102">\<webProxyScript> Element (Network Settings)</span></span>

<span data-ttu-id="e2650-103">Web プロキシを検出するために使用するスクリプトの特性を構成します。</span><span class="sxs-lookup"><span data-stu-id="e2650-103">Configures the characteristics of the script used to discover Web proxies.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webProxyScript>**

## <a name="syntax"></a><span data-ttu-id="e2650-104">構文</span><span class="sxs-lookup"><span data-stu-id="e2650-104">Syntax</span></span>  
  
```xml  
<webProxyScript  
  downloadTimeout="hh:mm:ss"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e2650-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e2650-105">Attributes and Elements</span></span>  

 <span data-ttu-id="e2650-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="e2650-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e2650-107">属性</span><span class="sxs-lookup"><span data-stu-id="e2650-107">Attributes</span></span>  
  
|<span data-ttu-id="e2650-108">属性</span><span class="sxs-lookup"><span data-stu-id="e2650-108">Attribute</span></span>|<span data-ttu-id="e2650-109">[説明]</span><span class="sxs-lookup"><span data-stu-id="e2650-109">Description</span></span>|  
|---------------|-----------------|  
|`downloadTimeout`|<span data-ttu-id="e2650-110">スクリプトをダウンロードする最長時間を、時間、分、および秒単位で指定します。</span><span class="sxs-lookup"><span data-stu-id="e2650-110">Specifies the maximum time to download the script in hours, minutes, and seconds.</span></span> <span data-ttu-id="e2650-111">既定値は1分です。</span><span class="sxs-lookup"><span data-stu-id="e2650-111">The default value is one minute.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e2650-112">子要素</span><span class="sxs-lookup"><span data-stu-id="e2650-112">Child Elements</span></span>  

 <span data-ttu-id="e2650-113">なし。</span><span class="sxs-lookup"><span data-stu-id="e2650-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e2650-114">親要素</span><span class="sxs-lookup"><span data-stu-id="e2650-114">Parent Elements</span></span>  
  
|<span data-ttu-id="e2650-115">要素</span><span class="sxs-lookup"><span data-stu-id="e2650-115">Element</span></span>|<span data-ttu-id="e2650-116">説明</span><span class="sxs-lookup"><span data-stu-id="e2650-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e2650-117">設定</span><span class="sxs-lookup"><span data-stu-id="e2650-117">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="e2650-118"><xref:System.Net> 名前空間の基本的なネットワーク オプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="e2650-118">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e2650-119">解説</span><span class="sxs-lookup"><span data-stu-id="e2650-119">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="e2650-120">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="e2650-120">Configuration Files</span></span>  

 <span data-ttu-id="e2650-121">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="e2650-121">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2650-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="e2650-122">See also</span></span>

- [<span data-ttu-id="e2650-123">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="e2650-123">Network Settings Schema</span></span>](index.md)
