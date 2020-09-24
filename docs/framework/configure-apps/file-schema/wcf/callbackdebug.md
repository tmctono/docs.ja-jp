---
title: <callbackDebug>
ms.date: 03/30/2017
ms.assetid: 4073feda-1857-4be4-9947-227afb847ced
ms.openlocfilehash: 02632cc3f668bb9e4cc6f8c9726d7bcb3cab2c5d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183820"
---
# \<callbackDebug>

<span data-ttu-id="3c43a-101">Windows Communication Foundation (WCF) コールバックオブジェクトのサービスデバッグを指定します。</span><span class="sxs-lookup"><span data-stu-id="3c43a-101">Specifies service debugging for a Windows Communication Foundation (WCF) callback object.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<callbackDebug>**  
  
## <a name="syntax"></a><span data-ttu-id="3c43a-102">構文</span><span class="sxs-lookup"><span data-stu-id="3c43a-102">Syntax</span></span>  
  
```xml  
<callbackDebug includeExceptionDetailInFaults="Boolean" />
```  
  
## <a name="type"></a><span data-ttu-id="3c43a-103">種類</span><span class="sxs-lookup"><span data-stu-id="3c43a-103">Type</span></span>  

 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3c43a-104">属性および要素</span><span class="sxs-lookup"><span data-stu-id="3c43a-104">Attributes and Elements</span></span>  

 <span data-ttu-id="3c43a-105">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="3c43a-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3c43a-106">属性</span><span class="sxs-lookup"><span data-stu-id="3c43a-106">Attributes</span></span>  
  
|<span data-ttu-id="3c43a-107">属性</span><span class="sxs-lookup"><span data-stu-id="3c43a-107">Attribute</span></span>|<span data-ttu-id="3c43a-108">[説明]</span><span class="sxs-lookup"><span data-stu-id="3c43a-108">Description</span></span>|  
|---------------|-----------------|  
|`includeExceptionDetailInFaults`|<span data-ttu-id="3c43a-109">クライアント コールバック オブジェクトが SOAP エラー内のマネージド例外情報をサービスに返すかどうかを指定する値。</span><span class="sxs-lookup"><span data-stu-id="3c43a-109">A value that specifies whether client callback objects return managed exception information in SOAP faults back to the service.</span></span><br /><br /> <span data-ttu-id="3c43a-110">プログラムでこの属性を `true` に設定すると、デバッグするために、クライアント コールバック オブジェクト内のマネージド例外情報がサービスに戻るフローを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="3c43a-110">If you set this attribute to `true` programmatically, you can enable the flow of managed exception information in a client callback object back to the service for debugging purposes.</span></span> <span data-ttu-id="3c43a-111">**注意:**  マネージ例外情報をクライアントに返すことは、セキュリティ上のリスクになる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3c43a-111">**Caution:**  Returning managed exception information to clients can be a security risk.</span></span> <span data-ttu-id="3c43a-112">これは、例外の詳細が、認証されていないクライアントによって使用可能な内部サービスの実装に関する情報を公開するためです。</span><span class="sxs-lookup"><span data-stu-id="3c43a-112">This is because exception details expose information about the internal service implementation that could be used by unauthorized clients.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3c43a-113">子要素</span><span class="sxs-lookup"><span data-stu-id="3c43a-113">Child Elements</span></span>  

 <span data-ttu-id="3c43a-114">なし。</span><span class="sxs-lookup"><span data-stu-id="3c43a-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3c43a-115">親要素</span><span class="sxs-lookup"><span data-stu-id="3c43a-115">Parent Elements</span></span>  
  
|<span data-ttu-id="3c43a-116">要素</span><span class="sxs-lookup"><span data-stu-id="3c43a-116">Element</span></span>|<span data-ttu-id="3c43a-117">説明</span><span class="sxs-lookup"><span data-stu-id="3c43a-117">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="3c43a-118">エンドポイントの動作を指定します。</span><span class="sxs-lookup"><span data-stu-id="3c43a-118">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3c43a-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="3c43a-119">See also</span></span>

- <xref:System.ServiceModel.Configuration.CallbackDebugElement>
- <xref:System.ServiceModel.Description.CallbackDebugBehavior>
