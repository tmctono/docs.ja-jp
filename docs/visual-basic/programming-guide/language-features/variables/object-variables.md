---
title: オブジェクト変数
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], about object variables
- variables [Visual Basic], object
- objects [Visual Basic], accessing
- object variables [Visual Basic]
ms.assetid: 6169a196-2b13-4ba5-a205-154bc1b87844
ms.openlocfilehash: 7eb860bc732f923316b8ce1d7b94ecdb368bfec3
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351792"
---
# <a name="object-variables-in-visual-basic"></a><span data-ttu-id="7d0b2-102">Visual Basic におけるオブジェクト変数</span><span class="sxs-lookup"><span data-stu-id="7d0b2-102">Object Variables in Visual Basic</span></span>

<span data-ttu-id="7d0b2-103">変数は、値を直接格納するだけでなく、オブジェクトを参照することもできます。</span><span class="sxs-lookup"><span data-stu-id="7d0b2-103">In addition to storing values directly, a variable can refer to an object.</span></span> <span data-ttu-id="7d0b2-104">変数に値を代入するのと同じ理由で、オブジェクトを変数に代入します。</span><span class="sxs-lookup"><span data-stu-id="7d0b2-104">You assign an object to a variable for the same reasons you assign any value to a variable:</span></span>

- <span data-ttu-id="7d0b2-105">多くの場合、変数名は、オブジェクト自体にアクセスするために必要なメソッドとプロパティの完全なパスよりも短く、覚えやすくなります。</span><span class="sxs-lookup"><span data-stu-id="7d0b2-105">A variable name is often shorter and easier to remember than the full path of methods and properties necessary to access the object itself.</span></span>

- <span data-ttu-id="7d0b2-106">オブジェクトを参照する変数を使用する方が、必要なメソッドやプロパティを通じてオブジェクト自体に繰り返しアクセスするよりも効率的です。</span><span class="sxs-lookup"><span data-stu-id="7d0b2-106">Using a variable that refers to an object is more efficient than repeatedly accessing the object itself through the necessary methods or properties.</span></span>

- <span data-ttu-id="7d0b2-107">変数を変更して、コードの実行中に他のオブジェクトを参照することができます。</span><span class="sxs-lookup"><span data-stu-id="7d0b2-107">You can change a variable to refer to other objects while your code is running.</span></span>

## <a name="making-code-shorter"></a><span data-ttu-id="7d0b2-108">コードを短くする</span><span class="sxs-lookup"><span data-stu-id="7d0b2-108">Making Code Shorter</span></span>

<span data-ttu-id="7d0b2-109">オブジェクト変数を使用すると、入力するコードを短くすることができます。</span><span class="sxs-lookup"><span data-stu-id="7d0b2-109">You can use object variables to shorten the code you have to type.</span></span> <span data-ttu-id="7d0b2-110">次の例では、メソッドとプロパティの完全パスを使用して、<xref:System.Windows.Forms.Control> オブジェクトにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="7d0b2-110">The following example uses the full path of methods and properties to access a <xref:System.Windows.Forms.Control> object.</span></span>

```vb
' Assume Me is a valid Form, or replace Me with a valid Form.
Me.ActiveForm.ActiveControl.Text = "Test"
Me.ActiveForm.ActiveControl.Location = New Point(100, 100)
Me.ActiveForm.ActiveControl.Show()
```

<span data-ttu-id="7d0b2-111">コントロールにオブジェクト変数を使用すると、このコードを短縮し、実行速度を上げることができます。</span><span class="sxs-lookup"><span data-stu-id="7d0b2-111">You can shorten this code, and speed up execution, if you use an object variable for the control.</span></span> <span data-ttu-id="7d0b2-112">オブジェクト変数は、代入する特定のクラス (この場合は`Control`) を使用して宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d0b2-112">You should declare the object variable with the specific class that you intend to assign to it (`Control` in this case).</span></span> <span data-ttu-id="7d0b2-113">変数にオブジェクトを割り当てると、参照先のオブジェクトを扱う場合とまったく同じように処理できます。</span><span class="sxs-lookup"><span data-stu-id="7d0b2-113">Once you assign an object to the variable, you can treat it exactly the same as you treat the object to which it refers.</span></span> <span data-ttu-id="7d0b2-114">オブジェクトのプロパティを設定または取得することも、そのメソッドを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="7d0b2-114">You can set or retrieve the properties of the object or use any of its methods.</span></span> <span data-ttu-id="7d0b2-115">次の例では、オブジェクト変数を使用して、前の例のコードを簡略化します。</span><span class="sxs-lookup"><span data-stu-id="7d0b2-115">The following example uses an object variable to simplify the code in the preceding example.</span></span>

```vb
Dim ctrlActv As System.Windows.Forms.Control = Me.ActiveForm.ActiveControl
ctrlActv.Text = "Test"
ctrlActv.Location = New Point(100, 100)
ctrlActv.Show()
```

## <a name="see-also"></a><span data-ttu-id="7d0b2-116">参照</span><span class="sxs-lookup"><span data-stu-id="7d0b2-116">See also</span></span>

- [<span data-ttu-id="7d0b2-117">変数宣言</span><span class="sxs-lookup"><span data-stu-id="7d0b2-117">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="7d0b2-118">方法 : 長い修飾パスを持つオブジェクトへのアクセス時間を短縮する</span><span class="sxs-lookup"><span data-stu-id="7d0b2-118">How to: Speed Up Access to an Object with a Long Qualification Path</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-speed-up-access-to-an-object-with-a-long-qualification-path.md)
- [<span data-ttu-id="7d0b2-119">オブジェクト変数の宣言</span><span class="sxs-lookup"><span data-stu-id="7d0b2-119">Object Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [<span data-ttu-id="7d0b2-120">オブジェクト変数の代入</span><span class="sxs-lookup"><span data-stu-id="7d0b2-120">Object Variable Assignment</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [<span data-ttu-id="7d0b2-121">オブジェクト変数の値</span><span class="sxs-lookup"><span data-stu-id="7d0b2-121">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
