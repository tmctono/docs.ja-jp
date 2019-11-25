---
title: <see>
ms.date: 07/20/2015
helpviewer_keywords:
- see XML tag
- <see> XML tag
ms.assetid: 7e18f60b-ef4a-4678-a797-5eb918635ca9
ms.openlocfilehash: 3c149b8ff60bcc2aba06856ad95f461fb18da4b6
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352229"
---
# <a name="see-visual-basic"></a><span data-ttu-id="5e466-101">\<see> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5e466-101">\<see> (Visual Basic)</span></span>
<span data-ttu-id="5e466-102">Specifies a link to another member.</span><span class="sxs-lookup"><span data-stu-id="5e466-102">Specifies a link to another member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e466-103">構文</span><span class="sxs-lookup"><span data-stu-id="5e466-103">Syntax</span></span>  
  
```xml  
<see cref="member"/>  
```  
  
## <a name="parameters"></a><span data-ttu-id="5e466-104">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5e466-104">Parameters</span></span>  
 `member`  
 <span data-ttu-id="5e466-105">現在のコンパイル環境からの呼び出しに利用できる、メンバーまたはフィールドへの参照。</span><span class="sxs-lookup"><span data-stu-id="5e466-105">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="5e466-106">コンパイラは、指定されたコード要素が存在するかどうかを確認し、`member` を出力 XML 内の要素名に渡します。</span><span class="sxs-lookup"><span data-stu-id="5e466-106">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.</span></span> <span data-ttu-id="5e466-107">`member` は、二重引用符 (" ") で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="5e466-107">`member` must appear within double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5e466-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="5e466-108">Remarks</span></span>  
 <span data-ttu-id="5e466-109">Use the `<see>` tag to specify a link from within text.</span><span class="sxs-lookup"><span data-stu-id="5e466-109">Use the `<see>` tag to specify a link from within text.</span></span> <span data-ttu-id="5e466-110">Use [\<seealso>](../../../visual-basic/language-reference/xmldoc/seealso.md) to indicate text that you might want to appear in a "See Also" section.</span><span class="sxs-lookup"><span data-stu-id="5e466-110">Use [\<seealso>](../../../visual-basic/language-reference/xmldoc/seealso.md) to indicate text that you might want to appear in a "See Also" section.</span></span>  
  
 <span data-ttu-id="5e466-111">コンパイル時に [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="5e466-111">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5e466-112">例</span><span class="sxs-lookup"><span data-stu-id="5e466-112">Example</span></span>  
 <span data-ttu-id="5e466-113">This example uses the `<see>` tag in the `UpdateRecord` remarks section to refer to the `DoesRecordExist` method.</span><span class="sxs-lookup"><span data-stu-id="5e466-113">This example uses the `<see>` tag in the `UpdateRecord` remarks section to refer to the `DoesRecordExist` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="5e466-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="5e466-114">See also</span></span>

- [<span data-ttu-id="5e466-115">XML のコメント用タグ</span><span class="sxs-lookup"><span data-stu-id="5e466-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
