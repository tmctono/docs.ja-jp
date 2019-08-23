---
title: <namespaceTable>
ms.date: 03/30/2017
ms.assetid: 64801766-01b7-4c65-9ce6-70ad5af67689
ms.openlocfilehash: 0316e983446644671ead2f8f843dc91b493b29c9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933165"
---
# <a name="namespacetable"></a><span data-ttu-id="449f6-101">\<namespaceTable ></span><span class="sxs-lookup"><span data-stu-id="449f6-101">\<namespaceTable></span></span>

<span data-ttu-id="449f6-102">名前空間とプレフィックスのマッピングを含む要素セットを定義する構成セクションを表します。これは、ルーティングの XPath フィルターで使用されます。</span><span class="sxs-lookup"><span data-stu-id="449f6-102">Represents a configuration section for defining a set of elements that contain namespace to prefix mappings that can then be used in XPath filters for routing.</span></span>

<span data-ttu-id="449f6-103">**\<system.serviceModel>**  </span><span class="sxs-lookup"><span data-stu-id="449f6-103">**\<system.serviceModel>** </span></span>  
<span data-ttu-id="449f6-104">&nbsp;&nbsp; **\<ルーティング >**  </span><span class="sxs-lookup"><span data-stu-id="449f6-104">&nbsp;&nbsp;**\<routing>** </span></span>  
<span data-ttu-id="449f6-105">&nbsp;&nbsp;&nbsp;&nbsp; **\<namespaceTable>**</span><span class="sxs-lookup"><span data-stu-id="449f6-105">&nbsp;&nbsp;&nbsp;&nbsp;**\<namespaceTable>**</span></span>
  
## <a name="syntax"></a><span data-ttu-id="449f6-106">構文</span><span class="sxs-lookup"><span data-stu-id="449f6-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <routing>
    <namespaceTable>
      <add namespace="String"
           prefix="String" />
    </namespaceTable>
  </routing>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="449f6-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="449f6-107">Attributes and elements</span></span>

<span data-ttu-id="449f6-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="449f6-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="449f6-109">属性</span><span class="sxs-lookup"><span data-stu-id="449f6-109">Attributes</span></span>

<span data-ttu-id="449f6-110">なし</span><span class="sxs-lookup"><span data-stu-id="449f6-110">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="449f6-111">子要素</span><span class="sxs-lookup"><span data-stu-id="449f6-111">Child elements</span></span>

|     | <span data-ttu-id="449f6-112">説明</span><span class="sxs-lookup"><span data-stu-id="449f6-112">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="449f6-113"> **\<フィルター >** </span><span class="sxs-lookup"><span data-stu-id="449f6-113">**\<filter>**</span></span>](filter.md) | <span data-ttu-id="449f6-114">XPath 式に使用される名前空間とプレフィックスのマッピングを定義します。</span><span class="sxs-lookup"><span data-stu-id="449f6-114">Defines a namespace prefix mapping used for XPath expressions.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="449f6-115">親要素</span><span class="sxs-lookup"><span data-stu-id="449f6-115">Parent elements</span></span>

|     | <span data-ttu-id="449f6-116">説明</span><span class="sxs-lookup"><span data-stu-id="449f6-116">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="449f6-117"> **\<ルーティング >** </span><span class="sxs-lookup"><span data-stu-id="449f6-117">**\<routing>**</span></span>](routing.md) | <span data-ttu-id="449f6-118">一連のルーティングフィルターを定義するための構成セクションを表します。これにより、受信メッセージ<xref:System.ServiceModel.Dispatcher.MessageFilter>を評価するときに使用する Windows Communication Foundation (WCF) の種類、およびターゲットエンドポイントを定義するルーティングテーブルを決定します。フィルターが一致したときにメッセージをに送信します。</span><span class="sxs-lookup"><span data-stu-id="449f6-118">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span> |

## <a name="see-also"></a><span data-ttu-id="449f6-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="449f6-119">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.NamespaceElementCollection?displayProperty=nameWithType>
