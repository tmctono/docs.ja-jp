---
title: <add> の <defaultPorts>
ms.date: 03/30/2017
ms.assetid: f162ce42-963b-4779-96a7-d6d8b4ea0d2f
ms.openlocfilehash: 5200c8893a89488b72c2c71d1a3703bf2aad1235
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704558"
---
# <a name="add-of-defaultports"></a><span data-ttu-id="d9416-102">\<追加 > の\<defaultPorts ></span><span class="sxs-lookup"><span data-stu-id="d9416-102">\<add> of \<defaultPorts></span></span>
<span data-ttu-id="d9416-103">クライアント アプリケーションがリッスンする既定の通信エンドポイント。</span><span class="sxs-lookup"><span data-stu-id="d9416-103">A default communications endpoint that the client application listens to.</span></span>  
  
 <span data-ttu-id="d9416-104">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="d9416-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="d9416-105">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="d9416-105">\<behaviors></span></span>  
<span data-ttu-id="d9416-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="d9416-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="d9416-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="d9416-107">\<behavior></span></span>  
<span data-ttu-id="d9416-108">\<useRequestHeadersForMetadataAddress ></span><span class="sxs-lookup"><span data-stu-id="d9416-108">\<useRequestHeadersForMetadataAddress></span></span>  
<span data-ttu-id="d9416-109">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="d9416-109">\<defaultPorts></span></span>  
<span data-ttu-id="d9416-110">\<add></span><span class="sxs-lookup"><span data-stu-id="d9416-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9416-111">構文</span><span class="sxs-lookup"><span data-stu-id="d9416-111">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add port="Integer"
         scheme="String" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d9416-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="d9416-112">Attributes and Elements</span></span>  
 <span data-ttu-id="d9416-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="d9416-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d9416-114">属性</span><span class="sxs-lookup"><span data-stu-id="d9416-114">Attributes</span></span>  
  
|<span data-ttu-id="d9416-115">属性</span><span class="sxs-lookup"><span data-stu-id="d9416-115">Attribute</span></span>|<span data-ttu-id="d9416-116">説明</span><span class="sxs-lookup"><span data-stu-id="d9416-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d9416-117">ポート</span><span class="sxs-lookup"><span data-stu-id="d9416-117">port</span></span>|<span data-ttu-id="d9416-118">既定の通信ポート番号を指定する整数。</span><span class="sxs-lookup"><span data-stu-id="d9416-118">An integer that specifies the default communications port number</span></span>|  
|<span data-ttu-id="d9416-119">scheme</span><span class="sxs-lookup"><span data-stu-id="d9416-119">scheme</span></span>|<span data-ttu-id="d9416-120">通信ポートに関連付けられているプロトコル設定のグループを示す文字列。</span><span class="sxs-lookup"><span data-stu-id="d9416-120">A string that specifies the group of protocol settings associated with a communications port.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d9416-121">子要素</span><span class="sxs-lookup"><span data-stu-id="d9416-121">Child Elements</span></span>  
 <span data-ttu-id="d9416-122">なし。</span><span class="sxs-lookup"><span data-stu-id="d9416-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d9416-123">親要素</span><span class="sxs-lookup"><span data-stu-id="d9416-123">Parent Elements</span></span>  
  
|<span data-ttu-id="d9416-124">要素</span><span class="sxs-lookup"><span data-stu-id="d9416-124">Element</span></span>|<span data-ttu-id="d9416-125">説明</span><span class="sxs-lookup"><span data-stu-id="d9416-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d9416-126">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="d9416-126">\<defaultPorts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/defaultports.md)|<span data-ttu-id="d9416-127">クライアント アプリケーションがリッスンする既定の通信エンドポイントの一覧を表示する既定のポートのコレクション。</span><span class="sxs-lookup"><span data-stu-id="d9416-127">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d9416-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="d9416-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.DefaultPortElement>
