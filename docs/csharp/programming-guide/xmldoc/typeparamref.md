---
title: <typeparamref> - C# プログラミング ガイド
ms.date: 07/20/2015
f1_keywords:
- typeparamref
helpviewer_keywords:
- typeparamref C# XML tag
- <typeparamref> C# XML tag
ms.assetid: 6d8ffc58-12c5-4688-8db6-833a7ded5886
ms.openlocfilehash: 266eadad322fd3c4167c7a911cb57ef1e1333012
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "76789656"
---
# <a name="typeparamref-c-programming-guide"></a><span data-ttu-id="73349-102">\<typeparamref> (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="73349-102">\<typeparamref> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="73349-103">構文</span><span class="sxs-lookup"><span data-stu-id="73349-103">Syntax</span></span>

```xml
<typeparamref name="name"/>
```

## <a name="parameters"></a><span data-ttu-id="73349-104">パラメーター</span><span class="sxs-lookup"><span data-stu-id="73349-104">Parameters</span></span>

- `name`

  <span data-ttu-id="73349-105">型パラメーターの名前。</span><span class="sxs-lookup"><span data-stu-id="73349-105">The name of the type parameter.</span></span> <span data-ttu-id="73349-106">名前は二重引用符 (" ") で囲みます。</span><span class="sxs-lookup"><span data-stu-id="73349-106">Enclose the name in double quotation marks (" ").</span></span>

## <a name="remarks"></a><span data-ttu-id="73349-107">解説</span><span class="sxs-lookup"><span data-stu-id="73349-107">Remarks</span></span>

<span data-ttu-id="73349-108">ジェネリック型およびメソッドの型パラメーターの詳細については、「[ジェネリック (C# プログラミング ガイド)](../generics/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="73349-108">For more information on type parameters in generic types and methods, see [Generics](../generics/index.md).</span></span>

<span data-ttu-id="73349-109">ドキュメント ファイルを使用するときに何らかの方法で単語の書式 (斜体など) を指定するには、このタグを使用します。</span><span class="sxs-lookup"><span data-stu-id="73349-109">Use this tag to enable consumers of the documentation file to format the word in some distinct way, for example in italics.</span></span>

<span data-ttu-id="73349-110">コンパイル時に [-doc](../../language-reference/compiler-options/doc-compiler-option.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="73349-110">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="73349-111">例</span><span class="sxs-lookup"><span data-stu-id="73349-111">Example</span></span>

[!code-csharp[csProgGuideDocComments#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#13)]

## <a name="see-also"></a><span data-ttu-id="73349-112">参照</span><span class="sxs-lookup"><span data-stu-id="73349-112">See also</span></span>

- [<span data-ttu-id="73349-113">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="73349-113">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="73349-114">ドキュメント コメント用の推奨タグ</span><span class="sxs-lookup"><span data-stu-id="73349-114">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
