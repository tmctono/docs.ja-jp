---
title: <c> - C# プログラミング ガイド
ms.date: 07/20/2015
f1_keywords:
- c
- <c>
helpviewer_keywords:
- text, marking as code [C#]
- code, marking text as [C#]
- c C# XML tag
- <c> C# XML tag
ms.assetid: aad5b16e-a29e-445e-bd0d-eea0b138d7b2
ms.openlocfilehash: d5b28ee6db52d191f8454592d792ac0a1e1dc73b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "76793451"
---
# <a name="c-c-programming-guide"></a><span data-ttu-id="a4b75-102">\<c> (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="a4b75-102">\<c> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="a4b75-103">構文</span><span class="sxs-lookup"><span data-stu-id="a4b75-103">Syntax</span></span>

```xml
<c>text</c>
```

## <a name="parameters"></a><span data-ttu-id="a4b75-104">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a4b75-104">Parameters</span></span>

- `text`

  <span data-ttu-id="a4b75-105">コードとして指定するテキストです。</span><span class="sxs-lookup"><span data-stu-id="a4b75-105">The text you would like to indicate as code.</span></span>

## <a name="remarks"></a><span data-ttu-id="a4b75-106">解説</span><span class="sxs-lookup"><span data-stu-id="a4b75-106">Remarks</span></span>

<span data-ttu-id="a4b75-107">\<c> タグを使用すると、説明内のテキストをコードとして指定できます。</span><span class="sxs-lookup"><span data-stu-id="a4b75-107">The \<c> tag gives you a way to indicate that text within a description should be marked as code.</span></span> <span data-ttu-id="a4b75-108">複数行をコードとして指定する場合は、[\<code>](./code.md) タグを使用します。</span><span class="sxs-lookup"><span data-stu-id="a4b75-108">Use [\<code>](./code.md) to indicate multiple lines as code.</span></span>

<span data-ttu-id="a4b75-109">コンパイル時に [-doc](../../language-reference/compiler-options/doc-compiler-option.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="a4b75-109">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="a4b75-110">例</span><span class="sxs-lookup"><span data-stu-id="a4b75-110">Example</span></span>

[!code-csharp[csProgGuideDocComments#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#2)]
  
## <a name="see-also"></a><span data-ttu-id="a4b75-111">参照</span><span class="sxs-lookup"><span data-stu-id="a4b75-111">See also</span></span>

- [<span data-ttu-id="a4b75-112">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="a4b75-112">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="a4b75-113">ドキュメント コメント用の推奨タグ</span><span class="sxs-lookup"><span data-stu-id="a4b75-113">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
