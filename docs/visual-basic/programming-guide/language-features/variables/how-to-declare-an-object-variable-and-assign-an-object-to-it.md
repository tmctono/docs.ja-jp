---
title: '方法: Visual Basic でオブジェクト変数を宣言し、オブジェクト変数にオブジェクトを代入する'
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], declaring
- declaring object variables [Visual Basic]
ms.assetid: 2fa77dde-1fb2-439a-80d4-3e9787649fad
ms.openlocfilehash: d9a8c1fb30bfa5988d48202e41202e7ede0f5f27
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410504"
---
# <a name="how-to-declare-an-object-variable-and-assign-an-object-to-it-in-visual-basic"></a><span data-ttu-id="d73e3-102">方法: Visual Basic でオブジェクト変数を宣言してオブジェクトを代入する</span><span class="sxs-lookup"><span data-stu-id="d73e3-102">How to: Declare an Object Variable and Assign an Object to It in Visual Basic</span></span>

<span data-ttu-id="d73e3-103">[Object データ型](../../../language-reference/data-types/object-data-type.md)の変数は、[Dim ステートメント](../../../language-reference/statements/dim-statement.md)で `As Object` を指定して宣言します。</span><span class="sxs-lookup"><span data-stu-id="d73e3-103">You declare a variable of the [Object Data Type](../../../language-reference/data-types/object-data-type.md) by specifying `As Object` in a [Dim Statement](../../../language-reference/statements/dim-statement.md).</span></span> <span data-ttu-id="d73e3-104">このような変数にオブジェクトを代入するには、代入ステートメントまたは初期化句で等号 (`=`) の後にオブジェクトを配置します。</span><span class="sxs-lookup"><span data-stu-id="d73e3-104">You assign an object to such a variable by placing the object after the equal sign (`=`) in an assignment statement or initialization clause.</span></span>

## <a name="example"></a><span data-ttu-id="d73e3-105">例</span><span class="sxs-lookup"><span data-stu-id="d73e3-105">Example</span></span>

<span data-ttu-id="d73e3-106">次の例では、`Object` 変数を宣言して、現在のインスタンスをこれに代入します。</span><span class="sxs-lookup"><span data-stu-id="d73e3-106">The following example declares an `Object` variable and assigns the current instance to it.</span></span>

```vb
Dim thisObject As Object
thisObject = "This is an Object"
```

<span data-ttu-id="d73e3-107">宣言に変数の初期化を含めると、宣言と代入を同時に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="d73e3-107">You can combine the declaration and assignment by initializing the variable as part of its declaration.</span></span> <span data-ttu-id="d73e3-108">次の例は、前の例と同じです。</span><span class="sxs-lookup"><span data-stu-id="d73e3-108">The following example is equivalent to the preceding example.</span></span>

```vb
Dim thisObject As Object= "This is an Object"
```

## <a name="compile-the-code"></a><span data-ttu-id="d73e3-109">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="d73e3-109">Compile the code</span></span>

<span data-ttu-id="d73e3-110">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d73e3-110">This example requires:</span></span>

- <span data-ttu-id="d73e3-111"><xref:System> 名前空間への参照</span><span class="sxs-lookup"><span data-stu-id="d73e3-111">A reference to the <xref:System> namespace.</span></span>

- <span data-ttu-id="d73e3-112">`Dim` ステートメントを入れるクラス、構造体、またはモジュール。</span><span class="sxs-lookup"><span data-stu-id="d73e3-112">A class, structure, or module in which to put the `Dim` statement.</span></span>

- <span data-ttu-id="d73e3-113">代入ステートメントを入れるプロシージャ。</span><span class="sxs-lookup"><span data-stu-id="d73e3-113">A procedure in which to put the assignment statement.</span></span>

## <a name="see-also"></a><span data-ttu-id="d73e3-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="d73e3-114">See also</span></span>

- [<span data-ttu-id="d73e3-115">変数宣言</span><span class="sxs-lookup"><span data-stu-id="d73e3-115">Variable Declaration</span></span>](variable-declaration.md)
- [<span data-ttu-id="d73e3-116">オブジェクト変数</span><span class="sxs-lookup"><span data-stu-id="d73e3-116">Object Variables</span></span>](object-variables.md)
- [<span data-ttu-id="d73e3-117">オブジェクト変数の宣言</span><span class="sxs-lookup"><span data-stu-id="d73e3-117">Object Variable Declaration</span></span>](object-variable-declaration.md)
- [<span data-ttu-id="d73e3-118">Object 型</span><span class="sxs-lookup"><span data-stu-id="d73e3-118">Object Data Type</span></span>](../../../language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="d73e3-119">Dim ステートメント</span><span class="sxs-lookup"><span data-stu-id="d73e3-119">Dim Statement</span></span>](../../../language-reference/statements/dim-statement.md)
- [<span data-ttu-id="d73e3-120">ローカル型の推論</span><span class="sxs-lookup"><span data-stu-id="d73e3-120">Local Type Inference</span></span>](local-type-inference.md)
- [<span data-ttu-id="d73e3-121">Option Strict ステートメント</span><span class="sxs-lookup"><span data-stu-id="d73e3-121">Option Strict Statement</span></span>](../../../language-reference/statements/option-strict-statement.md)
