---
title: '方法: コードのセクションを折りたたんで非表示にする (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic, code collapsing
- Visual Basic, code hiding
- Visual Basic code, collapsing and hiding
ms.assetid: b770e8f5-e07d-491a-ab4b-a977980f9ba2
ms.openlocfilehash: 4f11982cc0aa7654c1e456fb15d918a68bc4791b
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2019
ms.locfileid: "71054119"
---
# <a name="how-to-collapse-and-hide-sections-of-code-visual-basic"></a><span data-ttu-id="11b1c-102">方法: コードのセクションを折りたたんで非表示にする (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="11b1c-102">How to: Collapse and Hide Sections of Code (Visual Basic)</span></span>

<span data-ttu-id="11b1c-103">`#Region`ディレクティブを使用すると、Visual Basic ファイル内のコードのセクションを折りたたんで非表示にすることができます。</span><span class="sxs-lookup"><span data-stu-id="11b1c-103">The `#Region` directive enables you to collapse and hide sections of code in Visual Basic files.</span></span> <span data-ttu-id="11b1c-104">`#Region`ディレクティブを使用すると、Visual Studio コードエディターを使用して展開または折りたたむことができるコードブロックを指定できます。</span><span class="sxs-lookup"><span data-stu-id="11b1c-104">The `#Region` directive lets you specify a block of code that you can expand or collapse when using the Visual Studio code editor.</span></span> <span data-ttu-id="11b1c-105">コードを選択的に非表示にする機能により、ファイルの管理が容易になり、読みやすくなります。</span><span class="sxs-lookup"><span data-stu-id="11b1c-105">The ability to hide code selectively makes your files more manageable and easier to read.</span></span> <span data-ttu-id="11b1c-106">詳細については、「[アウトライン](/visualstudio/ide/outlining)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="11b1c-106">For more information, see [Outlining](/visualstudio/ide/outlining).</span></span>

<span data-ttu-id="11b1c-107">`#Region`ディレクティブは、などのコードブロック`#If...#End If`のセマンティクスをサポートします。</span><span class="sxs-lookup"><span data-stu-id="11b1c-107">`#Region` directives support code block semantics such as `#If...#End If`.</span></span> <span data-ttu-id="11b1c-108">つまり、1つのブロックで開始し、別のブロックで終了することはできません。start と end は同じブロック内になければなりません。</span><span class="sxs-lookup"><span data-stu-id="11b1c-108">This means they cannot begin in one block and end in another; the start and end must be in the same block.</span></span> <span data-ttu-id="11b1c-109">`#Region`ディレクティブは、関数内ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="11b1c-109">`#Region` directives are not supported within functions.</span></span>

## <a name="to-collapse-and-hide-a-section-of-code"></a><span data-ttu-id="11b1c-110">コードのセクションを折りたたんで非表示にするには</span><span class="sxs-lookup"><span data-stu-id="11b1c-110">To collapse and hide a section of code</span></span>

<span data-ttu-id="11b1c-111">次の例に示すように`#Region` 、 `#End Region`コードのセクションをステートメントとステートメントの間に配置します。</span><span class="sxs-lookup"><span data-stu-id="11b1c-111">Place the section of code between the `#Region` and `#End Region` statements, as in the following example:</span></span>

[!code-vb[VbVbalrConditionalComp#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#6)]

<span data-ttu-id="11b1c-112">ブロック`#Region`は、コードファイル内で複数回使用できます。したがって、ユーザーは、プロシージャやクラスを折りたたむことができる独自のブロックを定義できます。</span><span class="sxs-lookup"><span data-stu-id="11b1c-112">The `#Region` block can be used multiple times in a code file; thus, users can define their own blocks of procedures and classes that can, in turn, be collapsed.</span></span> <span data-ttu-id="11b1c-113">`#Region`ブロックは、他の`#Region`ブロック内で入れ子にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="11b1c-113">`#Region` blocks can also be nested within other `#Region` blocks.</span></span>

> [!NOTE]
> <span data-ttu-id="11b1c-114">コードを非表示にしても、コンパイルが妨げら`#If...#End If`れることはなく、ステートメントにも影響しません。</span><span class="sxs-lookup"><span data-stu-id="11b1c-114">Hiding code does not prevent it from being compiled and does not affect `#If...#End If` statements.</span></span>

## <a name="see-also"></a><span data-ttu-id="11b1c-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="11b1c-115">See also</span></span>

- [<span data-ttu-id="11b1c-116">条件付きコンパイル</span><span class="sxs-lookup"><span data-stu-id="11b1c-116">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- [<span data-ttu-id="11b1c-117">#Region ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="11b1c-117">#Region Directive</span></span>](../../../visual-basic/language-reference/directives/region-directive.md)
- [<span data-ttu-id="11b1c-118">#If...Then...#Else ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="11b1c-118">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [<span data-ttu-id="11b1c-119">アウトライン</span><span class="sxs-lookup"><span data-stu-id="11b1c-119">Outlining</span></span>](/visualstudio/ide/outlining)
