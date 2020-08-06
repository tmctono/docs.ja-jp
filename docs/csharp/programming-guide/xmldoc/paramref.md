---
title: <paramref> - C# プログラミング ガイド
description: XML <paramref> タグについて説明します。 このタグを使用すると、コード内の単語がパラメーターであると示すことができます。
ms.date: 07/20/2015
f1_keywords:
- paramref
- <paramref>
helpviewer_keywords:
- <paramref> C# XML tag
- paramref C# XML tag
ms.assetid: 756c24c1-f591-40e8-a838-559761539b0b
ms.openlocfilehash: 133f43abfaf349806404d6d37fb472e3145c51b7
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381841"
---
# <a name="paramref-c-programming-guide"></a><span data-ttu-id="8e7fe-104">\<paramref> (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="8e7fe-104">\<paramref> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="8e7fe-105">構文</span><span class="sxs-lookup"><span data-stu-id="8e7fe-105">Syntax</span></span>

```xml
<paramref name="name"/>
```

## <a name="parameters"></a><span data-ttu-id="8e7fe-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8e7fe-106">Parameters</span></span>

- `name`

  <span data-ttu-id="8e7fe-107">参照されるパラメーターの名前です。</span><span class="sxs-lookup"><span data-stu-id="8e7fe-107">The name of the parameter to refer to.</span></span> <span data-ttu-id="8e7fe-108">名前は二重引用符 (" ") で囲みます。</span><span class="sxs-lookup"><span data-stu-id="8e7fe-108">Enclose the name in double quotation marks (" ").</span></span>

## <a name="remarks"></a><span data-ttu-id="8e7fe-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="8e7fe-109">Remarks</span></span>

<span data-ttu-id="8e7fe-110">`<paramref>` タグを使用すると、`<summary>` または `<remarks>` ブロックなどのコード コメント内の単語がパラメーターを参照することを示すことができます。</span><span class="sxs-lookup"><span data-stu-id="8e7fe-110">The `<paramref>` tag gives you a way to indicate that a word in the code comments, for example in a `<summary>` or `<remarks>` block refers to a parameter.</span></span> <span data-ttu-id="8e7fe-111">この単語を、太字や斜体のフォントを使うなど、何らかの独自の方法で書式設定するために XML ファイルを処理できます。</span><span class="sxs-lookup"><span data-stu-id="8e7fe-111">The XML file can be processed to format this word in some distinct way, such as with a bold or italic font.</span></span>

<span data-ttu-id="8e7fe-112">コンパイル時に [-doc](../../language-reference/compiler-options/doc-compiler-option.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="8e7fe-112">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="8e7fe-113">例</span><span class="sxs-lookup"><span data-stu-id="8e7fe-113">Example</span></span>

[!code-csharp[csProgGuideDocComments#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#7)]

## <a name="see-also"></a><span data-ttu-id="8e7fe-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="8e7fe-114">See also</span></span>

- [<span data-ttu-id="8e7fe-115">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="8e7fe-115">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="8e7fe-116">ドキュメント コメント用の推奨タグ</span><span class="sxs-lookup"><span data-stu-id="8e7fe-116">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
