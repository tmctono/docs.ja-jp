---
title: <routing>
ms.date: 03/30/2017
ms.assetid: a210c209-3940-4288-9a8e-39b1e62606bc
ms.openlocfilehash: cc7c1a64f9481a7ab41cf35241ade04bd690dae0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61786387"
---
# <a name="routing"></a><span data-ttu-id="3ae8d-101">\<ルーティング ></span><span class="sxs-lookup"><span data-stu-id="3ae8d-101">\<routing></span></span>

<span data-ttu-id="3ae8d-102">Windows Communication Foundation (WCF) の種類を指定するルーティング フィルター セットを定義する構成セクションを表します<xref:System.ServiceModel.Dispatcher.MessageFilter>受信メッセージの評価とルーティング テーブルをするターゲット エンドポイントを定義するときに使用される。フィルターが一致したときにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="3ae8d-102">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>

<span data-ttu-id="3ae8d-103">[**\<system.serviceModel>**](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="3ae8d-103">[**\<system.serviceModel>**](system-servicemodel.md) </span></span>  
<span data-ttu-id="3ae8d-104">&nbsp;&nbsp;**\<ルーティング >**</span><span class="sxs-lookup"><span data-stu-id="3ae8d-104">&nbsp;&nbsp;**\<routing>**</span></span>
  
## <a name="syntax"></a><span data-ttu-id="3ae8d-105">構文</span><span class="sxs-lookup"><span data-stu-id="3ae8d-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3ae8d-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="3ae8d-106">Attributes and elements</span></span>

<span data-ttu-id="3ae8d-107">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="3ae8d-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="3ae8d-108">属性</span><span class="sxs-lookup"><span data-stu-id="3ae8d-108">Attributes</span></span>

<span data-ttu-id="3ae8d-109">なし</span><span class="sxs-lookup"><span data-stu-id="3ae8d-109">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="3ae8d-110">子要素</span><span class="sxs-lookup"><span data-stu-id="3ae8d-110">Child elements</span></span>

|     | <span data-ttu-id="3ae8d-111">説明</span><span class="sxs-lookup"><span data-stu-id="3ae8d-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="3ae8d-112">**\<filters>**</span><span class="sxs-lookup"><span data-stu-id="3ae8d-112">**\<filters>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md) | <span data-ttu-id="3ae8d-113">受信メッセージを評価するときに使用する Windows Communication Foundation (WCF) の MessageFilter の種類を決定するルーティング フィルター セットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3ae8d-113">Contains a set of routing filters that determine the type of Windows Communication Foundation (WCF) MessageFilter will be used when evaluating incoming messages.</span></span> |
| [<span data-ttu-id="3ae8d-114">**\<filterTables>**</span><span class="sxs-lookup"><span data-stu-id="3ae8d-114">**\<filterTables>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filtertables.md) | <span data-ttu-id="3ae8d-115">ルーティング フィルターとターゲット エンドポイントとのマッピングを格納します。フィルターが一致したときにエンドポイントを指定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="3ae8d-115">Contains mappings between the routing filters and the target endpoints to specify which endpoint to use when the filter matches.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="3ae8d-116">親要素</span><span class="sxs-lookup"><span data-stu-id="3ae8d-116">Parent elements</span></span>

|     | <span data-ttu-id="3ae8d-117">説明</span><span class="sxs-lookup"><span data-stu-id="3ae8d-117">Description</span></span> |
| --- | ----------- |
| <span data-ttu-id="3ae8d-118">**\<system.ServiceModel>**</span><span class="sxs-lookup"><span data-stu-id="3ae8d-118">**\<system.ServiceModel>**</span></span> | <span data-ttu-id="3ae8d-119">すべての WCF 構成要素のルート要素です。</span><span class="sxs-lookup"><span data-stu-id="3ae8d-119">The root element of all WCF configuration elements.</span></span> |

## <a name="see-also"></a><span data-ttu-id="3ae8d-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="3ae8d-120">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
