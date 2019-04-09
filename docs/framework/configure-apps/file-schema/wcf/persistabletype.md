---
title: <persistableType>
ms.date: 03/30/2017
ms.assetid: e5425fe6-523a-4076-aab4-2c2515b1d830
ms.openlocfilehash: 939a29e90ee21e94ccb78842d6f7224e9a6288d0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59083739"
---
# <a name="persistabletype"></a><span data-ttu-id="e5e42-101">\<persistableType ></span><span class="sxs-lookup"><span data-stu-id="e5e42-101">\<persistableType></span></span>
<span data-ttu-id="e5e42-102">すべての永続型を指定します。</span><span class="sxs-lookup"><span data-stu-id="e5e42-102">Specifies all the persistable types.</span></span>  
  
 <span data-ttu-id="e5e42-103">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="e5e42-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="e5e42-104">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="e5e42-104">\<comContracts></span></span>  
<span data-ttu-id="e5e42-105">\<comContract></span><span class="sxs-lookup"><span data-stu-id="e5e42-105">\<comContract></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5e42-106">構文</span><span class="sxs-lookup"><span data-stu-id="e5e42-106">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="e5e42-107">型</span><span class="sxs-lookup"><span data-stu-id="e5e42-107">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e5e42-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e5e42-108">Attributes and Elements</span></span>  
 <span data-ttu-id="e5e42-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="e5e42-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e5e42-110">属性</span><span class="sxs-lookup"><span data-stu-id="e5e42-110">Attributes</span></span>  
  
|<span data-ttu-id="e5e42-111">属性</span><span class="sxs-lookup"><span data-stu-id="e5e42-111">Attribute</span></span>|<span data-ttu-id="e5e42-112">説明</span><span class="sxs-lookup"><span data-stu-id="e5e42-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e5e42-113">ID</span><span class="sxs-lookup"><span data-stu-id="e5e42-113">id</span></span>|<span data-ttu-id="e5e42-114">永続型の一意の ID を指定する文字列を含む必須属性。</span><span class="sxs-lookup"><span data-stu-id="e5e42-114">A required attribute that contains a string that specifies a unique identifier for a persistable type.</span></span>|  
|<span data-ttu-id="e5e42-115">name</span><span class="sxs-lookup"><span data-stu-id="e5e42-115">name</span></span>|<span data-ttu-id="e5e42-116">永続型の名前を指定する文字列を含む省略可能な属性。</span><span class="sxs-lookup"><span data-stu-id="e5e42-116">An optional attribute that contains a string that specifies the name of the persistable type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e5e42-117">子要素</span><span class="sxs-lookup"><span data-stu-id="e5e42-117">Child Elements</span></span>  
 <span data-ttu-id="e5e42-118">なし</span><span class="sxs-lookup"><span data-stu-id="e5e42-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e5e42-119">親要素</span><span class="sxs-lookup"><span data-stu-id="e5e42-119">Parent Elements</span></span>  
  
|<span data-ttu-id="e5e42-120">要素</span><span class="sxs-lookup"><span data-stu-id="e5e42-120">Element</span></span>|<span data-ttu-id="e5e42-121">説明</span><span class="sxs-lookup"><span data-stu-id="e5e42-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e5e42-122">\<persistableTypes></span><span class="sxs-lookup"><span data-stu-id="e5e42-122">\<persistableTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/persistabletypes.md)|<span data-ttu-id="e5e42-123">`persistableType` 要素のコレクション。</span><span class="sxs-lookup"><span data-stu-id="e5e42-123">A collection of `persistableType` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e5e42-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="e5e42-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComPersistableTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ComPersistableTypeElement>
- [<span data-ttu-id="e5e42-125">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="e5e42-125">\<comContracts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)
- [<span data-ttu-id="e5e42-126">COM+ アプリケーションとの統合</span><span class="sxs-lookup"><span data-stu-id="e5e42-126">Integrating with COM+ Applications</span></span>](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="e5e42-127">方法: COM+ サービス設定を構成する</span><span class="sxs-lookup"><span data-stu-id="e5e42-127">How to: Configure COM+ Service Settings</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
