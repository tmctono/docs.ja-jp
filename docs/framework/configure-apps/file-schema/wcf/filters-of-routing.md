---
title: <filters> の <routing>
ms.date: 03/30/2017
ms.assetid: 7993cf90-9afd-4c3c-9608-184d5da1105c
ms.openlocfilehash: ba60958ad33b46b40285f3f70001273bb3af3a63
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925611"
---
# <a name="filters-of-routing"></a><span data-ttu-id="59790-102">\<ルーティング > の\<> をフィルター処理します</span><span class="sxs-lookup"><span data-stu-id="59790-102">\<filters> of \<routing></span></span>

<span data-ttu-id="59790-103">受信メッセージを評価するときに使用する Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter>の種類を決定する一連のルーティングフィルターを定義するための構成セクションを表します。</span><span class="sxs-lookup"><span data-stu-id="59790-103">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages.</span></span>

<span data-ttu-id="59790-104">[ **\<system.serviceModel>** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="59790-104">[**\<system.serviceModel>**](system-servicemodel.md) </span></span>  
<span data-ttu-id="59790-105">&nbsp;&nbsp;[ **\<ルーティング >** ](routing.md) </span><span class="sxs-lookup"><span data-stu-id="59790-105">&nbsp;&nbsp;[**\<routing>**](routing.md) </span></span>  
<span data-ttu-id="59790-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<フィルター >**</span><span class="sxs-lookup"><span data-stu-id="59790-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<filters>**</span></span>
  
## <a name="syntax"></a><span data-ttu-id="59790-107">構文</span><span class="sxs-lookup"><span data-stu-id="59790-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <routing>
    <filters>
      <filter customType="String"
              filterData="String"
              filterType="Action/Address/AddressPrefix/And/Custom/Endpoint/MatchAll/XPath"
              name="String" />
    </filters>
  </routing>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="59790-108">属性と要素</span><span class="sxs-lookup"><span data-stu-id="59790-108">Attributes and elements</span></span>

<span data-ttu-id="59790-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="59790-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="59790-110">属性</span><span class="sxs-lookup"><span data-stu-id="59790-110">Attributes</span></span>

<span data-ttu-id="59790-111">なし</span><span class="sxs-lookup"><span data-stu-id="59790-111">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="59790-112">子要素</span><span class="sxs-lookup"><span data-stu-id="59790-112">Child elements</span></span>

|     | <span data-ttu-id="59790-113">説明</span><span class="sxs-lookup"><span data-stu-id="59790-113">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="59790-114"> **\<フィルター >** </span><span class="sxs-lookup"><span data-stu-id="59790-114">**\<filter>**</span></span>](filter.md) | <span data-ttu-id="59790-115">受信メッセージを評価するときに使用される Windows Communication Foundation (WCF<xref:System.ServiceModel.Dispatcher.MessageFilter> ) の種類を決定するルーティングフィルターを格納します。</span><span class="sxs-lookup"><span data-stu-id="59790-115">Contains a routing filter that determines the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> will be used when evaluating incoming messages.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="59790-116">親要素</span><span class="sxs-lookup"><span data-stu-id="59790-116">Parent elements</span></span>

|     | <span data-ttu-id="59790-117">説明</span><span class="sxs-lookup"><span data-stu-id="59790-117">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="59790-118"> **\<ルーティング >** </span><span class="sxs-lookup"><span data-stu-id="59790-118">**\<routing>**</span></span>](routing.md) | <span data-ttu-id="59790-119">一連のルーティングフィルターを定義するための構成セクションを表します。これにより、受信メッセージ<xref:System.ServiceModel.Dispatcher.MessageFilter>を評価するときに使用する Windows Communication Foundation (WCF) の種類、およびターゲットエンドポイントを定義するルーティングテーブルを決定します。フィルターが一致したときにメッセージをに送信します。</span><span class="sxs-lookup"><span data-stu-id="59790-119">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span> |

## <a name="see-also"></a><span data-ttu-id="59790-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="59790-120">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>
