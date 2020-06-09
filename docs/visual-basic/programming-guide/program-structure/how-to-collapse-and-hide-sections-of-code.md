---
title: '方法: コードのセクションを折りたたんで非表示にする'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic, code collapsing
- Visual Basic, code hiding
- Visual Basic code, collapsing and hiding
ms.assetid: b770e8f5-e07d-491a-ab4b-a977980f9ba2
ms.openlocfilehash: c11affe9c4dd4251ba8ff4b87029d314970b5fcb
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404850"
---
# <a name="how-to-collapse-and-hide-sections-of-code-visual-basic"></a><span data-ttu-id="f64ff-102">方法: コードのセクションを折りたたんで非表示にする (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f64ff-102">How to: Collapse and Hide Sections of Code (Visual Basic)</span></span>

<span data-ttu-id="f64ff-103">`#Region` ディレクティブを使用すると、Visual Basic ファイル内のコードのセクションを折りたたんで非表示にすることができます。</span><span class="sxs-lookup"><span data-stu-id="f64ff-103">The `#Region` directive enables you to collapse and hide sections of code in Visual Basic files.</span></span> <span data-ttu-id="f64ff-104">`#Region` ディレクティブでは、Visual Studio コード エディターを使用するときに展開および折りたたみが可能なコード ブロックを指定できます。</span><span class="sxs-lookup"><span data-stu-id="f64ff-104">The `#Region` directive lets you specify a block of code that you can expand or collapse when using the Visual Studio code editor.</span></span> <span data-ttu-id="f64ff-105">コードを選択的に非表示にする機能により、ファイルが管理しやすくなり、読みやすくなります。</span><span class="sxs-lookup"><span data-stu-id="f64ff-105">The ability to hide code selectively makes your files more manageable and easier to read.</span></span> <span data-ttu-id="f64ff-106">詳細については、「[アウトライン](/visualstudio/ide/outlining)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f64ff-106">For more information, see [Outlining](/visualstudio/ide/outlining).</span></span>

<span data-ttu-id="f64ff-107">`#Region` ディレクティブでは、`#If...#End If` などのコード ブロック セマンティクスがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="f64ff-107">`#Region` directives support code block semantics such as `#If...#End If`.</span></span> <span data-ttu-id="f64ff-108">つまり、あるブロックで開始し、別のブロックで終了することはできません。開始と終了は同じブロック内である必要があります。</span><span class="sxs-lookup"><span data-stu-id="f64ff-108">This means they cannot begin in one block and end in another; the start and end must be in the same block.</span></span> <span data-ttu-id="f64ff-109">`#Region` ディレクティブは、関数内ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="f64ff-109">`#Region` directives are not supported within functions.</span></span>

## <a name="to-collapse-and-hide-a-section-of-code"></a><span data-ttu-id="f64ff-110">コードのセクションを折りたたんで非表示にするには</span><span class="sxs-lookup"><span data-stu-id="f64ff-110">To collapse and hide a section of code</span></span>

<span data-ttu-id="f64ff-111">次の例のように、`#Region` ステートメントと `#End Region` ステートメントの間にコードのセクションを配置します。</span><span class="sxs-lookup"><span data-stu-id="f64ff-111">Place the section of code between the `#Region` and `#End Region` statements, as in the following example:</span></span>

[!code-vb[VbVbalrConditionalComp#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#6)]

<span data-ttu-id="f64ff-112">`#Region` ブロックは、コード ファイル内で何回も使用できます。そのため、ユーザーはプロシージャやクラスの独自のブロックを定義し、それらを折りたたむことができます。</span><span class="sxs-lookup"><span data-stu-id="f64ff-112">The `#Region` block can be used multiple times in a code file; thus, users can define their own blocks of procedures and classes that can, in turn, be collapsed.</span></span> <span data-ttu-id="f64ff-113">`#Region` ブロックは、他の `#Region` ブロック内に入れ子にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="f64ff-113">`#Region` blocks can also be nested within other `#Region` blocks.</span></span>

> [!NOTE]
> <span data-ttu-id="f64ff-114">コードを非表示にしても、コンパイルが妨げられることはなく、`#If...#End If` ステートメントには影響しません。</span><span class="sxs-lookup"><span data-stu-id="f64ff-114">Hiding code does not prevent it from being compiled and does not affect `#If...#End If` statements.</span></span>

## <a name="see-also"></a><span data-ttu-id="f64ff-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="f64ff-115">See also</span></span>

- [<span data-ttu-id="f64ff-116">条件付きコンパイル</span><span class="sxs-lookup"><span data-stu-id="f64ff-116">Conditional Compilation</span></span>](conditional-compilation.md)
- [<span data-ttu-id="f64ff-117">#Region ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="f64ff-117">#Region Directive</span></span>](../../language-reference/directives/region-directive.md)
- [<span data-ttu-id="f64ff-118">#If...Then...#Else ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="f64ff-118">#If...Then...#Else Directives</span></span>](../../language-reference/directives/if-then-else-directives.md)
- [<span data-ttu-id="f64ff-119">アウトライン</span><span class="sxs-lookup"><span data-stu-id="f64ff-119">Outlining</span></span>](/visualstudio/ide/outlining)
