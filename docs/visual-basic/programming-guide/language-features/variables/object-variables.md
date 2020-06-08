---
title: オブジェクト変数
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], about object variables
- variables [Visual Basic], object
- objects [Visual Basic], accessing
- object variables [Visual Basic]
ms.assetid: 6169a196-2b13-4ba5-a205-154bc1b87844
ms.openlocfilehash: a5e61f9308d3484dc228a7d09cc2fd30a2f41b35
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410336"
---
# <a name="object-variables-in-visual-basic"></a><span data-ttu-id="06909-102">Visual Basic におけるオブジェクト変数</span><span class="sxs-lookup"><span data-stu-id="06909-102">Object Variables in Visual Basic</span></span>

<span data-ttu-id="06909-103">変数では、値を直接格納するだけでなく、オブジェクトを参照することもできます。</span><span class="sxs-lookup"><span data-stu-id="06909-103">In addition to storing values directly, a variable can refer to an object.</span></span> <span data-ttu-id="06909-104">変数に任意の値を代入するのと同じ理由で、オブジェクトを変数に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="06909-104">You assign an object to a variable for the same reasons you assign any value to a variable:</span></span>

- <span data-ttu-id="06909-105">変数名は大抵、オブジェクトそのものにアクセスするために必要なメソッドやプロパティの完全なパスよりも短く、覚えやすいものです。</span><span class="sxs-lookup"><span data-stu-id="06909-105">A variable name is often shorter and easier to remember than the full path of methods and properties necessary to access the object itself.</span></span>

- <span data-ttu-id="06909-106">オブジェクトを参照する変数を使用する方が、必要なメソッドやプロパティを通じてオブジェクト自体に繰り返しアクセスするよりも効率的です。</span><span class="sxs-lookup"><span data-stu-id="06909-106">Using a variable that refers to an object is more efficient than repeatedly accessing the object itself through the necessary methods or properties.</span></span>

- <span data-ttu-id="06909-107">変数を変更して、コードの実行中に他のオブジェクトを参照することができます。</span><span class="sxs-lookup"><span data-stu-id="06909-107">You can change a variable to refer to other objects while your code is running.</span></span>

## <a name="making-code-shorter"></a><span data-ttu-id="06909-108">コードを短くする</span><span class="sxs-lookup"><span data-stu-id="06909-108">Making Code Shorter</span></span>

<span data-ttu-id="06909-109">オブジェクト変数を使用すると、入力するコードを短くすることができます。</span><span class="sxs-lookup"><span data-stu-id="06909-109">You can use object variables to shorten the code you have to type.</span></span> <span data-ttu-id="06909-110">次の例では、メソッドとプロパティの完全なパスを使用して、<xref:System.Windows.Forms.Control> オブジェクトにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="06909-110">The following example uses the full path of methods and properties to access a <xref:System.Windows.Forms.Control> object.</span></span>

```vb
' Assume Me is a valid Form, or replace Me with a valid Form.
Me.ActiveForm.ActiveControl.Text = "Test"
Me.ActiveForm.ActiveControl.Location = New Point(100, 100)
Me.ActiveForm.ActiveControl.Show()
```

<span data-ttu-id="06909-111">コントロールにオブジェクト変数を使用すると、このコードを短くして、実行速度を上げることができます。</span><span class="sxs-lookup"><span data-stu-id="06909-111">You can shorten this code, and speed up execution, if you use an object variable for the control.</span></span> <span data-ttu-id="06909-112">オブジェクト変数は、割り当てる特定のクラス (この場合は `Control`) を使用して宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="06909-112">You should declare the object variable with the specific class that you intend to assign to it (`Control` in this case).</span></span> <span data-ttu-id="06909-113">オブジェクトを変数に割り当てると、参照先のオブジェクトを扱う場合とまったく同じように扱うことができます。</span><span class="sxs-lookup"><span data-stu-id="06909-113">Once you assign an object to the variable, you can treat it exactly the same as you treat the object to which it refers.</span></span> <span data-ttu-id="06909-114">オブジェクトのプロパティを設定または取得することも、そのメソッドのいずれかを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="06909-114">You can set or retrieve the properties of the object or use any of its methods.</span></span> <span data-ttu-id="06909-115">次の例では、オブジェクト変数を使用して、前の例のコードを簡略化します。</span><span class="sxs-lookup"><span data-stu-id="06909-115">The following example uses an object variable to simplify the code in the preceding example.</span></span>

```vb
Dim ctrlActv As System.Windows.Forms.Control = Me.ActiveForm.ActiveControl
ctrlActv.Text = "Test"
ctrlActv.Location = New Point(100, 100)
ctrlActv.Show()
```

## <a name="see-also"></a><span data-ttu-id="06909-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="06909-116">See also</span></span>

- [<span data-ttu-id="06909-117">変数宣言</span><span class="sxs-lookup"><span data-stu-id="06909-117">Variable Declaration</span></span>](variable-declaration.md)
- [<span data-ttu-id="06909-118">方法: 長い修飾パスを持つオブジェクトへのアクセス時間を短縮する</span><span class="sxs-lookup"><span data-stu-id="06909-118">How to: Speed Up Access to an Object with a Long Qualification Path</span></span>](how-to-speed-up-access-to-an-object-with-a-long-qualification-path.md)
- [<span data-ttu-id="06909-119">オブジェクト変数の宣言</span><span class="sxs-lookup"><span data-stu-id="06909-119">Object Variable Declaration</span></span>](object-variable-declaration.md)
- [<span data-ttu-id="06909-120">オブジェクト変数の代入</span><span class="sxs-lookup"><span data-stu-id="06909-120">Object Variable Assignment</span></span>](object-variable-assignment.md)
- [<span data-ttu-id="06909-121">オブジェクト変数の値</span><span class="sxs-lookup"><span data-stu-id="06909-121">Object Variable Values</span></span>](object-variable-values.md)
