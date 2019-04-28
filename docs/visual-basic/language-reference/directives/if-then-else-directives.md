---
title: '#もし。。。Then... #Else ディレクティブ (Visual Basic)'
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
ms.openlocfilehash: 8c0aece749edf144fdd5c8ede9ec7e2e4c96ad54
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61746743"
---
# <a name="ifthenelse-directives"></a><span data-ttu-id="f1303-102">#If...Then...#Else ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="f1303-102">#If...Then...#Else Directives</span></span>
<span data-ttu-id="f1303-103">選択した Visual Basic のコード ブロックを条件付きでコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="f1303-103">Conditionally compiles selected blocks of Visual Basic code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1303-104">構文</span><span class="sxs-lookup"><span data-stu-id="f1303-104">Syntax</span></span>  
  
```  
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
  
## <a name="parts"></a><span data-ttu-id="f1303-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="f1303-105">Parts</span></span>  
 `expression`  
 <span data-ttu-id="f1303-106">必要な`#If`と`#ElseIf`ステートメントの省略可能な他の場所。</span><span class="sxs-lookup"><span data-stu-id="f1303-106">Required for `#If` and `#ElseIf` statements, optional elsewhere.</span></span> <span data-ttu-id="f1303-107">1 つまたは複数の条件付きコンパイラ定数、リテラル、および演算子に評価されるのみで構成される、任意の式`True`または`False`します。</span><span class="sxs-lookup"><span data-stu-id="f1303-107">Any expression, consisting exclusively of one or more conditional compiler constants, literals, and operators, that evaluates to `True` or `False`.</span></span>  
  
 `statements`  
 <span data-ttu-id="f1303-108">必要な`#If`ステートメント ブロック、省略可能な他の場所。</span><span class="sxs-lookup"><span data-stu-id="f1303-108">Required for `#If` statement block, optional elsewhere.</span></span> <span data-ttu-id="f1303-109">Visual Basic プログラムの行またはコンパイラ ディレクティブに関連付けられている式が評価された場合にコンパイルされる`True`します。</span><span class="sxs-lookup"><span data-stu-id="f1303-109">Visual Basic program lines or compiler directives that are compiled if the associated expression evaluates to `True`.</span></span>  
  
 `#End If`  
 <span data-ttu-id="f1303-110">終了、`#If`ステートメント ブロックです。</span><span class="sxs-lookup"><span data-stu-id="f1303-110">Terminates the `#If` statement block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f1303-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="f1303-111">Remarks</span></span>  
 <span data-ttu-id="f1303-112">画面の動作で、`#If...Then...#Else`ディレクティブが同じのように見える、`If...Then...Else`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="f1303-112">On the surface, the behavior of the `#If...Then...#Else` directives appears the same as that of the `If...Then...Else` statements.</span></span> <span data-ttu-id="f1303-113">ただし、`#If...Then...#Else`ディレクティブ、コンパイラによってどのようなコンパイルは一方の評価、`If...Then...Else`ステートメントが実行時に条件を評価します。</span><span class="sxs-lookup"><span data-stu-id="f1303-113">However, the `#If...Then...#Else` directives evaluate what is compiled by the compiler, whereas the `If...Then...Else` statements evaluate conditions at run time.</span></span>  
  
 <span data-ttu-id="f1303-114">条件付きコンパイルは通常、さまざまなプラットフォーム向けの同じプログラムのコンパイルに使用されます。</span><span class="sxs-lookup"><span data-stu-id="f1303-114">Conditional compilation is typically used to compile the same program for different platforms.</span></span> <span data-ttu-id="f1303-115">使用を防ぐために実行可能ファイルに表示されないコードをデバッグします。</span><span class="sxs-lookup"><span data-stu-id="f1303-115">It is also used to prevent debugging code from appearing in an executable file.</span></span> <span data-ttu-id="f1303-116">条件付きコンパイル時に除外するコードは、サイズやパフォーマンスに影響を与えませんために完全に、最終的な実行可能ファイルから省略されます。</span><span class="sxs-lookup"><span data-stu-id="f1303-116">Code excluded during conditional compilation is completely omitted from the final executable file, so it has no effect on size or performance.</span></span>  
  
 <span data-ttu-id="f1303-117">使用して、任意の評価の結果に関係なくすべての式が評価されます`Option Compare Binary`します。</span><span class="sxs-lookup"><span data-stu-id="f1303-117">Regardless of the outcome of any evaluation, all expressions are evaluated using `Option Compare Binary`.</span></span> <span data-ttu-id="f1303-118">`Option Compare`ステートメントでは式には影響しません`#If`と`#ElseIf`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="f1303-118">The `Option Compare` statement does not affect expressions in `#If` and `#ElseIf` statements.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f1303-119">単一行の形式、 `#If`、 `#Else`、 `#ElseIf`、および`#End If`ディレクティブが存在しません。</span><span class="sxs-lookup"><span data-stu-id="f1303-119">No single-line form of the `#If`, `#Else`, `#ElseIf`, and `#End If` directives exists.</span></span> <span data-ttu-id="f1303-120">その他のコードは、ディレクティブのいずれかと同じ行に表示できません。</span><span class="sxs-lookup"><span data-stu-id="f1303-120">No other code can appear on the same line as any of the directives.</span></span> 

<span data-ttu-id="f1303-121">条件付きコンパイル ブロック内のステートメントは、完全な論理ステートメントである必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1303-121">The statements within a conditional compilation block must be complete logical statements.</span></span> <span data-ttu-id="f1303-122">たとえば、関数の属性のみを条件付きでコンパイルすることはできませんが、条件付きでその属性と共に関数を宣言することができます。</span><span class="sxs-lookup"><span data-stu-id="f1303-122">For example, you cannot conditionally compile only the attributes of a function, but you can conditionally declare the function along with its attributes:</span></span>

```vb
   #If DEBUG Then
   <WebMethod()>
   Public Function SomeFunction() As String
   #Else
   <WebMethod(CacheDuration:=86400)>
   Public Function SomeFunction() As String
   #End If
```

## <a name="example"></a><span data-ttu-id="f1303-123">例</span><span class="sxs-lookup"><span data-stu-id="f1303-123">Example</span></span>
 <span data-ttu-id="f1303-124">この例では、`#If...Then...#Else`コンストラクトを特定のステートメントをコンパイルするかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="f1303-124">This example uses the `#If...Then...#Else` construct to determine whether to compile certain statements.</span></span>  
  
 [!code-vb[VbVbalrConditionalComp#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="f1303-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="f1303-125">See also</span></span>

- [<span data-ttu-id="f1303-126">#Const ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="f1303-126">#Const Directive</span></span>](../../../visual-basic/language-reference/directives/const-directive.md)
- [<span data-ttu-id="f1303-127">If...Then...Else ステートメント</span><span class="sxs-lookup"><span data-stu-id="f1303-127">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [<span data-ttu-id="f1303-128">条件付きコンパイル</span><span class="sxs-lookup"><span data-stu-id="f1303-128">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- <xref:System.Diagnostics.ConditionalAttribute?displayProperty=nameWithType>
