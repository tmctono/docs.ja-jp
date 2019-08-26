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
ms.openlocfilehash: 7d4343cf38f0ea1ae42b77cc1d0c755920c4a421
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2019
ms.locfileid: "69587735"
---
# <a name="returns-c-programming-guide"></a><span data-ttu-id="bb3c1-102">\<returns> (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="bb3c1-102">\<returns> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="bb3c1-103">構文</span><span class="sxs-lookup"><span data-stu-id="bb3c1-103">Syntax</span></span>  
  
```xml  
<returns>description</returns>  
```  
  
## <a name="parameters"></a><span data-ttu-id="bb3c1-104">parameters</span><span class="sxs-lookup"><span data-stu-id="bb3c1-104">Parameters</span></span>  
 `description`  
 <span data-ttu-id="bb3c1-105">戻り値の説明。</span><span class="sxs-lookup"><span data-stu-id="bb3c1-105">A description of the return value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bb3c1-106">解説</span><span class="sxs-lookup"><span data-stu-id="bb3c1-106">Remarks</span></span>  
 <span data-ttu-id="bb3c1-107">\<returns> タグは、戻り値を説明するためにメソッドの宣言のコメントで使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb3c1-107">The \<returns> tag should be used in the comment for a method declaration to describe the return value.</span></span>  
  
 <span data-ttu-id="bb3c1-108">コンパイル時に [/doc](../../language-reference/compiler-options/doc-compiler-option.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="bb3c1-108">Compile with [/doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bb3c1-109">例</span><span class="sxs-lookup"><span data-stu-id="bb3c1-109">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#10)]  
  
## <a name="see-also"></a><span data-ttu-id="bb3c1-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="bb3c1-110">See also</span></span>

- [<span data-ttu-id="bb3c1-111">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="bb3c1-111">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="bb3c1-112">ドキュメント コメントとして推奨されるタグ</span><span class="sxs-lookup"><span data-stu-id="bb3c1-112">Recommended Tags for Documentation Comments</span></span>](./recommended-tags-for-documentation-comments.md)
