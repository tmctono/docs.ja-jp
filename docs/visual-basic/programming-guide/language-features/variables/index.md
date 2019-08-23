---
title: Visual Basic における変数
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic]
- values [Visual Basic], storing
ms.assetid: 4cfaa06d-4ae3-4307-897b-cf599dc24caa
ms.openlocfilehash: 30baab24c54b5158da53f1ba88206d8f1564ebaf
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69953348"
---
# <a name="variables-in-visual-basic"></a><span data-ttu-id="a68b0-102">Visual Basic における変数</span><span class="sxs-lookup"><span data-stu-id="a68b0-102">Variables in Visual Basic</span></span>
<span data-ttu-id="a68b0-103">Visual Basic で計算を実行するときは、多くの場合、値を格納する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a68b0-103">You often have to store values when you perform calculations with Visual Basic.</span></span> <span data-ttu-id="a68b0-104">たとえば、いくつかの値を計算し、比較し、比較の結果に応じて、さまざまな操作を実行する必要があるとします。</span><span class="sxs-lookup"><span data-stu-id="a68b0-104">For example, you might want to calculate several values, compare them, and perform different operations on them, depending on the result of the comparison.</span></span> <span data-ttu-id="a68b0-105">比較する場合には、その値を保持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a68b0-105">You have to retain the values if you want to compare them.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="a68b0-106">使用方法</span><span class="sxs-lookup"><span data-stu-id="a68b0-106">Usage</span></span>  
 <span data-ttu-id="a68b0-107">Visual Basic は、ほとんどのプログラミング言語と同様に、値を格納するために変数を使用します。</span><span class="sxs-lookup"><span data-stu-id="a68b0-107">Visual Basic, just like most programming languages, uses variables for storing values.</span></span> <span data-ttu-id="a68b0-108">*変数*には (変数に含まれる値を参照するために使用する語である) 名前があります。</span><span class="sxs-lookup"><span data-stu-id="a68b0-108">A *variable* has a name (the word that you use to refer to the value that the variable contains).</span></span> <span data-ttu-id="a68b0-109">変数には、(変数に格納できるデータの種類を決定する) データ型もあります。</span><span class="sxs-lookup"><span data-stu-id="a68b0-109">A variable also has a data type (which determines the kind of data that the variable can store).</span></span> <span data-ttu-id="a68b0-110">密接に関連するデータ項目のインデックス セットを格納する必要がある場合、変数で配列を表現することもできます。</span><span class="sxs-lookup"><span data-stu-id="a68b0-110">A variable can represent an array if it has to store an indexed set of closely related data items.</span></span>  
  
 <span data-ttu-id="a68b0-111">ローカル型推論では、データ型を明示的に指定せずに変数を宣言できます。</span><span class="sxs-lookup"><span data-stu-id="a68b0-111">Local type inference enables you to declare variables without explicitly stating a data type.</span></span> <span data-ttu-id="a68b0-112">代わりに、コンパイラは、初期化式の型から変数の型を推測します。</span><span class="sxs-lookup"><span data-stu-id="a68b0-112">Instead, the compiler infers the type of the variable from the type of the initialization expression.</span></span> <span data-ttu-id="a68b0-113">詳細については、「[ローカル型の推論](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)」と「[Option Infer ステートメント](../../../../visual-basic/language-reference/statements/option-infer-statement.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a68b0-113">For more information, see [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) and [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md).</span></span>  
  
## <a name="assigning-values"></a><span data-ttu-id="a68b0-114">値の代入</span><span class="sxs-lookup"><span data-stu-id="a68b0-114">Assigning Values</span></span>  
 <span data-ttu-id="a68b0-115">次の例のように、計算を実行し、結果を変数に割り当てるために、代入ステートメントを使用できます。</span><span class="sxs-lookup"><span data-stu-id="a68b0-115">You use assignment statements to perform calculations and assign the result to a variable, as the following example shows.</span></span>  
  
 [!code-vb[VbVbalrVariables#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrVariables/VB/Class1.vb#1)]  
  
> [!NOTE]
> <span data-ttu-id="a68b0-116">この例の等号 (`=`) は、等値演算子ではなく代入演算子です。</span><span class="sxs-lookup"><span data-stu-id="a68b0-116">The equal sign (`=`) in this example is an assignment operator, not an equality operator.</span></span> <span data-ttu-id="a68b0-117">この値は、変数 `applesSold` に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="a68b0-117">The value is being assigned to the variable `applesSold`.</span></span>  
  
 <span data-ttu-id="a68b0-118">詳細については、「[方法 :変数](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md)との間でデータを移動します。</span><span class="sxs-lookup"><span data-stu-id="a68b0-118">For more information, see [How to: Move Data Into and Out of a Variable](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md).</span></span>  
  
## <a name="variables-and-properties"></a><span data-ttu-id="a68b0-119">変数とプロパティ</span><span class="sxs-lookup"><span data-stu-id="a68b0-119">Variables and Properties</span></span>  
 <span data-ttu-id="a68b0-120">変数と同様に、*プロパティ*はアクセス可能な値です。</span><span class="sxs-lookup"><span data-stu-id="a68b0-120">Like a variable, a *property* represents a value that you can access.</span></span> <span data-ttu-id="a68b0-121">ただし、変数よりも複雑です。</span><span class="sxs-lookup"><span data-stu-id="a68b0-121">However, it is more complex than a variable.</span></span> <span data-ttu-id="a68b0-122">プロパティは、その値を設定し取得する方法を制御するコード ブロックを使用します。</span><span class="sxs-lookup"><span data-stu-id="a68b0-122">A property uses code blocks that control how to set and retrieve its value.</span></span> <span data-ttu-id="a68b0-123">詳細については、「[Visual Basic のプロパティと変数の違い](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a68b0-123">For more information, see [Differences Between Properties and Variables in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a68b0-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="a68b0-124">See also</span></span>

- [<span data-ttu-id="a68b0-125">変数宣言</span><span class="sxs-lookup"><span data-stu-id="a68b0-125">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="a68b0-126">オブジェクト変数</span><span class="sxs-lookup"><span data-stu-id="a68b0-126">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="a68b0-127">変数のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="a68b0-127">Troubleshooting Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/troubleshooting-variables.md)
- [<span data-ttu-id="a68b0-128">方法: 変数にデータを移動する</span><span class="sxs-lookup"><span data-stu-id="a68b0-128">How to: Move Data Into and Out of a Variable</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md)
- [<span data-ttu-id="a68b0-129">Visual Basic のプロパティと変数の違い</span><span class="sxs-lookup"><span data-stu-id="a68b0-129">Differences Between Properties and Variables in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md)
- [<span data-ttu-id="a68b0-130">ローカル型の推論</span><span class="sxs-lookup"><span data-stu-id="a68b0-130">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
