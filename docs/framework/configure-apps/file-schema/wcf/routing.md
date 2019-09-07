---
title: <routing>
ms.date: 03/30/2017
ms.assetid: a210c209-3940-4288-9a8e-39b1e62606bc
ms.openlocfilehash: fcf2d4eec93fd7127c6f800e1c739ad1fac49203
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399973"
---
# <a name="routing"></a><span data-ttu-id="593ad-101">\<ルーティング ></span><span class="sxs-lookup"><span data-stu-id="593ad-101">\<routing></span></span>

<span data-ttu-id="593ad-102">一連のルーティングフィルターを定義するための構成セクションを表します。これにより、受信メッセージ<xref:System.ServiceModel.Dispatcher.MessageFilter>を評価するときに使用する Windows Communication Foundation (WCF) の種類、およびターゲットエンドポイントを定義するルーティングテーブルを決定します。フィルターが一致したときにメッセージをに送信します。</span><span class="sxs-lookup"><span data-stu-id="593ad-102">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>

<span data-ttu-id="593ad-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="593ad-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="593ad-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="593ad-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="593ad-105">&nbsp;&nbsp;&nbsp;&nbsp; **\<ルーティング >**</span><span class="sxs-lookup"><span data-stu-id="593ad-105">&nbsp;&nbsp;&nbsp;&nbsp;**\<routing>**</span></span>
  
## <a name="syntax"></a><span data-ttu-id="593ad-106">構文</span><span class="sxs-lookup"><span data-stu-id="593ad-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="593ad-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="593ad-107">Attributes and elements</span></span>

<span data-ttu-id="593ad-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="593ad-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="593ad-109">属性</span><span class="sxs-lookup"><span data-stu-id="593ad-109">Attributes</span></span>

<span data-ttu-id="593ad-110">なし</span><span class="sxs-lookup"><span data-stu-id="593ad-110">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="593ad-111">子要素</span><span class="sxs-lookup"><span data-stu-id="593ad-111">Child elements</span></span>

|     | <span data-ttu-id="593ad-112">説明</span><span class="sxs-lookup"><span data-stu-id="593ad-112">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="593ad-113"> **\<フィルター >** </span><span class="sxs-lookup"><span data-stu-id="593ad-113">**\<filters>**</span></span>](filters-of-routing.md) | <span data-ttu-id="593ad-114">受信メッセージを評価するときに使用される Windows Communication Foundation (WCF) MessageFilter の種類を決定するルーティングフィルターのセットを格納します。</span><span class="sxs-lookup"><span data-stu-id="593ad-114">Contains a set of routing filters that determine the type of Windows Communication Foundation (WCF) MessageFilter will be used when evaluating incoming messages.</span></span> |
| [<span data-ttu-id="593ad-115"> **\<filterTables >** </span><span class="sxs-lookup"><span data-stu-id="593ad-115">**\<filterTables>**</span></span>](filtertables.md) | <span data-ttu-id="593ad-116">ルーティング フィルターとターゲット エンドポイントとのマッピングを格納します。フィルターが一致したときにエンドポイントを指定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="593ad-116">Contains mappings between the routing filters and the target endpoints to specify which endpoint to use when the filter matches.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="593ad-117">親要素</span><span class="sxs-lookup"><span data-stu-id="593ad-117">Parent elements</span></span>

|     | <span data-ttu-id="593ad-118">説明</span><span class="sxs-lookup"><span data-stu-id="593ad-118">Description</span></span> |
| --- | ----------- |
| <span data-ttu-id="593ad-119">**\<system.ServiceModel>**</span><span class="sxs-lookup"><span data-stu-id="593ad-119">**\<system.ServiceModel>**</span></span> | <span data-ttu-id="593ad-120">すべての WCF 構成要素のルート要素です。</span><span class="sxs-lookup"><span data-stu-id="593ad-120">The root element of all WCF configuration elements.</span></span> |

## <a name="see-also"></a><span data-ttu-id="593ad-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="593ad-121">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
