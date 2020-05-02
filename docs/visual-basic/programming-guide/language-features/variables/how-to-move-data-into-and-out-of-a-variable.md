---
title: '方法: 変数に値を格納する、および変数から値を取得する'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], retrieving values
- variables [Visual Basic], storing data
ms.assetid: 93744f46-bf78-4fa0-9640-1de01bc38d9a
ms.openlocfilehash: bc5a7377a5e2e4c7ebe7291fd5f0093c4d6e996d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346904"
---
# <a name="how-to-move-data-into-and-out-of-a-variable-visual-basic"></a><span data-ttu-id="b6633-102">方法: 変数に値を格納する、および変数から値を取得する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b6633-102">How to: Move Data Into and Out of a Variable (Visual Basic)</span></span>

<span data-ttu-id="b6633-103">変数に値を格納するには、代入ステートメントの左辺に変数名を指定します。</span><span class="sxs-lookup"><span data-stu-id="b6633-103">You store a value in a variable by putting the variable name on the left side of an assignment statement.</span></span>

## <a name="putting-data-in-a-variable"></a><span data-ttu-id="b6633-104">変数にデータを格納する</span><span class="sxs-lookup"><span data-stu-id="b6633-104">Putting Data in a Variable</span></span>

#### <a name="to-store-a-value-in-a-variable"></a><span data-ttu-id="b6633-105">変数に値を格納するには</span><span class="sxs-lookup"><span data-stu-id="b6633-105">To store a value in a variable</span></span>

- <span data-ttu-id="b6633-106">代入ステートメントの左辺に変数名を使用します。</span><span class="sxs-lookup"><span data-stu-id="b6633-106">Use the variable name on the left side of an assignment statement.</span></span>

    <span data-ttu-id="b6633-107">次の例では、変数 `alpha` の値を設定します。</span><span class="sxs-lookup"><span data-stu-id="b6633-107">The following example sets the value of the variable `alpha`.</span></span>

    ```vb
    alpha = (beta * 6.27) / (gamma + 2.1)
    ```

    <span data-ttu-id="b6633-108">代入ステートメントの右辺で生成された値がその変数に格納されます。</span><span class="sxs-lookup"><span data-stu-id="b6633-108">The value generated on the right side of the assignment statement is stored in the variable.</span></span>

## <a name="getting-data-from-a-variable"></a><span data-ttu-id="b6633-109">変数からのデータの取得</span><span class="sxs-lookup"><span data-stu-id="b6633-109">Getting Data from a Variable</span></span>

<span data-ttu-id="b6633-110">変数の値を取得するには、式に変数名を含めます。</span><span class="sxs-lookup"><span data-stu-id="b6633-110">You retrieve a variable's value by including the variable name in an expression.</span></span>

#### <a name="to-retrieve-a-value-from-a-variable"></a><span data-ttu-id="b6633-111">変数から値を取得するには</span><span class="sxs-lookup"><span data-stu-id="b6633-111">To retrieve a value from a variable</span></span>

- <span data-ttu-id="b6633-112">式内に変数名を使用します。</span><span class="sxs-lookup"><span data-stu-id="b6633-112">Use the variable name in an expression.</span></span> <span data-ttu-id="b6633-113">定数またはリテラルを使用できる場所であればどこでも変数を使用できます。ただし、定数の値を定義する式内は例外です。</span><span class="sxs-lookup"><span data-stu-id="b6633-113">You can use a variable anywhere you can use a constant or a literal, except in an expression that defines the value of a constant.</span></span>

  <span data-ttu-id="b6633-114">\- または -</span><span class="sxs-lookup"><span data-stu-id="b6633-114">\-or-</span></span>

- <span data-ttu-id="b6633-115">代入ステートメント内で等号 (`=`) の後に変数名を使用します。</span><span class="sxs-lookup"><span data-stu-id="b6633-115">Use the variable name following the equal (`=`) sign in an assignment statement.</span></span>

  <span data-ttu-id="b6633-116">次の例では、変数 `startValue` の値を読み取ってから、式内で変数 `counter` の値を使用しています。</span><span class="sxs-lookup"><span data-stu-id="b6633-116">The following example reads the value of the variable `startValue` and then uses the value of the variable `counter` in an expression.</span></span>

  ```vb
  counter = startValue
  cellValue = (counter + 5) ^ 2
  ```

  <span data-ttu-id="b6633-117">変数の値は定数の場合と同様に式に含められ、そして代入ステートメントの左辺にある変数またはプロパティに格納されます。</span><span class="sxs-lookup"><span data-stu-id="b6633-117">The value of the variable participates in the expression just as a constant would, and then it is stored in the variable or property on the left side of the assignment statement.</span></span>

## <a name="see-also"></a><span data-ttu-id="b6633-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="b6633-118">See also</span></span>

- [<span data-ttu-id="b6633-119">変数</span><span class="sxs-lookup"><span data-stu-id="b6633-119">Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/index.md)
- [<span data-ttu-id="b6633-120">変数宣言</span><span class="sxs-lookup"><span data-stu-id="b6633-120">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="b6633-121">オブジェクト変数</span><span class="sxs-lookup"><span data-stu-id="b6633-121">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
