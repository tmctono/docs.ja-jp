---
title: <seealso>
ms.date: 07/20/2015
helpviewer_keywords:
- <seealso> XML tag
- seealso XML tag
ms.assetid: 36050c95-1af2-4284-b9b6-1a70691ed978
ms.openlocfilehash: f435fa2ab86d81053cd185f5d90ec22996a1458d
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "90869413"
---
# <a name="seealso-visual-basic"></a><span data-ttu-id="58461-101">\<seealso> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="58461-101">\<seealso> (Visual Basic)</span></span>

<span data-ttu-id="58461-102">関連項目セクションに表示されるリンクを指定します。</span><span class="sxs-lookup"><span data-stu-id="58461-102">Specifies a link that appears in the See Also section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58461-103">構文</span><span class="sxs-lookup"><span data-stu-id="58461-103">Syntax</span></span>  
  
```xml  
<seealso cref="member"/>  
```  
  
## <a name="parameters"></a><span data-ttu-id="58461-104">パラメーター</span><span class="sxs-lookup"><span data-stu-id="58461-104">Parameters</span></span>  

 `member`  
 <span data-ttu-id="58461-105">現在のコンパイル環境からの呼び出しに利用できる、メンバーまたはフィールドへの参照。</span><span class="sxs-lookup"><span data-stu-id="58461-105">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="58461-106">コンパイラは、指定されたコード要素が存在するかどうかを確認し、`member` を出力 XML 内の要素名に渡します。</span><span class="sxs-lookup"><span data-stu-id="58461-106">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.</span></span> <span data-ttu-id="58461-107">`member` は、二重引用符 (" ") で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="58461-107">`member` must appear within double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="58461-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="58461-108">Remarks</span></span>  

 <span data-ttu-id="58461-109">`<seealso>` タグを使用して、関連項目セクションに表示するテキストを指定します。</span><span class="sxs-lookup"><span data-stu-id="58461-109">Use the `<seealso>` tag to specify the text that you want to appear in a See Also section.</span></span> <span data-ttu-id="58461-110">[\<see>](see.md) を使用すると、テキスト内からリンクを指定できます。</span><span class="sxs-lookup"><span data-stu-id="58461-110">Use [\<see>](see.md) to specify a link from within text.</span></span>  
  
 <span data-ttu-id="58461-111">コンパイル時に [-doc](../../reference/command-line-compiler/doc.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="58461-111">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="58461-112">例</span><span class="sxs-lookup"><span data-stu-id="58461-112">Example</span></span>  

 <span data-ttu-id="58461-113">この例では、`DoesRecordExist` 解説セクションの `<seealso>` タグを使用して、`UpdateRecord` メソッドを参照します。</span><span class="sxs-lookup"><span data-stu-id="58461-113">This example uses the `<seealso>` tag in the `DoesRecordExist` remarks section to refer to the `UpdateRecord` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="58461-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="58461-114">See also</span></span>

- [<span data-ttu-id="58461-115">XML のコメント用タグ</span><span class="sxs-lookup"><span data-stu-id="58461-115">XML Comment Tags</span></span>](index.md)
