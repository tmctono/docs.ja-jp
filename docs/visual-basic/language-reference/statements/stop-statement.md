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
ms.openlocfilehash: a617038ec51d98c62b6cf7e3c124c8af01305bac
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957621"
---
# <a name="stop-statement-visual-basic"></a><span data-ttu-id="3a6b2-102">Stop ステートメント (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3a6b2-102">Stop Statement (Visual Basic)</span></span>
<span data-ttu-id="3a6b2-103">実行を中断します。</span><span class="sxs-lookup"><span data-stu-id="3a6b2-103">Suspends execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a6b2-104">構文</span><span class="sxs-lookup"><span data-stu-id="3a6b2-104">Syntax</span></span>  
  
```  
Stop  
```  
  
## <a name="remarks"></a><span data-ttu-id="3a6b2-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="3a6b2-105">Remarks</span></span>  
 <span data-ttu-id="3a6b2-106">ステートメントをプロシージャ`Stop`内の任意の場所に配置して、実行を中断することができます。</span><span class="sxs-lookup"><span data-stu-id="3a6b2-106">You can place `Stop` statements anywhere in procedures to suspend execution.</span></span> <span data-ttu-id="3a6b2-107">`Stop`ステートメントを使用することは、コードにブレークポイントを設定することと似ています。</span><span class="sxs-lookup"><span data-stu-id="3a6b2-107">Using the `Stop` statement is similar to setting a breakpoint in the code.</span></span>  
  
 <span data-ttu-id="3a6b2-108">ステートメント`Stop`は実行を中断します`End`が、とは異なり、コンパイルされた実行可能 (.exe) ファイルに存在しない限り、ファイルを閉じたり変数をクリアしたりすることはありません。</span><span class="sxs-lookup"><span data-stu-id="3a6b2-108">The `Stop` statement suspends execution, but unlike `End`, it does not close any files or clear any variables, unless it is encountered in a compiled executable (.exe) file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3a6b2-109">統合開発環境 (IDE: integrated development environment) の外部で実行されているコードでステートメントが検出されると、デバッガーが呼び出されます。`Stop`</span><span class="sxs-lookup"><span data-stu-id="3a6b2-109">If the `Stop` statement is encountered in code that is running outside of the integrated development environment (IDE), the debugger is invoked.</span></span> <span data-ttu-id="3a6b2-110">これは、コードがデバッグモードとリテールモードのどちらでコンパイルされたかに関係なく当てはまります。</span><span class="sxs-lookup"><span data-stu-id="3a6b2-110">This is true regardless of whether the code was compiled in debug or retail mode.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3a6b2-111">例</span><span class="sxs-lookup"><span data-stu-id="3a6b2-111">Example</span></span>  
 <span data-ttu-id="3a6b2-112">この例では`Stop` 、ステートメントを使用し`For...Next`て、ループを通じて各反復処理の実行を中断します。</span><span class="sxs-lookup"><span data-stu-id="3a6b2-112">This example uses the `Stop` statement to suspend execution for each iteration through the `For...Next` loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#56)]  
  
## <a name="see-also"></a><span data-ttu-id="3a6b2-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="3a6b2-113">See also</span></span>

- [<span data-ttu-id="3a6b2-114">End ステートメント</span><span class="sxs-lookup"><span data-stu-id="3a6b2-114">End Statement</span></span>](../../../visual-basic/language-reference/statements/end-statement.md)
