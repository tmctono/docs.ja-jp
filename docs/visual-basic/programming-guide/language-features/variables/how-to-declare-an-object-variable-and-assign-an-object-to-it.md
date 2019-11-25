---
title: 'How to: Declare an Object Variable and Assign an Object to It'
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], declaring
- declaring object variables [Visual Basic]
ms.assetid: 2fa77dde-1fb2-439a-80d4-3e9787649fad
ms.openlocfilehash: 4cfad1d820b584d4610d24c392b14ac3958471b7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352904"
---
# <a name="how-to-declare-an-object-variable-and-assign-an-object-to-it-in-visual-basic"></a><span data-ttu-id="13a58-102">方法 : Visual Basic でオブジェクト変数を宣言し、オブジェクト変数にオブジェクトを代入する</span><span class="sxs-lookup"><span data-stu-id="13a58-102">How to: Declare an Object Variable and Assign an Object to It in Visual Basic</span></span>

<span data-ttu-id="13a58-103">You declare a variable of the [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) by specifying `As Object` in a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md).</span><span class="sxs-lookup"><span data-stu-id="13a58-103">You declare a variable of the [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) by specifying `As Object` in a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md).</span></span> <span data-ttu-id="13a58-104">You assign an object to such a variable by placing the object after the equal sign (`=`) in an assignment statement or initialization clause.</span><span class="sxs-lookup"><span data-stu-id="13a58-104">You assign an object to such a variable by placing the object after the equal sign (`=`) in an assignment statement or initialization clause.</span></span>

## <a name="example"></a><span data-ttu-id="13a58-105">例</span><span class="sxs-lookup"><span data-stu-id="13a58-105">Example</span></span>

<span data-ttu-id="13a58-106">The following example declares an `Object` variable and assigns the current instance to it.</span><span class="sxs-lookup"><span data-stu-id="13a58-106">The following example declares an `Object` variable and assigns the current instance to it.</span></span>

```vb
Dim thisObject As Object
thisObject = "This is an Object"
```

<span data-ttu-id="13a58-107">You can combine the declaration and assignment by initializing the variable as part of its declaration.</span><span class="sxs-lookup"><span data-stu-id="13a58-107">You can combine the declaration and assignment by initializing the variable as part of its declaration.</span></span> <span data-ttu-id="13a58-108">The following example is equivalent to the preceding example.</span><span class="sxs-lookup"><span data-stu-id="13a58-108">The following example is equivalent to the preceding example.</span></span>

```vb
Dim thisObject As Object= "This is an Object"
```

## <a name="compiling-the-code"></a><span data-ttu-id="13a58-109">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="13a58-109">Compiling the Code</span></span>

<span data-ttu-id="13a58-110">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="13a58-110">This example requires:</span></span>

- <span data-ttu-id="13a58-111"><xref:System> 名前空間への参照</span><span class="sxs-lookup"><span data-stu-id="13a58-111">A reference to the <xref:System> namespace.</span></span>

- <span data-ttu-id="13a58-112">A class, structure, or module in which to put the `Dim` statement.</span><span class="sxs-lookup"><span data-stu-id="13a58-112">A class, structure, or module in which to put the `Dim` statement.</span></span>

- <span data-ttu-id="13a58-113">A procedure in which to put the assignment statement.</span><span class="sxs-lookup"><span data-stu-id="13a58-113">A procedure in which to put the assignment statement.</span></span>

## <a name="see-also"></a><span data-ttu-id="13a58-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="13a58-114">See also</span></span>

- [<span data-ttu-id="13a58-115">変数宣言</span><span class="sxs-lookup"><span data-stu-id="13a58-115">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="13a58-116">オブジェクト変数</span><span class="sxs-lookup"><span data-stu-id="13a58-116">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="13a58-117">オブジェクト変数の宣言</span><span class="sxs-lookup"><span data-stu-id="13a58-117">Object Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [<span data-ttu-id="13a58-118">Object 型</span><span class="sxs-lookup"><span data-stu-id="13a58-118">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="13a58-119">Dim ステートメント</span><span class="sxs-lookup"><span data-stu-id="13a58-119">Dim Statement</span></span>](../../../../visual-basic/language-reference/statements/dim-statement.md)
- [<span data-ttu-id="13a58-120">ローカル型の推論</span><span class="sxs-lookup"><span data-stu-id="13a58-120">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="13a58-121">Option Strict ステートメント</span><span class="sxs-lookup"><span data-stu-id="13a58-121">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
