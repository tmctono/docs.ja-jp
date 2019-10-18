---
title: <exception> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <exception> XML tag
- exception XML tag
ms.assetid: c0517549-171e-4dae-ab88-a9c1700b6eee
ms.openlocfilehash: 16ffb4f6b57dabb3650376c913a7d7608a00646d
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2019
ms.locfileid: "72523923"
---
# <a name="exception-visual-basic"></a><span data-ttu-id="e3623-102">\<exception > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e3623-102">\<exception> (Visual Basic)</span></span>
<span data-ttu-id="e3623-103">スローできる例外を指定します。</span><span class="sxs-lookup"><span data-stu-id="e3623-103">Specifies which exceptions can be thrown.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3623-104">構文</span><span class="sxs-lookup"><span data-stu-id="e3623-104">Syntax</span></span>  
  
```xml  
<exception cref="member">description</exception>  
```  
  
## <a name="parameters"></a><span data-ttu-id="e3623-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e3623-105">Parameters</span></span>  
 `member`  
 <span data-ttu-id="e3623-106">現在のコンパイル環境から使用できる例外の参照。</span><span class="sxs-lookup"><span data-stu-id="e3623-106">A reference to an exception that is available from the current compilation environment.</span></span> <span data-ttu-id="e3623-107">コンパイラは、指定された例外が存在し、出力の XML で `member` が正規要素名に変換されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e3623-107">The compiler checks that the given exception exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="e3623-108">`member` は、二重引用符 (" ") で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3623-108">`member` must appear within double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="e3623-109">説明です。</span><span class="sxs-lookup"><span data-stu-id="e3623-109">A description.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e3623-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="e3623-110">Remarks</span></span>  
 <span data-ttu-id="e3623-111">@No__t_0 タグを使用して、スローできる例外を指定します。</span><span class="sxs-lookup"><span data-stu-id="e3623-111">Use the `<exception>` tag to specify which exceptions can be thrown.</span></span> <span data-ttu-id="e3623-112">このタグは、メソッドの定義に適用されます。</span><span class="sxs-lookup"><span data-stu-id="e3623-112">This tag is applied to a method definition.</span></span>  
  
 <span data-ttu-id="e3623-113">コンパイル時に [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="e3623-113">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e3623-114">例</span><span class="sxs-lookup"><span data-stu-id="e3623-114">Example</span></span>  
 <span data-ttu-id="e3623-115">この例では、`<exception>` タグを使用して、`IntDivide` 関数がスローできる例外を記述します。</span><span class="sxs-lookup"><span data-stu-id="e3623-115">This example uses the `<exception>` tag to describe an exception that the `IntDivide` function can throw.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="e3623-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="e3623-116">See also</span></span>

- [<span data-ttu-id="e3623-117">XML のコメント用タグ</span><span class="sxs-lookup"><span data-stu-id="e3623-117">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
