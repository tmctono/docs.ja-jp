---
title: <workflowControlEndpoint>
ms.date: 03/30/2017
ms.assetid: 6c89e76c-643b-4b6a-9b25-628f753d7027
ms.openlocfilehash: 670c1573fe4378a18c19d0a58fe58241745725bd
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70854787"
---
# \<workflowControlEndpoint>
<span data-ttu-id="cae5b-101">この構成要素は、ワークフロー インスタンスの実行の制御 (作成、実行、保留、終了など) に使用する標準エンドポイントを定義します。</span><span class="sxs-lookup"><span data-stu-id="cae5b-101">This configuration element defines a standard endpoint for controlling the execution of workflow instances (create, run, suspend, terminate, etc).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowControlEndpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="cae5b-102">構文</span><span class="sxs-lookup"><span data-stu-id="cae5b-102">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <workflowControlEndpoint>
      <standardEndpoint name="String" />
    </workflowControlEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cae5b-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="cae5b-103">Attributes and Elements</span></span>  
 <span data-ttu-id="cae5b-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="cae5b-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cae5b-105">属性</span><span class="sxs-lookup"><span data-stu-id="cae5b-105">Attributes</span></span>  
  
|<span data-ttu-id="cae5b-106">属性</span><span class="sxs-lookup"><span data-stu-id="cae5b-106">Attribute</span></span>|<span data-ttu-id="cae5b-107">説明</span><span class="sxs-lookup"><span data-stu-id="cae5b-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cae5b-108">name</span><span class="sxs-lookup"><span data-stu-id="cae5b-108">name</span></span>|<span data-ttu-id="cae5b-109">標準エンドポイントの構成名を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="cae5b-109">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="cae5b-110">この名前は、サービス エンドポイントの `endpointConfiguration` 属性で使用され、標準エンドポイントと構成を関連付けます。</span><span class="sxs-lookup"><span data-stu-id="cae5b-110">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cae5b-111">子要素</span><span class="sxs-lookup"><span data-stu-id="cae5b-111">Child Elements</span></span>  
 <span data-ttu-id="cae5b-112">なし。</span><span class="sxs-lookup"><span data-stu-id="cae5b-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cae5b-113">親要素</span><span class="sxs-lookup"><span data-stu-id="cae5b-113">Parent Elements</span></span>  
  
|<span data-ttu-id="cae5b-114">要素</span><span class="sxs-lookup"><span data-stu-id="cae5b-114">Element</span></span>|<span data-ttu-id="cae5b-115">Description</span><span class="sxs-lookup"><span data-stu-id="cae5b-115">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="cae5b-116">1 つ以上のプロパティ (アドレス、バインディング、コントラクト) が固定されている、あらかじめ定義されたエンドポイントである標準エンドポイントのコレクション。</span><span class="sxs-lookup"><span data-stu-id="cae5b-116">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cae5b-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="cae5b-117">See also</span></span>

- <xref:System.ServiceModel.Activities.WorkflowControlEndpoint>
