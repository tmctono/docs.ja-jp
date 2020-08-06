---
title: <remarks> - C# プログラミング ガイド
description: XML タグについて説明 <remarks> します。 このタグを使用して型の情報を追加し、指定された情報を補足します <summary>.
ms.date: 07/20/2015
f1_keywords:
- remarks
- <remarks>
helpviewer_keywords:
- remarks C# XML tag
- <remarks> C# XML tag
ms.assetid: f8641391-31f3-4735-af7a-c502a5b6a251
ms.openlocfilehash: d38905d100e24158e7a1412f6be9f01a7ced2382
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381503"
---
# <a name="remarks-c-programming-guide"></a><span data-ttu-id="bdf3d-106">\<remarks> (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="bdf3d-106">\<remarks> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="bdf3d-107">構文</span><span class="sxs-lookup"><span data-stu-id="bdf3d-107">Syntax</span></span>

```xml
<remarks>description</remarks>
```

## <a name="parameters"></a><span data-ttu-id="bdf3d-108">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bdf3d-108">Parameters</span></span>

- `Description`

  <span data-ttu-id="bdf3d-109">メンバーの説明。</span><span class="sxs-lookup"><span data-stu-id="bdf3d-109">A description of the member.</span></span>

## <a name="remarks"></a><span data-ttu-id="bdf3d-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="bdf3d-110">Remarks</span></span>

<span data-ttu-id="bdf3d-111">`<remarks>` タグを使用して、型の情報を追加し、[\<summary>](./summary.md) で指定された情報を補足します。</span><span class="sxs-lookup"><span data-stu-id="bdf3d-111">The `<remarks>` tag is used to add information about a type, supplementing the information specified with [\<summary>](./summary.md).</span></span> <span data-ttu-id="bdf3d-112">この情報はオブジェクト ブラウザー ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="bdf3d-112">This information is displayed in the Object Browser window.</span></span>

<span data-ttu-id="bdf3d-113">コンパイル時に [-doc](../../language-reference/compiler-options/doc-compiler-option.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="bdf3d-113">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="bdf3d-114">例</span><span class="sxs-lookup"><span data-stu-id="bdf3d-114">Example</span></span>

[!code-csharp[csProgGuideDocComments#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#9)]

## <a name="see-also"></a><span data-ttu-id="bdf3d-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="bdf3d-115">See also</span></span>

- [<span data-ttu-id="bdf3d-116">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="bdf3d-116">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="bdf3d-117">ドキュメント コメント用の推奨タグ</span><span class="sxs-lookup"><span data-stu-id="bdf3d-117">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
