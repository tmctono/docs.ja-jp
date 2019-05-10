---
title: '方法: オブジェクトが変数になる任意のインスタンス (Visual Basic) を参照していません'
ms.date: 07/20/2015
helpviewer_keywords:
- Nothing keyword [Visual Basic], variable assignment
- object variables [Visual Basic], null reference
ms.assetid: e6d30578-bdae-4142-a3ac-a10697bf696a
ms.openlocfilehash: 820d4cb9d17bf467d257bfbba5f43f07228c0b4f
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64663556"
---
# <a name="how-to-make-an-object-variable-not-refer-to-any-instance-visual-basic"></a><span data-ttu-id="2d689-102">方法: オブジェクトが変数になる任意のインスタンス (Visual Basic) を参照していません</span><span class="sxs-lookup"><span data-stu-id="2d689-102">How to: Make an Object Variable Not Refer to Any Instance (Visual Basic)</span></span>
<span data-ttu-id="2d689-103">任意のオブジェクトのインスタンスからオブジェクト変数設定することで関連付けを解除することができます[Nothing](../../../../visual-basic/language-reference/nothing.md)します。</span><span class="sxs-lookup"><span data-stu-id="2d689-103">You can disassociate an object variable from any object instance by setting it to [Nothing](../../../../visual-basic/language-reference/nothing.md).</span></span>  
  
### <a name="to-disassociate-an-object-variable-from-any-object-instance"></a><span data-ttu-id="2d689-104">任意のオブジェクトのインスタンスからオブジェクト変数の関連付けを解除するには</span><span class="sxs-lookup"><span data-stu-id="2d689-104">To disassociate an object variable from any object instance</span></span>  
  
- <span data-ttu-id="2d689-105">変数を設定します`Nothing`代入ステートメントでします。</span><span class="sxs-lookup"><span data-stu-id="2d689-105">Set the variable to `Nothing` in an assignment statement.</span></span>  
  
    ```  
    ' Assume account is a defined class  
    Dim currentAccount As account  
    currentAccount = Nothing  
    ```  
  
## <a name="robust-programming"></a><span data-ttu-id="2d689-106">信頼性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="2d689-106">Robust Programming</span></span>  
 <span data-ttu-id="2d689-107">設定されているオブジェクト変数のメンバーにアクセスしようとすると、コード`Nothing`、<xref:System.NullReferenceException>に発生します。</span><span class="sxs-lookup"><span data-stu-id="2d689-107">If your code tries to access a member of an object variable that has been set to `Nothing`, a <xref:System.NullReferenceException> occurs.</span></span> <span data-ttu-id="2d689-108">オブジェクト変数を設定した場合`Nothing`多くの場合、またはのメンバーへのアクセスを囲むことをお勧め、変数が初期化されていないが可能ですが場合、は、`Try...Catch...Finally`ブロックします。</span><span class="sxs-lookup"><span data-stu-id="2d689-108">If you set an object variable to `Nothing` frequently, or if it is possible the variable is not initialized, it is a good idea to enclose member accesses in a `Try...Catch...Finally` block.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="2d689-109">.NET Framework セキュリティ</span><span class="sxs-lookup"><span data-stu-id="2d689-109">.NET Framework Security</span></span>  
 <span data-ttu-id="2d689-110">機密情報や機密データを格納するオブジェクトをオブジェクト変数を使用する場合変数を設定することができます`Nothing`ときにアクティブに処理するいないとそれらのオブジェクトのいずれか。</span><span class="sxs-lookup"><span data-stu-id="2d689-110">If you use an object variable for objects that contain confidential or sensitive data, you can set the variable to `Nothing` when you are not actively dealing with one of those objects.</span></span> <span data-ttu-id="2d689-111">これにより、悪意のあるコードがデータにアクセスする可能性が減少します。</span><span class="sxs-lookup"><span data-stu-id="2d689-111">This reduces the chance of malicious code gaining access to the data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d689-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="2d689-112">See also</span></span>

- <xref:System.NullReferenceException>
- [<span data-ttu-id="2d689-113">オブジェクト変数</span><span class="sxs-lookup"><span data-stu-id="2d689-113">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="2d689-114">オブジェクト変数の代入</span><span class="sxs-lookup"><span data-stu-id="2d689-114">Object Variable Assignment</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [<span data-ttu-id="2d689-115">Nothing</span><span class="sxs-lookup"><span data-stu-id="2d689-115">Nothing</span></span>](../../../../visual-basic/language-reference/nothing.md)
- [<span data-ttu-id="2d689-116">Try...Catch...Finally ステートメント</span><span class="sxs-lookup"><span data-stu-id="2d689-116">Try...Catch...Finally Statement</span></span>](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
