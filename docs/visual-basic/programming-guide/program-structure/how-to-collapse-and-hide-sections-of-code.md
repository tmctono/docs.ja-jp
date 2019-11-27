---
title: '方法 : コードのセクションを折りたたんで非表示にする'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic, code collapsing
- Visual Basic, code hiding
- Visual Basic code, collapsing and hiding
ms.assetid: b770e8f5-e07d-491a-ab4b-a977980f9ba2
ms.openlocfilehash: e7aacdc3f41199127b00d276b382ec4a5f258da0
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347409"
---
# <a name="how-to-collapse-and-hide-sections-of-code-visual-basic"></a><span data-ttu-id="544c5-102">方法: コードのセクションを折りたたんで非表示にする (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="544c5-102">How to: Collapse and Hide Sections of Code (Visual Basic)</span></span>

<span data-ttu-id="544c5-103">`#Region` ディレクティブを使用すると、Visual Basic ファイル内のコードのセクションを折りたたんで非表示にすることができます。</span><span class="sxs-lookup"><span data-stu-id="544c5-103">The `#Region` directive enables you to collapse and hide sections of code in Visual Basic files.</span></span> <span data-ttu-id="544c5-104">`#Region` ディレクティブを使用すると、Visual Studio コードエディターを使用して展開または折りたたむことができるコードブロックを指定できます。</span><span class="sxs-lookup"><span data-stu-id="544c5-104">The `#Region` directive lets you specify a block of code that you can expand or collapse when using the Visual Studio code editor.</span></span> <span data-ttu-id="544c5-105">コードを選択的に非表示にする機能により、ファイルの管理が容易になり、読みやすくなります。</span><span class="sxs-lookup"><span data-stu-id="544c5-105">The ability to hide code selectively makes your files more manageable and easier to read.</span></span> <span data-ttu-id="544c5-106">詳細については、「[アウトライン](/visualstudio/ide/outlining)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="544c5-106">For more information, see [Outlining](/visualstudio/ide/outlining).</span></span>

<span data-ttu-id="544c5-107">`#Region` ディレクティブは、`#If...#End If`などのコードブロックのセマンティクスをサポートします。</span><span class="sxs-lookup"><span data-stu-id="544c5-107">`#Region` directives support code block semantics such as `#If...#End If`.</span></span> <span data-ttu-id="544c5-108">つまり、1つのブロックで開始し、別のブロックで終了することはできません。start と end は同じブロック内になければなりません。</span><span class="sxs-lookup"><span data-stu-id="544c5-108">This means they cannot begin in one block and end in another; the start and end must be in the same block.</span></span> <span data-ttu-id="544c5-109">`#Region` ディレクティブは、関数内ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="544c5-109">`#Region` directives are not supported within functions.</span></span>

## <a name="to-collapse-and-hide-a-section-of-code"></a><span data-ttu-id="544c5-110">コードのセクションを折りたたんで非表示にするには</span><span class="sxs-lookup"><span data-stu-id="544c5-110">To collapse and hide a section of code</span></span>

<span data-ttu-id="544c5-111">次の例に示すように、`#Region` と `#End Region` のステートメントの間にコードのセクションを配置します。</span><span class="sxs-lookup"><span data-stu-id="544c5-111">Place the section of code between the `#Region` and `#End Region` statements, as in the following example:</span></span>

[!code-vb[VbVbalrConditionalComp#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#6)]

<span data-ttu-id="544c5-112">`#Region` ブロックは、コードファイル内で複数回使用できます。そのため、ユーザーは、折りたたまれる可能性があるプロシージャとクラスの独自のブロックを定義できます。</span><span class="sxs-lookup"><span data-stu-id="544c5-112">The `#Region` block can be used multiple times in a code file; thus, users can define their own blocks of procedures and classes that can, in turn, be collapsed.</span></span> <span data-ttu-id="544c5-113">`#Region` ブロックは、他の `#Region` ブロック内で入れ子にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="544c5-113">`#Region` blocks can also be nested within other `#Region` blocks.</span></span>

> [!NOTE]
> <span data-ttu-id="544c5-114">コードを非表示にしても、コンパイルが妨げられることはなく、`#If...#End If` のステートメントには影響しません。</span><span class="sxs-lookup"><span data-stu-id="544c5-114">Hiding code does not prevent it from being compiled and does not affect `#If...#End If` statements.</span></span>

## <a name="see-also"></a><span data-ttu-id="544c5-115">参照</span><span class="sxs-lookup"><span data-stu-id="544c5-115">See also</span></span>

- [<span data-ttu-id="544c5-116">条件付きコンパイル</span><span class="sxs-lookup"><span data-stu-id="544c5-116">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- [<span data-ttu-id="544c5-117">#Region ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="544c5-117">#Region Directive</span></span>](../../../visual-basic/language-reference/directives/region-directive.md)
- [<span data-ttu-id="544c5-118">#If...Then...#Else ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="544c5-118">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [<span data-ttu-id="544c5-119">アウトライン</span><span class="sxs-lookup"><span data-stu-id="544c5-119">Outlining</span></span>](/visualstudio/ide/outlining)
