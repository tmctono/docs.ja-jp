---
title: '#If...Then...#Else ディレクティブ'
ms.date: 04/11/2018
f1_keywords:
- vb.#EndIf
- '#End If'
- '#Then'
- '#ElseIf'
- vb.#ElseIf
- vb.#Else
- vb.#If
helpviewer_keywords:
- Visual Basic code, compiling
- '#If directive [Visual Basic]'
- conditional compilation [Visual Basic], directives
- '#End if directive [Visual Basic]'
- selective compiling
- else directive (#else)
- '#Else directive [Visual Basic]'
ms.assetid: 10bba104-e3fd-451b-b672-faa472530502
ms.openlocfilehash: 40e93b718241c9819e3c0fd84595e76eb0c86472
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343813"
---
# <a name="ifthenelse-directives"></a><span data-ttu-id="e699e-102">#If...Then...#Else ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="e699e-102">#If...Then...#Else Directives</span></span>

<span data-ttu-id="e699e-103">選択された Visual Basic コードのブロックを条件付きでコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="e699e-103">Conditionally compiles selected blocks of Visual Basic code.</span></span>

## <a name="syntax"></a><span data-ttu-id="e699e-104">構文</span><span class="sxs-lookup"><span data-stu-id="e699e-104">Syntax</span></span>

```vb
#If expression Then
   statements
[ #ElseIf expression Then
   [ statements ]
...
#ElseIf expression Then
   [ statements ] ]
[ #Else
   [ statements ] ]
#End If
```

## <a name="parts"></a><span data-ttu-id="e699e-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="e699e-105">Parts</span></span>

`expression`  
<span data-ttu-id="e699e-106">`#If` および `#ElseIf` のステートメント、他の場所では省略可能です。</span><span class="sxs-lookup"><span data-stu-id="e699e-106">Required for `#If` and `#ElseIf` statements, optional elsewhere.</span></span> <span data-ttu-id="e699e-107">`True` または `False`に評価される1つ以上の条件付きコンパイラ定数、リテラル、および演算子で構成される任意の式。</span><span class="sxs-lookup"><span data-stu-id="e699e-107">Any expression, consisting exclusively of one or more conditional compiler constants, literals, and operators, that evaluates to `True` or `False`.</span></span>

`statements`  
<span data-ttu-id="e699e-108">`#If` ステートメントブロックに必要です。他の場所では省略可能です。</span><span class="sxs-lookup"><span data-stu-id="e699e-108">Required for `#If` statement block, optional elsewhere.</span></span> <span data-ttu-id="e699e-109">関連付けられた式が `True`に評価される場合にコンパイルされるプログラムラインまたはコンパイラディレクティブを Visual Basic します。</span><span class="sxs-lookup"><span data-stu-id="e699e-109">Visual Basic program lines or compiler directives that are compiled if the associated expression evaluates to `True`.</span></span>

`#End If`  
<span data-ttu-id="e699e-110">`#If` ステートメントブロックを終了します。</span><span class="sxs-lookup"><span data-stu-id="e699e-110">Terminates the `#If` statement block.</span></span>

## <a name="remarks"></a><span data-ttu-id="e699e-111">コメント</span><span class="sxs-lookup"><span data-stu-id="e699e-111">Remarks</span></span>

<span data-ttu-id="e699e-112">サーフェイスでは、`#If...Then...#Else` ディレクティブの動作は、`If...Then...Else` ステートメントと同じになります。</span><span class="sxs-lookup"><span data-stu-id="e699e-112">On the surface, the behavior of the `#If...Then...#Else` directives appears the same as that of the `If...Then...Else` statements.</span></span> <span data-ttu-id="e699e-113">ただし、`#If...Then...#Else` ディレクティブは、コンパイラによってコンパイルされた内容を評価します。一方、`If...Then...Else` ステートメントは、実行時に条件を評価します。</span><span class="sxs-lookup"><span data-stu-id="e699e-113">However, the `#If...Then...#Else` directives evaluate what is compiled by the compiler, whereas the `If...Then...Else` statements evaluate conditions at run time.</span></span>

<span data-ttu-id="e699e-114">通常、条件付きコンパイルは、異なるプラットフォームに対して同じプログラムをコンパイルするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="e699e-114">Conditional compilation is typically used to compile the same program for different platforms.</span></span> <span data-ttu-id="e699e-115">また、デバッグコードが実行可能ファイルに表示されないようにするためにも使用されます。</span><span class="sxs-lookup"><span data-stu-id="e699e-115">It is also used to prevent debugging code from appearing in an executable file.</span></span> <span data-ttu-id="e699e-116">条件付きコンパイル中に除外されたコードは、最終的な実行可能ファイルから完全に省略されるため、サイズやパフォーマンスには影響しません。</span><span class="sxs-lookup"><span data-stu-id="e699e-116">Code excluded during conditional compilation is completely omitted from the final executable file, so it has no effect on size or performance.</span></span>

<span data-ttu-id="e699e-117">評価の結果に関係なく、すべての式は `Option Compare Binary`を使用して評価されます。</span><span class="sxs-lookup"><span data-stu-id="e699e-117">Regardless of the outcome of any evaluation, all expressions are evaluated using `Option Compare Binary`.</span></span> <span data-ttu-id="e699e-118">`Option Compare` ステートメントは、`#If` および `#ElseIf` ステートメントの式には影響しません。</span><span class="sxs-lookup"><span data-stu-id="e699e-118">The `Option Compare` statement does not affect expressions in `#If` and `#ElseIf` statements.</span></span>

> [!NOTE]
> <span data-ttu-id="e699e-119">`#If`、`#Else`、`#ElseIf`、および `#End If` ディレクティブの単一行形式は存在しません。</span><span class="sxs-lookup"><span data-stu-id="e699e-119">No single-line form of the `#If`, `#Else`, `#ElseIf`, and `#End If` directives exists.</span></span> <span data-ttu-id="e699e-120">ディレクティブと同じ行に他のコードを記述することはできません。</span><span class="sxs-lookup"><span data-stu-id="e699e-120">No other code can appear on the same line as any of the directives.</span></span>

<span data-ttu-id="e699e-121">条件付きコンパイルブロック内のステートメントは、完全な論理ステートメントである必要があります。</span><span class="sxs-lookup"><span data-stu-id="e699e-121">The statements within a conditional compilation block must be complete logical statements.</span></span> <span data-ttu-id="e699e-122">たとえば、条件付きで関数の属性のみをコンパイルすることはできませんが、その属性と共に関数を条件付きで宣言することはできます。</span><span class="sxs-lookup"><span data-stu-id="e699e-122">For example, you cannot conditionally compile only the attributes of a function, but you can conditionally declare the function along with its attributes:</span></span>

```vb
#If DEBUG Then
<WebMethod()>
Public Function SomeFunction() As String
#Else
<WebMethod(CacheDuration:=86400)>
Public Function SomeFunction() As String
#End If
```

## <a name="example"></a><span data-ttu-id="e699e-123">例</span><span class="sxs-lookup"><span data-stu-id="e699e-123">Example</span></span>

<span data-ttu-id="e699e-124">この例では、`#If...Then...#Else` コンストラクトを使用して、特定のステートメントをコンパイルするかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="e699e-124">This example uses the `#If...Then...#Else` construct to determine whether to compile certain statements.</span></span>

[!code-vb[VbVbalrConditionalComp#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#1)]

## <a name="see-also"></a><span data-ttu-id="e699e-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="e699e-125">See also</span></span>

- [<span data-ttu-id="e699e-126">#Const ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="e699e-126">#Const Directive</span></span>](../../../visual-basic/language-reference/directives/const-directive.md)
- [<span data-ttu-id="e699e-127">If...Then...Else ステートメント</span><span class="sxs-lookup"><span data-stu-id="e699e-127">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [<span data-ttu-id="e699e-128">条件付きコンパイル</span><span class="sxs-lookup"><span data-stu-id="e699e-128">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- <xref:System.Diagnostics.ConditionalAttribute?displayProperty=nameWithType>
