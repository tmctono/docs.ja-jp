---
title: <backupLists>
ms.date: 03/30/2017
ms.assetid: 593b3390-f65b-4684-ad40-0596b62f0954
ms.openlocfilehash: 5f2bb030d13389e15cb44f1ddff3b8168b4f2140
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850260"
---
# \<backupLists>
<span data-ttu-id="df29c-101">エラー処理に使用されるバックアップ サービス セットを定義する構成セクションを表します。</span><span class="sxs-lookup"><span data-stu-id="df29c-101">Represents a configuration section for defining a set of backup services used in error handling.</span></span> <span data-ttu-id="df29c-102">各子要素は、プライマリ エンドポイントに接続できないときにルーティング サービスが使用するエンドポイント セットを列挙したバックアップ リストです。</span><span class="sxs-lookup"><span data-stu-id="df29c-102">Each child element is a backup list that enumerates a set of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="df29c-103">リストの最初のエンドポイントがダウンしていると、ルーティング サービスは自動的にリスト内で次にあるエンドポイントにフェールオーバーします。</span><span class="sxs-lookup"><span data-stu-id="df29c-103">If the first endpoint in the list is down, the Routing Service will automatically fail-over to the next one in the list.</span></span>  <span data-ttu-id="df29c-104">これにより、クライアント アプリケーションに複雑なパターンの処理方法やサービスの配置場所を示すことなく、アプリケーションの信頼性を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="df29c-104">This gives you a quick way to add reliability to your application without having to teach your client application how to handle complex patterns or where all of your services are deployed.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<backupLists>**  
  
## <a name="syntax"></a><span data-ttu-id="df29c-105">構文</span><span class="sxs-lookup"><span data-stu-id="df29c-105">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="df29c-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="df29c-106">Attributes and Elements</span></span>  
 <span data-ttu-id="df29c-107">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="df29c-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="df29c-108">属性</span><span class="sxs-lookup"><span data-stu-id="df29c-108">Attributes</span></span>  
 <span data-ttu-id="df29c-109">なし。</span><span class="sxs-lookup"><span data-stu-id="df29c-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="df29c-110">子要素</span><span class="sxs-lookup"><span data-stu-id="df29c-110">Child Elements</span></span>  
  
|<span data-ttu-id="df29c-111">要素</span><span class="sxs-lookup"><span data-stu-id="df29c-111">Element</span></span>|<span data-ttu-id="df29c-112">説明</span><span class="sxs-lookup"><span data-stu-id="df29c-112">Description</span></span>|  
|-------------|-----------------|  
|[\<filter>](filter.md)|<span data-ttu-id="df29c-113">プライマリ エンドポイントに接続できないときにルーティング サービスが使用するエンドポイントのリストを格納します。</span><span class="sxs-lookup"><span data-stu-id="df29c-113">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="df29c-114">.</span><span class="sxs-lookup"><span data-stu-id="df29c-114">.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="df29c-115">親要素</span><span class="sxs-lookup"><span data-stu-id="df29c-115">Parent Elements</span></span>  
  
|<span data-ttu-id="df29c-116">要素</span><span class="sxs-lookup"><span data-stu-id="df29c-116">Element</span></span>|<span data-ttu-id="df29c-117">説明</span><span class="sxs-lookup"><span data-stu-id="df29c-117">Description</span></span>|  
|-------------|-----------------|  
|[\<routing>](routing.md)|<span data-ttu-id="df29c-118">一連のルーティングフィルターを定義するための構成セクションを表します。これにより、受信メッセージを評価するときに使用される Windows Communication Foundation (WCF) の種類、 <xref:System.ServiceModel.Dispatcher.MessageFilter> およびフィルターが一致したときにメッセージを送信するターゲットエンドポイントを定義するルーティングテーブルが決定されます。</span><span class="sxs-lookup"><span data-stu-id="df29c-118">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="df29c-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="df29c-119">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection?displayProperty=nameWithType>
