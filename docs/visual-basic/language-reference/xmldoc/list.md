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
ms.openlocfilehash: 61b0b018b3d06a2307aa280a748b7d07c5fa7915
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57496067"
---
# <a name="list-visual-basic"></a><span data-ttu-id="2ba78-102">\<リスト > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2ba78-102">\<list> (Visual Basic)</span></span>
<span data-ttu-id="2ba78-103">リストまたはテーブルを定義します。</span><span class="sxs-lookup"><span data-stu-id="2ba78-103">Defines a list or table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ba78-104">構文</span><span class="sxs-lookup"><span data-stu-id="2ba78-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="2ba78-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2ba78-105">Parameters</span></span>  
 `type`  
 <span data-ttu-id="2ba78-106">リストの型。</span><span class="sxs-lookup"><span data-stu-id="2ba78-106">The type of the list.</span></span> <span data-ttu-id="2ba78-107">箇条書き、番号付きリスト、または 2 つの列のテーブルには、"table"の"number"の"bullet"があります。</span><span class="sxs-lookup"><span data-stu-id="2ba78-107">Must be a "bullet" for a bulleted list, "number" for a numbered list, or "table" for a two-column table.</span></span>  
  
 `term`  
 <span data-ttu-id="2ba78-108">場合のみ使用`type`"table"には</span><span class="sxs-lookup"><span data-stu-id="2ba78-108">Only used when `type` is "table."</span></span> <span data-ttu-id="2ba78-109">説明タグで定義されている用語を定義します。</span><span class="sxs-lookup"><span data-stu-id="2ba78-109">A term to define, which is defined in the description tag.</span></span>  
  
 `description`  
 <span data-ttu-id="2ba78-110">ときに`type`"bullet"または"number" `description` 、リスト内の項目は、ときに`type`は"table"`description`の定義は、 `term`。</span><span class="sxs-lookup"><span data-stu-id="2ba78-110">When `type` is "bullet" or "number," `description` is an item in the list When `type` is "table," `description` is the definition of `term`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2ba78-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="2ba78-111">Remarks</span></span>  
 <span data-ttu-id="2ba78-112">`<listheader>`ブロックは、テーブルまたは定義の一覧の見出しを定義します。</span><span class="sxs-lookup"><span data-stu-id="2ba78-112">The `<listheader>` block defines the heading of either a table or definition list.</span></span> <span data-ttu-id="2ba78-113">のみのエントリを指定する必要があるテーブルを定義するときに`term`見出し。</span><span class="sxs-lookup"><span data-stu-id="2ba78-113">When defining a table, you only have to supply an entry for `term` in the heading.</span></span>  
  
 <span data-ttu-id="2ba78-114">リスト内の各項目を指定した、`<item>`ブロックします。</span><span class="sxs-lookup"><span data-stu-id="2ba78-114">Each item in the list is specified with an `<item>` block.</span></span> <span data-ttu-id="2ba78-115">定義リストを作成するときに、両方を指定する必要があります`term`と`description`します。</span><span class="sxs-lookup"><span data-stu-id="2ba78-115">When creating a definition list, you must specify both `term` and `description`.</span></span> <span data-ttu-id="2ba78-116">ただし、テーブル、箇条書きまたは番号付きリストだけであるエントリを指定する`description`します。</span><span class="sxs-lookup"><span data-stu-id="2ba78-116">However, for a table, bulleted list, or numbered list, you only have to supply an entry for `description`.</span></span>  
  
 <span data-ttu-id="2ba78-117">リストまたはテーブルとして多く持つことができます`<item>`に応じてをブロックします。</span><span class="sxs-lookup"><span data-stu-id="2ba78-117">A list or table can have as many `<item>` blocks as needed.</span></span>  
  
 <span data-ttu-id="2ba78-118">コンパイル時に [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="2ba78-118">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2ba78-119">例</span><span class="sxs-lookup"><span data-stu-id="2ba78-119">Example</span></span>  
 <span data-ttu-id="2ba78-120">この例では、 `<list>` 「解説」セクションで、箇条書きリストを定義するタグ。</span><span class="sxs-lookup"><span data-stu-id="2ba78-120">This example uses the `<list>` tag to define a bulleted list in the remarks section.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="2ba78-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="2ba78-121">See also</span></span>
- [<span data-ttu-id="2ba78-122">XML のコメント用タグ</span><span class="sxs-lookup"><span data-stu-id="2ba78-122">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
