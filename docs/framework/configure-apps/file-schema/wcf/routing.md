---
title: <routing>
ms.date: 03/30/2017
ms.assetid: a210c209-3940-4288-9a8e-39b1e62606bc
ms.openlocfilehash: 3c7e9cb1284ab55c8dd199d9fb47a223698814f0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69934124"
---
# <a name="routing"></a><span data-ttu-id="7b554-101">\<ルーティング ></span><span class="sxs-lookup"><span data-stu-id="7b554-101">\<routing></span></span>

<span data-ttu-id="7b554-102">一連のルーティングフィルターを定義するための構成セクションを表します。これにより、受信メッセージ<xref:System.ServiceModel.Dispatcher.MessageFilter>を評価するときに使用する Windows Communication Foundation (WCF) の種類、およびターゲットエンドポイントを定義するルーティングテーブルを決定します。フィルターが一致したときにメッセージをに送信します。</span><span class="sxs-lookup"><span data-stu-id="7b554-102">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>

<span data-ttu-id="7b554-103">[ **\<system.serviceModel>** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="7b554-103">[**\<system.serviceModel>**](system-servicemodel.md) </span></span>  
<span data-ttu-id="7b554-104">&nbsp;&nbsp; **\<ルーティング >**</span><span class="sxs-lookup"><span data-stu-id="7b554-104">&nbsp;&nbsp;**\<routing>**</span></span>
  
## <a name="syntax"></a><span data-ttu-id="7b554-105">構文</span><span class="sxs-lookup"><span data-stu-id="7b554-105">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <routing>
    <filters>
      <filter customType="String"
              filterData="String"
              filterType="Action/Address/AddressPrefix/And/Custom/Endpoint/MatchAll/XPath"
              name="String" />
    </filters>
    <routingTables>
      <table name="String">
        <entries>
          <add endpoint="String"
               filterName="String"
               priority="Integer" />
        </entries>
      </table>
    </routingTables>
  </routing>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7b554-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="7b554-106">Attributes and elements</span></span>

<span data-ttu-id="7b554-107">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="7b554-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="7b554-108">属性</span><span class="sxs-lookup"><span data-stu-id="7b554-108">Attributes</span></span>

<span data-ttu-id="7b554-109">なし</span><span class="sxs-lookup"><span data-stu-id="7b554-109">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="7b554-110">子要素</span><span class="sxs-lookup"><span data-stu-id="7b554-110">Child elements</span></span>

|     | <span data-ttu-id="7b554-111">説明</span><span class="sxs-lookup"><span data-stu-id="7b554-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="7b554-112"> **\<フィルター >** </span><span class="sxs-lookup"><span data-stu-id="7b554-112">**\<filters>**</span></span>](filters-of-routing.md) | <span data-ttu-id="7b554-113">受信メッセージを評価するときに使用される Windows Communication Foundation (WCF) MessageFilter の種類を決定するルーティングフィルターのセットを格納します。</span><span class="sxs-lookup"><span data-stu-id="7b554-113">Contains a set of routing filters that determine the type of Windows Communication Foundation (WCF) MessageFilter will be used when evaluating incoming messages.</span></span> |
| [<span data-ttu-id="7b554-114"> **\<filterTables >** </span><span class="sxs-lookup"><span data-stu-id="7b554-114">**\<filterTables>**</span></span>](filtertables.md) | <span data-ttu-id="7b554-115">ルーティング フィルターとターゲット エンドポイントとのマッピングを格納します。フィルターが一致したときにエンドポイントを指定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="7b554-115">Contains mappings between the routing filters and the target endpoints to specify which endpoint to use when the filter matches.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="7b554-116">親要素</span><span class="sxs-lookup"><span data-stu-id="7b554-116">Parent elements</span></span>

|     | <span data-ttu-id="7b554-117">説明</span><span class="sxs-lookup"><span data-stu-id="7b554-117">Description</span></span> |
| --- | ----------- |
| <span data-ttu-id="7b554-118">**\<system.ServiceModel>**</span><span class="sxs-lookup"><span data-stu-id="7b554-118">**\<system.ServiceModel>**</span></span> | <span data-ttu-id="7b554-119">すべての WCF 構成要素のルート要素です。</span><span class="sxs-lookup"><span data-stu-id="7b554-119">The root element of all WCF configuration elements.</span></span> |

## <a name="see-also"></a><span data-ttu-id="7b554-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="7b554-120">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
