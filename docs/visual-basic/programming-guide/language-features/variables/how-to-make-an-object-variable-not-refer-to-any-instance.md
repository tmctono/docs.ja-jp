---
title: '方法: オブジェクト変数がインスタンスを参照しないようにする (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- Nothing keyword [Visual Basic], variable assignment
- object variables [Visual Basic], null reference
ms.assetid: e6d30578-bdae-4142-a3ac-a10697bf696a
ms.openlocfilehash: e647f2f891b06aa1767faac49b01df98ea31ec1c
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004905"
---
# <a name="how-to-make-an-object-variable-not-refer-to-any-instance-visual-basic"></a><span data-ttu-id="0c0e3-102">方法: オブジェクト変数がインスタンスを参照しないようにする (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0c0e3-102">How to: Make an Object Variable Not Refer to Any Instance (Visual Basic)</span></span>
<span data-ttu-id="0c0e3-103">オブジェクト変数を[Nothing](../../../../visual-basic/language-reference/nothing.md)に設定することによって、オブジェクトのインスタンスの関連付けを解除できます。</span><span class="sxs-lookup"><span data-stu-id="0c0e3-103">You can disassociate an object variable from any object instance by setting it to [Nothing](../../../../visual-basic/language-reference/nothing.md).</span></span>  
  
### <a name="to-disassociate-an-object-variable-from-any-object-instance"></a><span data-ttu-id="0c0e3-104">オブジェクト変数とオブジェクトインスタンスの関連付けを解除するには</span><span class="sxs-lookup"><span data-stu-id="0c0e3-104">To disassociate an object variable from any object instance</span></span>  
  
- <span data-ttu-id="0c0e3-105">代入ステートメントで、変数を `Nothing` に設定します。</span><span class="sxs-lookup"><span data-stu-id="0c0e3-105">Set the variable to `Nothing` in an assignment statement.</span></span>  
  
    ```vb  
    ' Assume account is a defined class  
    Dim currentAccount As account  
    currentAccount = Nothing  
    ```  
  
## <a name="robust-programming"></a><span data-ttu-id="0c0e3-106">信頼性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="0c0e3-106">Robust Programming</span></span>  
 <span data-ttu-id="0c0e3-107">コードが `Nothing` に設定されているオブジェクト変数のメンバーにアクセスしようとすると、<xref:System.NullReferenceException> が発生します。</span><span class="sxs-lookup"><span data-stu-id="0c0e3-107">If your code tries to access a member of an object variable that has been set to `Nothing`, a <xref:System.NullReferenceException> occurs.</span></span> <span data-ttu-id="0c0e3-108">オブジェクト変数を `Nothing` に頻繁に設定した場合、または変数が初期化されていない可能性がある場合は、メンバーアクセスを `Try...Catch...Finally` ブロックで囲むことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0c0e3-108">If you set an object variable to `Nothing` frequently, or if it is possible the variable is not initialized, it is a good idea to enclose member accesses in a `Try...Catch...Finally` block.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="0c0e3-109">.NET Framework セキュリティ</span><span class="sxs-lookup"><span data-stu-id="0c0e3-109">.NET Framework Security</span></span>  
 <span data-ttu-id="0c0e3-110">機密データを含むオブジェクトに対してオブジェクト変数を使用する場合は、これらのオブジェクトのいずれかをアクティブに処理していないときに、変数を `Nothing` に設定できます。</span><span class="sxs-lookup"><span data-stu-id="0c0e3-110">If you use an object variable for objects that contain confidential or sensitive data, you can set the variable to `Nothing` when you are not actively dealing with one of those objects.</span></span> <span data-ttu-id="0c0e3-111">これにより、悪意のあるコードがデータにアクセスする可能性が低くなります。</span><span class="sxs-lookup"><span data-stu-id="0c0e3-111">This reduces the chance of malicious code gaining access to the data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c0e3-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="0c0e3-112">See also</span></span>

- <xref:System.NullReferenceException>
- [<span data-ttu-id="0c0e3-113">オブジェクト変数</span><span class="sxs-lookup"><span data-stu-id="0c0e3-113">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="0c0e3-114">オブジェクト変数の代入</span><span class="sxs-lookup"><span data-stu-id="0c0e3-114">Object Variable Assignment</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [<span data-ttu-id="0c0e3-115">Nothing</span><span class="sxs-lookup"><span data-stu-id="0c0e3-115">Nothing</span></span>](../../../../visual-basic/language-reference/nothing.md)
- [<span data-ttu-id="0c0e3-116">Try...Catch...Finally ステートメント</span><span class="sxs-lookup"><span data-stu-id="0c0e3-116">Try...Catch...Finally Statement</span></span>](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
