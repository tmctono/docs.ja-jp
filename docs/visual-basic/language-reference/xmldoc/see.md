---
title: <see> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- see XML tag
- <see> XML tag
ms.assetid: 7e18f60b-ef4a-4678-a797-5eb918635ca9
ms.openlocfilehash: e3ae5fb63540e47e5b8da2e2d60d5bd736e019d7
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524659"
---
# <a name="see-visual-basic"></a><span data-ttu-id="a54bb-102">\<see > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a54bb-102">\<see> (Visual Basic)</span></span>
<span data-ttu-id="a54bb-103">別のメンバーへのリンクを指定します。</span><span class="sxs-lookup"><span data-stu-id="a54bb-103">Specifies a link to another member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a54bb-104">構文</span><span class="sxs-lookup"><span data-stu-id="a54bb-104">Syntax</span></span>  
  
```xml  
<see cref="member"/>  
```  
  
## <a name="parameters"></a><span data-ttu-id="a54bb-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a54bb-105">Parameters</span></span>  
 `member`  
 <span data-ttu-id="a54bb-106">現在のコンパイル環境からの呼び出しに利用できる、メンバーまたはフィールドへの参照。</span><span class="sxs-lookup"><span data-stu-id="a54bb-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="a54bb-107">コンパイラは、指定されたコード要素が存在するかどうかを確認し、`member` を出力 XML 内の要素名に渡します。</span><span class="sxs-lookup"><span data-stu-id="a54bb-107">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.</span></span> <span data-ttu-id="a54bb-108">`member` は、二重引用符 (" ") で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="a54bb-108">`member` must appear within double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a54bb-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="a54bb-109">Remarks</span></span>  
 <span data-ttu-id="a54bb-110">@No__t_0 タグを使用して、テキスト内からリンクを指定します。</span><span class="sxs-lookup"><span data-stu-id="a54bb-110">Use the `<see>` tag to specify a link from within text.</span></span> <span data-ttu-id="a54bb-111">[@No__t_1seealso >](../../../visual-basic/language-reference/xmldoc/seealso.md)を使用して、"関連項目" セクションに表示するテキストを指定します。</span><span class="sxs-lookup"><span data-stu-id="a54bb-111">Use [\<seealso>](../../../visual-basic/language-reference/xmldoc/seealso.md) to indicate text that you might want to appear in a "See Also" section.</span></span>  
  
 <span data-ttu-id="a54bb-112">コンパイル時に [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="a54bb-112">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a54bb-113">例</span><span class="sxs-lookup"><span data-stu-id="a54bb-113">Example</span></span>  
 <span data-ttu-id="a54bb-114">この例では、`UpdateRecord` 解説セクションの `<see>` タグを使用して、`DoesRecordExist` メソッドを参照します。</span><span class="sxs-lookup"><span data-stu-id="a54bb-114">This example uses the `<see>` tag in the `UpdateRecord` remarks section to refer to the `DoesRecordExist` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="a54bb-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="a54bb-115">See also</span></span>

- [<span data-ttu-id="a54bb-116">XML のコメント用タグ</span><span class="sxs-lookup"><span data-stu-id="a54bb-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
