---
title: <namespaceTable>
ms.date: 03/30/2017
ms.assetid: 64801766-01b7-4c65-9ce6-70ad5af67689
ms.openlocfilehash: aefe7beec7335d80341e670961800907c2bd0200
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855101"
---
# <a name="namespacetable"></a><span data-ttu-id="87966-101">\<namespaceTable ></span><span class="sxs-lookup"><span data-stu-id="87966-101">\<namespaceTable></span></span>

<span data-ttu-id="87966-102">名前空間とプレフィックスのマッピングを含む要素セットを定義する構成セクションを表します。これは、ルーティングの XPath フィルターで使用されます。</span><span class="sxs-lookup"><span data-stu-id="87966-102">Represents a configuration section for defining a set of elements that contain namespace to prefix mappings that can then be used in XPath filters for routing.</span></span>

<span data-ttu-id="87966-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="87966-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="87966-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="87966-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="87966-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<ルーティング >** ](routing.md)</span><span class="sxs-lookup"><span data-stu-id="87966-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)</span></span>\
<span data-ttu-id="87966-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<namespaceTable >**</span><span class="sxs-lookup"><span data-stu-id="87966-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<namespaceTable>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87966-107">構文</span><span class="sxs-lookup"><span data-stu-id="87966-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="87966-108">属性と要素</span><span class="sxs-lookup"><span data-stu-id="87966-108">Attributes and elements</span></span>

<span data-ttu-id="87966-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="87966-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="87966-110">属性</span><span class="sxs-lookup"><span data-stu-id="87966-110">Attributes</span></span>

<span data-ttu-id="87966-111">なし</span><span class="sxs-lookup"><span data-stu-id="87966-111">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="87966-112">子要素</span><span class="sxs-lookup"><span data-stu-id="87966-112">Child elements</span></span>

|     | <span data-ttu-id="87966-113">説明</span><span class="sxs-lookup"><span data-stu-id="87966-113">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="87966-114"> **\<フィルター >** </span><span class="sxs-lookup"><span data-stu-id="87966-114">**\<filter>**</span></span>](filter.md) | <span data-ttu-id="87966-115">XPath 式に使用される名前空間とプレフィックスのマッピングを定義します。</span><span class="sxs-lookup"><span data-stu-id="87966-115">Defines a namespace prefix mapping used for XPath expressions.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="87966-116">親要素</span><span class="sxs-lookup"><span data-stu-id="87966-116">Parent elements</span></span>

|     | <span data-ttu-id="87966-117">説明</span><span class="sxs-lookup"><span data-stu-id="87966-117">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="87966-118"> **\<ルーティング >** </span><span class="sxs-lookup"><span data-stu-id="87966-118">**\<routing>**</span></span>](routing.md) | <span data-ttu-id="87966-119">一連のルーティングフィルターを定義するための構成セクションを表します。これにより、受信メッセージ<xref:System.ServiceModel.Dispatcher.MessageFilter>を評価するときに使用する Windows Communication Foundation (WCF) の種類、およびターゲットエンドポイントを定義するルーティングテーブルを決定します。フィルターが一致したときにメッセージをに送信します。</span><span class="sxs-lookup"><span data-stu-id="87966-119">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span> |

## <a name="see-also"></a><span data-ttu-id="87966-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="87966-120">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.NamespaceElementCollection?displayProperty=nameWithType>
