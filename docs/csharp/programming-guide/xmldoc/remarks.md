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
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "76793372"
---
# <a name="remarks-c-programming-guide"></a><span data-ttu-id="4ecf2-102">\<remarks> (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="4ecf2-102">\<remarks> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="4ecf2-103">構文</span><span class="sxs-lookup"><span data-stu-id="4ecf2-103">Syntax</span></span>

```xml
<remarks>description</remarks>
```

## <a name="parameters"></a><span data-ttu-id="4ecf2-104">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4ecf2-104">Parameters</span></span>

- `Description`

  <span data-ttu-id="4ecf2-105">メンバーの説明。</span><span class="sxs-lookup"><span data-stu-id="4ecf2-105">A description of the member.</span></span>

## <a name="remarks"></a><span data-ttu-id="4ecf2-106">解説</span><span class="sxs-lookup"><span data-stu-id="4ecf2-106">Remarks</span></span>

<span data-ttu-id="4ecf2-107">\<remarks> タグを使用して、型の情報を追加し、[\<summary>](./summary.md) で指定された情報を補足します。</span><span class="sxs-lookup"><span data-stu-id="4ecf2-107">The \<remarks> tag is used to add information about a type, supplementing the information specified with [\<summary>](./summary.md).</span></span> <span data-ttu-id="4ecf2-108">この情報はオブジェクト ブラウザー ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="4ecf2-108">This information is displayed in the Object Browser window.</span></span>

<span data-ttu-id="4ecf2-109">コンパイル時に [-doc](../../language-reference/compiler-options/doc-compiler-option.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="4ecf2-109">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="4ecf2-110">例</span><span class="sxs-lookup"><span data-stu-id="4ecf2-110">Example</span></span>

[!code-csharp[csProgGuideDocComments#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#9)]

## <a name="see-also"></a><span data-ttu-id="4ecf2-111">参照</span><span class="sxs-lookup"><span data-stu-id="4ecf2-111">See also</span></span>

- [<span data-ttu-id="4ecf2-112">C# プログラミングガイド</span><span class="sxs-lookup"><span data-stu-id="4ecf2-112">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="4ecf2-113">ドキュメント コメント用の推奨タグ</span><span class="sxs-lookup"><span data-stu-id="4ecf2-113">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
