---
title: <workflowControlEndpoint>
ms.date: 03/30/2017
ms.assetid: 6c89e76c-643b-4b6a-9b25-628f753d7027
ms.openlocfilehash: a9c16d1036a8177120cd152d4ac211ad084d588e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61769643"
---
# <a name="workflowcontrolendpoint"></a><span data-ttu-id="8dbe6-101">\<workflowControlEndpoint></span><span class="sxs-lookup"><span data-stu-id="8dbe6-101">\<workflowControlEndpoint></span></span>
<span data-ttu-id="8dbe6-102">この構成要素は、ワークフロー インスタンスの実行の制御 (作成、実行、保留、終了など) に使用する標準エンドポイントを定義します。</span><span class="sxs-lookup"><span data-stu-id="8dbe6-102">This configuration element defines a standard endpoint for controlling the execution of workflow instances (create, run, suspend, terminate, etc).</span></span>  
  
<span data-ttu-id="8dbe6-103">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="8dbe6-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="8dbe6-104">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="8dbe6-104">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8dbe6-105">構文</span><span class="sxs-lookup"><span data-stu-id="8dbe6-105">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <workflowControlEndpoint>
      <standardEndpoint name="String" />
    </workflowControlEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8dbe6-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="8dbe6-106">Attributes and Elements</span></span>  
 <span data-ttu-id="8dbe6-107">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="8dbe6-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8dbe6-108">属性</span><span class="sxs-lookup"><span data-stu-id="8dbe6-108">Attributes</span></span>  
  
|<span data-ttu-id="8dbe6-109">属性</span><span class="sxs-lookup"><span data-stu-id="8dbe6-109">Attribute</span></span>|<span data-ttu-id="8dbe6-110">説明</span><span class="sxs-lookup"><span data-stu-id="8dbe6-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8dbe6-111">name</span><span class="sxs-lookup"><span data-stu-id="8dbe6-111">name</span></span>|<span data-ttu-id="8dbe6-112">標準エンドポイントの構成名を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="8dbe6-112">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="8dbe6-113">この名前は、サービス エンドポイントの `endpointConfiguration` 属性で使用され、標準エンドポイントと構成を関連付けます。</span><span class="sxs-lookup"><span data-stu-id="8dbe6-113">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8dbe6-114">子要素</span><span class="sxs-lookup"><span data-stu-id="8dbe6-114">Child Elements</span></span>  
 <span data-ttu-id="8dbe6-115">なし。</span><span class="sxs-lookup"><span data-stu-id="8dbe6-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8dbe6-116">親要素</span><span class="sxs-lookup"><span data-stu-id="8dbe6-116">Parent Elements</span></span>  
  
|<span data-ttu-id="8dbe6-117">要素</span><span class="sxs-lookup"><span data-stu-id="8dbe6-117">Element</span></span>|<span data-ttu-id="8dbe6-118">説明</span><span class="sxs-lookup"><span data-stu-id="8dbe6-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8dbe6-119">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="8dbe6-119">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="8dbe6-120">1 つ以上のプロパティ (アドレス、バインディング、コントラクト) が固定されている、あらかじめ定義されたエンドポイントである標準エンドポイントのコレクション。</span><span class="sxs-lookup"><span data-stu-id="8dbe6-120">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8dbe6-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="8dbe6-121">See also</span></span>

- <xref:System.ServiceModel.Activities.WorkflowControlEndpoint>
