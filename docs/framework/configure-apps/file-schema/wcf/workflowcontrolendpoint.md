---
title: <workflowControlEndpoint>
ms.date: 03/30/2017
ms.assetid: 6c89e76c-643b-4b6a-9b25-628f753d7027
ms.openlocfilehash: 670c1573fe4378a18c19d0a58fe58241745725bd
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854787"
---
# <a name="workflowcontrolendpoint"></a><span data-ttu-id="d605e-101">\<workflowControlEndpoint ></span><span class="sxs-lookup"><span data-stu-id="d605e-101">\<workflowControlEndpoint></span></span>
<span data-ttu-id="d605e-102">この構成要素は、ワークフロー インスタンスの実行の制御 (作成、実行、保留、終了など) に使用する標準エンドポイントを定義します。</span><span class="sxs-lookup"><span data-stu-id="d605e-102">This configuration element defines a standard endpoint for controlling the execution of workflow instances (create, run, suspend, terminate, etc).</span></span>  
  
<span data-ttu-id="d605e-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d605e-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="d605e-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="d605e-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="d605e-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<standardEndpoints >** ](standardendpoints.md)</span><span class="sxs-lookup"><span data-stu-id="d605e-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)</span></span>\
<span data-ttu-id="d605e-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<workflowControlEndpoint >**</span><span class="sxs-lookup"><span data-stu-id="d605e-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowControlEndpoint>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d605e-107">構文</span><span class="sxs-lookup"><span data-stu-id="d605e-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <workflowControlEndpoint>
      <standardEndpoint name="String" />
    </workflowControlEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d605e-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="d605e-108">Attributes and Elements</span></span>  
 <span data-ttu-id="d605e-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="d605e-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d605e-110">属性</span><span class="sxs-lookup"><span data-stu-id="d605e-110">Attributes</span></span>  
  
|<span data-ttu-id="d605e-111">属性</span><span class="sxs-lookup"><span data-stu-id="d605e-111">Attribute</span></span>|<span data-ttu-id="d605e-112">説明</span><span class="sxs-lookup"><span data-stu-id="d605e-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d605e-113">name</span><span class="sxs-lookup"><span data-stu-id="d605e-113">name</span></span>|<span data-ttu-id="d605e-114">標準エンドポイントの構成名を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="d605e-114">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="d605e-115">この名前は、サービス エンドポイントの `endpointConfiguration` 属性で使用され、標準エンドポイントと構成を関連付けます。</span><span class="sxs-lookup"><span data-stu-id="d605e-115">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d605e-116">子要素</span><span class="sxs-lookup"><span data-stu-id="d605e-116">Child Elements</span></span>  
 <span data-ttu-id="d605e-117">なし。</span><span class="sxs-lookup"><span data-stu-id="d605e-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d605e-118">親要素</span><span class="sxs-lookup"><span data-stu-id="d605e-118">Parent Elements</span></span>  
  
|<span data-ttu-id="d605e-119">要素</span><span class="sxs-lookup"><span data-stu-id="d605e-119">Element</span></span>|<span data-ttu-id="d605e-120">説明</span><span class="sxs-lookup"><span data-stu-id="d605e-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d605e-121">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="d605e-121">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="d605e-122">1 つ以上のプロパティ (アドレス、バインディング、コントラクト) が固定されている、あらかじめ定義されたエンドポイントである標準エンドポイントのコレクション。</span><span class="sxs-lookup"><span data-stu-id="d605e-122">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d605e-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="d605e-123">See also</span></span>

- <xref:System.ServiceModel.Activities.WorkflowControlEndpoint>
