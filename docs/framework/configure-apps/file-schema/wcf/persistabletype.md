---
title: <persistableType>
ms.date: 03/30/2017
ms.assetid: e5425fe6-523a-4076-aab4-2c2515b1d830
ms.openlocfilehash: fcfd338e289b5151688724f0e84b6878707d32be
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933832"
---
# <a name="persistabletype"></a><span data-ttu-id="52ec4-101">\<persistableType ></span><span class="sxs-lookup"><span data-stu-id="52ec4-101">\<persistableType></span></span>
<span data-ttu-id="52ec4-102">すべての永続型を指定します。</span><span class="sxs-lookup"><span data-stu-id="52ec4-102">Specifies all the persistable types.</span></span>  
  
 <span data-ttu-id="52ec4-103">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="52ec4-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="52ec4-104">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="52ec4-104">\<comContracts></span></span>  
<span data-ttu-id="52ec4-105">\<comContract ></span><span class="sxs-lookup"><span data-stu-id="52ec4-105">\<comContract></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52ec4-106">構文</span><span class="sxs-lookup"><span data-stu-id="52ec4-106">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="52ec4-107">型</span><span class="sxs-lookup"><span data-stu-id="52ec4-107">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="52ec4-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="52ec4-108">Attributes and Elements</span></span>  
 <span data-ttu-id="52ec4-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="52ec4-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="52ec4-110">属性</span><span class="sxs-lookup"><span data-stu-id="52ec4-110">Attributes</span></span>  
  
|<span data-ttu-id="52ec4-111">属性</span><span class="sxs-lookup"><span data-stu-id="52ec4-111">Attribute</span></span>|<span data-ttu-id="52ec4-112">説明</span><span class="sxs-lookup"><span data-stu-id="52ec4-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="52ec4-113">id</span><span class="sxs-lookup"><span data-stu-id="52ec4-113">id</span></span>|<span data-ttu-id="52ec4-114">永続型の一意の ID を指定する文字列を含む必須属性。</span><span class="sxs-lookup"><span data-stu-id="52ec4-114">A required attribute that contains a string that specifies a unique identifier for a persistable type.</span></span>|  
|<span data-ttu-id="52ec4-115">name</span><span class="sxs-lookup"><span data-stu-id="52ec4-115">name</span></span>|<span data-ttu-id="52ec4-116">永続型の名前を指定する文字列を含む省略可能な属性。</span><span class="sxs-lookup"><span data-stu-id="52ec4-116">An optional attribute that contains a string that specifies the name of the persistable type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="52ec4-117">子要素</span><span class="sxs-lookup"><span data-stu-id="52ec4-117">Child Elements</span></span>  
 <span data-ttu-id="52ec4-118">なし</span><span class="sxs-lookup"><span data-stu-id="52ec4-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="52ec4-119">親要素</span><span class="sxs-lookup"><span data-stu-id="52ec4-119">Parent Elements</span></span>  
  
|<span data-ttu-id="52ec4-120">要素</span><span class="sxs-lookup"><span data-stu-id="52ec4-120">Element</span></span>|<span data-ttu-id="52ec4-121">説明</span><span class="sxs-lookup"><span data-stu-id="52ec4-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="52ec4-122">\<persistableTypes></span><span class="sxs-lookup"><span data-stu-id="52ec4-122">\<persistableTypes></span></span>](persistabletypes.md)|<span data-ttu-id="52ec4-123">`persistableType` 要素のコレクション。</span><span class="sxs-lookup"><span data-stu-id="52ec4-123">A collection of `persistableType` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="52ec4-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="52ec4-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComPersistableTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ComPersistableTypeElement>
- [<span data-ttu-id="52ec4-125">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="52ec4-125">\<comContracts></span></span>](comcontracts.md)
- [<span data-ttu-id="52ec4-126">COM+ アプリケーションとの統合</span><span class="sxs-lookup"><span data-stu-id="52ec4-126">Integrating with COM+ Applications</span></span>](../../../wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="52ec4-127">方法: COM + サービス設定の構成</span><span class="sxs-lookup"><span data-stu-id="52ec4-127">How to: Configure COM+ Service Settings</span></span>](../../../wcf/feature-details/how-to-configure-com-service-settings.md)
