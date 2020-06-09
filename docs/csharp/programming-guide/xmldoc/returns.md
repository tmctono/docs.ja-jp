---
title: <returns> - C# プログラミング ガイド
ms.date: 07/20/2015
f1_keywords:
- returns
- <returns>
helpviewer_keywords:
- <returns> C# XML tag
- returns C# XML tag
ms.assetid: bb2d9958-62fc-47c7-9511-6311171f119f
ms.openlocfilehash: 7bc950a8d89a3ac2b5c3b7a68e05c7778e97f85c
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287234"
---
# <a name="returns-c-programming-guide"></a><span data-ttu-id="b2c70-102">\<returns> (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="b2c70-102">\<returns> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="b2c70-103">構文</span><span class="sxs-lookup"><span data-stu-id="b2c70-103">Syntax</span></span>

```xml
<returns>description</returns>
```

## <a name="parameters"></a><span data-ttu-id="b2c70-104">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b2c70-104">Parameters</span></span>

- `description`

  <span data-ttu-id="b2c70-105">戻り値の説明。</span><span class="sxs-lookup"><span data-stu-id="b2c70-105">A description of the return value.</span></span>

## <a name="remarks"></a><span data-ttu-id="b2c70-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="b2c70-106">Remarks</span></span>

<span data-ttu-id="b2c70-107">`<returns>` タグは、戻り値を説明するためにメソッドの宣言のコメントで使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2c70-107">The `<returns>` tag should be used in the comment for a method declaration to describe the return value.</span></span>

<span data-ttu-id="b2c70-108">コンパイル時に [-doc](../../language-reference/compiler-options/doc-compiler-option.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="b2c70-108">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="b2c70-109">例</span><span class="sxs-lookup"><span data-stu-id="b2c70-109">Example</span></span>

[!code-csharp[csProgGuideDocComments#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#10)]

## <a name="see-also"></a><span data-ttu-id="b2c70-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="b2c70-110">See also</span></span>

- [<span data-ttu-id="b2c70-111">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="b2c70-111">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="b2c70-112">ドキュメント コメント用の推奨タグ</span><span class="sxs-lookup"><span data-stu-id="b2c70-112">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
