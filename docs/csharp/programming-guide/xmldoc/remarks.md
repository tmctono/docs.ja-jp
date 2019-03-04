---
title: <remarks> - C# プログラミング ガイド
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- remarks
- <remarks>
helpviewer_keywords:
- remarks C# XML tag
- <remarks> C# XML tag
ms.assetid: f8641391-31f3-4735-af7a-c502a5b6a251
ms.openlocfilehash: 3e6625c55a6f5c29fb55bff2eb87959f3237652e
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2019
ms.locfileid: "56975851"
---
# <a name="remarks-c-programming-guide"></a><span data-ttu-id="d465c-102">\<remarks> (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="d465c-102">\<remarks> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="d465c-103">構文</span><span class="sxs-lookup"><span data-stu-id="d465c-103">Syntax</span></span>  
  
```xml  
<remarks>description</remarks>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d465c-104">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d465c-104">Parameters</span></span>  
 `Description`  
 <span data-ttu-id="d465c-105">メンバーの説明。</span><span class="sxs-lookup"><span data-stu-id="d465c-105">A description of the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d465c-106">解説</span><span class="sxs-lookup"><span data-stu-id="d465c-106">Remarks</span></span>  
 <span data-ttu-id="d465c-107">\<remarks> タグを使用して、型の情報を追加し、[\<summary>](../../../csharp/programming-guide/xmldoc/summary.md) で指定された情報を補足します。</span><span class="sxs-lookup"><span data-stu-id="d465c-107">The \<remarks> tag is used to add information about a type, supplementing the information specified with [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md).</span></span> <span data-ttu-id="d465c-108">この情報はオブジェクト ブラウザー ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="d465c-108">This information is displayed in the Object Browser window.</span></span>  
  
 <span data-ttu-id="d465c-109">コンパイル時に [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="d465c-109">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d465c-110">例</span><span class="sxs-lookup"><span data-stu-id="d465c-110">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#9)]  
  
## <a name="see-also"></a><span data-ttu-id="d465c-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="d465c-111">See also</span></span>

- [<span data-ttu-id="d465c-112">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="d465c-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="d465c-113">ドキュメント コメントとして推奨されるタグ</span><span class="sxs-lookup"><span data-stu-id="d465c-113">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
