---
title: 変数 '<variablename>' は、囲まれたブロック内の変数を非表示にします。
ms.date: 07/20/2015
f1_keywords:
- vbc30616
- bc30616
helpviewer_keywords:
- BC30616
ms.assetid: e7658ebc-da45-451b-a409-a0f8915f0beb
ms.openlocfilehash: 4312abef83728f432e2f6a492e5acad3450719b1
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2019
ms.locfileid: "71592062"
---
# <a name="variable-variablename-hides-a-variable-in-an-enclosing-block"></a><span data-ttu-id="297fe-102">変数 ' \<variablename > ' は、それを囲むブロック内の変数を非表示にします</span><span class="sxs-lookup"><span data-stu-id="297fe-102">Variable '\<variablename>' hides a variable in an enclosing block</span></span>
<span data-ttu-id="297fe-103">ブロックで囲まれた変数に、別のローカル変数と同じ名前が指定されています。</span><span class="sxs-lookup"><span data-stu-id="297fe-103">A variable enclosed in a block has the same name as another local variable.</span></span>  
  
 <span data-ttu-id="297fe-104">**エラー ID:** BC30616</span><span class="sxs-lookup"><span data-stu-id="297fe-104">**Error ID:** BC30616</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="297fe-105">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="297fe-105">To correct this error</span></span>  
  
- <span data-ttu-id="297fe-106">囲まれたブロック内の変数の名前を変更して、他のローカル変数と同じにならないようにします。</span><span class="sxs-lookup"><span data-stu-id="297fe-106">Rename the variable in the enclosed block so that it is not the same as any other local variables.</span></span> <span data-ttu-id="297fe-107">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="297fe-107">For example:</span></span>  
  
    ```vb  
    Dim a, b, x As Integer  
    If a = b Then  
       Dim y As Integer = 20 ' Uniquely named block variable.  
    End If  
    ```  
  
- <span data-ttu-id="297fe-108">このエラーの一般的な原因は、イベントハンドラー内で `Catch e As Exception` を使用することです。</span><span class="sxs-lookup"><span data-stu-id="297fe-108">A common cause for this error is the use of `Catch e As Exception` inside an event handler.</span></span> <span data-ttu-id="297fe-109">この場合は、`Catch` ブロック変数に `e` ではなく-1 @no__t 名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="297fe-109">If this is the case, name the `Catch` block variable `ex` rather than `e`.</span></span>  
  
- <span data-ttu-id="297fe-110">このエラーのもう1つの一般的な原因は、別の `Catch` ブロック内の @no__t 0 ブロック内で宣言されたローカル変数にアクセスしようとすることです。</span><span class="sxs-lookup"><span data-stu-id="297fe-110">Another common source of this error is an attempt to access a local variable declared within a `Try` block in a separate `Catch` block.</span></span> <span data-ttu-id="297fe-111">これを修正するには、変数を @no__t 0 の構造体の外に宣言します。</span><span class="sxs-lookup"><span data-stu-id="297fe-111">To correct this, declare the variable outside the `Try...Catch...Finally` structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="297fe-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="297fe-112">See also</span></span>

- [<span data-ttu-id="297fe-113">Try...Catch...Finally ステートメント</span><span class="sxs-lookup"><span data-stu-id="297fe-113">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="297fe-114">変数宣言</span><span class="sxs-lookup"><span data-stu-id="297fe-114">Variable Declaration</span></span>](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
