---
title: '方法: オブジェクトが変数になる任意のインスタンス (Visual Basic) を参照していません'
ms.date: 07/20/2015
helpviewer_keywords:
- Nothing keyword [Visual Basic], variable assignment
- object variables [Visual Basic], null reference
ms.assetid: e6d30578-bdae-4142-a3ac-a10697bf696a
ms.openlocfilehash: 373d4ae84c44b212ad02b0b4266af75921e40423
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61769058"
---
# <a name="how-to-make-an-object-variable-not-refer-to-any-instance-visual-basic"></a><span data-ttu-id="c935b-102">方法: オブジェクトが変数になる任意のインスタンス (Visual Basic) を参照していません</span><span class="sxs-lookup"><span data-stu-id="c935b-102">How to: Make an Object Variable Not Refer to Any Instance (Visual Basic)</span></span>
<span data-ttu-id="c935b-103">任意のオブジェクトのインスタンスからオブジェクト変数設定することで関連付けを解除することができます[Nothing](../../../../visual-basic/language-reference/nothing.md)します。</span><span class="sxs-lookup"><span data-stu-id="c935b-103">You can disassociate an object variable from any object instance by setting it to [Nothing](../../../../visual-basic/language-reference/nothing.md).</span></span>  
  
### <a name="to-disassociate-an-object-variable-from-any-object-instance"></a><span data-ttu-id="c935b-104">任意のオブジェクトのインスタンスからオブジェクト変数の関連付けを解除するには</span><span class="sxs-lookup"><span data-stu-id="c935b-104">To disassociate an object variable from any object instance</span></span>  
  
- <span data-ttu-id="c935b-105">変数を設定します`Nothing`代入ステートメントでします。</span><span class="sxs-lookup"><span data-stu-id="c935b-105">Set the variable to `Nothing` in an assignment statement.</span></span>  
  
    ```  
    ' Assume account is a defined class  
    Dim currentAccount As account  
    currentAccount = Nothing  
    ```  
  
## <a name="robust-programming"></a><span data-ttu-id="c935b-106">信頼性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="c935b-106">Robust Programming</span></span>  
 <span data-ttu-id="c935b-107">設定されているオブジェクト変数のメンバーにアクセスしようとすると、コード`Nothing`、<xref:System.NullReferenceException>に発生します。</span><span class="sxs-lookup"><span data-stu-id="c935b-107">If your code tries to access a member of an object variable that has been set to `Nothing`, a <xref:System.NullReferenceException> occurs.</span></span> <span data-ttu-id="c935b-108">オブジェクト変数を設定した場合`Nothing`多くの場合、またはのメンバーへのアクセスを囲むことをお勧め、変数が初期化されていないが可能ですが場合、は、`Try...Catch...Finally`ブロックします。</span><span class="sxs-lookup"><span data-stu-id="c935b-108">If you set an object variable to `Nothing` frequently, or if it is possible the variable is not initialized, it is a good idea to enclose member accesses in a `Try...Catch...Finally` block.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="c935b-109">.NET Framework セキュリティ</span><span class="sxs-lookup"><span data-stu-id="c935b-109">.NET Framework Security</span></span>  
 <span data-ttu-id="c935b-110">機密情報や機密データを格納するオブジェクトをオブジェクト変数を使用する場合変数を設定することができます`Nothing`ときにアクティブに処理するいないとそれらのオブジェクトのいずれか。</span><span class="sxs-lookup"><span data-stu-id="c935b-110">If you use an object variable for objects that contain confidential or sensitive data, you can set the variable to `Nothing` when you are not actively dealing with one of those objects.</span></span> <span data-ttu-id="c935b-111">これにより、悪意のあるコードがデータにアクセスする可能性が減少します。</span><span class="sxs-lookup"><span data-stu-id="c935b-111">This reduces the chance of malicious code gaining access to the data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c935b-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="c935b-112">See also</span></span>

- <xref:System.NullReferenceException>
- [<span data-ttu-id="c935b-113">オブジェクト変数</span><span class="sxs-lookup"><span data-stu-id="c935b-113">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="c935b-114">オブジェクト変数の代入</span><span class="sxs-lookup"><span data-stu-id="c935b-114">Object Variable Assignment</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [<span data-ttu-id="c935b-115">Nothing</span><span class="sxs-lookup"><span data-stu-id="c935b-115">Nothing</span></span>](../../../../visual-basic/language-reference/nothing.md)
- [<span data-ttu-id="c935b-116">Try...Catch...Finally ステートメント</span><span class="sxs-lookup"><span data-stu-id="c935b-116">Try...Catch...Finally Statement</span></span>](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
