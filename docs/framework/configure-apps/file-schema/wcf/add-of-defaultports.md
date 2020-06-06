---
title: <add> の <defaultPorts>
ms.date: 03/30/2017
ms.assetid: f162ce42-963b-4779-96a7-d6d8b4ea0d2f
ms.openlocfilehash: f5de2aa897a3bc37d08932451a2c7b94bc603b9e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400647"
---
# <a name="add-of-defaultports"></a><span data-ttu-id="35f4d-102">\<add> の \<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="35f4d-102">\<add> of \<defaultPorts></span></span>
<span data-ttu-id="35f4d-103">クライアント アプリケーションがリッスンする既定の通信エンドポイント。</span><span class="sxs-lookup"><span data-stu-id="35f4d-103">A default communications endpoint that the client application listens to.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<useRequestHeadersForMetadataAddress>**](userequestheadersformetadataaddress.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultPorts>**](defaultports.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="35f4d-104">構文</span><span class="sxs-lookup"><span data-stu-id="35f4d-104">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add port="Integer"
         scheme="String" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="35f4d-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="35f4d-105">Attributes and Elements</span></span>  
 <span data-ttu-id="35f4d-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="35f4d-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="35f4d-107">属性</span><span class="sxs-lookup"><span data-stu-id="35f4d-107">Attributes</span></span>  
  
|<span data-ttu-id="35f4d-108">属性</span><span class="sxs-lookup"><span data-stu-id="35f4d-108">Attribute</span></span>|<span data-ttu-id="35f4d-109">説明</span><span class="sxs-lookup"><span data-stu-id="35f4d-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="35f4d-110">port</span><span class="sxs-lookup"><span data-stu-id="35f4d-110">port</span></span>|<span data-ttu-id="35f4d-111">既定の通信ポート番号を指定する整数。</span><span class="sxs-lookup"><span data-stu-id="35f4d-111">An integer that specifies the default communications port number</span></span>|  
|<span data-ttu-id="35f4d-112">scheme</span><span class="sxs-lookup"><span data-stu-id="35f4d-112">scheme</span></span>|<span data-ttu-id="35f4d-113">通信ポートに関連付けられているプロトコル設定のグループを示す文字列。</span><span class="sxs-lookup"><span data-stu-id="35f4d-113">A string that specifies the group of protocol settings associated with a communications port.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="35f4d-114">子要素</span><span class="sxs-lookup"><span data-stu-id="35f4d-114">Child Elements</span></span>  
 <span data-ttu-id="35f4d-115">なし。</span><span class="sxs-lookup"><span data-stu-id="35f4d-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="35f4d-116">親要素</span><span class="sxs-lookup"><span data-stu-id="35f4d-116">Parent Elements</span></span>  
  
|<span data-ttu-id="35f4d-117">要素</span><span class="sxs-lookup"><span data-stu-id="35f4d-117">Element</span></span>|<span data-ttu-id="35f4d-118">Description</span><span class="sxs-lookup"><span data-stu-id="35f4d-118">Description</span></span>|  
|-------------|-----------------|  
|[\<defaultPorts>](defaultports.md)|<span data-ttu-id="35f4d-119">クライアント アプリケーションがリッスンする既定の通信エンドポイントの一覧を表示する既定のポートのコレクション。</span><span class="sxs-lookup"><span data-stu-id="35f4d-119">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="35f4d-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="35f4d-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.DefaultPortElement>
