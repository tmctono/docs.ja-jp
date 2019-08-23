---
title: <callbackDebug>
ms.date: 03/30/2017
ms.assetid: 4073feda-1857-4be4-9947-227afb847ced
ms.openlocfilehash: 91e7bd63bf496f2c38776d88173ed2ac12a3b888
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926315"
---
# <a name="callbackdebug"></a><span data-ttu-id="95a5a-101">\<> のデバッグ</span><span class="sxs-lookup"><span data-stu-id="95a5a-101">\<callbackDebug></span></span>
<span data-ttu-id="95a5a-102">Windows Communication Foundation (WCF) コールバックオブジェクトのサービスデバッグを指定します。</span><span class="sxs-lookup"><span data-stu-id="95a5a-102">Specifies service debugging for a Windows Communication Foundation (WCF) callback object.</span></span>  
  
 <span data-ttu-id="95a5a-103">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="95a5a-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="95a5a-104">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="95a5a-104">\<behaviors></span></span>  
<span data-ttu-id="95a5a-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="95a5a-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="95a5a-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="95a5a-106">\<behavior></span></span>  
<span data-ttu-id="95a5a-107">\<> のデバッグ</span><span class="sxs-lookup"><span data-stu-id="95a5a-107">\<callbackDebug></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95a5a-108">構文</span><span class="sxs-lookup"><span data-stu-id="95a5a-108">Syntax</span></span>  
  
```xml  
<callbackDebug includeExceptionDetailInFaults="Boolean" />
```  
  
## <a name="type"></a><span data-ttu-id="95a5a-109">型</span><span class="sxs-lookup"><span data-stu-id="95a5a-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="95a5a-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="95a5a-110">Attributes and Elements</span></span>  
 <span data-ttu-id="95a5a-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="95a5a-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="95a5a-112">属性</span><span class="sxs-lookup"><span data-stu-id="95a5a-112">Attributes</span></span>  
  
|<span data-ttu-id="95a5a-113">属性</span><span class="sxs-lookup"><span data-stu-id="95a5a-113">Attribute</span></span>|<span data-ttu-id="95a5a-114">説明</span><span class="sxs-lookup"><span data-stu-id="95a5a-114">Description</span></span>|  
|---------------|-----------------|  
|`includeExceptionDetailInFaults`|<span data-ttu-id="95a5a-115">クライアント コールバック オブジェクトが SOAP エラー内のマネージド例外情報をサービスに返すかどうかを指定する値。</span><span class="sxs-lookup"><span data-stu-id="95a5a-115">A value that specifies whether client callback objects return managed exception information in SOAP faults back to the service.</span></span><br /><br /> <span data-ttu-id="95a5a-116">プログラムでこの属性を `true` に設定すると、デバッグするために、クライアント コールバック オブジェクト内のマネージド例外情報がサービスに戻るフローを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="95a5a-116">If you set this attribute to `true` programmatically, you can enable the flow of managed exception information in a client callback object back to the service for debugging purposes.</span></span> <span data-ttu-id="95a5a-117">**注意:** マネージド例外情報をクライアントに返すことは、セキュリティ リスクになり得ます。</span><span class="sxs-lookup"><span data-stu-id="95a5a-117">**Caution:**  Returning managed exception information to clients can be a security risk.</span></span> <span data-ttu-id="95a5a-118">これは、例外の詳細が、認証されていないクライアントによって使用可能な内部サービスの実装に関する情報を公開するためです。</span><span class="sxs-lookup"><span data-stu-id="95a5a-118">This is because exception details expose information about the internal service implementation that could be used by unauthorized clients.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="95a5a-119">子要素</span><span class="sxs-lookup"><span data-stu-id="95a5a-119">Child Elements</span></span>  
 <span data-ttu-id="95a5a-120">なし。</span><span class="sxs-lookup"><span data-stu-id="95a5a-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="95a5a-121">親要素</span><span class="sxs-lookup"><span data-stu-id="95a5a-121">Parent Elements</span></span>  
  
|<span data-ttu-id="95a5a-122">要素</span><span class="sxs-lookup"><span data-stu-id="95a5a-122">Element</span></span>|<span data-ttu-id="95a5a-123">説明</span><span class="sxs-lookup"><span data-stu-id="95a5a-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="95a5a-124">\<behavior></span><span class="sxs-lookup"><span data-stu-id="95a5a-124">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="95a5a-125">エンドポイントの動作を指定します。</span><span class="sxs-lookup"><span data-stu-id="95a5a-125">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="95a5a-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="95a5a-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.CallbackDebugElement>
- <xref:System.ServiceModel.Description.CallbackDebugBehavior>
