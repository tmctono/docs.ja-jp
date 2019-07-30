---
title: '方法: 変数にデータを移動する (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], retrieving values
- variables [Visual Basic], storing data
ms.assetid: 93744f46-bf78-4fa0-9640-1de01bc38d9a
ms.openlocfilehash: df55f122c4ea029a383196f8d9684295ac8926aa
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2019
ms.locfileid: "68631127"
---
# <a name="how-to-move-data-into-and-out-of-a-variable-visual-basic"></a><span data-ttu-id="22e0a-102">方法: 変数にデータを移動する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="22e0a-102">How to: Move Data Into and Out of a Variable (Visual Basic)</span></span>

<span data-ttu-id="22e0a-103">変数に値を格納するには、代入ステートメントの左側に変数名を指定します。</span><span class="sxs-lookup"><span data-stu-id="22e0a-103">You store a value in a variable by putting the variable name on the left side of an assignment statement.</span></span>

## <a name="putting-data-in-a-variable"></a><span data-ttu-id="22e0a-104">変数にデータを格納する</span><span class="sxs-lookup"><span data-stu-id="22e0a-104">Putting Data in a Variable</span></span>

#### <a name="to-store-a-value-in-a-variable"></a><span data-ttu-id="22e0a-105">変数に値を格納するには</span><span class="sxs-lookup"><span data-stu-id="22e0a-105">To store a value in a variable</span></span>

- <span data-ttu-id="22e0a-106">代入ステートメントの左側にある変数名を使用します。</span><span class="sxs-lookup"><span data-stu-id="22e0a-106">Use the variable name on the left side of an assignment statement.</span></span>

    <span data-ttu-id="22e0a-107">次の例では、変数`alpha`の値を設定します。</span><span class="sxs-lookup"><span data-stu-id="22e0a-107">The following example sets the value of the variable `alpha`.</span></span>

    ```vb
    alpha = (beta * 6.27) / (gamma + 2.1)
    ```

    <span data-ttu-id="22e0a-108">代入ステートメントの右辺に生成される値は、変数に格納されます。</span><span class="sxs-lookup"><span data-stu-id="22e0a-108">The value generated on the right side of the assignment statement is stored in the variable.</span></span>

## <a name="getting-data-from-a-variable"></a><span data-ttu-id="22e0a-109">変数からのデータの取得</span><span class="sxs-lookup"><span data-stu-id="22e0a-109">Getting Data from a Variable</span></span>

<span data-ttu-id="22e0a-110">変数の値を取得するには、式に変数名を含めます。</span><span class="sxs-lookup"><span data-stu-id="22e0a-110">You retrieve a variable's value by including the variable name in an expression.</span></span>

#### <a name="to-retrieve-a-value-from-a-variable"></a><span data-ttu-id="22e0a-111">変数から値を取得するには</span><span class="sxs-lookup"><span data-stu-id="22e0a-111">To retrieve a value from a variable</span></span>

- <span data-ttu-id="22e0a-112">式では変数名を使用します。</span><span class="sxs-lookup"><span data-stu-id="22e0a-112">Use the variable name in an expression.</span></span> <span data-ttu-id="22e0a-113">定数またはリテラルを使用できる場所であればどこでも変数を使用できます。ただし、定数の値を定義する式では使用できません。</span><span class="sxs-lookup"><span data-stu-id="22e0a-113">You can use a variable anywhere you can use a constant or a literal, except in an expression that defines the value of a constant.</span></span>

  <span data-ttu-id="22e0a-114">\- または -</span><span class="sxs-lookup"><span data-stu-id="22e0a-114">\-or-</span></span>

- <span data-ttu-id="22e0a-115">代入ステートメントの等号 (`=`) に続く変数名を使用します。</span><span class="sxs-lookup"><span data-stu-id="22e0a-115">Use the variable name following the equal (`=`) sign in an assignment statement.</span></span>

  <span data-ttu-id="22e0a-116">次の例では、変数`startValue`の値を読み取り、式で変数`counter`の値を使用します。</span><span class="sxs-lookup"><span data-stu-id="22e0a-116">The following example reads the value of the variable `startValue` and then uses the value of the variable `counter` in an expression.</span></span>

  ```vb
  counter = startValue
  cellValue = (counter + 5) ^ 2
  ```

  <span data-ttu-id="22e0a-117">変数の値は定数と同様に式に参加し、代入ステートメントの左側にある変数またはプロパティに格納されます。</span><span class="sxs-lookup"><span data-stu-id="22e0a-117">The value of the variable participates in the expression just as a constant would, and then it is stored in the variable or property on the left side of the assignment statement.</span></span>

## <a name="see-also"></a><span data-ttu-id="22e0a-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="22e0a-118">See also</span></span>

- [<span data-ttu-id="22e0a-119">変数</span><span class="sxs-lookup"><span data-stu-id="22e0a-119">Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/index.md)
- [<span data-ttu-id="22e0a-120">変数宣言</span><span class="sxs-lookup"><span data-stu-id="22e0a-120">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="22e0a-121">オブジェクト変数</span><span class="sxs-lookup"><span data-stu-id="22e0a-121">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
