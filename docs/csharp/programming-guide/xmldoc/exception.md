---
title: <exception> - C# プログラミング ガイド
description: XML <exception> タグについて説明します。 このタグによって、スローできる例外を指定できます。これはメソッド、プロパティ、イベント、およびインデクサーに適用できます。
ms.date: 07/20/2015
f1_keywords:
- exception
- <exception>
helpviewer_keywords:
- <exception> C# XML tag
- exception C# XML tag
ms.assetid: dd73aac5-3c74-4fcf-9498-f11bff3a2f3c
ms.openlocfilehash: 22a28f3fe6de5a0db9aea0f1fd7963d4e6fcee05
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381737"
---
# <a name="exception-c-programming-guide"></a><span data-ttu-id="c9280-104">\<exception> (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="c9280-104">\<exception> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="c9280-105">構文</span><span class="sxs-lookup"><span data-stu-id="c9280-105">Syntax</span></span>

```xml
<exception cref="member">description</exception>
```

## <a name="parameters"></a><span data-ttu-id="c9280-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c9280-106">Parameters</span></span>

- <span data-ttu-id="c9280-107">cref = "`member`"</span><span class="sxs-lookup"><span data-stu-id="c9280-107">cref = " `member`"</span></span>

  <span data-ttu-id="c9280-108">現在のコンパイル環境から使用できる例外の参照。</span><span class="sxs-lookup"><span data-stu-id="c9280-108">A reference to an exception that is available from the current compilation environment.</span></span> <span data-ttu-id="c9280-109">コンパイラは、指定された例外が存在し、出力の XML で `member` が正規要素名に変換されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c9280-109">The compiler checks that the given exception exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="c9280-110">`member` は、二重引用符 (" ") で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9280-110">`member` must appear within double quotation marks (" ").</span></span>

  <span data-ttu-id="c9280-111">ジェネリック型を参照するよう `member` を書式設定する方法について詳しくは、[XML ファイルの処理](processing-the-xml-file.md)に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c9280-111">For more information on how to format `member` to reference a generic type, see [Processing the XML File](processing-the-xml-file.md).</span></span>

- `description`

  <span data-ttu-id="c9280-112">例外の説明。</span><span class="sxs-lookup"><span data-stu-id="c9280-112">A description of the exception.</span></span>

## <a name="remarks"></a><span data-ttu-id="c9280-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="c9280-113">Remarks</span></span>

<span data-ttu-id="c9280-114">`<exception>` タグを使用すると、スローできる例外を指定できます。</span><span class="sxs-lookup"><span data-stu-id="c9280-114">The `<exception>` tag lets you specify which exceptions can be thrown.</span></span> <span data-ttu-id="c9280-115">このタブは、メソッド、プロパティ、イベント、インデクサーの定義に適用できます。</span><span class="sxs-lookup"><span data-stu-id="c9280-115">This tag can be applied to definitions for methods, properties, events, and indexers.</span></span>

<span data-ttu-id="c9280-116">コンパイル時に [-doc](../../language-reference/compiler-options/doc-compiler-option.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="c9280-116">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

<span data-ttu-id="c9280-117">例外処理の詳細については、「[例外と例外処理](../exceptions/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c9280-117">For more information about exception handling, see [Exceptions and Exception Handling](../exceptions/index.md).</span></span>

## <a name="example"></a><span data-ttu-id="c9280-118">例</span><span class="sxs-lookup"><span data-stu-id="c9280-118">Example</span></span>

[!code-csharp[csProgGuideDocComments#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#4)]

## <a name="see-also"></a><span data-ttu-id="c9280-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="c9280-119">See also</span></span>

- [<span data-ttu-id="c9280-120">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="c9280-120">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="c9280-121">ドキュメント コメント用の推奨タグ</span><span class="sxs-lookup"><span data-stu-id="c9280-121">Recommended tags for documentation comments</span></span>](recommended-tags-for-documentation-comments.md)
