---
title: '方法: オブジェクト初期化子 (Visual Basic) を使用してオブジェクトを宣言します。'
ms.date: 07/20/2015
helpviewer_keywords:
- declaring objects using object initializer
- object initializers [Visual Basic]
- initializers [Visual Basic]
- Video How tos, Visual Basic
ms.assetid: 0f53a553-efd6-466d-80bf-6b679e5cd174
ms.openlocfilehash: 775c40cbb62272f913297d5a58914a0c82c5a7d7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59305313"
---
# <a name="how-to-declare-an-object-by-using-an-object-initializer-visual-basic"></a><span data-ttu-id="f1cdd-102">方法: オブジェクト初期化子 (Visual Basic) を使用してオブジェクトを宣言します。</span><span class="sxs-lookup"><span data-stu-id="f1cdd-102">How to: Declare an Object by Using an Object Initializer (Visual Basic)</span></span>
<span data-ttu-id="f1cdd-103">オブジェクト初期化子を使用すると、宣言および 1 つのステートメント内のクラスのインスタンスをインスタンス化できます。</span><span class="sxs-lookup"><span data-stu-id="f1cdd-103">Object initializers enable you to declare and instantiate an instance of a class in a single statement.</span></span> <span data-ttu-id="f1cdd-104">さらに、パラメーター化されたコンス トラクターを呼び出さずに、同時インスタンスの 1 つまたは複数のメンバーを初期化できます。</span><span class="sxs-lookup"><span data-stu-id="f1cdd-104">In addition, you can initialize one or more members of the instance at the same time, without invoking a parameterized constructor.</span></span>  
  
 <span data-ttu-id="f1cdd-105">名前付きの型のインスタンスを作成する、オブジェクト初期化子を使用すると、指定した順序で指定されたメンバーの初期化後に、クラスの既定のコンス トラクターが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="f1cdd-105">When you use an object initializer to create an instance of a named type, the default constructor for the class is called, followed by initialization of designated members in the order you specify.</span></span>  
  
 <span data-ttu-id="f1cdd-106">インスタンスを作成する方法は、次の手順を`Student`3 つの異なる方法でクラス。</span><span class="sxs-lookup"><span data-stu-id="f1cdd-106">The following procedure shows how to create an instance of a `Student` class in three different ways.</span></span> <span data-ttu-id="f1cdd-107">クラスには、名、姓、名、およびその他のクラスの年プロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="f1cdd-107">The class has first name, last name, and class year properties, among others.</span></span> <span data-ttu-id="f1cdd-108">新しいインスタンスを作成、3 つの宣言の各`Student`、プロパティを持つ`First`プロパティ「マイケル ・」に設定`Last`「tucker です」に設定され、その他のすべてのメンバーが既定値に設定します。</span><span class="sxs-lookup"><span data-stu-id="f1cdd-108">Each of the three declarations creates a new instance of `Student`, with property `First` set to "Michael", property `Last` set to "Tucker", and all other members set to their default values.</span></span> <span data-ttu-id="f1cdd-109">手順では、各宣言の結果は、次の例は、オブジェクト初期化子を使用しないのと同じです。</span><span class="sxs-lookup"><span data-stu-id="f1cdd-109">The result of each declaration in the procedure is equivalent to the following example, which does not use an object initializer.</span></span>  
  
 [!code-vb[VbVbalrObjectInit#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#20)]  
  
 <span data-ttu-id="f1cdd-110">実装については、`Student`クラスを参照してください[方法。項目の一覧を作成](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)です。</span><span class="sxs-lookup"><span data-stu-id="f1cdd-110">For an implementation of the `Student` class, see [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).</span></span> <span data-ttu-id="f1cdd-111">コードをコピーするには、クラスを設定しの一覧を作成するには、そのトピックから`Student`オブジェクトを使用します。</span><span class="sxs-lookup"><span data-stu-id="f1cdd-111">You can copy the code from that topic to set up the class and create a list of `Student` objects to work with.</span></span>  
  
### <a name="to-create-an-object-of-a-named-class-by-using-an-object-initializer"></a><span data-ttu-id="f1cdd-112">オブジェクト初期化子を使用して名前付きクラスのオブジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="f1cdd-112">To create an object of a named class by using an object initializer</span></span>  
  
1. <span data-ttu-id="f1cdd-113">コンス トラクターを使用する場合、宣言を開始します。</span><span class="sxs-lookup"><span data-stu-id="f1cdd-113">Begin the declaration as if you planned to use a constructor.</span></span>  
  
     `Dim student1 As New Student`  
  
2. <span data-ttu-id="f1cdd-114">キーワードを入力`With`、初期化リストを中かっこでその後にします。</span><span class="sxs-lookup"><span data-stu-id="f1cdd-114">Type the keyword `With`, followed by an initialization list in braces.</span></span>  
  
     `Dim student1 As New Student With { <initialization list> }`  
  
3. <span data-ttu-id="f1cdd-115">初期化リストで初期化し、初期値を割り当てるしたい各プロパティが含まれます。</span><span class="sxs-lookup"><span data-stu-id="f1cdd-115">In the initialization list, include each property that you want to initialize and assign an initial value to it.</span></span> <span data-ttu-id="f1cdd-116">プロパティの名前の前にピリオドです。</span><span class="sxs-lookup"><span data-stu-id="f1cdd-116">The name of the property is preceded by a period.</span></span>  
  
     [!code-vb[VbVbalrObjectInit#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#21)]  
  
     <span data-ttu-id="f1cdd-117">クラスの 1 つまたは複数のメンバーを初期化することができます。</span><span class="sxs-lookup"><span data-stu-id="f1cdd-117">You can initialize one or more members of the class.</span></span>  
  
4. <span data-ttu-id="f1cdd-118">または、クラスの新しいインスタンスを宣言し、値を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="f1cdd-118">Alternatively, you can declare a new instance of the class and then assign a value to it.</span></span> <span data-ttu-id="f1cdd-119">インスタンスを最初に、宣言`Student`:</span><span class="sxs-lookup"><span data-stu-id="f1cdd-119">First, declare an instance of `Student`:</span></span>  
  
     `Dim student2 As Student`  
  
5. <span data-ttu-id="f1cdd-120">インスタンスの作成を開始`Student`通常どおりにします。</span><span class="sxs-lookup"><span data-stu-id="f1cdd-120">Begin the creation of an instance of `Student` in the normal way.</span></span>  
  
     `Dim student2 As Student = New Student`  
  
6. <span data-ttu-id="f1cdd-121">型`With`と 1 つまたは複数のメンバーの新しいインスタンスを初期化するためにオブジェクト初期化子、します。</span><span class="sxs-lookup"><span data-stu-id="f1cdd-121">Type `With` and then an object initializer to initialize one or more members of the new instance.</span></span>  
  
     [!code-vb[VbVbalrObjectInit#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#22)]  
  
7. <span data-ttu-id="f1cdd-122">省略すると、前の手順で定義を簡略化できます`As Student`します。</span><span class="sxs-lookup"><span data-stu-id="f1cdd-122">You can simplify the definition in the previous step by omitting `As Student`.</span></span> <span data-ttu-id="f1cdd-123">コンパイラが判断した場合、これを行うと、`student3`のインスタンスである`Student`ローカル型推論を使用しています。</span><span class="sxs-lookup"><span data-stu-id="f1cdd-123">If you do this, the compiler determines that `student3` is an instance of `Student` by using local type inference.</span></span>  
  
     [!code-vb[VbVbalrObjectInit#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#23)]  
  
     <span data-ttu-id="f1cdd-124">詳細については、次を参照してください。[ローカル型推論](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)します。</span><span class="sxs-lookup"><span data-stu-id="f1cdd-124">For more information, see [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1cdd-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="f1cdd-125">See also</span></span>

- [<span data-ttu-id="f1cdd-126">ローカル型の推論</span><span class="sxs-lookup"><span data-stu-id="f1cdd-126">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="f1cdd-127">方法: 項目の一覧を作成します。</span><span class="sxs-lookup"><span data-stu-id="f1cdd-127">How to: Create a List of Items</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)
- [<span data-ttu-id="f1cdd-128">オブジェクト初期化子:名前付きの匿名型</span><span class="sxs-lookup"><span data-stu-id="f1cdd-128">Object Initializers: Named and Anonymous Types</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [<span data-ttu-id="f1cdd-129">匿名型</span><span class="sxs-lookup"><span data-stu-id="f1cdd-129">Anonymous Types</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
