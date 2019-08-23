---
title: <add> の <defaultPorts>
ms.date: 03/30/2017
ms.assetid: f162ce42-963b-4779-96a7-d6d8b4ea0d2f
ms.openlocfilehash: d2723dad14a63c4b05fdb70157f7eb21d193d3ab
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926709"
---
# <a name="add-of-defaultports"></a><span data-ttu-id="4b71a-102">\<defaultports の\<> を追加し ></span><span class="sxs-lookup"><span data-stu-id="4b71a-102">\<add> of \<defaultPorts></span></span>
<span data-ttu-id="4b71a-103">クライアント アプリケーションがリッスンする既定の通信エンドポイント。</span><span class="sxs-lookup"><span data-stu-id="4b71a-103">A default communications endpoint that the client application listens to.</span></span>  
  
 <span data-ttu-id="4b71a-104">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="4b71a-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="4b71a-105">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="4b71a-105">\<behaviors></span></span>  
<span data-ttu-id="4b71a-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="4b71a-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="4b71a-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="4b71a-107">\<behavior></span></span>  
<span data-ttu-id="4b71a-108">\<useRequestHeadersForMetadataAddress ></span><span class="sxs-lookup"><span data-stu-id="4b71a-108">\<useRequestHeadersForMetadataAddress></span></span>  
<span data-ttu-id="4b71a-109">\<defaultPorts ></span><span class="sxs-lookup"><span data-stu-id="4b71a-109">\<defaultPorts></span></span>  
<span data-ttu-id="4b71a-110">\<add></span><span class="sxs-lookup"><span data-stu-id="4b71a-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b71a-111">構文</span><span class="sxs-lookup"><span data-stu-id="4b71a-111">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add port="Integer"
         scheme="String" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4b71a-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="4b71a-112">Attributes and Elements</span></span>  
 <span data-ttu-id="4b71a-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="4b71a-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4b71a-114">属性</span><span class="sxs-lookup"><span data-stu-id="4b71a-114">Attributes</span></span>  
  
|<span data-ttu-id="4b71a-115">属性</span><span class="sxs-lookup"><span data-stu-id="4b71a-115">Attribute</span></span>|<span data-ttu-id="4b71a-116">説明</span><span class="sxs-lookup"><span data-stu-id="4b71a-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4b71a-117">ポート</span><span class="sxs-lookup"><span data-stu-id="4b71a-117">port</span></span>|<span data-ttu-id="4b71a-118">既定の通信ポート番号を指定する整数。</span><span class="sxs-lookup"><span data-stu-id="4b71a-118">An integer that specifies the default communications port number</span></span>|  
|<span data-ttu-id="4b71a-119">scheme</span><span class="sxs-lookup"><span data-stu-id="4b71a-119">scheme</span></span>|<span data-ttu-id="4b71a-120">通信ポートに関連付けられているプロトコル設定のグループを示す文字列。</span><span class="sxs-lookup"><span data-stu-id="4b71a-120">A string that specifies the group of protocol settings associated with a communications port.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4b71a-121">子要素</span><span class="sxs-lookup"><span data-stu-id="4b71a-121">Child Elements</span></span>  
 <span data-ttu-id="4b71a-122">なし。</span><span class="sxs-lookup"><span data-stu-id="4b71a-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4b71a-123">親要素</span><span class="sxs-lookup"><span data-stu-id="4b71a-123">Parent Elements</span></span>  
  
|<span data-ttu-id="4b71a-124">要素</span><span class="sxs-lookup"><span data-stu-id="4b71a-124">Element</span></span>|<span data-ttu-id="4b71a-125">説明</span><span class="sxs-lookup"><span data-stu-id="4b71a-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4b71a-126">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="4b71a-126">\<defaultPorts></span></span>](defaultports.md)|<span data-ttu-id="4b71a-127">クライアント アプリケーションがリッスンする既定の通信エンドポイントの一覧を表示する既定のポートのコレクション。</span><span class="sxs-lookup"><span data-stu-id="4b71a-127">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4b71a-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="4b71a-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.DefaultPortElement>
