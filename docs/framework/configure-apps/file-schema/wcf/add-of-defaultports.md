---
title: <add> の <defaultPorts>
ms.date: 03/30/2017
ms.assetid: f162ce42-963b-4779-96a7-d6d8b4ea0d2f
ms.openlocfilehash: f5de2aa897a3bc37d08932451a2c7b94bc603b9e
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400647"
---
# <a name="add-of-defaultports"></a><span data-ttu-id="a800c-102">\<defaultports の\<> を追加し ></span><span class="sxs-lookup"><span data-stu-id="a800c-102">\<add> of \<defaultPorts></span></span>
<span data-ttu-id="a800c-103">クライアント アプリケーションがリッスンする既定の通信エンドポイント。</span><span class="sxs-lookup"><span data-stu-id="a800c-103">A default communications endpoint that the client application listens to.</span></span>  
  
<span data-ttu-id="a800c-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a800c-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a800c-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="a800c-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="a800c-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="a800c-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="a800c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="a800c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="a800c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="a800c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="a800c-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<useRequestHeadersForMetadataAddress >** ](userequestheadersformetadataaddress.md)</span><span class="sxs-lookup"><span data-stu-id="a800c-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<useRequestHeadersForMetadataAddress>**](userequestheadersformetadataaddress.md)</span></span>\
<span data-ttu-id="a800c-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<defaultPorts >** ](defaultports.md)</span><span class="sxs-lookup"><span data-stu-id="a800c-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultPorts>**](defaultports.md)</span></span>\
<span data-ttu-id="a800c-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> の追加**</span><span class="sxs-lookup"><span data-stu-id="a800c-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a800c-112">構文</span><span class="sxs-lookup"><span data-stu-id="a800c-112">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add port="Integer"
         scheme="String" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a800c-113">属性および要素</span><span class="sxs-lookup"><span data-stu-id="a800c-113">Attributes and Elements</span></span>  
 <span data-ttu-id="a800c-114">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="a800c-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a800c-115">属性</span><span class="sxs-lookup"><span data-stu-id="a800c-115">Attributes</span></span>  
  
|<span data-ttu-id="a800c-116">属性</span><span class="sxs-lookup"><span data-stu-id="a800c-116">Attribute</span></span>|<span data-ttu-id="a800c-117">説明</span><span class="sxs-lookup"><span data-stu-id="a800c-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a800c-118">ポート</span><span class="sxs-lookup"><span data-stu-id="a800c-118">port</span></span>|<span data-ttu-id="a800c-119">既定の通信ポート番号を指定する整数。</span><span class="sxs-lookup"><span data-stu-id="a800c-119">An integer that specifies the default communications port number</span></span>|  
|<span data-ttu-id="a800c-120">scheme</span><span class="sxs-lookup"><span data-stu-id="a800c-120">scheme</span></span>|<span data-ttu-id="a800c-121">通信ポートに関連付けられているプロトコル設定のグループを示す文字列。</span><span class="sxs-lookup"><span data-stu-id="a800c-121">A string that specifies the group of protocol settings associated with a communications port.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a800c-122">子要素</span><span class="sxs-lookup"><span data-stu-id="a800c-122">Child Elements</span></span>  
 <span data-ttu-id="a800c-123">なし。</span><span class="sxs-lookup"><span data-stu-id="a800c-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a800c-124">親要素</span><span class="sxs-lookup"><span data-stu-id="a800c-124">Parent Elements</span></span>  
  
|<span data-ttu-id="a800c-125">要素</span><span class="sxs-lookup"><span data-stu-id="a800c-125">Element</span></span>|<span data-ttu-id="a800c-126">説明</span><span class="sxs-lookup"><span data-stu-id="a800c-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a800c-127">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="a800c-127">\<defaultPorts></span></span>](defaultports.md)|<span data-ttu-id="a800c-128">クライアント アプリケーションがリッスンする既定の通信エンドポイントの一覧を表示する既定のポートのコレクション。</span><span class="sxs-lookup"><span data-stu-id="a800c-128">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a800c-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="a800c-129">See also</span></span>

- <xref:System.ServiceModel.Configuration.DefaultPortElement>
