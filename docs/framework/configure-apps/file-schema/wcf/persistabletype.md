---
title: <persistableType>
ms.date: 03/30/2017
ms.assetid: e5425fe6-523a-4076-aab4-2c2515b1d830
ms.openlocfilehash: 328caaefe0cc24da45b460cab0a672dc8a6ccce1
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855070"
---
# <a name="persistabletype"></a><span data-ttu-id="f4495-101">\<persistableType ></span><span class="sxs-lookup"><span data-stu-id="f4495-101">\<persistableType></span></span>
<span data-ttu-id="f4495-102">すべての永続型を指定します。</span><span class="sxs-lookup"><span data-stu-id="f4495-102">Specifies all the persistable types.</span></span>  
  
<span data-ttu-id="f4495-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f4495-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f4495-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="f4495-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="f4495-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comContracts >** ](comcontracts.md)</span><span class="sxs-lookup"><span data-stu-id="f4495-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContracts>**](comcontracts.md)</span></span>\
<span data-ttu-id="f4495-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comContract >** ](comcontract.md)</span><span class="sxs-lookup"><span data-stu-id="f4495-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContract>**](comcontract.md)</span></span>\
<span data-ttu-id="f4495-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<persistableTypes >** ](persistabletypes.md)</span><span class="sxs-lookup"><span data-stu-id="f4495-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<persistableTypes>**](persistabletypes.md)</span></span>\
<span data-ttu-id="f4495-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<persistableType >**</span><span class="sxs-lookup"><span data-stu-id="f4495-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<persistableType>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4495-109">構文</span><span class="sxs-lookup"><span data-stu-id="f4495-109">Syntax</span></span>  
  
```xml  
<comContracts>
  <comContract>
    <persistableTypes>
      <persistableType id="String"
                       name="String">
      </persistableType>
    </persistableTypes>
  </comContract>
</comContracts>
```  
  
## <a name="type"></a><span data-ttu-id="f4495-110">型</span><span class="sxs-lookup"><span data-stu-id="f4495-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f4495-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="f4495-111">Attributes and Elements</span></span>  
 <span data-ttu-id="f4495-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="f4495-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f4495-113">属性</span><span class="sxs-lookup"><span data-stu-id="f4495-113">Attributes</span></span>  
  
|<span data-ttu-id="f4495-114">属性</span><span class="sxs-lookup"><span data-stu-id="f4495-114">Attribute</span></span>|<span data-ttu-id="f4495-115">説明</span><span class="sxs-lookup"><span data-stu-id="f4495-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f4495-116">id</span><span class="sxs-lookup"><span data-stu-id="f4495-116">id</span></span>|<span data-ttu-id="f4495-117">永続型の一意の ID を指定する文字列を含む必須属性。</span><span class="sxs-lookup"><span data-stu-id="f4495-117">A required attribute that contains a string that specifies a unique identifier for a persistable type.</span></span>|  
|<span data-ttu-id="f4495-118">name</span><span class="sxs-lookup"><span data-stu-id="f4495-118">name</span></span>|<span data-ttu-id="f4495-119">永続型の名前を指定する文字列を含む省略可能な属性。</span><span class="sxs-lookup"><span data-stu-id="f4495-119">An optional attribute that contains a string that specifies the name of the persistable type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f4495-120">子要素</span><span class="sxs-lookup"><span data-stu-id="f4495-120">Child Elements</span></span>  
 <span data-ttu-id="f4495-121">なし</span><span class="sxs-lookup"><span data-stu-id="f4495-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f4495-122">親要素</span><span class="sxs-lookup"><span data-stu-id="f4495-122">Parent Elements</span></span>  
  
|<span data-ttu-id="f4495-123">要素</span><span class="sxs-lookup"><span data-stu-id="f4495-123">Element</span></span>|<span data-ttu-id="f4495-124">説明</span><span class="sxs-lookup"><span data-stu-id="f4495-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f4495-125">\<persistableTypes></span><span class="sxs-lookup"><span data-stu-id="f4495-125">\<persistableTypes></span></span>](persistabletypes.md)|<span data-ttu-id="f4495-126">`persistableType` 要素のコレクション。</span><span class="sxs-lookup"><span data-stu-id="f4495-126">A collection of `persistableType` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f4495-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="f4495-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComPersistableTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ComPersistableTypeElement>
- [<span data-ttu-id="f4495-128">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="f4495-128">\<comContracts></span></span>](comcontracts.md)
- [<span data-ttu-id="f4495-129">COM+ アプリケーションとの統合</span><span class="sxs-lookup"><span data-stu-id="f4495-129">Integrating with COM+ Applications</span></span>](../../../wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="f4495-130">方法: COM + サービス設定の構成</span><span class="sxs-lookup"><span data-stu-id="f4495-130">How to: Configure COM+ Service Settings</span></span>](../../../wcf/feature-details/how-to-configure-com-service-settings.md)
