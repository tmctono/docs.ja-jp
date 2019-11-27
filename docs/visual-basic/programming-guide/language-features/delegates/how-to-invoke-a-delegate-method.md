---
title: '方法: デリゲート メソッドを呼び出す'
ms.date: 07/20/2015
ms.assetid: b56866ae-abf9-4a5a-a855-486359455e9c
ms.openlocfilehash: 520bacfbe6103490e0459cd5af149c1d55a8fce4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345266"
---
# <a name="how-to-invoke-a-delegate-method-visual-basic"></a><span data-ttu-id="3d2bf-102">方法: デリゲート メソッドを呼び出す (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3d2bf-102">How to: Invoke a Delegate Method (Visual Basic)</span></span>

<span data-ttu-id="3d2bf-103">この例では、メソッドをデリゲートに関連付けて、デリゲートを使用してそのメソッドを呼び出す方法を示します。</span><span class="sxs-lookup"><span data-stu-id="3d2bf-103">This example shows how to associate a method with a delegate and then invoke that method through the delegate.</span></span>

### <a name="create-the-delegate-and-matching-procedures"></a><span data-ttu-id="3d2bf-104">デリゲートと一致するプロシージャを作成する</span><span class="sxs-lookup"><span data-stu-id="3d2bf-104">Create the delegate and matching procedures</span></span>

1. <span data-ttu-id="3d2bf-105">`MySubDelegate`という名前のデリゲートを作成します。</span><span class="sxs-lookup"><span data-stu-id="3d2bf-105">Create a delegate named `MySubDelegate`.</span></span>

    ```vb
    Delegate Sub MySubDelegate(ByVal x As Integer)
    ```

2. <span data-ttu-id="3d2bf-106">デリゲートと同じシグネチャを持つメソッドを含むクラスを宣言します。</span><span class="sxs-lookup"><span data-stu-id="3d2bf-106">Declare a class that contains a method with the same signature as the delegate.</span></span>

    ```vb
    Class class1
        Sub Sub1(ByVal x As Integer)
            MsgBox("The value of x is: " & CStr(x))
        End Sub
    End Class
    ```

3. <span data-ttu-id="3d2bf-107">デリゲートのインスタンスを作成し、組み込みの `Invoke` メソッドを呼び出すことによって、デリゲートに関連付けられているメソッドを呼び出すメソッドを定義します。</span><span class="sxs-lookup"><span data-stu-id="3d2bf-107">Define a method that creates an instance of the delegate and invokes the method associated with the delegate by calling the built-in `Invoke` method.</span></span>

    ```vb
    Protected Sub DelegateTest()
        Dim c1 As New class1
        ' Create an instance of the delegate.
        Dim msd As MySubDelegate = AddressOf c1.Sub1
        ' Call the method.
        msd.Invoke(10)
    End Sub
    ```

## <a name="see-also"></a><span data-ttu-id="3d2bf-108">参照</span><span class="sxs-lookup"><span data-stu-id="3d2bf-108">See also</span></span>

- [<span data-ttu-id="3d2bf-109">Delegate ステートメント</span><span class="sxs-lookup"><span data-stu-id="3d2bf-109">Delegate Statement</span></span>](../../../../visual-basic/language-reference/statements/delegate-statement.md)
- [<span data-ttu-id="3d2bf-110">デリゲート</span><span class="sxs-lookup"><span data-stu-id="3d2bf-110">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="3d2bf-111">イベント</span><span class="sxs-lookup"><span data-stu-id="3d2bf-111">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)
- [<span data-ttu-id="3d2bf-112">マルチスレッド アプリケーション</span><span class="sxs-lookup"><span data-stu-id="3d2bf-112">Multithreaded Applications</span></span>](../../../../standard/threading/using-threads-and-threading.md)
