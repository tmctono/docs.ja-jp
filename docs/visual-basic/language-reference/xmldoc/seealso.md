---
title: <seealso> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <seealso> XML tag
- seealso XML tag
ms.assetid: 36050c95-1af2-4284-b9b6-1a70691ed978
ms.openlocfilehash: 9f857be6d0bd46233a49c7d2ff0931670baa95a6
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2019
ms.locfileid: "56965302"
---
# <a name="seealso-visual-basic"></a><span data-ttu-id="101b4-102">\<seealso > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="101b4-102">\<seealso> (Visual Basic)</span></span>
<span data-ttu-id="101b4-103">「参照」セクションに表示されるリンクを指定します。</span><span class="sxs-lookup"><span data-stu-id="101b4-103">Specifies a link that appears in the See Also section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="101b4-104">構文</span><span class="sxs-lookup"><span data-stu-id="101b4-104">Syntax</span></span>  
  
```xml  
<seealso cref="member"/>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="101b4-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="101b4-105">Parameters</span></span>  
 `member`  
 <span data-ttu-id="101b4-106">現在のコンパイル環境からの呼び出しに利用できる、メンバーまたはフィールドへの参照。</span><span class="sxs-lookup"><span data-stu-id="101b4-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="101b4-107">コンパイラは、指定されたコード要素が存在するかどうかを確認し、`member` を出力 XML 内の要素名に渡します。</span><span class="sxs-lookup"><span data-stu-id="101b4-107">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.</span></span> <span data-ttu-id="101b4-108">`member` は、二重引用符 (" ") で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="101b4-108">`member` must appear within double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="101b4-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="101b4-109">Remarks</span></span>  
 <span data-ttu-id="101b4-110">使用して、 `<seealso>` 「参照」セクションに表示するテキストを指定するタグ。</span><span class="sxs-lookup"><span data-stu-id="101b4-110">Use the `<seealso>` tag to specify the text that you want to appear in a See Also section.</span></span> <span data-ttu-id="101b4-111">[\<see>](../../../visual-basic/language-reference/xmldoc/see.md) タグを使用すると、テキスト内からリンクを指定できます。</span><span class="sxs-lookup"><span data-stu-id="101b4-111">Use [\<see>](../../../visual-basic/language-reference/xmldoc/see.md) to specify a link from within text.</span></span>  
  
 <span data-ttu-id="101b4-112">コンパイル時に [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="101b4-112">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="101b4-113">例</span><span class="sxs-lookup"><span data-stu-id="101b4-113">Example</span></span>  
 <span data-ttu-id="101b4-114">この例では、`<seealso>`にタグを付ける、`DoesRecordExist`解説セクションを参照する、`UpdateRecord`メソッド。</span><span class="sxs-lookup"><span data-stu-id="101b4-114">This example uses the `<seealso>` tag in the `DoesRecordExist` remarks section to refer to the `UpdateRecord` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="101b4-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="101b4-115">See also</span></span>
- [<span data-ttu-id="101b4-116">XML のコメント用タグ</span><span class="sxs-lookup"><span data-stu-id="101b4-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
