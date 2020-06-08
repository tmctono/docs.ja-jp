---
title: <list>
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
ms.openlocfilehash: 955c1a4c5c5619f908b8d03dbf12360c23574478
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400087"
---
# <a name="list-visual-basic"></a><span data-ttu-id="8ffe9-101">\<list> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8ffe9-101">\<list> (Visual Basic)</span></span>
<span data-ttu-id="8ffe9-102">リストまたはテーブルを定義します。</span><span class="sxs-lookup"><span data-stu-id="8ffe9-102">Defines a list or table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ffe9-103">構文</span><span class="sxs-lookup"><span data-stu-id="8ffe9-103">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="8ffe9-104">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8ffe9-104">Parameters</span></span>  
 `type`  
 <span data-ttu-id="8ffe9-105">リストの種類。</span><span class="sxs-lookup"><span data-stu-id="8ffe9-105">The type of the list.</span></span> <span data-ttu-id="8ffe9-106">箇条書きの場合は "bullet"、番号付きリストの場合は "number"、2 列のテーブルの場合は "table" にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ffe9-106">Must be a "bullet" for a bulleted list, "number" for a numbered list, or "table" for a two-column table.</span></span>  
  
 `term`  
 <span data-ttu-id="8ffe9-107">`type` が "table" の場合にのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="8ffe9-107">Only used when `type` is "table."</span></span> <span data-ttu-id="8ffe9-108">定義対象の用語。description タグで定義されています。</span><span class="sxs-lookup"><span data-stu-id="8ffe9-108">A term to define, which is defined in the description tag.</span></span>  
  
 `description`  
 <span data-ttu-id="8ffe9-109">`type` が "bullet" または "number" の場合、`description` は リストの項目です。`type` が "table" の場合、`description` は `term` の定義です。</span><span class="sxs-lookup"><span data-stu-id="8ffe9-109">When `type` is "bullet" or "number," `description` is an item in the list When `type` is "table," `description` is the definition of `term`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8ffe9-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="8ffe9-110">Remarks</span></span>  
 <span data-ttu-id="8ffe9-111">`<listheader>` ブロックでは、テーブルまたは定義リストの見出しが定義されます。</span><span class="sxs-lookup"><span data-stu-id="8ffe9-111">The `<listheader>` block defines the heading of either a table or definition list.</span></span> <span data-ttu-id="8ffe9-112">テーブルを定義するときは、見出しの `term` のエントリを指定することだけが必要です。</span><span class="sxs-lookup"><span data-stu-id="8ffe9-112">When defining a table, you only have to supply an entry for `term` in the heading.</span></span>  
  
 <span data-ttu-id="8ffe9-113">リストの各項目は、`<item>` ブロックで指定されます。</span><span class="sxs-lookup"><span data-stu-id="8ffe9-113">Each item in the list is specified with an `<item>` block.</span></span> <span data-ttu-id="8ffe9-114">定義リストを作成する場合は、`term` と `description` の両方を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ffe9-114">When creating a definition list, you must specify both `term` and `description`.</span></span> <span data-ttu-id="8ffe9-115">ただし、テーブル、箇条書き、または番号付きリストの場合は、`description` のエントリを指定するだけです。</span><span class="sxs-lookup"><span data-stu-id="8ffe9-115">However, for a table, bulleted list, or numbered list, you only have to supply an entry for `description`.</span></span>  
  
 <span data-ttu-id="8ffe9-116">リストまたはテーブルでは、必要な数の `<item>` ブロックを使用できます。</span><span class="sxs-lookup"><span data-stu-id="8ffe9-116">A list or table can have as many `<item>` blocks as needed.</span></span>  
  
 <span data-ttu-id="8ffe9-117">コンパイル時に [-doc](../../reference/command-line-compiler/doc.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="8ffe9-117">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8ffe9-118">例</span><span class="sxs-lookup"><span data-stu-id="8ffe9-118">Example</span></span>  
 <span data-ttu-id="8ffe9-119">この例では、`<list>` タグを使用して、解説セクションの箇条書きを定義します。</span><span class="sxs-lookup"><span data-stu-id="8ffe9-119">This example uses the `<list>` tag to define a bulleted list in the remarks section.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="8ffe9-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="8ffe9-120">See also</span></span>

- [<span data-ttu-id="8ffe9-121">XML のコメント用タグ</span><span class="sxs-lookup"><span data-stu-id="8ffe9-121">XML Comment Tags</span></span>](index.md)
