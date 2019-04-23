---
title: <workflowControlEndpoint>
ms.date: 03/30/2017
ms.assetid: 6c89e76c-643b-4b6a-9b25-628f753d7027
ms.openlocfilehash: a9c16d1036a8177120cd152d4ac211ad084d588e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59150385"
---
# <a name="workflowcontrolendpoint"></a><span data-ttu-id="61eec-101">\<workflowControlEndpoint></span><span class="sxs-lookup"><span data-stu-id="61eec-101">\<workflowControlEndpoint></span></span>
<span data-ttu-id="61eec-102">この構成要素は、ワークフロー インスタンスの実行の制御 (作成、実行、保留、終了など) に使用する標準エンドポイントを定義します。</span><span class="sxs-lookup"><span data-stu-id="61eec-102">This configuration element defines a standard endpoint for controlling the execution of workflow instances (create, run, suspend, terminate, etc).</span></span>  
  
<span data-ttu-id="61eec-103">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="61eec-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="61eec-104">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="61eec-104">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61eec-105">構文</span><span class="sxs-lookup"><span data-stu-id="61eec-105">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <workflowControlEndpoint>
      <standardEndpoint name="String" />
    </workflowControlEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="61eec-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="61eec-106">Attributes and Elements</span></span>  
 <span data-ttu-id="61eec-107">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="61eec-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="61eec-108">属性</span><span class="sxs-lookup"><span data-stu-id="61eec-108">Attributes</span></span>  
  
|<span data-ttu-id="61eec-109">属性</span><span class="sxs-lookup"><span data-stu-id="61eec-109">Attribute</span></span>|<span data-ttu-id="61eec-110">説明</span><span class="sxs-lookup"><span data-stu-id="61eec-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="61eec-111">name</span><span class="sxs-lookup"><span data-stu-id="61eec-111">name</span></span>|<span data-ttu-id="61eec-112">標準エンドポイントの構成名を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="61eec-112">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="61eec-113">この名前は、サービス エンドポイントの `endpointConfiguration` 属性で使用され、標準エンドポイントと構成を関連付けます。</span><span class="sxs-lookup"><span data-stu-id="61eec-113">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="61eec-114">子要素</span><span class="sxs-lookup"><span data-stu-id="61eec-114">Child Elements</span></span>  
 <span data-ttu-id="61eec-115">なし。</span><span class="sxs-lookup"><span data-stu-id="61eec-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="61eec-116">親要素</span><span class="sxs-lookup"><span data-stu-id="61eec-116">Parent Elements</span></span>  
  
|<span data-ttu-id="61eec-117">要素</span><span class="sxs-lookup"><span data-stu-id="61eec-117">Element</span></span>|<span data-ttu-id="61eec-118">説明</span><span class="sxs-lookup"><span data-stu-id="61eec-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="61eec-119">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="61eec-119">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="61eec-120">1 つ以上のプロパティ (アドレス、バインディング、コントラクト) が固定されている、あらかじめ定義されたエンドポイントである標準エンドポイントのコレクション。</span><span class="sxs-lookup"><span data-stu-id="61eec-120">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="61eec-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="61eec-121">See also</span></span>

- <xref:System.ServiceModel.Activities.WorkflowControlEndpoint>
