---
title: '方法: 変数 (Visual Basic) との間のデータを移動します。'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], retrieving values
- variables [Visual Basic], storing data
ms.assetid: 93744f46-bf78-4fa0-9640-1de01bc38d9a
ms.openlocfilehash: 30d1c0ab91724ac556e59b272782513ee8b8067b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61756599"
---
# <a name="how-to-move-data-into-and-out-of-a-variable-visual-basic"></a><span data-ttu-id="94ec0-102">方法: 変数 (Visual Basic) との間のデータを移動します。</span><span class="sxs-lookup"><span data-stu-id="94ec0-102">How to: Move Data Into and Out of a Variable (Visual Basic)</span></span>
<span data-ttu-id="94ec0-103">変数にデータを格納するには、代入ステートメントの左側にある変数名を置きます。</span><span class="sxs-lookup"><span data-stu-id="94ec0-103">You store a value in a variable by putting the variable name on the left side of an assignment statement.</span></span>  
  
## <a name="putting-data-in-a-variable"></a><span data-ttu-id="94ec0-104">変数にデータを配置します。</span><span class="sxs-lookup"><span data-stu-id="94ec0-104">Putting Data in a Variable</span></span>  
  
#### <a name="to-store-a-value-in-a-variable"></a><span data-ttu-id="94ec0-105">変数に値を格納するには</span><span class="sxs-lookup"><span data-stu-id="94ec0-105">To store a value in a variable</span></span>  
  
- <span data-ttu-id="94ec0-106">代入ステートメントの左側にある変数名を使用します。</span><span class="sxs-lookup"><span data-stu-id="94ec0-106">Use the variable name on the left side of an assignment statement.</span></span>  
  
     <span data-ttu-id="94ec0-107">次の例では、変数の値を設定する`alpha`します。</span><span class="sxs-lookup"><span data-stu-id="94ec0-107">The following example sets the value of the variable `alpha`.</span></span>  
  
    ```  
    alpha = (beta * 6.27) / (gamma + 2.1)  
    ```  
  
     <span data-ttu-id="94ec0-108">代入ステートメントの右側にある生成された値は、変数に格納されます。</span><span class="sxs-lookup"><span data-stu-id="94ec0-108">The value generated on the right side of the assignment statement is stored in the variable.</span></span>  
  
## <a name="getting-data-from-a-variable"></a><span data-ttu-id="94ec0-109">変数からのデータの取得</span><span class="sxs-lookup"><span data-stu-id="94ec0-109">Getting Data from a Variable</span></span>  
 <span data-ttu-id="94ec0-110">変数の値を取得するには、式の中で変数名を含めます。</span><span class="sxs-lookup"><span data-stu-id="94ec0-110">You retrieve a variable's value by including the variable name in an expression.</span></span>  
  
#### <a name="to-retrieve-a-value-from-a-variable"></a><span data-ttu-id="94ec0-111">変数から値を取得するには</span><span class="sxs-lookup"><span data-stu-id="94ec0-111">To retrieve a value from a variable</span></span>  
  
- <span data-ttu-id="94ec0-112">式の中で変数名を使用します。</span><span class="sxs-lookup"><span data-stu-id="94ec0-112">Use the variable name in an expression.</span></span> <span data-ttu-id="94ec0-113">変数を使用する任意の場所またはを使用できます、定数、リテラル、以外の定数の値を定義する式の中でします。</span><span class="sxs-lookup"><span data-stu-id="94ec0-113">You can use a variable anywhere you can use a constant or a literal, except in an expression that defines the value of a constant.</span></span>  
  
     <span data-ttu-id="94ec0-114">- または -</span><span class="sxs-lookup"><span data-stu-id="94ec0-114">-or-</span></span>  
  
- <span data-ttu-id="94ec0-115">等号の後、変数名を使用して (`=`)、代入ステートメントにサインインします。</span><span class="sxs-lookup"><span data-stu-id="94ec0-115">Use the variable name following the equal (`=`) sign in an assignment statement.</span></span>  
  
     <span data-ttu-id="94ec0-116">次の例は、変数の値を読み取ります`startValue`し、変数の値を使用して`counter`式で。</span><span class="sxs-lookup"><span data-stu-id="94ec0-116">The following example reads the value of the variable `startValue` and then uses the value of the variable `counter` in an expression.</span></span>  
  
    ```  
    counter = startValue  
    cellValue = (counter + 5) ^ 2  
    ```  
  
     <span data-ttu-id="94ec0-117">変数の値は、定数とし、変数または代入ステートメントの左側にあるプロパティに格納されます、式に参加します。</span><span class="sxs-lookup"><span data-stu-id="94ec0-117">The value of the variable participates in the expression just as a constant would, and then it is stored in the variable or property on the left side of the assignment statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94ec0-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="94ec0-118">See also</span></span>

- [<span data-ttu-id="94ec0-119">変数</span><span class="sxs-lookup"><span data-stu-id="94ec0-119">Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/index.md)
- [<span data-ttu-id="94ec0-120">変数宣言</span><span class="sxs-lookup"><span data-stu-id="94ec0-120">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="94ec0-121">オブジェクト変数</span><span class="sxs-lookup"><span data-stu-id="94ec0-121">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
