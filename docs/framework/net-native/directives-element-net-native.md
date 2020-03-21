---
title: <Directives>要素 (.NET ネイティブ)
ms.date: 03/30/2017
ms.assetid: 444846f3-48d5-4341-a43e-69f7221389eb
ms.openlocfilehash: 49c1aaf005b80a6c1c1fa382eebc2cb0dbfa4be7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181055"
---
# <a name="directives-element-net-native"></a><span data-ttu-id="ace2b-102">\<要素 (.NET ネイティブ)>ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="ace2b-102">\<Directives> Element (.NET Native)</span></span>
<span data-ttu-id="ace2b-103">NET ネイティブのすべてのランタイム ディレクティブ ファイルのルート要素。</span><span class="sxs-lookup"><span data-stu-id="ace2b-103">The root element in every runtime directives file for .NET Native.</span></span>  
  
 `<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">`
  
## <a name="syntax"></a><span data-ttu-id="ace2b-104">構文</span><span class="sxs-lookup"><span data-stu-id="ace2b-104">Syntax</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <!-- child elements -->
</Directives>  
```  
  
## <a name="attributes"></a><span data-ttu-id="ace2b-105">属性</span><span class="sxs-lookup"><span data-stu-id="ace2b-105">Attributes</span></span>  
  
|<span data-ttu-id="ace2b-106">属性</span><span class="sxs-lookup"><span data-stu-id="ace2b-106">Attribute</span></span>|<span data-ttu-id="ace2b-107">説明</span><span class="sxs-lookup"><span data-stu-id="ace2b-107">Description</span></span>|  
|---------------|-----------------|  
|`xmlns`|<span data-ttu-id="ace2b-108">XML 名前空間。</span><span class="sxs-lookup"><span data-stu-id="ace2b-108">The XML namespace.</span></span> <span data-ttu-id="ace2b-109">その値は常に **" "http://schemas.microsoft.com/netfx/2013/01/metadataです**。</span><span class="sxs-lookup"><span data-stu-id="ace2b-109">Its value is always **"http://schemas.microsoft.com/netfx/2013/01/metadata"**.</span></span>|  
  
## <a name="child-elements"></a><span data-ttu-id="ace2b-110">子要素</span><span class="sxs-lookup"><span data-stu-id="ace2b-110">Child elements</span></span>  
  
|<span data-ttu-id="ace2b-111">要素</span><span class="sxs-lookup"><span data-stu-id="ace2b-111">Element</span></span>|<span data-ttu-id="ace2b-112">説明</span><span class="sxs-lookup"><span data-stu-id="ace2b-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ace2b-113">\<アプリケーション></span><span class="sxs-lookup"><span data-stu-id="ace2b-113">\<Application></span></span>](application-element-net-native.md)|<span data-ttu-id="ace2b-114">リフレクションで使用可能なメタデータを持つアプリケーション全体の型と型のメンバーのコンテナーとして機能します。</span><span class="sxs-lookup"><span data-stu-id="ace2b-114">Serves as a container for application-wide types and type members whose metadata is available for reflection.</span></span>|  
|[<span data-ttu-id="ace2b-115">\<図書館></span><span class="sxs-lookup"><span data-stu-id="ace2b-115">\<Library></span></span>](library-element-net-native.md)|<span data-ttu-id="ace2b-116">実行時にメタデータを必要とする子型と型のメンバーを持つアセンブリを定義します。</span><span class="sxs-lookup"><span data-stu-id="ace2b-116">Defines the assembly whose child types and type members require metadata at run time.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ace2b-117">解説</span><span class="sxs-lookup"><span data-stu-id="ace2b-117">Remarks</span></span>  
 <span data-ttu-id="ace2b-118">各ランタイム ディレクティブ ファイルには、`<Directives>` 要素を 1 つのみ含めることができます。</span><span class="sxs-lookup"><span data-stu-id="ace2b-118">Each runtime directives file can contain only one `<Directives>` element.</span></span>  
  
 <span data-ttu-id="ace2b-119">要素`<Directives>`には、0 個または 1 つの[\<アプリケーション>](application-element-net-native.md)要素、および 0、1 つ、または複数の[\<ライブラリ>](library-element-net-native.md)要素を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="ace2b-119">The `<Directives>` element can contain zero or one [\<Application>](application-element-net-native.md) element, and zero, one, or more [\<Library>](library-element-net-native.md) elements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ace2b-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="ace2b-120">See also</span></span>

- [<span data-ttu-id="ace2b-121">ランタイム ディレクティブ (rd.xml) 構成ファイル リファレン</span><span class="sxs-lookup"><span data-stu-id="ace2b-121">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="ace2b-122">ランタイム ディレクティブ要素</span><span class="sxs-lookup"><span data-stu-id="ace2b-122">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
