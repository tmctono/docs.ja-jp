---
title: <seealso> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <seealso> XML tag
- seealso XML tag
ms.assetid: 36050c95-1af2-4284-b9b6-1a70691ed978
ms.openlocfilehash: 0231ff748949874f4b477cac15d891d313b25f4f
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524650"
---
# <a name="seealso-visual-basic"></a><span data-ttu-id="ee715-102">\<seealso > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ee715-102">\<seealso> (Visual Basic)</span></span>
<span data-ttu-id="ee715-103">「関連項目」セクションに表示されるリンクを指定します。</span><span class="sxs-lookup"><span data-stu-id="ee715-103">Specifies a link that appears in the See Also section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee715-104">構文</span><span class="sxs-lookup"><span data-stu-id="ee715-104">Syntax</span></span>  
  
```xml  
<seealso cref="member"/>  
```  
  
## <a name="parameters"></a><span data-ttu-id="ee715-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ee715-105">Parameters</span></span>  
 `member`  
 <span data-ttu-id="ee715-106">現在のコンパイル環境からの呼び出しに利用できる、メンバーまたはフィールドへの参照。</span><span class="sxs-lookup"><span data-stu-id="ee715-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="ee715-107">コンパイラは、指定されたコード要素が存在するかどうかを確認し、`member` を出力 XML 内の要素名に渡します。</span><span class="sxs-lookup"><span data-stu-id="ee715-107">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.</span></span> <span data-ttu-id="ee715-108">`member` は、二重引用符 (" ") で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="ee715-108">`member` must appear within double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ee715-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="ee715-109">Remarks</span></span>  
 <span data-ttu-id="ee715-110">@No__t_0 タグを使用して、「関連項目」セクションに表示するテキストを指定します。</span><span class="sxs-lookup"><span data-stu-id="ee715-110">Use the `<seealso>` tag to specify the text that you want to appear in a See Also section.</span></span> <span data-ttu-id="ee715-111">[\<see>](../../../visual-basic/language-reference/xmldoc/see.md) タグを使用すると、テキスト内からリンクを指定できます。</span><span class="sxs-lookup"><span data-stu-id="ee715-111">Use [\<see>](../../../visual-basic/language-reference/xmldoc/see.md) to specify a link from within text.</span></span>  
  
 <span data-ttu-id="ee715-112">コンパイル時に [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="ee715-112">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ee715-113">例</span><span class="sxs-lookup"><span data-stu-id="ee715-113">Example</span></span>  
 <span data-ttu-id="ee715-114">この例では、`DoesRecordExist` 解説セクションの `<seealso>` タグを使用して、`UpdateRecord` メソッドを参照します。</span><span class="sxs-lookup"><span data-stu-id="ee715-114">This example uses the `<seealso>` tag in the `DoesRecordExist` remarks section to refer to the `UpdateRecord` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="ee715-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="ee715-115">See also</span></span>

- [<span data-ttu-id="ee715-116">XML のコメント用タグ</span><span class="sxs-lookup"><span data-stu-id="ee715-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
