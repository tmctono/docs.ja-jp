---
title: '方法: オブジェクト変数を宣言し、Visual Basic でオブジェクトを割り当てる'
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], declaring
- declaring object variables [Visual Basic]
ms.assetid: 2fa77dde-1fb2-439a-80d4-3e9787649fad
ms.openlocfilehash: e172d62e5bfadded254d5a5fd25b1dcf2da9634d
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64663588"
---
# <a name="how-to-declare-an-object-variable-and-assign-an-object-to-it-in-visual-basic"></a><span data-ttu-id="7eb58-102">方法: オブジェクト変数を宣言し、Visual Basic でオブジェクトを割り当てる</span><span class="sxs-lookup"><span data-stu-id="7eb58-102">How to: Declare an Object Variable and Assign an Object to It in Visual Basic</span></span>
<span data-ttu-id="7eb58-103">変数を宣言する、 [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md)を指定して`As Object`で、 [Dim ステートメント](../../../../visual-basic/language-reference/statements/dim-statement.md)します。</span><span class="sxs-lookup"><span data-stu-id="7eb58-103">You declare a variable of the [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) by specifying `As Object` in a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md).</span></span> <span data-ttu-id="7eb58-104">等号の後、オブジェクトを配置することで、このような変数にオブジェクトを代入する (`=`) 代入ステートメントまたは初期化句でします。</span><span class="sxs-lookup"><span data-stu-id="7eb58-104">You assign an object to such a variable by placing the object after the equal sign (`=`) in an assignment statement or initialization clause.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7eb58-105">例</span><span class="sxs-lookup"><span data-stu-id="7eb58-105">Example</span></span>  
 <span data-ttu-id="7eb58-106">次の例で、`Object`変数と、現在のインスタンスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="7eb58-106">The following example declares an `Object` variable and assigns the current instance to it.</span></span>  
  
```  
      Dim thisObject As Object  
thisObject = "This is an Object"  
```  
  
 <span data-ttu-id="7eb58-107">宣言の一部として変数を初期化することにより、宣言と代入を組み合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="7eb58-107">You can combine the declaration and assignment by initializing the variable as part of its declaration.</span></span> <span data-ttu-id="7eb58-108">次の例では、前の例と同じです。</span><span class="sxs-lookup"><span data-stu-id="7eb58-108">The following example is equivalent to the preceding example.</span></span>  
  
```  
Dim thisObject As Object= "This is an Object"  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7eb58-109">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="7eb58-109">Compiling the Code</span></span>  
 <span data-ttu-id="7eb58-110">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="7eb58-110">This example requires:</span></span>  
  
- <span data-ttu-id="7eb58-111"><xref:System> 名前空間への参照</span><span class="sxs-lookup"><span data-stu-id="7eb58-111">A reference to the <xref:System> namespace.</span></span>  
  
- <span data-ttu-id="7eb58-112">クラス、構造体、または配置されるモジュール、`Dim`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="7eb58-112">A class, structure, or module in which to put the `Dim` statement.</span></span>  
  
- <span data-ttu-id="7eb58-113">代入ステートメントを記述するためのプロシージャです。</span><span class="sxs-lookup"><span data-stu-id="7eb58-113">A procedure in which to put the assignment statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7eb58-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="7eb58-114">See also</span></span>

- [<span data-ttu-id="7eb58-115">変数宣言</span><span class="sxs-lookup"><span data-stu-id="7eb58-115">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="7eb58-116">オブジェクト変数</span><span class="sxs-lookup"><span data-stu-id="7eb58-116">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="7eb58-117">オブジェクト変数の宣言</span><span class="sxs-lookup"><span data-stu-id="7eb58-117">Object Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [<span data-ttu-id="7eb58-118">Object 型</span><span class="sxs-lookup"><span data-stu-id="7eb58-118">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="7eb58-119">Dim ステートメント</span><span class="sxs-lookup"><span data-stu-id="7eb58-119">Dim Statement</span></span>](../../../../visual-basic/language-reference/statements/dim-statement.md)
- [<span data-ttu-id="7eb58-120">ローカル型の推論</span><span class="sxs-lookup"><span data-stu-id="7eb58-120">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="7eb58-121">Option Strict ステートメント</span><span class="sxs-lookup"><span data-stu-id="7eb58-121">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
