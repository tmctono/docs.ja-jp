---
title: <filters> の <routing>
ms.date: 03/30/2017
ms.assetid: 7993cf90-9afd-4c3c-9608-184d5da1105c
ms.openlocfilehash: c9bc3a2c379e14d8cf687676a3ec40702d150e1e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855235"
---
# <a name="filters-of-routing"></a><span data-ttu-id="cc31b-102">\<filters> の \<routing></span><span class="sxs-lookup"><span data-stu-id="cc31b-102">\<filters> of \<routing></span></span>

<span data-ttu-id="cc31b-103"><xref:System.ServiceModel.Dispatcher.MessageFilter>受信メッセージを評価するときに使用する Windows Communication Foundation (WCF) の種類を決定する一連のルーティングフィルターを定義するための構成セクションを表します。</span><span class="sxs-lookup"><span data-stu-id="cc31b-103">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages.</span></span>

[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<filters>**  
  
## <a name="syntax"></a><span data-ttu-id="cc31b-104">構文</span><span class="sxs-lookup"><span data-stu-id="cc31b-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cc31b-105">属性と要素</span><span class="sxs-lookup"><span data-stu-id="cc31b-105">Attributes and elements</span></span>

<span data-ttu-id="cc31b-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="cc31b-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="cc31b-107">属性</span><span class="sxs-lookup"><span data-stu-id="cc31b-107">Attributes</span></span>

<span data-ttu-id="cc31b-108">なし</span><span class="sxs-lookup"><span data-stu-id="cc31b-108">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="cc31b-109">子要素</span><span class="sxs-lookup"><span data-stu-id="cc31b-109">Child elements</span></span>

|     | <span data-ttu-id="cc31b-110">Description</span><span class="sxs-lookup"><span data-stu-id="cc31b-110">Description</span></span> |
| --- | ----------- |
| [**\<filter>**](filter.md) | <span data-ttu-id="cc31b-111"><xref:System.ServiceModel.Dispatcher.MessageFilter>受信メッセージを評価するときに使用される Windows Communication Foundation (WCF) の種類を決定するルーティングフィルターを格納します。</span><span class="sxs-lookup"><span data-stu-id="cc31b-111">Contains a routing filter that determines the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> will be used when evaluating incoming messages.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="cc31b-112">親要素</span><span class="sxs-lookup"><span data-stu-id="cc31b-112">Parent elements</span></span>

|     | <span data-ttu-id="cc31b-113">Description</span><span class="sxs-lookup"><span data-stu-id="cc31b-113">Description</span></span> |
| --- | ----------- |
| [**\<routing>**](routing.md) | <span data-ttu-id="cc31b-114">一連のルーティングフィルターを定義するための構成セクションを表します。これにより、受信メッセージを評価するときに使用される Windows Communication Foundation (WCF) の種類、 <xref:System.ServiceModel.Dispatcher.MessageFilter> およびフィルターが一致したときにメッセージを送信するターゲットエンドポイントを定義するルーティングテーブルが決定されます。</span><span class="sxs-lookup"><span data-stu-id="cc31b-114">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span> |

## <a name="see-also"></a><span data-ttu-id="cc31b-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="cc31b-115">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>
