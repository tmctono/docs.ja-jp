---
title: <typeparamref> - C# プログラミング ガイド
description: XML <typeparamref> タグについて説明します。 このタグを使用すると、ドキュメント ファイルを使用するときに、何らかの方法で単語の書式を指定できます (斜体など)。
ms.date: 07/20/2015
f1_keywords:
- typeparamref
helpviewer_keywords:
- typeparamref C# XML tag
- <typeparamref> C# XML tag
ms.assetid: 6d8ffc58-12c5-4688-8db6-833a7ded5886
ms.openlocfilehash: a39e896f1242452c7bcc94faa1e7ef3086ae2149
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2020
ms.locfileid: "87380723"
---
# <a name="typeparamref-c-programming-guide"></a><span data-ttu-id="4d2f3-104">\<typeparamref> (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="4d2f3-104">\<typeparamref> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="4d2f3-105">構文</span><span class="sxs-lookup"><span data-stu-id="4d2f3-105">Syntax</span></span>

```xml
<typeparamref name="name"/>
```

## <a name="parameters"></a><span data-ttu-id="4d2f3-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4d2f3-106">Parameters</span></span>

- `name`

  <span data-ttu-id="4d2f3-107">型パラメーターの名前。</span><span class="sxs-lookup"><span data-stu-id="4d2f3-107">The name of the type parameter.</span></span> <span data-ttu-id="4d2f3-108">名前は二重引用符 (" ") で囲みます。</span><span class="sxs-lookup"><span data-stu-id="4d2f3-108">Enclose the name in double quotation marks (" ").</span></span>

## <a name="remarks"></a><span data-ttu-id="4d2f3-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="4d2f3-109">Remarks</span></span>

<span data-ttu-id="4d2f3-110">ジェネリック型およびメソッドの型パラメーターの詳細については、「[ジェネリック (C# プログラミング ガイド)](../generics/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4d2f3-110">For more information on type parameters in generic types and methods, see [Generics](../generics/index.md).</span></span>

<span data-ttu-id="4d2f3-111">ドキュメント ファイルを使用するときに何らかの方法で単語の書式 (斜体など) を指定するには、このタグを使用します。</span><span class="sxs-lookup"><span data-stu-id="4d2f3-111">Use this tag to enable consumers of the documentation file to format the word in some distinct way, for example in italics.</span></span>

<span data-ttu-id="4d2f3-112">コンパイル時に [-doc](../../language-reference/compiler-options/doc-compiler-option.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="4d2f3-112">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="4d2f3-113">例</span><span class="sxs-lookup"><span data-stu-id="4d2f3-113">Example</span></span>

[!code-csharp[csProgGuideDocComments#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#13)]

## <a name="see-also"></a><span data-ttu-id="4d2f3-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="4d2f3-114">See also</span></span>

- [<span data-ttu-id="4d2f3-115">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="4d2f3-115">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="4d2f3-116">ドキュメント コメント用の推奨タグ</span><span class="sxs-lookup"><span data-stu-id="4d2f3-116">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
