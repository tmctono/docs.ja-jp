---
title: <seealso>
ms.date: 07/20/2015
helpviewer_keywords:
- <seealso> XML tag
- seealso XML tag
ms.assetid: 36050c95-1af2-4284-b9b6-1a70691ed978
ms.openlocfilehash: 27bb2c271631170082709d9e3d76cd39eefbc860
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352214"
---
# <a name="seealso-visual-basic"></a><span data-ttu-id="19616-101">\<seealso> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="19616-101">\<seealso> (Visual Basic)</span></span>
<span data-ttu-id="19616-102">「関連項目」セクションに表示されるリンクを指定します。</span><span class="sxs-lookup"><span data-stu-id="19616-102">Specifies a link that appears in the See Also section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19616-103">構文</span><span class="sxs-lookup"><span data-stu-id="19616-103">Syntax</span></span>  
  
```xml  
<seealso cref="member"/>  
```  
  
## <a name="parameters"></a><span data-ttu-id="19616-104">パラメーター</span><span class="sxs-lookup"><span data-stu-id="19616-104">Parameters</span></span>  
 `member`  
 <span data-ttu-id="19616-105">現在のコンパイル環境からの呼び出しに利用できる、メンバーまたはフィールドへの参照。</span><span class="sxs-lookup"><span data-stu-id="19616-105">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="19616-106">コンパイラは、指定されたコード要素が存在するかどうかを確認し、`member` を出力 XML 内の要素名に渡します。</span><span class="sxs-lookup"><span data-stu-id="19616-106">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.</span></span> <span data-ttu-id="19616-107">`member` は、二重引用符 (" ") で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="19616-107">`member` must appear within double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="19616-108">コメント</span><span class="sxs-lookup"><span data-stu-id="19616-108">Remarks</span></span>  
 <span data-ttu-id="19616-109">`<seealso>` タグを使用して、「関連項目」セクションに表示するテキストを指定します。</span><span class="sxs-lookup"><span data-stu-id="19616-109">Use the `<seealso>` tag to specify the text that you want to appear in a See Also section.</span></span> <span data-ttu-id="19616-110">[\<see>](../../../visual-basic/language-reference/xmldoc/see.md) タグを使用すると、テキスト内からリンクを指定できます。</span><span class="sxs-lookup"><span data-stu-id="19616-110">Use [\<see>](../../../visual-basic/language-reference/xmldoc/see.md) to specify a link from within text.</span></span>  
  
 <span data-ttu-id="19616-111">コンパイル時に [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="19616-111">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="19616-112">例</span><span class="sxs-lookup"><span data-stu-id="19616-112">Example</span></span>  
 <span data-ttu-id="19616-113">この例では、`DoesRecordExist` 解説セクションの `<seealso>` タグを使用して、`UpdateRecord` メソッドを参照します。</span><span class="sxs-lookup"><span data-stu-id="19616-113">This example uses the `<seealso>` tag in the `DoesRecordExist` remarks section to refer to the `UpdateRecord` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="19616-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="19616-114">See also</span></span>

- [<span data-ttu-id="19616-115">XML のコメント用タグ</span><span class="sxs-lookup"><span data-stu-id="19616-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
