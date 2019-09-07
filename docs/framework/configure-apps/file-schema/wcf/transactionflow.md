---
title: <transactionFlow>
ms.date: 03/30/2017
ms.assetid: 8c7b4c5b-ace3-4fe3-89ff-7b13c9aacd13
ms.openlocfilehash: 8247dd62f4dda853487fe52f00f8f548b627c075
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399393"
---
# <a name="transactionflow"></a><span data-ttu-id="b1a94-101">\<transactionFlow ></span><span class="sxs-lookup"><span data-stu-id="b1a94-101">\<transactionFlow></span></span>
<span data-ttu-id="b1a94-102">カスタム バインドのトランザクション フロー サポートを指定します。</span><span class="sxs-lookup"><span data-stu-id="b1a94-102">Specifies transaction flow support for the custom binding.</span></span>  
  
<span data-ttu-id="b1a94-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b1a94-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b1a94-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="b1a94-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="b1a94-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<バインド >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="b1a94-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="b1a94-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="b1a94-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="b1a94-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<バインド >** </span><span class="sxs-lookup"><span data-stu-id="b1a94-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="b1a94-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<transactionFlow >**</span><span class="sxs-lookup"><span data-stu-id="b1a94-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transactionFlow>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1a94-109">構文</span><span class="sxs-lookup"><span data-stu-id="b1a94-109">Syntax</span></span>  
  
```xml  
<transactionFlow transactionProtocol="OleTransactions/WSAtomicTransactionOctober2004" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b1a94-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="b1a94-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b1a94-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="b1a94-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b1a94-112">属性</span><span class="sxs-lookup"><span data-stu-id="b1a94-112">Attributes</span></span>  
  
|<span data-ttu-id="b1a94-113">属性</span><span class="sxs-lookup"><span data-stu-id="b1a94-113">Attribute</span></span>|<span data-ttu-id="b1a94-114">説明</span><span class="sxs-lookup"><span data-stu-id="b1a94-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b1a94-115">transactionProtocol</span><span class="sxs-lookup"><span data-stu-id="b1a94-115">transactionProtocol</span></span>|<span data-ttu-id="b1a94-116">使用されるトランザクション プロトコルを指定します。</span><span class="sxs-lookup"><span data-stu-id="b1a94-116">Specifies the transaction protocol to be used.</span></span> <span data-ttu-id="b1a94-117">以下の値が有効です。</span><span class="sxs-lookup"><span data-stu-id="b1a94-117">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="b1a94-118">-OleTransactions</span><span class="sxs-lookup"><span data-stu-id="b1a94-118">-   OleTransactions</span></span><br /><span data-ttu-id="b1a94-119">-WSAtomicTransactionOctober2004</span><span class="sxs-lookup"><span data-stu-id="b1a94-119">-   WSAtomicTransactionOctober2004</span></span><br /><br /> <span data-ttu-id="b1a94-120">既定値は OleTransactions です。</span><span class="sxs-lookup"><span data-stu-id="b1a94-120">The default is OleTransactions.</span></span><br /><br /> <span data-ttu-id="b1a94-121">この属性は <xref:System.ServiceModel.TransactionProtocol> 型です。</span><span class="sxs-lookup"><span data-stu-id="b1a94-121">This attribute is of type <xref:System.ServiceModel.TransactionProtocol>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b1a94-122">子要素</span><span class="sxs-lookup"><span data-stu-id="b1a94-122">Child Elements</span></span>  
 <span data-ttu-id="b1a94-123">なし。</span><span class="sxs-lookup"><span data-stu-id="b1a94-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b1a94-124">親要素</span><span class="sxs-lookup"><span data-stu-id="b1a94-124">Parent Elements</span></span>  
  
|<span data-ttu-id="b1a94-125">要素</span><span class="sxs-lookup"><span data-stu-id="b1a94-125">Element</span></span>|<span data-ttu-id="b1a94-126">説明</span><span class="sxs-lookup"><span data-stu-id="b1a94-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b1a94-127">\<binding></span><span class="sxs-lookup"><span data-stu-id="b1a94-127">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="b1a94-128">カスタム バインドのすべてのバインド機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="b1a94-128">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b1a94-129">Remarks</span><span class="sxs-lookup"><span data-stu-id="b1a94-129">Remarks</span></span>  
 <span data-ttu-id="b1a94-130">この要素により、受信トランザクションの目的のプロトコル形式を指定できるだけでなく、エンドポイントのバインディング設定で受信トランザクション フローを有効または無効にできます。</span><span class="sxs-lookup"><span data-stu-id="b1a94-130">This element allows you to enable or disable incoming transaction flow in an endpoint’s binding settings, as well as to specify the desired protocol format for incoming transactions.</span></span> <span data-ttu-id="b1a94-131">この構成要素の使用方法の詳細については、「 [ServiceModel トランザクション構成](../../../wcf/feature-details/servicemodel-transaction-configuration.md)」および「[トランザクションフローの有効化](../../../wcf/feature-details/enabling-transaction-flow.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1a94-131">For more information on using this configuration element, see [ServiceModel Transaction Configuration](../../../wcf/feature-details/servicemodel-transaction-configuration.md) and [Enabling Transaction Flow](../../../wcf/feature-details/enabling-transaction-flow.md).</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="b1a94-132">`OleTransactions` プロトコルを使用してエンドポイント間でトランザクションをフローさせるとき、フロー先のエンドポイントが `OleTransactions` 以外のプロトコルを使用して再びフローを試みると、トランザクション タイムアウトが失われる場合があります。</span><span class="sxs-lookup"><span data-stu-id="b1a94-132">When using the `OleTransactions` protocol to flow transactions from endpoint to endpoint, the transaction timeout can be lost if the destination endpoint attempts to flow again using any protocol other than `OleTransactions`.</span></span> <span data-ttu-id="b1a94-133">その結果、OleTransactions ホップより後のすべてのダウンレベル ノードが、予想より遅くタイムアウトする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b1a94-133">This can cause all down-level nodes after the OleTransactions hop to timeout later than expected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1a94-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="b1a94-134">See also</span></span>

- <xref:System.ServiceModel.Configuration.TransactionFlowElement>
- <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="b1a94-135">ServiceModel トランザクションの構成</span><span class="sxs-lookup"><span data-stu-id="b1a94-135">ServiceModel Transaction Configuration</span></span>](../../../wcf/feature-details/servicemodel-transaction-configuration.md)
- [<span data-ttu-id="b1a94-136">トランザクション フローの有効化</span><span class="sxs-lookup"><span data-stu-id="b1a94-136">Enabling Transaction Flow</span></span>](../../../wcf/feature-details/enabling-transaction-flow.md)
- [<span data-ttu-id="b1a94-137">バインディング</span><span class="sxs-lookup"><span data-stu-id="b1a94-137">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="b1a94-138">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="b1a94-138">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="b1a94-139">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="b1a94-139">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="b1a94-140">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="b1a94-140">\<customBinding></span></span>](custombinding.md)
