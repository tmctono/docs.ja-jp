---
title: '方法: 折りたたみし、コード (Visual Basic) のセクションを非表示'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic, code collapsing
- Visual Basic, code hiding
- Visual Basic code, collapsing and hiding
ms.assetid: b770e8f5-e07d-491a-ab4b-a977980f9ba2
ms.openlocfilehash: 367527fd638f6855077caf8ff5911edb333dfcbf
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64648765"
---
# <a name="how-to-collapse-and-hide-sections-of-code-visual-basic"></a><span data-ttu-id="0c2ca-102">方法: 折りたたみし、コード (Visual Basic) のセクションを非表示</span><span class="sxs-lookup"><span data-stu-id="0c2ca-102">How to: Collapse and Hide Sections of Code (Visual Basic)</span></span>
<span data-ttu-id="0c2ca-103">`#Region`ディレクティブでは、折りたたんでのコード Visual Basic ファイルのセクションを非表示にすることができます。</span><span class="sxs-lookup"><span data-stu-id="0c2ca-103">The `#Region` directive enables you to collapse and hide sections of code in Visual Basic files.</span></span> <span data-ttu-id="0c2ca-104">`#Region`ディレクティブでは、Visual Studio コード エディターを使用する場合は、拡張可能なコードまたは折りたたみのブロックを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="0c2ca-104">The `#Region` directive lets you specify a block of code that you can expand or collapse when using the Visual Studio code editor.</span></span> <span data-ttu-id="0c2ca-105">選択的にコードを非表示にする機能は、ファイルをより管理しやすく、読みやすくになります。</span><span class="sxs-lookup"><span data-stu-id="0c2ca-105">The ability to hide code selectively makes your files more manageable and easier to read.</span></span> <span data-ttu-id="0c2ca-106">詳細については、「[アウトライン](/visualstudio/ide/outlining)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c2ca-106">For more information, see [Outlining](/visualstudio/ide/outlining).</span></span>  
  
 <span data-ttu-id="0c2ca-107">`#Region` ディレクティブのサポート コード ブロックのセマンティクス`#If...#End If`します。</span><span class="sxs-lookup"><span data-stu-id="0c2ca-107">`#Region` directives support code block semantics such as `#If...#End If`.</span></span> <span data-ttu-id="0c2ca-108">つまり、1 つのブロックの開始し、は別の終了ことはできません。先頭と末尾は、同じブロック内にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c2ca-108">This means they cannot begin in one block and end in another; the start and end must be in the same block.</span></span> <span data-ttu-id="0c2ca-109">`#Region` ディレクティブは、関数内ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="0c2ca-109">`#Region` directives are not supported within functions.</span></span>  
  
### <a name="to-collapse-and-hide-a-section-of-code"></a><span data-ttu-id="0c2ca-110">折りたたみし、コードのセクションを非表示にするには</span><span class="sxs-lookup"><span data-stu-id="0c2ca-110">To collapse and hide a section of code</span></span>  
  
- <span data-ttu-id="0c2ca-111">間のコード セクションの配置、`#Region`と`#End Region`ステートメントは、次の例のように。</span><span class="sxs-lookup"><span data-stu-id="0c2ca-111">Place the section of code between the `#Region` and `#End Region` statements, as in the following example:</span></span>  
  
     [!code-vb[VbVbalrConditionalComp#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#6)]  
  
     <span data-ttu-id="0c2ca-112">`#Region`ブロックは、コード ファイルで複数回使用できますが。 そのため、ユーザーがプロシージャおよび折りたたむことができ、さらに、クラスの独自のブロックを定義できます。</span><span class="sxs-lookup"><span data-stu-id="0c2ca-112">The `#Region` block can be used multiple times in a code file; thus, users can define their own blocks of procedures and classes that can, in turn, be collapsed.</span></span> <span data-ttu-id="0c2ca-113">`#Region` 内でその他のブロックをネストすることも`#Region`ブロックします。</span><span class="sxs-lookup"><span data-stu-id="0c2ca-113">`#Region` blocks can also be nested within other `#Region` blocks.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0c2ca-114">コードを非表示にコンパイルされないは防止されませんしには影響しません`#If...#End If`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="0c2ca-114">Hiding code does not prevent it from being compiled and does not affect `#If...#End If` statements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c2ca-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="0c2ca-115">See also</span></span>

- [<span data-ttu-id="0c2ca-116">条件付きコンパイル</span><span class="sxs-lookup"><span data-stu-id="0c2ca-116">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- [<span data-ttu-id="0c2ca-117">#Region ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="0c2ca-117">#Region Directive</span></span>](../../../visual-basic/language-reference/directives/region-directive.md)
- [<span data-ttu-id="0c2ca-118">#If...Then...#Else ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="0c2ca-118">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [<span data-ttu-id="0c2ca-119">アウトライン</span><span class="sxs-lookup"><span data-stu-id="0c2ca-119">Outlining</span></span>](/visualstudio/ide/outlining)
