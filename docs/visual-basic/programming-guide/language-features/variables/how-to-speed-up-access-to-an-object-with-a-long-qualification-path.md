---
title: '方法: 長い修飾パスを使用してオブジェクトへのアクセスを高速化する (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], accessing
- variables [Visual Basic], object
- With statement [Visual Basic]
- With block
- object variables [Visual Basic], accessing
ms.assetid: 3eb7657f-c9fe-4e05-8bc3-4bb14d5ae585
ms.openlocfilehash: a8e50a2ed04037b48091321dc0c9ac2ea1db35f4
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2019
ms.locfileid: "68631101"
---
# <a name="how-to-speed-up-access-to-an-object-with-a-long-qualification-path-visual-basic"></a><span data-ttu-id="57d7a-102">方法: 長い修飾パスを使用してオブジェクトへのアクセスを高速化する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="57d7a-102">How to: Speed Up Access to an Object with a Long Qualification Path (Visual Basic)</span></span>

<span data-ttu-id="57d7a-103">複数のメソッドおよびプロパティの修飾パスを必要とするオブジェクトに頻繁にアクセスする場合は、修飾パスを繰り返さないことでコードを高速化できます。</span><span class="sxs-lookup"><span data-stu-id="57d7a-103">If you frequently access an object that requires a qualification path of several methods and properties, you can speed up your code by not repeating the qualification path.</span></span>

<span data-ttu-id="57d7a-104">修飾パスの繰り返しを回避するには、2つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="57d7a-104">There are two ways you can avoid repeating the qualification path.</span></span> <span data-ttu-id="57d7a-105">オブジェクトは変数に割り当てることができます。または、 `With`...`End With`ブロック。</span><span class="sxs-lookup"><span data-stu-id="57d7a-105">You can assign the object to a variable, or you can use it in a `With`...`End With` block.</span></span>

### <a name="to-speed-up-access-to-a-heavily-qualified-object-by-assigning-it-to-a-variable"></a><span data-ttu-id="57d7a-106">変数に割り当てて、高い修飾オブジェクトへのアクセスを高速化するには</span><span class="sxs-lookup"><span data-stu-id="57d7a-106">To speed up access to a heavily qualified object by assigning it to a variable</span></span>

1. <span data-ttu-id="57d7a-107">頻繁にアクセスするオブジェクトの型の変数を宣言します。</span><span class="sxs-lookup"><span data-stu-id="57d7a-107">Declare a variable of the type of the object that you are accessing frequently.</span></span> <span data-ttu-id="57d7a-108">宣言の初期化部分に修飾パスを指定します。</span><span class="sxs-lookup"><span data-stu-id="57d7a-108">Specify the qualification path in the initialization part of the declaration.</span></span>

    ```vb
    Dim ctrlActv As Control = someForm.ActiveForm.ActiveControl
    ```

2. <span data-ttu-id="57d7a-109">オブジェクトのメンバーにアクセスするには、変数を使用します。</span><span class="sxs-lookup"><span data-stu-id="57d7a-109">Use the variable to access the object's members.</span></span>

    ```vb
    ctrlActv.Text = "Test"
    ctrlActv.Location = New Point(100, 100)
    ctrlActv.Show()
    ```

### <a name="to-speed-up-access-to-a-heavily-qualified-object-by-using-a-withend-with-block"></a><span data-ttu-id="57d7a-110">With... を使用して、高い修飾オブジェクトへのアクセスを高速化するには末尾をブロックにする</span><span class="sxs-lookup"><span data-stu-id="57d7a-110">To speed up access to a heavily qualified object by using a With...End With block</span></span>

1. <span data-ttu-id="57d7a-111">`With`ステートメントに修飾パスを配置します。</span><span class="sxs-lookup"><span data-stu-id="57d7a-111">Put the qualification path in a `With` statement.</span></span>

    ```vb
    With someForm.ActiveForm.ActiveControl
    ```

2. <span data-ttu-id="57d7a-112">ステートメントの`With` `End With`前に、ブロック内のオブジェクトのメンバーにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="57d7a-112">Access the object's members inside the `With` block, before the `End With` statement.</span></span>

    ```vb
        .Text = "Test"
        .Location = New Point(100, 100)
        .Show()
    End With
    ```

## <a name="see-also"></a><span data-ttu-id="57d7a-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="57d7a-113">See also</span></span>

- [<span data-ttu-id="57d7a-114">オブジェクト変数</span><span class="sxs-lookup"><span data-stu-id="57d7a-114">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="57d7a-115">With...End With ステートメント</span><span class="sxs-lookup"><span data-stu-id="57d7a-115">With...End With Statement</span></span>](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)
