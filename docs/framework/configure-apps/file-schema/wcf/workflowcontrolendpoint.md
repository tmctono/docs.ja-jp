---
title: <workflowControlEndpoint>
ms.date: 03/30/2017
ms.assetid: 6c89e76c-643b-4b6a-9b25-628f753d7027
ms.openlocfilehash: 572ff7e119828897860944a430e5f51f5d1c3cad
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91194844"
---
# \<workflowControlEndpoint>

<span data-ttu-id="01949-101">この構成要素は、ワークフロー インスタンスの実行の制御 (作成、実行、保留、終了など) に使用する標準エンドポイントを定義します。</span><span class="sxs-lookup"><span data-stu-id="01949-101">This configuration element defines a standard endpoint for controlling the execution of workflow instances (create, run, suspend, terminate, etc).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowControlEndpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="01949-102">構文</span><span class="sxs-lookup"><span data-stu-id="01949-102">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <workflowControlEndpoint>
      <standardEndpoint name="String" />
    </workflowControlEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="01949-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="01949-103">Attributes and Elements</span></span>  

 <span data-ttu-id="01949-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="01949-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="01949-105">属性</span><span class="sxs-lookup"><span data-stu-id="01949-105">Attributes</span></span>  
  
|<span data-ttu-id="01949-106">属性</span><span class="sxs-lookup"><span data-stu-id="01949-106">Attribute</span></span>|<span data-ttu-id="01949-107">説明</span><span class="sxs-lookup"><span data-stu-id="01949-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="01949-108">name</span><span class="sxs-lookup"><span data-stu-id="01949-108">name</span></span>|<span data-ttu-id="01949-109">標準エンドポイントの構成名を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="01949-109">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="01949-110">この名前は、サービス エンドポイントの `endpointConfiguration` 属性で使用され、標準エンドポイントと構成を関連付けます。</span><span class="sxs-lookup"><span data-stu-id="01949-110">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="01949-111">子要素</span><span class="sxs-lookup"><span data-stu-id="01949-111">Child Elements</span></span>  

 <span data-ttu-id="01949-112">なし。</span><span class="sxs-lookup"><span data-stu-id="01949-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="01949-113">親要素</span><span class="sxs-lookup"><span data-stu-id="01949-113">Parent Elements</span></span>  
  
|<span data-ttu-id="01949-114">要素</span><span class="sxs-lookup"><span data-stu-id="01949-114">Element</span></span>|<span data-ttu-id="01949-115">説明</span><span class="sxs-lookup"><span data-stu-id="01949-115">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="01949-116">1 つ以上のプロパティ (アドレス、バインディング、コントラクト) が固定されている、あらかじめ定義されたエンドポイントである標準エンドポイントのコレクション。</span><span class="sxs-lookup"><span data-stu-id="01949-116">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="01949-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="01949-117">See also</span></span>

- <xref:System.ServiceModel.Activities.WorkflowControlEndpoint>
