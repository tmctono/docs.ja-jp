---
title: <backupLists>
ms.date: 03/30/2017
ms.assetid: 593b3390-f65b-4684-ad40-0596b62f0954
ms.openlocfilehash: 5f2bb030d13389e15cb44f1ddff3b8168b4f2140
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850260"
---
# <a name="backuplists"></a><span data-ttu-id="0453c-101">\<backupLists ></span><span class="sxs-lookup"><span data-stu-id="0453c-101">\<backupLists></span></span>
<span data-ttu-id="0453c-102">エラー処理に使用されるバックアップ サービス セットを定義する構成セクションを表します。</span><span class="sxs-lookup"><span data-stu-id="0453c-102">Represents a configuration section for defining a set of backup services used in error handling.</span></span> <span data-ttu-id="0453c-103">各子要素は、プライマリエンドポイントに到達できない場合にルーティングサービスによって使用される一連のエンドポイントを列挙するバックアップリストです。</span><span class="sxs-lookup"><span data-stu-id="0453c-103">Each child element is a backup list that enumerates a set of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="0453c-104">リストの最初のエンドポイントがダウンしていると、ルーティング サービスは自動的にリスト内で次にあるエンドポイントにフェールオーバーします。</span><span class="sxs-lookup"><span data-stu-id="0453c-104">If the first endpoint in the list is down, the Routing Service will automatically fail-over to the next one in the list.</span></span>  <span data-ttu-id="0453c-105">これにより、クライアント アプリケーションに複雑なパターンの処理方法やサービスの配置場所を示すことなく、アプリケーションの信頼性を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="0453c-105">This gives you a quick way to add reliability to your application without having to teach your client application how to handle complex patterns or where all of your services are deployed.</span></span>  
  
<span data-ttu-id="0453c-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="0453c-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="0453c-107">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="0453c-107">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="0453c-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<ルーティング >** ](routing.md)</span><span class="sxs-lookup"><span data-stu-id="0453c-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)</span></span>\
<span data-ttu-id="0453c-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<backupLists >**</span><span class="sxs-lookup"><span data-stu-id="0453c-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<backupLists>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0453c-110">構文</span><span class="sxs-lookup"><span data-stu-id="0453c-110">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0453c-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="0453c-111">Attributes and Elements</span></span>  
 <span data-ttu-id="0453c-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="0453c-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0453c-113">属性</span><span class="sxs-lookup"><span data-stu-id="0453c-113">Attributes</span></span>  
 <span data-ttu-id="0453c-114">なし。</span><span class="sxs-lookup"><span data-stu-id="0453c-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0453c-115">子要素</span><span class="sxs-lookup"><span data-stu-id="0453c-115">Child Elements</span></span>  
  
|<span data-ttu-id="0453c-116">要素</span><span class="sxs-lookup"><span data-stu-id="0453c-116">Element</span></span>|<span data-ttu-id="0453c-117">説明</span><span class="sxs-lookup"><span data-stu-id="0453c-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0453c-118">\<filter></span><span class="sxs-lookup"><span data-stu-id="0453c-118">\<filter></span></span>](filter.md)|<span data-ttu-id="0453c-119">プライマリエンドポイントに到達できない場合に、ルーティングサービスで使用するエンドポイントの一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="0453c-119">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="0453c-120">.</span><span class="sxs-lookup"><span data-stu-id="0453c-120">.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0453c-121">親要素</span><span class="sxs-lookup"><span data-stu-id="0453c-121">Parent Elements</span></span>  
  
|<span data-ttu-id="0453c-122">要素</span><span class="sxs-lookup"><span data-stu-id="0453c-122">Element</span></span>|<span data-ttu-id="0453c-123">説明</span><span class="sxs-lookup"><span data-stu-id="0453c-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0453c-124">\<ルーティング ></span><span class="sxs-lookup"><span data-stu-id="0453c-124">\<routing></span></span>](routing.md)|<span data-ttu-id="0453c-125">一連のルーティングフィルターを定義するための構成セクションを表します。これにより、受信メッセージ<xref:System.ServiceModel.Dispatcher.MessageFilter>を評価するときに使用する Windows Communication Foundation (WCF) の種類、およびターゲットエンドポイントを定義するルーティングテーブルを決定します。フィルターが一致したときにメッセージをに送信します。</span><span class="sxs-lookup"><span data-stu-id="0453c-125">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0453c-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="0453c-126">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection?displayProperty=nameWithType>
