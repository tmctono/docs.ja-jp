---
title: <returns> - C# プログラミング ガイド
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- returns
- <returns>
helpviewer_keywords:
- <returns> C# XML tag
- returns C# XML tag
ms.assetid: bb2d9958-62fc-47c7-9511-6311171f119f
ms.openlocfilehash: e0beb366f7dc568c6efdc50c9abedb419c01e61b
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57477637"
---
# <a name="returns-c-programming-guide"></a><span data-ttu-id="accac-102">\<returns> (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="accac-102">\<returns> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="accac-103">構文</span><span class="sxs-lookup"><span data-stu-id="accac-103">Syntax</span></span>  
  
```xml  
<returns>description</returns>  
```  
  
## <a name="parameters"></a><span data-ttu-id="accac-104">パラメーター</span><span class="sxs-lookup"><span data-stu-id="accac-104">Parameters</span></span>  
 `description`  
 <span data-ttu-id="accac-105">戻り値の説明。</span><span class="sxs-lookup"><span data-stu-id="accac-105">A description of the return value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="accac-106">解説</span><span class="sxs-lookup"><span data-stu-id="accac-106">Remarks</span></span>  
 <span data-ttu-id="accac-107">\<returns> タグは、戻り値を説明するためにメソッドの宣言のコメントで使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="accac-107">The \<returns> tag should be used in the comment for a method declaration to describe the return value.</span></span>  
  
 <span data-ttu-id="accac-108">コンパイル時に [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="accac-108">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="accac-109">例</span><span class="sxs-lookup"><span data-stu-id="accac-109">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#10)]  
  
## <a name="see-also"></a><span data-ttu-id="accac-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="accac-110">See also</span></span>

- [<span data-ttu-id="accac-111">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="accac-111">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="accac-112">ドキュメント コメントとして推奨されるタグ</span><span class="sxs-lookup"><span data-stu-id="accac-112">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
