---
title: <filters> の <routing>
ms.date: 03/30/2017
ms.assetid: 7993cf90-9afd-4c3c-9608-184d5da1105c
ms.openlocfilehash: c9bc3a2c379e14d8cf687676a3ec40702d150e1e
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855235"
---
# <a name="filters-of-routing"></a><span data-ttu-id="e9b99-102">\<ルーティング > の\<> をフィルター処理します</span><span class="sxs-lookup"><span data-stu-id="e9b99-102">\<filters> of \<routing></span></span>

<span data-ttu-id="e9b99-103">受信メッセージを評価するときに使用する Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter>の種類を決定する一連のルーティングフィルターを定義するための構成セクションを表します。</span><span class="sxs-lookup"><span data-stu-id="e9b99-103">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages.</span></span>

<span data-ttu-id="e9b99-104">[ **\<system.serviceModel>** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="e9b99-104">[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="e9b99-105">&nbsp;&nbsp;[ **\<ルーティング >** ](routing.md)</span><span class="sxs-lookup"><span data-stu-id="e9b99-105">&nbsp;&nbsp;[**\<routing>**](routing.md)</span></span>\
<span data-ttu-id="e9b99-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<フィルター >**</span><span class="sxs-lookup"><span data-stu-id="e9b99-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<filters>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9b99-107">構文</span><span class="sxs-lookup"><span data-stu-id="e9b99-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e9b99-108">属性と要素</span><span class="sxs-lookup"><span data-stu-id="e9b99-108">Attributes and elements</span></span>

<span data-ttu-id="e9b99-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="e9b99-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="e9b99-110">属性</span><span class="sxs-lookup"><span data-stu-id="e9b99-110">Attributes</span></span>

<span data-ttu-id="e9b99-111">なし</span><span class="sxs-lookup"><span data-stu-id="e9b99-111">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="e9b99-112">子要素</span><span class="sxs-lookup"><span data-stu-id="e9b99-112">Child elements</span></span>

|     | <span data-ttu-id="e9b99-113">説明</span><span class="sxs-lookup"><span data-stu-id="e9b99-113">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="e9b99-114"> **\<フィルター >** </span><span class="sxs-lookup"><span data-stu-id="e9b99-114">**\<filter>**</span></span>](filter.md) | <span data-ttu-id="e9b99-115">受信メッセージを評価するときに使用される Windows Communication Foundation (WCF<xref:System.ServiceModel.Dispatcher.MessageFilter> ) の種類を決定するルーティングフィルターを格納します。</span><span class="sxs-lookup"><span data-stu-id="e9b99-115">Contains a routing filter that determines the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> will be used when evaluating incoming messages.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="e9b99-116">親要素</span><span class="sxs-lookup"><span data-stu-id="e9b99-116">Parent elements</span></span>

|     | <span data-ttu-id="e9b99-117">説明</span><span class="sxs-lookup"><span data-stu-id="e9b99-117">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="e9b99-118"> **\<ルーティング >** </span><span class="sxs-lookup"><span data-stu-id="e9b99-118">**\<routing>**</span></span>](routing.md) | <span data-ttu-id="e9b99-119">一連のルーティングフィルターを定義するための構成セクションを表します。これにより、受信メッセージ<xref:System.ServiceModel.Dispatcher.MessageFilter>を評価するときに使用する Windows Communication Foundation (WCF) の種類、およびターゲットエンドポイントを定義するルーティングテーブルを決定します。フィルターが一致したときにメッセージをに送信します。</span><span class="sxs-lookup"><span data-stu-id="e9b99-119">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span> |

## <a name="see-also"></a><span data-ttu-id="e9b99-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="e9b99-120">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>
