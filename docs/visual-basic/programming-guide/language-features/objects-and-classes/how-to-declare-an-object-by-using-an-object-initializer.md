---
title: '方法: オブジェクト初期化子を使用してオブジェクトを宣言する'
ms.date: 07/20/2015
helpviewer_keywords:
- declaring objects using object initializer
- object initializers [Visual Basic]
- initializers [Visual Basic]
- Video How tos, Visual Basic
ms.assetid: 0f53a553-efd6-466d-80bf-6b679e5cd174
ms.openlocfilehash: 61f520a528c3d40b9d34807d517a9bf27ad40da8
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "91075227"
---
# <a name="how-to-declare-an-object-by-using-an-object-initializer-visual-basic"></a><span data-ttu-id="f2582-102">方法: オブジェクト初期化子を使用してオブジェクトを宣言する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f2582-102">How to: Declare an Object by Using an Object Initializer (Visual Basic)</span></span>

<span data-ttu-id="f2582-103">オブジェクト初期化子を使用すると、1 つのステートメントで、クラスのインスタンスを宣言してインスタンス化できます。</span><span class="sxs-lookup"><span data-stu-id="f2582-103">Object initializers enable you to declare and instantiate an instance of a class in a single statement.</span></span> <span data-ttu-id="f2582-104">また、パラメーター化されたコンストラクターを呼び出さずに、インスタンスの 1 つ以上のメンバーを同時に初期化できます。</span><span class="sxs-lookup"><span data-stu-id="f2582-104">In addition, you can initialize one or more members of the instance at the same time, without invoking a parameterized constructor.</span></span>  
  
 <span data-ttu-id="f2582-105">オブジェクト初期化子を使用して、名前付きの型のインスタンスを作成すると、クラスのパラメーターなしのコンストラクターが呼び出され、続いて指定した順番で、指定したメンバーの初期化が行われます。</span><span class="sxs-lookup"><span data-stu-id="f2582-105">When you use an object initializer to create an instance of a named type, the parameterless constructor for the class is called, followed by initialization of designated members in the order you specify.</span></span>  
  
 <span data-ttu-id="f2582-106">次の手順は、3 つの異なる方法で `Student` クラスのインスタンスを作成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="f2582-106">The following procedure shows how to create an instance of a `Student` class in three different ways.</span></span> <span data-ttu-id="f2582-107">クラスには特に姓、名、および学年のプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="f2582-107">The class has first name, last name, and class year properties, among others.</span></span> <span data-ttu-id="f2582-108">3 つの各宣言では、プロパティ `First` を "Michael" に設定し、プロパティ `Last` を "Tucker" に設定し、その他のすべてのメンバーをそれらの既定値に設定して、`Student` の新しいインスタンスを作成しています。</span><span class="sxs-lookup"><span data-stu-id="f2582-108">Each of the three declarations creates a new instance of `Student`, with property `First` set to "Michael", property `Last` set to "Tucker", and all other members set to their default values.</span></span> <span data-ttu-id="f2582-109">プロシージャ内の各宣言の結果は、オブジェクト初期化子を使用しない次の例と同じです。</span><span class="sxs-lookup"><span data-stu-id="f2582-109">The result of each declaration in the procedure is equivalent to the following example, which does not use an object initializer.</span></span>  
  
 [!code-vb[VbVbalrObjectInit#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#20)]  
  
 <span data-ttu-id="f2582-110">`Student` クラスの実装については、「[方法:項目のリストを作成する](../../concepts/linq/how-to-create-a-list-of-items.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2582-110">For an implementation of the `Student` class, see [How to: Create a List of Items](../../concepts/linq/how-to-create-a-list-of-items.md).</span></span> <span data-ttu-id="f2582-111">そのトピックからコードをコピーして、クラスを設定し、操作する `Student` オブジェクトの一覧を作成できます。</span><span class="sxs-lookup"><span data-stu-id="f2582-111">You can copy the code from that topic to set up the class and create a list of `Student` objects to work with.</span></span>  
  
### <a name="to-create-an-object-of-a-named-class-by-using-an-object-initializer"></a><span data-ttu-id="f2582-112">オブジェクト初期化子を使用して、名前付きクラスのオブジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="f2582-112">To create an object of a named class by using an object initializer</span></span>  
  
1. <span data-ttu-id="f2582-113">コンストラクターを使用することを計画した場合と同様に、宣言を開始します。</span><span class="sxs-lookup"><span data-stu-id="f2582-113">Begin the declaration as if you planned to use a constructor.</span></span>  
  
     `Dim student1 As New Student`  
  
2. <span data-ttu-id="f2582-114">キーワード `With` の後に中かっこで囲んだ初期化リストを含めて入力します。</span><span class="sxs-lookup"><span data-stu-id="f2582-114">Type the keyword `With`, followed by an initialization list in braces.</span></span>  
  
     `Dim student1 As New Student With { <initialization list> }`  
  
3. <span data-ttu-id="f2582-115">初期化リストに、初期化して、それに初期値を代入する各プロパティを含めます。</span><span class="sxs-lookup"><span data-stu-id="f2582-115">In the initialization list, include each property that you want to initialize and assign an initial value to it.</span></span> <span data-ttu-id="f2582-116">プロパティの名前の前にピリオドを付けます。</span><span class="sxs-lookup"><span data-stu-id="f2582-116">The name of the property is preceded by a period.</span></span>  
  
     [!code-vb[VbVbalrObjectInit#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#21)]  
  
     <span data-ttu-id="f2582-117">クラスの 1 つ以上のメンバーを初期化できます。</span><span class="sxs-lookup"><span data-stu-id="f2582-117">You can initialize one or more members of the class.</span></span>  
  
4. <span data-ttu-id="f2582-118">または、クラスの新しいインスタンスを宣言してから、それに値を代入することもできます。</span><span class="sxs-lookup"><span data-stu-id="f2582-118">Alternatively, you can declare a new instance of the class and then assign a value to it.</span></span> <span data-ttu-id="f2582-119">まず、`Student` のインスタンスを宣言します。</span><span class="sxs-lookup"><span data-stu-id="f2582-119">First, declare an instance of `Student`:</span></span>  
  
     `Dim student2 As Student`  
  
5. <span data-ttu-id="f2582-120">通常の方法で `Student` のインスタンスの作成を開始します。</span><span class="sxs-lookup"><span data-stu-id="f2582-120">Begin the creation of an instance of `Student` in the normal way.</span></span>  
  
     `Dim student2 As Student = New Student`  
  
6. <span data-ttu-id="f2582-121">`With` に続けてオブジェクト初期化子を入力して、新しいインスタンスの 1 つ以上のメンバーを初期化します。</span><span class="sxs-lookup"><span data-stu-id="f2582-121">Type `With` and then an object initializer to initialize one or more members of the new instance.</span></span>  
  
     [!code-vb[VbVbalrObjectInit#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#22)]  
  
7. <span data-ttu-id="f2582-122">`As Student` を省略すると、前のステップの定義を簡略化できます。</span><span class="sxs-lookup"><span data-stu-id="f2582-122">You can simplify the definition in the previous step by omitting `As Student`.</span></span> <span data-ttu-id="f2582-123">これを行うと、コンパイラによって、ローカル型推論を使用して、`student3` が `Student` のインスタンスであると判断されます。</span><span class="sxs-lookup"><span data-stu-id="f2582-123">If you do this, the compiler determines that `student3` is an instance of `Student` by using local type inference.</span></span>  
  
     [!code-vb[VbVbalrObjectInit#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#23)]  
  
     <span data-ttu-id="f2582-124">詳細については、「[ローカル型の推論](../variables/local-type-inference.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2582-124">For more information, see [Local Type Inference](../variables/local-type-inference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2582-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="f2582-125">See also</span></span>

- [<span data-ttu-id="f2582-126">ローカル型の推論</span><span class="sxs-lookup"><span data-stu-id="f2582-126">Local Type Inference</span></span>](../variables/local-type-inference.md)
- [<span data-ttu-id="f2582-127">方法: 項目のリストを作成する</span><span class="sxs-lookup"><span data-stu-id="f2582-127">How to: Create a List of Items</span></span>](../../concepts/linq/how-to-create-a-list-of-items.md)
- [<span data-ttu-id="f2582-128">オブジェクト初期化子: 名前付きの型と匿名型</span><span class="sxs-lookup"><span data-stu-id="f2582-128">Object Initializers: Named and Anonymous Types</span></span>](object-initializers-named-and-anonymous-types.md)
- [<span data-ttu-id="f2582-129">匿名型</span><span class="sxs-lookup"><span data-stu-id="f2582-129">Anonymous Types</span></span>](anonymous-types.md)
