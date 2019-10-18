---
title: <list> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- listheader XML tag
- <item> XML tag
- <list> XML tag
- <listheader> XML tag
- term XML tag
- list XML tag
- <description> XML tag
- description XML tag
- item XML tag
- <term> XML tag
ms.assetid: ec35fced-d58e-4520-a764-0691256e014b
ms.openlocfilehash: 5d4295d485611e75e8b6c8d8f95e079654f0cfa3
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524749"
---
# <a name="list-visual-basic"></a><span data-ttu-id="ea242-102">\<list > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ea242-102">\<list> (Visual Basic)</span></span>
<span data-ttu-id="ea242-103">リストまたはテーブルを定義します。</span><span class="sxs-lookup"><span data-stu-id="ea242-103">Defines a list or table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea242-104">構文</span><span class="sxs-lookup"><span data-stu-id="ea242-104">Syntax</span></span>  
  
```xml  
<list type="type">  
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
  
## <a name="parameters"></a><span data-ttu-id="ea242-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ea242-105">Parameters</span></span>  
 `type`  
 <span data-ttu-id="ea242-106">リストの型。</span><span class="sxs-lookup"><span data-stu-id="ea242-106">The type of the list.</span></span> <span data-ttu-id="ea242-107">箇条書きの場合は "箇条書き"、番号付きリストの場合は "数値"、2列テーブルの場合は "table" にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea242-107">Must be a "bullet" for a bulleted list, "number" for a numbered list, or "table" for a two-column table.</span></span>  
  
 `term`  
 <span data-ttu-id="ea242-108">@No__t_0 が "table" の場合にのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="ea242-108">Only used when `type` is "table."</span></span> <span data-ttu-id="ea242-109">Description タグで定義されている定義対象の用語。</span><span class="sxs-lookup"><span data-stu-id="ea242-109">A term to define, which is defined in the description tag.</span></span>  
  
 `description`  
 <span data-ttu-id="ea242-110">@No__t_0 が "bullet" または "number" の場合、`description` は `type` が "table" の場合はリスト内の項目であり、`description` は `term` の定義です。</span><span class="sxs-lookup"><span data-stu-id="ea242-110">When `type` is "bullet" or "number," `description` is an item in the list When `type` is "table," `description` is the definition of `term`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ea242-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="ea242-111">Remarks</span></span>  
 <span data-ttu-id="ea242-112">@No__t_0 ブロックでは、テーブルまたは定義リストの見出しを定義します。</span><span class="sxs-lookup"><span data-stu-id="ea242-112">The `<listheader>` block defines the heading of either a table or definition list.</span></span> <span data-ttu-id="ea242-113">テーブルを定義する場合は、見出しに `term` のエントリを指定するだけで済みます。</span><span class="sxs-lookup"><span data-stu-id="ea242-113">When defining a table, you only have to supply an entry for `term` in the heading.</span></span>  
  
 <span data-ttu-id="ea242-114">リスト内の各項目には、`<item>` ブロックが指定されています。</span><span class="sxs-lookup"><span data-stu-id="ea242-114">Each item in the list is specified with an `<item>` block.</span></span> <span data-ttu-id="ea242-115">定義リストを作成する場合は、`term` と `description` の両方を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea242-115">When creating a definition list, you must specify both `term` and `description`.</span></span> <span data-ttu-id="ea242-116">ただし、テーブル、箇条書きリスト、番号付きリストの場合は、`description` のエントリを指定するだけで済みます。</span><span class="sxs-lookup"><span data-stu-id="ea242-116">However, for a table, bulleted list, or numbered list, you only have to supply an entry for `description`.</span></span>  
  
 <span data-ttu-id="ea242-117">リストまたはテーブルには、必要に応じて `<item>` ブロックをいくつでも含めることができます。</span><span class="sxs-lookup"><span data-stu-id="ea242-117">A list or table can have as many `<item>` blocks as needed.</span></span>  
  
 <span data-ttu-id="ea242-118">コンパイル時に [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="ea242-118">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ea242-119">例</span><span class="sxs-lookup"><span data-stu-id="ea242-119">Example</span></span>  
 <span data-ttu-id="ea242-120">この例では、`<list>` タグを使用して、「解説」で箇条書きリストを定義します。</span><span class="sxs-lookup"><span data-stu-id="ea242-120">This example uses the `<list>` tag to define a bulleted list in the remarks section.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="ea242-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="ea242-121">See also</span></span>

- [<span data-ttu-id="ea242-122">XML のコメント用タグ</span><span class="sxs-lookup"><span data-stu-id="ea242-122">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
