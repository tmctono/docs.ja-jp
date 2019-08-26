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
ms.openlocfilehash: 822ca8feafe48402f8217c10ef37fcdb1576c27a
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2019
ms.locfileid: "69587754"
---
# <a name="remarks-c-programming-guide"></a><span data-ttu-id="4c5fe-102">\<remarks> (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="4c5fe-102">\<remarks> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="4c5fe-103">構文</span><span class="sxs-lookup"><span data-stu-id="4c5fe-103">Syntax</span></span>  
  
```xml  
<remarks>description</remarks>  
```  
  
## <a name="parameters"></a><span data-ttu-id="4c5fe-104">parameters</span><span class="sxs-lookup"><span data-stu-id="4c5fe-104">Parameters</span></span>  
 `Description`  
 <span data-ttu-id="4c5fe-105">メンバーの説明。</span><span class="sxs-lookup"><span data-stu-id="4c5fe-105">A description of the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4c5fe-106">解説</span><span class="sxs-lookup"><span data-stu-id="4c5fe-106">Remarks</span></span>  
 <span data-ttu-id="4c5fe-107">\<remarks> タグを使用して、型の情報を追加し、[\<summary>](./summary.md) で指定された情報を補足します。</span><span class="sxs-lookup"><span data-stu-id="4c5fe-107">The \<remarks> tag is used to add information about a type, supplementing the information specified with [\<summary>](./summary.md).</span></span> <span data-ttu-id="4c5fe-108">この情報はオブジェクト ブラウザー ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="4c5fe-108">This information is displayed in the Object Browser window.</span></span>  
  
 <span data-ttu-id="4c5fe-109">コンパイル時に [/doc](../../language-reference/compiler-options/doc-compiler-option.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="4c5fe-109">Compile with [/doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4c5fe-110">例</span><span class="sxs-lookup"><span data-stu-id="4c5fe-110">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#9)]  
  
## <a name="see-also"></a><span data-ttu-id="4c5fe-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="4c5fe-111">See also</span></span>

- [<span data-ttu-id="4c5fe-112">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="4c5fe-112">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="4c5fe-113">ドキュメント コメントとして推奨されるタグ</span><span class="sxs-lookup"><span data-stu-id="4c5fe-113">Recommended Tags for Documentation Comments</span></span>](./recommended-tags-for-documentation-comments.md)
