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
ms.openlocfilehash: d660cb1739733c4e98ae0b7939476fe74e6cf200
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794835"
---
# <a name="inheritdoc-c-programming-guide"></a><span data-ttu-id="82cf0-102">\<inheritdoc> (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="82cf0-102">\<inheritdoc> (C# Programming Guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="82cf0-103">構文</span><span class="sxs-lookup"><span data-stu-id="82cf0-103">Syntax</span></span>  
  
```xml  
<inheritdoc/> 
```  

## <a name="inheritdoc"></a><span data-ttu-id="82cf0-104">InheritDoc</span><span class="sxs-lookup"><span data-stu-id="82cf0-104">InheritDoc</span></span>

<span data-ttu-id="82cf0-105">基底クラス、インターフェイス、および同様のメソッドから、XML コメントを継承します。</span><span class="sxs-lookup"><span data-stu-id="82cf0-105">Inherit XML comments from base classes, interfaces, and similar methods.</span></span> <span data-ttu-id="82cf0-106">これにより、重複する XML コメントの不要なコピーと貼り付けを行う必要がなくなり、XML コメントが自動的に同期されたままになります。</span><span class="sxs-lookup"><span data-stu-id="82cf0-106">This eliminates unwanted copying and pasting of duplicate XML comments and automatically keeps XML comments synchronized.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="82cf0-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="82cf0-107">Remarks</span></span>  
<span data-ttu-id="82cf0-108">基底クラスまたはインターフェイスに XML コメントを追加し、InheritDoc によってそのコメントが実装するクラスにコピーされるようにします。</span><span class="sxs-lookup"><span data-stu-id="82cf0-108">Add your XML comments in base classes or interfaces and let InheritDoc copy the comments to implementing classes.</span></span>

<span data-ttu-id="82cf0-109">同期メソッドに XML コメントを追加し、InheritDoc によってそのコメントが同じメソッドの非同期バージョンにコピーされるようにします。</span><span class="sxs-lookup"><span data-stu-id="82cf0-109">Add your XML comments to your synchronous methods and let InheritDoc copy the comments to your asynchronous versions of the same methods.</span></span>  

<span data-ttu-id="82cf0-110">特定のメンバーからコメントをコピーしたい場合は、`cref` 属性を使用してそのメンバーを指定できます。</span><span class="sxs-lookup"><span data-stu-id="82cf0-110">If you want to copy the comments from a specific member you can use the `cref` attribute to specify the member.</span></span>
  
## <a name="examples"></a><span data-ttu-id="82cf0-111">使用例</span><span class="sxs-lookup"><span data-stu-id="82cf0-111">Examples</span></span>
[!code-csharp[csProgGuideDocComments#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#16)]  

[!code-csharp[csProgGuideDocComments#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#17)]  

## <a name="see-also"></a><span data-ttu-id="82cf0-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="82cf0-112">See also</span></span>

- [<span data-ttu-id="82cf0-113">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="82cf0-113">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="82cf0-114">ドキュメント コメントとして推奨されるタグ</span><span class="sxs-lookup"><span data-stu-id="82cf0-114">Recommended Tags for Documentation Comments</span></span>](./recommended-tags-for-documentation-comments.md)
