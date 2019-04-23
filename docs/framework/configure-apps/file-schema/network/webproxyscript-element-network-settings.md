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
ms.openlocfilehash: e73ba86cc17fa51cbf4030f2304ab9141fcc0f26
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59218668"
---
# <a name="webproxyscript-element-network-settings"></a><span data-ttu-id="9a568-102">\<webProxyScript > 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="9a568-102">\<webProxyScript> Element (Network Settings)</span></span>
<span data-ttu-id="9a568-103">Web プロキシを検出するために使用するスクリプトの特性を構成します。</span><span class="sxs-lookup"><span data-stu-id="9a568-103">Configures the characteristics of the script used to discover Web proxies.</span></span>  
  
 <span data-ttu-id="9a568-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="9a568-104">\<configuration></span></span>  
<span data-ttu-id="9a568-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="9a568-105">\<system.net></span></span>  
<span data-ttu-id="9a568-106">\<settings></span><span class="sxs-lookup"><span data-stu-id="9a568-106">\<settings></span></span>  
<span data-ttu-id="9a568-107">\<webProxyScript ></span><span class="sxs-lookup"><span data-stu-id="9a568-107">\<webProxyScript></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a568-108">構文</span><span class="sxs-lookup"><span data-stu-id="9a568-108">Syntax</span></span>  
  
```xml  
<webProxyScript  
  downloadTimeout="hh:mm:ss"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9a568-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="9a568-109">Attributes and Elements</span></span>  
 <span data-ttu-id="9a568-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="9a568-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9a568-111">属性</span><span class="sxs-lookup"><span data-stu-id="9a568-111">Attributes</span></span>  
  
|<span data-ttu-id="9a568-112">属性</span><span class="sxs-lookup"><span data-stu-id="9a568-112">Attribute</span></span>|<span data-ttu-id="9a568-113">説明</span><span class="sxs-lookup"><span data-stu-id="9a568-113">Description</span></span>|  
|---------------|-----------------|  
|`downloadTimeout`|<span data-ttu-id="9a568-114">時間、分、および秒でスクリプトをダウンロードする最大時間を指定します。</span><span class="sxs-lookup"><span data-stu-id="9a568-114">Specifies the maximum time to download the script in hours, minutes, and seconds.</span></span> <span data-ttu-id="9a568-115">既定値は、1 分です。</span><span class="sxs-lookup"><span data-stu-id="9a568-115">The default value is one minute.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9a568-116">子要素</span><span class="sxs-lookup"><span data-stu-id="9a568-116">Child Elements</span></span>  
 <span data-ttu-id="9a568-117">なし。</span><span class="sxs-lookup"><span data-stu-id="9a568-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9a568-118">親要素</span><span class="sxs-lookup"><span data-stu-id="9a568-118">Parent Elements</span></span>  
  
|<span data-ttu-id="9a568-119">要素</span><span class="sxs-lookup"><span data-stu-id="9a568-119">Element</span></span>|<span data-ttu-id="9a568-120">説明</span><span class="sxs-lookup"><span data-stu-id="9a568-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9a568-121">settings</span><span class="sxs-lookup"><span data-stu-id="9a568-121">settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<span data-ttu-id="9a568-122"><xref:System.Net> 名前空間の基本的なネットワーク オプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="9a568-122">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9a568-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="9a568-123">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="9a568-124">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="9a568-124">Configuration Files</span></span>  
 <span data-ttu-id="9a568-125">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="9a568-125">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a568-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="9a568-126">See also</span></span>

- [<span data-ttu-id="9a568-127">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="9a568-127">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
