---
title: <persistableType>
ms.date: 03/30/2017
ms.assetid: e5425fe6-523a-4076-aab4-2c2515b1d830
ms.openlocfilehash: 6425b21fe50865beb7bb2876ea478b415fbe3944
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91181519"
---
# \<persistableType>

<span data-ttu-id="5a980-101">すべての永続型を指定します。</span><span class="sxs-lookup"><span data-stu-id="5a980-101">Specifies all the persistable types.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContracts>**](comcontracts.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContract>**](comcontract.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<persistableTypes>**](persistabletypes.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<persistableType>**  
  
## <a name="syntax"></a><span data-ttu-id="5a980-102">構文</span><span class="sxs-lookup"><span data-stu-id="5a980-102">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="5a980-103">種類</span><span class="sxs-lookup"><span data-stu-id="5a980-103">Type</span></span>  

 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5a980-104">属性および要素</span><span class="sxs-lookup"><span data-stu-id="5a980-104">Attributes and Elements</span></span>  

 <span data-ttu-id="5a980-105">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="5a980-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5a980-106">属性</span><span class="sxs-lookup"><span data-stu-id="5a980-106">Attributes</span></span>  
  
|<span data-ttu-id="5a980-107">属性</span><span class="sxs-lookup"><span data-stu-id="5a980-107">Attribute</span></span>|<span data-ttu-id="5a980-108">説明</span><span class="sxs-lookup"><span data-stu-id="5a980-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5a980-109">id</span><span class="sxs-lookup"><span data-stu-id="5a980-109">id</span></span>|<span data-ttu-id="5a980-110">永続型の一意の ID を指定する文字列を含む必須属性。</span><span class="sxs-lookup"><span data-stu-id="5a980-110">A required attribute that contains a string that specifies a unique identifier for a persistable type.</span></span>|  
|<span data-ttu-id="5a980-111">name</span><span class="sxs-lookup"><span data-stu-id="5a980-111">name</span></span>|<span data-ttu-id="5a980-112">永続型の名前を指定する文字列を含む省略可能な属性。</span><span class="sxs-lookup"><span data-stu-id="5a980-112">An optional attribute that contains a string that specifies the name of the persistable type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5a980-113">子要素</span><span class="sxs-lookup"><span data-stu-id="5a980-113">Child Elements</span></span>  

 <span data-ttu-id="5a980-114">None</span><span class="sxs-lookup"><span data-stu-id="5a980-114">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5a980-115">親要素</span><span class="sxs-lookup"><span data-stu-id="5a980-115">Parent Elements</span></span>  
  
|<span data-ttu-id="5a980-116">要素</span><span class="sxs-lookup"><span data-stu-id="5a980-116">Element</span></span>|<span data-ttu-id="5a980-117">説明</span><span class="sxs-lookup"><span data-stu-id="5a980-117">Description</span></span>|  
|-------------|-----------------|  
|[\<persistableTypes>](persistabletypes.md)|<span data-ttu-id="5a980-118">`persistableType` 要素のコレクション。</span><span class="sxs-lookup"><span data-stu-id="5a980-118">A collection of `persistableType` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5a980-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="5a980-119">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComPersistableTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ComPersistableTypeElement>
- [\<comContracts>](comcontracts.md)
- [<span data-ttu-id="5a980-120">COM + アプリケーションとの統合</span><span class="sxs-lookup"><span data-stu-id="5a980-120">Integrating with COM+ Applications</span></span>](../../../wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="5a980-121">方法: COM+ サービス設定を構成する</span><span class="sxs-lookup"><span data-stu-id="5a980-121">How to: Configure COM+ Service Settings</span></span>](../../../wcf/feature-details/how-to-configure-com-service-settings.md)
