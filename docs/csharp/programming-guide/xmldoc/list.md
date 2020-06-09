---
title: <list> - C# プログラミング ガイド
ms.date: 07/20/2015
f1_keywords:
- list
- <list>
helpviewer_keywords:
- list C# XML tag
- listheader C# XML tag
- <listheader> C# XML tag
- item C# XML tag
- <item> C# XML tag
- <list> C# XML tag
ms.assetid: c9620b1b-c2e6-43f1-ab88-8ab47308ffec
ms.openlocfilehash: 78eec992671dab1aa59717a007a8e3a2662f6e87
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287338"
---
# <a name="list-c-programming-guide"></a><span data-ttu-id="802f7-102">\<list> (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="802f7-102">\<list> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="802f7-103">構文</span><span class="sxs-lookup"><span data-stu-id="802f7-103">Syntax</span></span>

```xml
<list type="bullet|number|table">
    <listheader>
        <term>term</term>
        <description>description</description>
    </listheader>
    <item>
        <term>term</term>
        <description>description</description>
    </item>
</list>
```

## <a name="parameters"></a><span data-ttu-id="802f7-104">パラメーター</span><span class="sxs-lookup"><span data-stu-id="802f7-104">Parameters</span></span>

- `term`

  <span data-ttu-id="802f7-105">定義される用語であり、`description` で定義されます。</span><span class="sxs-lookup"><span data-stu-id="802f7-105">A term to define, which will be defined in `description`.</span></span>

- `description`

  <span data-ttu-id="802f7-106">行頭文字または番号付きリストの項目、または `term` の定義です。</span><span class="sxs-lookup"><span data-stu-id="802f7-106">Either an item in a bullet or numbered list or the definition of a `term`.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="802f7-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="802f7-107">Remarks</span></span>

<span data-ttu-id="802f7-108">`<listheader>` ブロックを使用して、テーブルまたは定義リストの見出し行を定義します。</span><span class="sxs-lookup"><span data-stu-id="802f7-108">The `<listheader>` block is used to define the heading row of either a table or definition list.</span></span> <span data-ttu-id="802f7-109">テーブルを定義するときにのみ、見出しの用語のエントリを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="802f7-109">When defining a table, you only need to supply an entry for term in the heading.</span></span>

<span data-ttu-id="802f7-110">リストの各項目は、`<item>` ブロックで指定されます。</span><span class="sxs-lookup"><span data-stu-id="802f7-110">Each item in the list is specified with an `<item>` block.</span></span> <span data-ttu-id="802f7-111">定義リストを作成する場合は、`term` と `description` の両方を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="802f7-111">When creating a definition list, you will need to specify both `term` and `description`.</span></span> <span data-ttu-id="802f7-112">ただし、テーブル、箇条書きリスト、または番号付きリストの場合は、`description` のエントリを指定するだけで済みます。</span><span class="sxs-lookup"><span data-stu-id="802f7-112">However, for a table, bulleted list, or numbered list, you only need to supply an entry for `description`.</span></span>

<span data-ttu-id="802f7-113">リストまたはテーブルでは、必要な数の `<item>` ブロックを使用できます。</span><span class="sxs-lookup"><span data-stu-id="802f7-113">A list or table can have as many `<item>` blocks as needed.</span></span>

<span data-ttu-id="802f7-114">コンパイル時に [-doc](../../language-reference/compiler-options/doc-compiler-option.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="802f7-114">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="802f7-115">例</span><span class="sxs-lookup"><span data-stu-id="802f7-115">Example</span></span>

[!code-csharp[csProgGuideDocComments#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#6)]

## <a name="see-also"></a><span data-ttu-id="802f7-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="802f7-116">See also</span></span>

- [<span data-ttu-id="802f7-117">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="802f7-117">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="802f7-118">ドキュメント コメント用の推奨タグ</span><span class="sxs-lookup"><span data-stu-id="802f7-118">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
