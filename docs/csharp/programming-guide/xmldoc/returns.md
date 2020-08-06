---
title: <returns> - C# プログラミング ガイド
description: XML タグについて説明 <returns> します。 このタグは、メソッド宣言のコメントで戻り値を記述するために使用されます。
ms.date: 07/20/2015
f1_keywords:
- returns
- <returns>
helpviewer_keywords:
- <returns> C# XML tag
- returns C# XML tag
ms.assetid: bb2d9958-62fc-47c7-9511-6311171f119f
ms.openlocfilehash: e461d46df619a351048ae7942e59847d39e490f9
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381399"
---
# <a name="returns-c-programming-guide"></a><span data-ttu-id="91a7d-105">\<returns> (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="91a7d-105">\<returns> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="91a7d-106">構文</span><span class="sxs-lookup"><span data-stu-id="91a7d-106">Syntax</span></span>

```xml
<returns>description</returns>
```

## <a name="parameters"></a><span data-ttu-id="91a7d-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="91a7d-107">Parameters</span></span>

- `description`

  <span data-ttu-id="91a7d-108">戻り値の説明。</span><span class="sxs-lookup"><span data-stu-id="91a7d-108">A description of the return value.</span></span>

## <a name="remarks"></a><span data-ttu-id="91a7d-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="91a7d-109">Remarks</span></span>

<span data-ttu-id="91a7d-110">`<returns>` タグは、戻り値を説明するためにメソッドの宣言のコメントで使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="91a7d-110">The `<returns>` tag should be used in the comment for a method declaration to describe the return value.</span></span>

<span data-ttu-id="91a7d-111">コンパイル時に [-doc](../../language-reference/compiler-options/doc-compiler-option.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="91a7d-111">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="91a7d-112">例</span><span class="sxs-lookup"><span data-stu-id="91a7d-112">Example</span></span>

[!code-csharp[csProgGuideDocComments#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#10)]

## <a name="see-also"></a><span data-ttu-id="91a7d-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="91a7d-113">See also</span></span>

- [<span data-ttu-id="91a7d-114">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="91a7d-114">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="91a7d-115">ドキュメント コメント用の推奨タグ</span><span class="sxs-lookup"><span data-stu-id="91a7d-115">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
