---
title: '#Const ディレクティブ'
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
ms.openlocfilehash: 278219edb1bb5d1c0bb015611d69cbe4ae70014b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343845"
---
# <a name="const-directive"></a><span data-ttu-id="ad62c-102">#Const ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="ad62c-102">#Const Directive</span></span>

<span data-ttu-id="ad62c-103">Visual Basic の条件付きコンパイラ定数を定義します。</span><span class="sxs-lookup"><span data-stu-id="ad62c-103">Defines conditional compiler constants for Visual Basic.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad62c-104">構文</span><span class="sxs-lookup"><span data-stu-id="ad62c-104">Syntax</span></span>  
  
```vb  
#Const constname = expression  
```  
  
## <a name="parts"></a><span data-ttu-id="ad62c-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="ad62c-105">Parts</span></span>  

 `constname`  
 <span data-ttu-id="ad62c-106">必須。</span><span class="sxs-lookup"><span data-stu-id="ad62c-106">Required.</span></span> <span data-ttu-id="ad62c-107">定義されている定数の名前。</span><span class="sxs-lookup"><span data-stu-id="ad62c-107">Name of the constant being defined.</span></span>  
  
 `expression`  
 <span data-ttu-id="ad62c-108">必須。</span><span class="sxs-lookup"><span data-stu-id="ad62c-108">Required.</span></span> <span data-ttu-id="ad62c-109">リテラル、その他の条件付きコンパイラ定数、または `Is`を除く任意またはすべての算術演算子または論理演算子を含む任意の組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="ad62c-109">Literal, other conditional compiler constant, or any combination that includes any or all arithmetic or logical operators except `Is`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ad62c-110">コメント</span><span class="sxs-lookup"><span data-stu-id="ad62c-110">Remarks</span></span>  

 <span data-ttu-id="ad62c-111">条件付きコンパイラ定数は、それらが表示されるファイルに対して常にプライベートです。</span><span class="sxs-lookup"><span data-stu-id="ad62c-111">Conditional compiler constants are always private to the file in which they appear.</span></span> <span data-ttu-id="ad62c-112">`#Const` ディレクティブを使用して、パブリックコンパイラ定数を作成することはできません。これらは、ユーザーインターフェイスまたは `/define` コンパイラオプションでのみ作成できます。</span><span class="sxs-lookup"><span data-stu-id="ad62c-112">You cannot create public compiler constants using the `#Const` directive; you can create them only in the user interface or with the `/define` compiler option.</span></span>  
  
 <span data-ttu-id="ad62c-113">`expression`では、条件付きコンパイラ定数とリテラルのみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="ad62c-113">You can use only conditional compiler constants and literals in `expression`.</span></span> <span data-ttu-id="ad62c-114">`Const` で定義された標準定数を使用すると、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="ad62c-114">Using a standard constant defined with `Const` causes an error.</span></span> <span data-ttu-id="ad62c-115">逆に、`#Const` キーワードで定義された定数は、条件付きコンパイルに対してのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="ad62c-115">Conversely, you can use constants defined with the `#Const` keyword only for conditional compilation.</span></span> <span data-ttu-id="ad62c-116">定数を未定義にすることもできます。その場合、値は `Nothing`になります。</span><span class="sxs-lookup"><span data-stu-id="ad62c-116">Constants can also be undefined, in which case they have a value of `Nothing`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ad62c-117">例</span><span class="sxs-lookup"><span data-stu-id="ad62c-117">Example</span></span>  

 <span data-ttu-id="ad62c-118">`#Const` ディレクティブの使用例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="ad62c-118">This example uses the `#Const` directive.</span></span>  
  
 [!code-vb[VbVbalrConditionalComp#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="ad62c-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="ad62c-119">See also</span></span>

- [<span data-ttu-id="ad62c-120">-define (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ad62c-120">-define (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/define.md)
- [<span data-ttu-id="ad62c-121">#If...Then...#Else ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="ad62c-121">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [<span data-ttu-id="ad62c-122">Const ステートメント</span><span class="sxs-lookup"><span data-stu-id="ad62c-122">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)
- [<span data-ttu-id="ad62c-123">条件付きコンパイル</span><span class="sxs-lookup"><span data-stu-id="ad62c-123">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- [<span data-ttu-id="ad62c-124">If...Then...Else ステートメント</span><span class="sxs-lookup"><span data-stu-id="ad62c-124">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
