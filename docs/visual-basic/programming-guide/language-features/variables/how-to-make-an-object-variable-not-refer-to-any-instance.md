---
title: '方法: オブジェクト変数がインスタンスを参照しないようにする'
ms.date: 07/20/2015
helpviewer_keywords:
- Nothing keyword [Visual Basic], variable assignment
- object variables [Visual Basic], null reference
ms.assetid: e6d30578-bdae-4142-a3ac-a10697bf696a
ms.openlocfilehash: 61bb06401ebd1e479c9256a80a12d87240831063
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "91080256"
---
# <a name="how-to-make-an-object-variable-not-refer-to-any-instance-visual-basic"></a><span data-ttu-id="7cc46-102">方法: オブジェクト変数がインスタンスを参照しないようにする (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7cc46-102">How to: Make an Object Variable Not Refer to Any Instance (Visual Basic)</span></span>

<span data-ttu-id="7cc46-103">オブジェクト変数を [Nothing](../../../language-reference/nothing.md) に設定すると、任意のオブジェクト インスタンスとの関連付けを解除できます。</span><span class="sxs-lookup"><span data-stu-id="7cc46-103">You can disassociate an object variable from any object instance by setting it to [Nothing](../../../language-reference/nothing.md).</span></span>  
  
### <a name="to-disassociate-an-object-variable-from-any-object-instance"></a><span data-ttu-id="7cc46-104">オブジェクト変数とオブジェクト インスタンスの関連付けを解除するには</span><span class="sxs-lookup"><span data-stu-id="7cc46-104">To disassociate an object variable from any object instance</span></span>  
  
- <span data-ttu-id="7cc46-105">代入ステートメントで変数を `Nothing` に設定します。</span><span class="sxs-lookup"><span data-stu-id="7cc46-105">Set the variable to `Nothing` in an assignment statement.</span></span>  
  
    ```vb  
    ' Assume account is a defined class  
    Dim currentAccount As account  
    currentAccount = Nothing  
    ```  
  
## <a name="robust-programming"></a><span data-ttu-id="7cc46-106">信頼性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="7cc46-106">Robust Programming</span></span>  

 <span data-ttu-id="7cc46-107">コードで、`Nothing` に設定されているオブジェクト変数のメンバーにアクセスしようとすると、<xref:System.NullReferenceException> が発生します。</span><span class="sxs-lookup"><span data-stu-id="7cc46-107">If your code tries to access a member of an object variable that has been set to `Nothing`, a <xref:System.NullReferenceException> occurs.</span></span> <span data-ttu-id="7cc46-108">オブジェクト変数を頻繁に `Nothing` に設定する場合、または変数が初期化されていない可能性がある場合は、メンバー アクセスを `Try...Catch...Finally` ブロックで囲むことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7cc46-108">If you set an object variable to `Nothing` frequently, or if it is possible the variable is not initialized, it is a good idea to enclose member accesses in a `Try...Catch...Finally` block.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="7cc46-109">.NET Framework セキュリティ</span><span class="sxs-lookup"><span data-stu-id="7cc46-109">.NET Framework Security</span></span>  

 <span data-ttu-id="7cc46-110">機密データを含むオブジェクトに対してオブジェクト変数を使用する場合は、これらのオブジェクトのいずれかをアクティブに処理していないときに、この変数を `Nothing` に設定できます。</span><span class="sxs-lookup"><span data-stu-id="7cc46-110">If you use an object variable for objects that contain confidential or sensitive data, you can set the variable to `Nothing` when you are not actively dealing with one of those objects.</span></span> <span data-ttu-id="7cc46-111">これにより、悪意のあるコードからデータにアクセスされる可能性が低くなります。</span><span class="sxs-lookup"><span data-stu-id="7cc46-111">This reduces the chance of malicious code gaining access to the data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cc46-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="7cc46-112">See also</span></span>

- <xref:System.NullReferenceException>
- [<span data-ttu-id="7cc46-113">オブジェクト変数</span><span class="sxs-lookup"><span data-stu-id="7cc46-113">Object Variables</span></span>](object-variables.md)
- [<span data-ttu-id="7cc46-114">オブジェクト変数の代入</span><span class="sxs-lookup"><span data-stu-id="7cc46-114">Object Variable Assignment</span></span>](object-variable-assignment.md)
- [<span data-ttu-id="7cc46-115">Nothing</span><span class="sxs-lookup"><span data-stu-id="7cc46-115">Nothing</span></span>](../../../language-reference/nothing.md)
- [<span data-ttu-id="7cc46-116">Try...Catch...Finally ステートメント</span><span class="sxs-lookup"><span data-stu-id="7cc46-116">Try...Catch...Finally Statement</span></span>](../../../language-reference/statements/try-catch-finally-statement.md)
