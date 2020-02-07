---
title: <paramref> - C# プログラミング ガイド
ms.date: 07/20/2015
f1_keywords:
- paramref
- <paramref>
helpviewer_keywords:
- <paramref> C# XML tag
- paramref C# XML tag
ms.assetid: 756c24c1-f591-40e8-a838-559761539b0b
ms.openlocfilehash: 12df257271369dc7f0a5c066b712a8d8e6c38761
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793401"
---
# <a name="paramref-c-programming-guide"></a><span data-ttu-id="74578-102">\<paramref> (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="74578-102">\<paramref> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="74578-103">構文</span><span class="sxs-lookup"><span data-stu-id="74578-103">Syntax</span></span>

```xml
<paramref name="name"/>
```

## <a name="parameters"></a><span data-ttu-id="74578-104">パラメーター</span><span class="sxs-lookup"><span data-stu-id="74578-104">Parameters</span></span>

- `name`

  <span data-ttu-id="74578-105">参照されるパラメーターの名前です。</span><span class="sxs-lookup"><span data-stu-id="74578-105">The name of the parameter to refer to.</span></span> <span data-ttu-id="74578-106">名前は二重引用符 (" ") で囲みます。</span><span class="sxs-lookup"><span data-stu-id="74578-106">Enclose the name in double quotation marks (" ").</span></span>

## <a name="remarks"></a><span data-ttu-id="74578-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="74578-107">Remarks</span></span>

<span data-ttu-id="74578-108">\<paramref> タグを使用すると、\<summary> または \<remarks> ブロックなどのコード コメント内の単語がパラメーターを参照することを示すことができます。</span><span class="sxs-lookup"><span data-stu-id="74578-108">The \<paramref> tag gives you a way to indicate that a word in the code comments, for example in a \<summary> or \<remarks> block refers to a parameter.</span></span> <span data-ttu-id="74578-109">この単語を、太字や斜体のフォントを使うなど、何らかの独自の方法で書式設定するために XML ファイルを処理できます。</span><span class="sxs-lookup"><span data-stu-id="74578-109">The XML file can be processed to format this word in some distinct way, such as with a bold or italic font.</span></span>

<span data-ttu-id="74578-110">コンパイル時に [-doc](../../language-reference/compiler-options/doc-compiler-option.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="74578-110">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="74578-111">例</span><span class="sxs-lookup"><span data-stu-id="74578-111">Example</span></span>

[!code-csharp[csProgGuideDocComments#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#7)]

## <a name="see-also"></a><span data-ttu-id="74578-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="74578-112">See also</span></span>

- [<span data-ttu-id="74578-113">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="74578-113">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="74578-114">ドキュメント コメント用の推奨タグ</span><span class="sxs-lookup"><span data-stu-id="74578-114">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
