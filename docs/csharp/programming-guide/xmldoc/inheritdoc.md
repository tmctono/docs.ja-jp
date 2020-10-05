---
title: <inheritdoc> - C# プログラミング ガイド
ms.date: 01/21/2020
f1_keywords:
- inheritdoc
- <inheritdoc>
helpviewer_keywords:
- <inheritdoc> C# XML tag
- inheritdoc C# XML tag
ms.assetid: 46d329b1-5b84-4537-9e17-73ca97313e4e
ms.openlocfilehash: 8c416275254892efdb9f15cd2ae0af5634c82357
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91184093"
---
# <a name="inheritdoc-c-programming-guide"></a><span data-ttu-id="bfdcb-102">\<inheritdoc> (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="bfdcb-102">\<inheritdoc> (C# Programming Guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="bfdcb-103">構文</span><span class="sxs-lookup"><span data-stu-id="bfdcb-103">Syntax</span></span>  
  
```xml  
<inheritdoc/>
```  

## <a name="inheritdoc"></a><span data-ttu-id="bfdcb-104">InheritDoc</span><span class="sxs-lookup"><span data-stu-id="bfdcb-104">InheritDoc</span></span>

<span data-ttu-id="bfdcb-105">基底クラス、インターフェイス、および同様のメソッドから、XML コメントを継承します。</span><span class="sxs-lookup"><span data-stu-id="bfdcb-105">Inherit XML comments from base classes, interfaces, and similar methods.</span></span> <span data-ttu-id="bfdcb-106">これにより、重複する XML コメントの不要なコピーと貼り付けを行う必要がなくなり、XML コメントが自動的に同期されたままになります。</span><span class="sxs-lookup"><span data-stu-id="bfdcb-106">This eliminates unwanted copying and pasting of duplicate XML comments and automatically keeps XML comments synchronized.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="bfdcb-107">解説</span><span class="sxs-lookup"><span data-stu-id="bfdcb-107">Remarks</span></span>  

<span data-ttu-id="bfdcb-108">基底クラスまたはインターフェイスに XML コメントを追加し、InheritDoc によってそのコメントが実装するクラスにコピーされるようにします。</span><span class="sxs-lookup"><span data-stu-id="bfdcb-108">Add your XML comments in base classes or interfaces and let InheritDoc copy the comments to implementing classes.</span></span>

<span data-ttu-id="bfdcb-109">同期メソッドに XML コメントを追加し、InheritDoc によってそのコメントが同じメソッドの非同期バージョンにコピーされるようにします。</span><span class="sxs-lookup"><span data-stu-id="bfdcb-109">Add your XML comments to your synchronous methods and let InheritDoc copy the comments to your asynchronous versions of the same methods.</span></span>  

<span data-ttu-id="bfdcb-110">特定のメンバーからコメントをコピーしたい場合は、`cref` 属性を使用してそのメンバーを指定できます。</span><span class="sxs-lookup"><span data-stu-id="bfdcb-110">If you want to copy the comments from a specific member you can use the `cref` attribute to specify the member.</span></span>
  
## <a name="examples"></a><span data-ttu-id="bfdcb-111">例</span><span class="sxs-lookup"><span data-stu-id="bfdcb-111">Examples</span></span>

[!code-csharp[csProgGuideDocComments#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#16)]  

[!code-csharp[csProgGuideDocComments#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#17)]  

## <a name="see-also"></a><span data-ttu-id="bfdcb-112">参照</span><span class="sxs-lookup"><span data-stu-id="bfdcb-112">See also</span></span>

- [<span data-ttu-id="bfdcb-113">C# プログラミングガイド</span><span class="sxs-lookup"><span data-stu-id="bfdcb-113">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="bfdcb-114">ドキュメント コメントとして推奨されるタグ</span><span class="sxs-lookup"><span data-stu-id="bfdcb-114">Recommended Tags for Documentation Comments</span></span>](./recommended-tags-for-documentation-comments.md)
