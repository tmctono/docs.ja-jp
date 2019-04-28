---
title: <namespaceTable>
ms.date: 03/30/2017
ms.assetid: 64801766-01b7-4c65-9ce6-70ad5af67689
ms.openlocfilehash: ee7a0c23adca883af279addf9d1f221bd4056d00
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772412"
---
# <a name="namespacetable"></a><span data-ttu-id="ba758-101">\<namespaceTable></span><span class="sxs-lookup"><span data-stu-id="ba758-101">\<namespaceTable></span></span>

<span data-ttu-id="ba758-102">名前空間とプレフィックスのマッピングを含む要素セットを定義する構成セクションを表します。これは、ルーティングの XPath フィルターで使用されます。</span><span class="sxs-lookup"><span data-stu-id="ba758-102">Represents a configuration section for defining a set of elements that contain namespace to prefix mappings that can then be used in XPath filters for routing.</span></span>

<span data-ttu-id="ba758-103">**\<system.serviceModel>** </span><span class="sxs-lookup"><span data-stu-id="ba758-103">**\<system.serviceModel>** </span></span>  
<span data-ttu-id="ba758-104">&nbsp;&nbsp;**\<ルーティング >** </span><span class="sxs-lookup"><span data-stu-id="ba758-104">&nbsp;&nbsp;**\<routing>** </span></span>  
<span data-ttu-id="ba758-105">&nbsp;&nbsp;&nbsp;&nbsp;**\<namespaceTable>**</span><span class="sxs-lookup"><span data-stu-id="ba758-105">&nbsp;&nbsp;&nbsp;&nbsp;**\<namespaceTable>**</span></span>
  
## <a name="syntax"></a><span data-ttu-id="ba758-106">構文</span><span class="sxs-lookup"><span data-stu-id="ba758-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ba758-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="ba758-107">Attributes and elements</span></span>

<span data-ttu-id="ba758-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="ba758-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="ba758-109">属性</span><span class="sxs-lookup"><span data-stu-id="ba758-109">Attributes</span></span>

<span data-ttu-id="ba758-110">なし</span><span class="sxs-lookup"><span data-stu-id="ba758-110">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="ba758-111">子要素</span><span class="sxs-lookup"><span data-stu-id="ba758-111">Child elements</span></span>

|     | <span data-ttu-id="ba758-112">説明</span><span class="sxs-lookup"><span data-stu-id="ba758-112">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="ba758-113">**\<フィルター >**</span><span class="sxs-lookup"><span data-stu-id="ba758-113">**\<filter>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md) | <span data-ttu-id="ba758-114">XPath 式に使用される名前空間とプレフィックスのマッピングを定義します。</span><span class="sxs-lookup"><span data-stu-id="ba758-114">Defines a namespace prefix mapping used for XPath expressions.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="ba758-115">親要素</span><span class="sxs-lookup"><span data-stu-id="ba758-115">Parent elements</span></span>

|     | <span data-ttu-id="ba758-116">説明</span><span class="sxs-lookup"><span data-stu-id="ba758-116">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="ba758-117">**\<ルーティング >**</span><span class="sxs-lookup"><span data-stu-id="ba758-117">**\<routing>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | <span data-ttu-id="ba758-118">Windows Communication Foundation (WCF) の種類を指定するルーティング フィルター セットを定義する構成セクションを表します<xref:System.ServiceModel.Dispatcher.MessageFilter>受信メッセージの評価とルーティング テーブルをするターゲット エンドポイントを定義するときに使用される。フィルターが一致したときにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="ba758-118">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span> |

## <a name="see-also"></a><span data-ttu-id="ba758-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="ba758-119">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.NamespaceElementCollection?displayProperty=nameWithType>
