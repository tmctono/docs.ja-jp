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
ms.openlocfilehash: dbad888cd0537f63c09840ac1053f924db9ea9bc
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "74089057"
---
# <a name="webproxyscript-element-network-settings"></a><span data-ttu-id="19703-102">\<webProxyScript> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="19703-102">\<webProxyScript> Element (Network Settings)</span></span>
<span data-ttu-id="19703-103">Web プロキシを検出するために使用するスクリプトの特性を構成します。</span><span class="sxs-lookup"><span data-stu-id="19703-103">Configures the characteristics of the script used to discover Web proxies.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webProxyScript>**

## <a name="syntax"></a><span data-ttu-id="19703-104">構文</span><span class="sxs-lookup"><span data-stu-id="19703-104">Syntax</span></span>  
  
```xml  
<webProxyScript  
  downloadTimeout="hh:mm:ss"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="19703-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="19703-105">Attributes and Elements</span></span>  
 <span data-ttu-id="19703-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="19703-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="19703-107">属性</span><span class="sxs-lookup"><span data-stu-id="19703-107">Attributes</span></span>  
  
|<span data-ttu-id="19703-108">属性</span><span class="sxs-lookup"><span data-stu-id="19703-108">Attribute</span></span>|<span data-ttu-id="19703-109">説明</span><span class="sxs-lookup"><span data-stu-id="19703-109">Description</span></span>|  
|---------------|-----------------|  
|`downloadTimeout`|<span data-ttu-id="19703-110">スクリプトをダウンロードする最長時間を、時間、分、および秒単位で指定します。</span><span class="sxs-lookup"><span data-stu-id="19703-110">Specifies the maximum time to download the script in hours, minutes, and seconds.</span></span> <span data-ttu-id="19703-111">既定値は1分です。</span><span class="sxs-lookup"><span data-stu-id="19703-111">The default value is one minute.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="19703-112">子要素</span><span class="sxs-lookup"><span data-stu-id="19703-112">Child Elements</span></span>  
 <span data-ttu-id="19703-113">なし。</span><span class="sxs-lookup"><span data-stu-id="19703-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="19703-114">親要素</span><span class="sxs-lookup"><span data-stu-id="19703-114">Parent Elements</span></span>  
  
|<span data-ttu-id="19703-115">要素</span><span class="sxs-lookup"><span data-stu-id="19703-115">Element</span></span>|<span data-ttu-id="19703-116">Description</span><span class="sxs-lookup"><span data-stu-id="19703-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="19703-117">設定</span><span class="sxs-lookup"><span data-stu-id="19703-117">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="19703-118"><xref:System.Net> 名前空間の基本的なネットワーク オプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="19703-118">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="19703-119">解説</span><span class="sxs-lookup"><span data-stu-id="19703-119">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="19703-120">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="19703-120">Configuration Files</span></span>  
 <span data-ttu-id="19703-121">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="19703-121">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19703-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="19703-122">See also</span></span>

- [<span data-ttu-id="19703-123">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="19703-123">Network Settings Schema</span></span>](index.md)
