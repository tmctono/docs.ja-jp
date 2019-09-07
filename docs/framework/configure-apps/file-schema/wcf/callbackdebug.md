---
title: <callbackDebug>
ms.date: 03/30/2017
ms.assetid: 4073feda-1857-4be4-9947-227afb847ced
ms.openlocfilehash: 92a8fa83b5cf5f429278ac8edc8439b627839aad
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400566"
---
# <a name="callbackdebug"></a><span data-ttu-id="67e7e-101">\<> のデバッグ</span><span class="sxs-lookup"><span data-stu-id="67e7e-101">\<callbackDebug></span></span>
<span data-ttu-id="67e7e-102">Windows Communication Foundation (WCF) コールバックオブジェクトのサービスデバッグを指定します。</span><span class="sxs-lookup"><span data-stu-id="67e7e-102">Specifies service debugging for a Windows Communication Foundation (WCF) callback object.</span></span>  
  
<span data-ttu-id="67e7e-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="67e7e-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="67e7e-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="67e7e-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="67e7e-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="67e7e-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="67e7e-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="67e7e-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="67e7e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="67e7e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="67e7e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> のデバッグ**</span><span class="sxs-lookup"><span data-stu-id="67e7e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<callbackDebug>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67e7e-109">構文</span><span class="sxs-lookup"><span data-stu-id="67e7e-109">Syntax</span></span>  
  
```xml  
<callbackDebug includeExceptionDetailInFaults="Boolean" />
```  
  
## <a name="type"></a><span data-ttu-id="67e7e-110">型</span><span class="sxs-lookup"><span data-stu-id="67e7e-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="67e7e-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="67e7e-111">Attributes and Elements</span></span>  
 <span data-ttu-id="67e7e-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="67e7e-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="67e7e-113">属性</span><span class="sxs-lookup"><span data-stu-id="67e7e-113">Attributes</span></span>  
  
|<span data-ttu-id="67e7e-114">属性</span><span class="sxs-lookup"><span data-stu-id="67e7e-114">Attribute</span></span>|<span data-ttu-id="67e7e-115">説明</span><span class="sxs-lookup"><span data-stu-id="67e7e-115">Description</span></span>|  
|---------------|-----------------|  
|`includeExceptionDetailInFaults`|<span data-ttu-id="67e7e-116">クライアント コールバック オブジェクトが SOAP エラー内のマネージド例外情報をサービスに返すかどうかを指定する値。</span><span class="sxs-lookup"><span data-stu-id="67e7e-116">A value that specifies whether client callback objects return managed exception information in SOAP faults back to the service.</span></span><br /><br /> <span data-ttu-id="67e7e-117">プログラムでこの属性を `true` に設定すると、デバッグするために、クライアント コールバック オブジェクト内のマネージド例外情報がサービスに戻るフローを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="67e7e-117">If you set this attribute to `true` programmatically, you can enable the flow of managed exception information in a client callback object back to the service for debugging purposes.</span></span> <span data-ttu-id="67e7e-118">**注意:** マネージド例外情報をクライアントに返すことは、セキュリティ リスクになり得ます。</span><span class="sxs-lookup"><span data-stu-id="67e7e-118">**Caution:**  Returning managed exception information to clients can be a security risk.</span></span> <span data-ttu-id="67e7e-119">これは、例外の詳細が、認証されていないクライアントによって使用可能な内部サービスの実装に関する情報を公開するためです。</span><span class="sxs-lookup"><span data-stu-id="67e7e-119">This is because exception details expose information about the internal service implementation that could be used by unauthorized clients.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="67e7e-120">子要素</span><span class="sxs-lookup"><span data-stu-id="67e7e-120">Child Elements</span></span>  
 <span data-ttu-id="67e7e-121">なし。</span><span class="sxs-lookup"><span data-stu-id="67e7e-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="67e7e-122">親要素</span><span class="sxs-lookup"><span data-stu-id="67e7e-122">Parent Elements</span></span>  
  
|<span data-ttu-id="67e7e-123">要素</span><span class="sxs-lookup"><span data-stu-id="67e7e-123">Element</span></span>|<span data-ttu-id="67e7e-124">説明</span><span class="sxs-lookup"><span data-stu-id="67e7e-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="67e7e-125">\<behavior></span><span class="sxs-lookup"><span data-stu-id="67e7e-125">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="67e7e-126">エンドポイントの動作を指定します。</span><span class="sxs-lookup"><span data-stu-id="67e7e-126">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="67e7e-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="67e7e-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.CallbackDebugElement>
- <xref:System.ServiceModel.Description.CallbackDebugBehavior>
