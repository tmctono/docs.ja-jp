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
ms.openlocfilehash: e37dac9cb9fed1df6ca027f09f2c95dbbc8ea66d
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793372"
---
# <a name="remarks-c-programming-guide"></a><span data-ttu-id="ceabb-102">\<remarks> (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="ceabb-102">\<remarks> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="ceabb-103">構文</span><span class="sxs-lookup"><span data-stu-id="ceabb-103">Syntax</span></span>

```xml
<remarks>description</remarks>
```

## <a name="parameters"></a><span data-ttu-id="ceabb-104">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ceabb-104">Parameters</span></span>

- `Description`

  <span data-ttu-id="ceabb-105">メンバーの説明。</span><span class="sxs-lookup"><span data-stu-id="ceabb-105">A description of the member.</span></span>

## <a name="remarks"></a><span data-ttu-id="ceabb-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="ceabb-106">Remarks</span></span>

<span data-ttu-id="ceabb-107">\<remarks> タグを使用して、型の情報を追加し、[\<summary>](./summary.md) で指定された情報を補足します。</span><span class="sxs-lookup"><span data-stu-id="ceabb-107">The \<remarks> tag is used to add information about a type, supplementing the information specified with [\<summary>](./summary.md).</span></span> <span data-ttu-id="ceabb-108">この情報はオブジェクト ブラウザー ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="ceabb-108">This information is displayed in the Object Browser window.</span></span>

<span data-ttu-id="ceabb-109">コンパイル時に [-doc](../../language-reference/compiler-options/doc-compiler-option.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="ceabb-109">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="ceabb-110">例</span><span class="sxs-lookup"><span data-stu-id="ceabb-110">Example</span></span>

[!code-csharp[csProgGuideDocComments#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#9)]

## <a name="see-also"></a><span data-ttu-id="ceabb-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="ceabb-111">See also</span></span>

- [<span data-ttu-id="ceabb-112">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="ceabb-112">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="ceabb-113">ドキュメント コメント用の推奨タグ</span><span class="sxs-lookup"><span data-stu-id="ceabb-113">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
