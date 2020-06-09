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
ms.openlocfilehash: a09bcd069e2f85f4a21736cb218c42c0e481d70b
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287468"
---
# <a name="c-c-programming-guide"></a><span data-ttu-id="9d751-102">\<c> (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="9d751-102">\<c> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="9d751-103">構文</span><span class="sxs-lookup"><span data-stu-id="9d751-103">Syntax</span></span>

```xml
<c>text</c>
```

## <a name="parameters"></a><span data-ttu-id="9d751-104">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9d751-104">Parameters</span></span>

- `text`

  <span data-ttu-id="9d751-105">コードとして指定するテキストです。</span><span class="sxs-lookup"><span data-stu-id="9d751-105">The text you would like to indicate as code.</span></span>

## <a name="remarks"></a><span data-ttu-id="9d751-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="9d751-106">Remarks</span></span>

<span data-ttu-id="9d751-107">`<c>` タグを使用すると、説明内のテキストをコードとしてマークする必要があることを指定できます。</span><span class="sxs-lookup"><span data-stu-id="9d751-107">The `<c>` tag gives you a way to indicate that text within a description should be marked as code.</span></span> <span data-ttu-id="9d751-108">複数行をコードとして示す場合は、[\<code>](./code.md) を使用します。</span><span class="sxs-lookup"><span data-stu-id="9d751-108">Use [\<code>](./code.md) to indicate multiple lines as code.</span></span>

<span data-ttu-id="9d751-109">コンパイル時に [-doc](../../language-reference/compiler-options/doc-compiler-option.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="9d751-109">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="9d751-110">例</span><span class="sxs-lookup"><span data-stu-id="9d751-110">Example</span></span>

[!code-csharp[csProgGuideDocComments#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#2)]
  
## <a name="see-also"></a><span data-ttu-id="9d751-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="9d751-111">See also</span></span>

- [<span data-ttu-id="9d751-112">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="9d751-112">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="9d751-113">ドキュメント コメント用の推奨タグ</span><span class="sxs-lookup"><span data-stu-id="9d751-113">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
