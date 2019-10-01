---
title: '#Const ディレクティブ (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.#Const
- '#vb.Const'
- '#Const'
helpviewer_keywords:
- '#Const directive'
- conditional compilation [Visual Basic], directives
- Const directive (#Const)
- Visual Basic compiler, compiler directives
- constants [Visual Basic], Const directive
- constants [Visual Basic], declaring
- Const statement [Visual Basic], directive (#Const)
- 'declaring constants [Visual Basic], #const directive'
ms.assetid: 707669e5-23f9-4f17-8622-a0d534429386
ms.openlocfilehash: 9b8d2da2158a8244b4533eb6ef49049949417216
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2019
ms.locfileid: "71696852"
---
# <a name="const-directive"></a><span data-ttu-id="b097a-102">#Const ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="b097a-102">#Const Directive</span></span>
<span data-ttu-id="b097a-103">Visual Basic の条件付きコンパイラ定数を定義します。</span><span class="sxs-lookup"><span data-stu-id="b097a-103">Defines conditional compiler constants for Visual Basic.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b097a-104">構文</span><span class="sxs-lookup"><span data-stu-id="b097a-104">Syntax</span></span>  
  
```vb  
#Const constname = expression  
```  
  
## <a name="parts"></a><span data-ttu-id="b097a-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="b097a-105">Parts</span></span>  
 `constname`  
 <span data-ttu-id="b097a-106">必須。</span><span class="sxs-lookup"><span data-stu-id="b097a-106">Required.</span></span> <span data-ttu-id="b097a-107">定義されている定数の名前。</span><span class="sxs-lookup"><span data-stu-id="b097a-107">Name of the constant being defined.</span></span>  
  
 `expression`  
 <span data-ttu-id="b097a-108">必須。</span><span class="sxs-lookup"><span data-stu-id="b097a-108">Required.</span></span> <span data-ttu-id="b097a-109">リテラル、その他の条件付きコンパイラ定数、またはすべての算術演算子または論理演算子を含む任意の組み合わせ (`Is` を除く)。</span><span class="sxs-lookup"><span data-stu-id="b097a-109">Literal, other conditional compiler constant, or any combination that includes any or all arithmetic or logical operators except `Is`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b097a-110">コメント</span><span class="sxs-lookup"><span data-stu-id="b097a-110">Remarks</span></span>  
 <span data-ttu-id="b097a-111">条件付きコンパイラ定数は、それらが表示されるファイルに対して常にプライベートです。</span><span class="sxs-lookup"><span data-stu-id="b097a-111">Conditional compiler constants are always private to the file in which they appear.</span></span> <span data-ttu-id="b097a-112">@No__t-0 ディレクティブを使用して、パブリックコンパイラ定数を作成することはできません。ユーザーインターフェイスまたは `/define` コンパイラオプションでのみ作成できます。</span><span class="sxs-lookup"><span data-stu-id="b097a-112">You cannot create public compiler constants using the `#Const` directive; you can create them only in the user interface or with the `/define` compiler option.</span></span>  
  
 <span data-ttu-id="b097a-113">@No__t-0 では、条件付きコンパイラ定数とリテラルのみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="b097a-113">You can use only conditional compiler constants and literals in `expression`.</span></span> <span data-ttu-id="b097a-114">@No__t-0 で定義された標準の定数を使用すると、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="b097a-114">Using a standard constant defined with `Const` causes an error.</span></span> <span data-ttu-id="b097a-115">逆に、`#Const` キーワードで定義された定数は、条件付きコンパイルにのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="b097a-115">Conversely, you can use constants defined with the `#Const` keyword only for conditional compilation.</span></span> <span data-ttu-id="b097a-116">定数は未定義にすることもできます。その場合、値は `Nothing` になります。</span><span class="sxs-lookup"><span data-stu-id="b097a-116">Constants can also be undefined, in which case they have a value of `Nothing`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b097a-117">例</span><span class="sxs-lookup"><span data-stu-id="b097a-117">Example</span></span>  
 <span data-ttu-id="b097a-118">`#Const` ディレクティブの使用例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="b097a-118">This example uses the `#Const` directive.</span></span>  
  
 [!code-vb[VbVbalrConditionalComp#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="b097a-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="b097a-119">See also</span></span>

- [<span data-ttu-id="b097a-120">/define (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b097a-120">/define (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/define.md)
- [<span data-ttu-id="b097a-121">#If...Then...#Else ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="b097a-121">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [<span data-ttu-id="b097a-122">Const ステートメント</span><span class="sxs-lookup"><span data-stu-id="b097a-122">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)
- [<span data-ttu-id="b097a-123">条件付きコンパイル</span><span class="sxs-lookup"><span data-stu-id="b097a-123">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- [<span data-ttu-id="b097a-124">If...Then...Else ステートメント</span><span class="sxs-lookup"><span data-stu-id="b097a-124">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
