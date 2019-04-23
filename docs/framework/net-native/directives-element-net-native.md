---
title: <Directives> 要素 (.NET ネイティブ)
ms.date: 03/30/2017
ms.assetid: 444846f3-48d5-4341-a43e-69f7221389eb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5cfc9dc5c8122f9b1b1696cedcd5d9a8ceead403
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59100224"
---
# <a name="directives-element-net-native"></a><span data-ttu-id="de733-102">\<ディレクティブ > 要素 (.NET ネイティブ)</span><span class="sxs-lookup"><span data-stu-id="de733-102">\<Directives> Element (.NET Native)</span></span>
<span data-ttu-id="de733-103">.NET ネイティブ用のすべてのランタイム ディレクティブ ファイルにルート要素です。</span><span class="sxs-lookup"><span data-stu-id="de733-103">The root element in every runtime directives file for .NET Native.</span></span>  
  
 `<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">` 
  
## <a name="syntax"></a><span data-ttu-id="de733-104">構文</span><span class="sxs-lookup"><span data-stu-id="de733-104">Syntax</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <!-- child elements -->   
</Directives>  
```  
  
## <a name="attributes"></a><span data-ttu-id="de733-105">属性</span><span class="sxs-lookup"><span data-stu-id="de733-105">Attributes</span></span>  
  
|<span data-ttu-id="de733-106">属性</span><span class="sxs-lookup"><span data-stu-id="de733-106">Attribute</span></span>|<span data-ttu-id="de733-107">説明</span><span class="sxs-lookup"><span data-stu-id="de733-107">Description</span></span>|  
|---------------|-----------------|  
|`xmlns`|<span data-ttu-id="de733-108">XML 名前空間。</span><span class="sxs-lookup"><span data-stu-id="de733-108">The XML namespace.</span></span> <span data-ttu-id="de733-109">その値は常に **"http://schemas.microsoft.com/netfx/2013/01/metadata"** します。</span><span class="sxs-lookup"><span data-stu-id="de733-109">Its value is always **"http://schemas.microsoft.com/netfx/2013/01/metadata"**.</span></span>|  
  
## <a name="child-elements"></a><span data-ttu-id="de733-110">子要素</span><span class="sxs-lookup"><span data-stu-id="de733-110">Child elements</span></span>  
  
|<span data-ttu-id="de733-111">要素</span><span class="sxs-lookup"><span data-stu-id="de733-111">Element</span></span>|<span data-ttu-id="de733-112">説明</span><span class="sxs-lookup"><span data-stu-id="de733-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="de733-113">\<Application></span><span class="sxs-lookup"><span data-stu-id="de733-113">\<Application></span></span>](../../../docs/framework/net-native/application-element-net-native.md)|<span data-ttu-id="de733-114">リフレクションで使用可能なメタデータを持つアプリケーション全体の型と型のメンバーのコンテナーとして機能します。</span><span class="sxs-lookup"><span data-stu-id="de733-114">Serves as a container for application-wide types and type members whose metadata is available for reflection.</span></span>|  
|[<span data-ttu-id="de733-115">\<Library></span><span class="sxs-lookup"><span data-stu-id="de733-115">\<Library></span></span>](../../../docs/framework/net-native/library-element-net-native.md)|<span data-ttu-id="de733-116">実行時にメタデータを必要とする子型と型のメンバーを持つアセンブリを定義します。</span><span class="sxs-lookup"><span data-stu-id="de733-116">Defines the assembly whose child types and type members require metadata at run time.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="de733-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="de733-117">Remarks</span></span>  
 <span data-ttu-id="de733-118">各ランタイム ディレクティブ ファイルには、`<Directives>` 要素を 1 つのみ含めることができます。</span><span class="sxs-lookup"><span data-stu-id="de733-118">Each runtime directives file can contain only one `<Directives>` element.</span></span>  
  
 <span data-ttu-id="de733-119">`<Directives>` 要素には、0 または 1 個の [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) 要素と、0 個以上の [\<Library>](../../../docs/framework/net-native/library-element-net-native.md) 要素を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="de733-119">The `<Directives>` element can contain zero or one [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) element, and zero, one, or more [\<Library>](../../../docs/framework/net-native/library-element-net-native.md) elements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de733-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="de733-120">See also</span></span>

- [<span data-ttu-id="de733-121">ランタイム ディレクティブ (rd.xml) 構成ファイル リファレンス</span><span class="sxs-lookup"><span data-stu-id="de733-121">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="de733-122">ランタイム ディレクティブ要素</span><span class="sxs-lookup"><span data-stu-id="de733-122">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)
