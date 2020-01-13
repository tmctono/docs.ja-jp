---
title: <remarks> - C# プログラミング ガイド
ms.date: 07/20/2015
f1_keywords:
- remarks
- <remarks>
helpviewer_keywords:
- remarks C# XML tag
- <remarks> C# XML tag
ms.assetid: f8641391-31f3-4735-af7a-c502a5b6a251
ms.openlocfilehash: 2391a8ee0bb55402ff5183c837e36d04a39e6555
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711702"
---
# <a name="remarks-c-programming-guide"></a><span data-ttu-id="f8a0f-102">\<remarks> (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="f8a0f-102">\<remarks> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="f8a0f-103">構文</span><span class="sxs-lookup"><span data-stu-id="f8a0f-103">Syntax</span></span>  
  
```xml  
<remarks>description</remarks>  
```  
  
## <a name="parameters"></a><span data-ttu-id="f8a0f-104">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f8a0f-104">Parameters</span></span>  
 `Description`  
 <span data-ttu-id="f8a0f-105">メンバーの説明。</span><span class="sxs-lookup"><span data-stu-id="f8a0f-105">A description of the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f8a0f-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="f8a0f-106">Remarks</span></span>  
 <span data-ttu-id="f8a0f-107">\<remarks> タグを使用して、型の情報を追加し、[\<summary>](./summary.md) で指定された情報を補足します。</span><span class="sxs-lookup"><span data-stu-id="f8a0f-107">The \<remarks> tag is used to add information about a type, supplementing the information specified with [\<summary>](./summary.md).</span></span> <span data-ttu-id="f8a0f-108">この情報はオブジェクト ブラウザー ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="f8a0f-108">This information is displayed in the Object Browser window.</span></span>  
  
 <span data-ttu-id="f8a0f-109">コンパイル時に [-doc](../../language-reference/compiler-options/doc-compiler-option.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="f8a0f-109">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f8a0f-110">例</span><span class="sxs-lookup"><span data-stu-id="f8a0f-110">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#9)]  
  
## <a name="see-also"></a><span data-ttu-id="f8a0f-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="f8a0f-111">See also</span></span>

- [<span data-ttu-id="f8a0f-112">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="f8a0f-112">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="f8a0f-113">ドキュメント コメントとして推奨されるタグ</span><span class="sxs-lookup"><span data-stu-id="f8a0f-113">Recommended Tags for Documentation Comments</span></span>](./recommended-tags-for-documentation-comments.md)
