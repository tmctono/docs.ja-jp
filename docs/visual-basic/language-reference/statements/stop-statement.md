---
title: Stop ステートメント (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Stop
helpviewer_keywords:
- breakpoints, Stop statements
- Stop statements [Visual Basic], syntax
- Stop statements [Visual Basic]
- execution [Visual Basic], suspending
- processing, interrupting
- processes, interrupting
- execution [Visual Basic], stopping
ms.assetid: c9a9fde0-d649-4662-9bef-bd0146ebc2a7
ms.openlocfilehash: e9382ee34842fc3a3b4b23f71848bda602c99780
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583218"
---
# <a name="stop-statement-visual-basic"></a><span data-ttu-id="1f226-102">Stop ステートメント (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1f226-102">Stop Statement (Visual Basic)</span></span>
<span data-ttu-id="1f226-103">実行を中断します。</span><span class="sxs-lookup"><span data-stu-id="1f226-103">Suspends execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f226-104">構文</span><span class="sxs-lookup"><span data-stu-id="1f226-104">Syntax</span></span>  
  
```vb  
Stop  
```  
  
## <a name="remarks"></a><span data-ttu-id="1f226-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="1f226-105">Remarks</span></span>  
 <span data-ttu-id="1f226-106">プロシージャ内の任意の場所に `Stop` ステートメントを配置して、実行を中断することができます。</span><span class="sxs-lookup"><span data-stu-id="1f226-106">You can place `Stop` statements anywhere in procedures to suspend execution.</span></span> <span data-ttu-id="1f226-107">@No__t_0 ステートメントの使用は、コードにブレークポイントを設定することと似ています。</span><span class="sxs-lookup"><span data-stu-id="1f226-107">Using the `Stop` statement is similar to setting a breakpoint in the code.</span></span>  
  
 <span data-ttu-id="1f226-108">@No__t_0 ステートメントは実行を中断しますが、`End` とは異なり、コンパイル済みの実行可能 (.exe) ファイルに存在しない限り、ファイルは閉じられず、変数はクリアされません。</span><span class="sxs-lookup"><span data-stu-id="1f226-108">The `Stop` statement suspends execution, but unlike `End`, it does not close any files or clear any variables, unless it is encountered in a compiled executable (.exe) file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1f226-109">統合開発環境 (IDE: integrated development environment) の外部で実行されているコードで `Stop` ステートメントが検出されると、デバッガーが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="1f226-109">If the `Stop` statement is encountered in code that is running outside of the integrated development environment (IDE), the debugger is invoked.</span></span> <span data-ttu-id="1f226-110">これは、コードがデバッグモードとリテールモードのどちらでコンパイルされたかに関係なく当てはまります。</span><span class="sxs-lookup"><span data-stu-id="1f226-110">This is true regardless of whether the code was compiled in debug or retail mode.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1f226-111">例</span><span class="sxs-lookup"><span data-stu-id="1f226-111">Example</span></span>  
 <span data-ttu-id="1f226-112">この例では、`Stop` ステートメントを使用して、`For...Next` ループを通じて各反復処理の実行を中断します。</span><span class="sxs-lookup"><span data-stu-id="1f226-112">This example uses the `Stop` statement to suspend execution for each iteration through the `For...Next` loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#56)]  
  
## <a name="see-also"></a><span data-ttu-id="1f226-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="1f226-113">See also</span></span>

- [<span data-ttu-id="1f226-114">End ステートメント</span><span class="sxs-lookup"><span data-stu-id="1f226-114">End Statement</span></span>](../../../visual-basic/language-reference/statements/end-statement.md)
