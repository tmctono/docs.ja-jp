---
title: '方法: オブジェクト変数を宣言し、それにオブジェクトを割り当てる'
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
# <a name="how-to-declare-an-object-variable-and-assign-an-object-to-it-in-visual-basic"></a><span data-ttu-id="8a4db-102">方法 : Visual Basic でオブジェクト変数を宣言し、オブジェクト変数にオブジェクトを代入する</span><span class="sxs-lookup"><span data-stu-id="8a4db-102">How to: Declare an Object Variable and Assign an Object to It in Visual Basic</span></span>

<span data-ttu-id="8a4db-103">[オブジェクトデータ型](../../../../visual-basic/language-reference/data-types/object-data-type.md)の変数を宣言するには、 [Dim ステートメント](../../../../visual-basic/language-reference/statements/dim-statement.md)で `As Object` を指定します。</span><span class="sxs-lookup"><span data-stu-id="8a4db-103">You declare a variable of the [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) by specifying `As Object` in a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md).</span></span> <span data-ttu-id="8a4db-104">このような変数にオブジェクトを代入するには、代入ステートメントまたは初期化句で等号 (`=`) の後にオブジェクトを配置します。</span><span class="sxs-lookup"><span data-stu-id="8a4db-104">You assign an object to such a variable by placing the object after the equal sign (`=`) in an assignment statement or initialization clause.</span></span>

## <a name="example"></a><span data-ttu-id="8a4db-105">例</span><span class="sxs-lookup"><span data-stu-id="8a4db-105">Example</span></span>

<span data-ttu-id="8a4db-106">次の例では、`Object` 変数を宣言し、現在のインスタンスをその変数に代入します。</span><span class="sxs-lookup"><span data-stu-id="8a4db-106">The following example declares an `Object` variable and assigns the current instance to it.</span></span>

```vb
Dim thisObject As Object
thisObject = "This is an Object"
```

<span data-ttu-id="8a4db-107">宣言の一部として変数を初期化することで、宣言と代入を組み合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="8a4db-107">You can combine the declaration and assignment by initializing the variable as part of its declaration.</span></span> <span data-ttu-id="8a4db-108">次の例は、前の例と同じです。</span><span class="sxs-lookup"><span data-stu-id="8a4db-108">The following example is equivalent to the preceding example.</span></span>

```vb
Dim thisObject As Object= "This is an Object"
```

## <a name="compiling-the-code"></a><span data-ttu-id="8a4db-109">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="8a4db-109">Compiling the Code</span></span>

<span data-ttu-id="8a4db-110">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8a4db-110">This example requires:</span></span>

- <span data-ttu-id="8a4db-111"><xref:System> 名前空間への参照</span><span class="sxs-lookup"><span data-stu-id="8a4db-111">A reference to the <xref:System> namespace.</span></span>

- <span data-ttu-id="8a4db-112">`Dim` ステートメントを格納するクラス、構造体、またはモジュール。</span><span class="sxs-lookup"><span data-stu-id="8a4db-112">A class, structure, or module in which to put the `Dim` statement.</span></span>

- <span data-ttu-id="8a4db-113">代入ステートメントを配置するプロシージャ。</span><span class="sxs-lookup"><span data-stu-id="8a4db-113">A procedure in which to put the assignment statement.</span></span>

## <a name="see-also"></a><span data-ttu-id="8a4db-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="8a4db-114">See also</span></span>

- [<span data-ttu-id="8a4db-115">変数宣言</span><span class="sxs-lookup"><span data-stu-id="8a4db-115">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="8a4db-116">オブジェクト変数</span><span class="sxs-lookup"><span data-stu-id="8a4db-116">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="8a4db-117">オブジェクト変数の宣言</span><span class="sxs-lookup"><span data-stu-id="8a4db-117">Object Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [<span data-ttu-id="8a4db-118">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="8a4db-118">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="8a4db-119">Dim ステートメント</span><span class="sxs-lookup"><span data-stu-id="8a4db-119">Dim Statement</span></span>](../../../../visual-basic/language-reference/statements/dim-statement.md)
- [<span data-ttu-id="8a4db-120">ローカル型の推論</span><span class="sxs-lookup"><span data-stu-id="8a4db-120">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="8a4db-121">Option Strict ステートメント</span><span class="sxs-lookup"><span data-stu-id="8a4db-121">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
