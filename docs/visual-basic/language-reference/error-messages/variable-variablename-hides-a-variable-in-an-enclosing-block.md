---
title: 変数 '<variablename>' は、囲まれたブロック内の変数を非表示にします。
ms.date: 07/20/2015
f1_keywords:
- vbc30616
- bc30616
helpviewer_keywords:
- BC30616
ms.assetid: e7658ebc-da45-451b-a409-a0f8915f0beb
ms.openlocfilehash: 15c35cbb829bec782771b584ea25b111b81b5e1f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61766891"
---
# <a name="variable-variablename-hides-a-variable-in-an-enclosing-block"></a><span data-ttu-id="305b3-102">変数 '\<variablename >'、それを囲むブロック内の変数を非表示になります</span><span class="sxs-lookup"><span data-stu-id="305b3-102">Variable '\<variablename>' hides a variable in an enclosing block</span></span>
<span data-ttu-id="305b3-103">ブロックで囲まれた変数では、別のローカル変数と同じ名前を持ちます。</span><span class="sxs-lookup"><span data-stu-id="305b3-103">A variable enclosed in a block has the same name as another local variable.</span></span>  
  
 <span data-ttu-id="305b3-104">**エラー ID:** BC30616</span><span class="sxs-lookup"><span data-stu-id="305b3-104">**Error ID:** BC30616</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="305b3-105">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="305b3-105">To correct this error</span></span>  
  
- <span data-ttu-id="305b3-106">囲まれたブロック内の変数の名前を変更して、他の任意のローカル変数と同じではないようにします。</span><span class="sxs-lookup"><span data-stu-id="305b3-106">Rename the variable in the enclosed block so that it is not the same as any other local variables.</span></span> <span data-ttu-id="305b3-107">例:</span><span class="sxs-lookup"><span data-stu-id="305b3-107">For example:</span></span>  
  
    ```  
    Dim a, b, x As Integer  
    If a = b Then  
       Dim y As Integer = 20 ' Uniquely named block variable.  
    End If  
    ```  
  
- <span data-ttu-id="305b3-108">このエラーの一般的な原因は、使用`Catch e As Exception`イベント ハンドラーの内部。</span><span class="sxs-lookup"><span data-stu-id="305b3-108">A common cause for this error is the use of `Catch e As Exception` inside an event handler.</span></span> <span data-ttu-id="305b3-109">この場合は、名前、`Catch`ブロック変数`ex`なく`e`します。</span><span class="sxs-lookup"><span data-stu-id="305b3-109">If this is the case, name the `Catch` block variable `ex` rather than `e`.</span></span>  
  
- <span data-ttu-id="305b3-110">このエラーのもう 1 つの一般的な原因は内で宣言されたローカル変数にアクセスしようとする`Try`個別のブロック`Catch`ブロック。</span><span class="sxs-lookup"><span data-stu-id="305b3-110">Another common source of this error is an attempt to access a local variable declared within a `Try` block in a separate `Catch` block.</span></span> <span data-ttu-id="305b3-111">これを修正するには、外部変数を宣言、`Try...Catch...Finally`構造体。</span><span class="sxs-lookup"><span data-stu-id="305b3-111">To correct this, declare the variable outside the `Try...Catch...Finally` structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="305b3-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="305b3-112">See also</span></span>

- [<span data-ttu-id="305b3-113">Try...Catch...Finally ステートメント</span><span class="sxs-lookup"><span data-stu-id="305b3-113">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="305b3-114">変数宣言</span><span class="sxs-lookup"><span data-stu-id="305b3-114">Variable Declaration</span></span>](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
