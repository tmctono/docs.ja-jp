---
title: '方法 : オブジェクト初期化子を使用してオブジェクトを宣言する'
ms.date: 07/20/2015
helpviewer_keywords:
- declaring objects using object initializer
- object initializers [Visual Basic]
- initializers [Visual Basic]
- Video How tos, Visual Basic
ms.assetid: 0f53a553-efd6-466d-80bf-6b679e5cd174
ms.openlocfilehash: ae04d338b61027c3917ad3a7f62ff40f0a95e53e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347137"
---
# <a name="how-to-declare-an-object-by-using-an-object-initializer-visual-basic"></a><span data-ttu-id="7d915-102">方法: オブジェクト初期化子を使用してオブジェクトを宣言する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7d915-102">How to: Declare an Object by Using an Object Initializer (Visual Basic)</span></span>
<span data-ttu-id="7d915-103">オブジェクト初期化子を使用すると、1つのステートメントでクラスのインスタンスを宣言およびインスタンス化できます。</span><span class="sxs-lookup"><span data-stu-id="7d915-103">Object initializers enable you to declare and instantiate an instance of a class in a single statement.</span></span> <span data-ttu-id="7d915-104">また、パラメーター化されたコンストラクターを呼び出さずに、インスタンスの1つ以上のメンバーを同時に初期化できます。</span><span class="sxs-lookup"><span data-stu-id="7d915-104">In addition, you can initialize one or more members of the instance at the same time, without invoking a parameterized constructor.</span></span>  
  
 <span data-ttu-id="7d915-105">オブジェクト初期化子を使用して名前付きの型のインスタンスを作成すると、クラスのパラメーターなしのコンストラクターが呼び出され、指定された順序で指定されたメンバーの初期化が行われます。</span><span class="sxs-lookup"><span data-stu-id="7d915-105">When you use an object initializer to create an instance of a named type, the parameterless constructor for the class is called, followed by initialization of designated members in the order you specify.</span></span>  
  
 <span data-ttu-id="7d915-106">次の手順は、3つの異なる方法で `Student` クラスのインスタンスを作成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="7d915-106">The following procedure shows how to create an instance of a `Student` class in three different ways.</span></span> <span data-ttu-id="7d915-107">クラスには、姓、名、およびクラス year プロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="7d915-107">The class has first name, last name, and class year properties, among others.</span></span> <span data-ttu-id="7d915-108">3つの各宣言は、`Student`の新しいインスタンスを作成し、プロパティ `First` を "Michael" に、プロパティ `Last` を "Tucker" に設定し、その他のすべてのメンバーを既定値に設定します。</span><span class="sxs-lookup"><span data-stu-id="7d915-108">Each of the three declarations creates a new instance of `Student`, with property `First` set to "Michael", property `Last` set to "Tucker", and all other members set to their default values.</span></span> <span data-ttu-id="7d915-109">プロシージャ内の各宣言の結果は、オブジェクト初期化子を使用しない次の例と同じです。</span><span class="sxs-lookup"><span data-stu-id="7d915-109">The result of each declaration in the procedure is equivalent to the following example, which does not use an object initializer.</span></span>  
  
 [!code-vb[VbVbalrObjectInit#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#20)]  
  
 <span data-ttu-id="7d915-110">`Student` クラスの実装については、「[方法: 項目のリストを作成](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d915-110">For an implementation of the `Student` class, see [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).</span></span> <span data-ttu-id="7d915-111">このトピックのコードをコピーして、クラスを設定し、操作する `Student` オブジェクトの一覧を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="7d915-111">You can copy the code from that topic to set up the class and create a list of `Student` objects to work with.</span></span>  
  
### <a name="to-create-an-object-of-a-named-class-by-using-an-object-initializer"></a><span data-ttu-id="7d915-112">オブジェクト初期化子を使用して名前付きクラスのオブジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="7d915-112">To create an object of a named class by using an object initializer</span></span>  
  
1. <span data-ttu-id="7d915-113">コンストラクターを使用する予定の場合と同様に、宣言を開始します。</span><span class="sxs-lookup"><span data-stu-id="7d915-113">Begin the declaration as if you planned to use a constructor.</span></span>  
  
     `Dim student1 As New Student`  
  
2. <span data-ttu-id="7d915-114">キーワード `With`を入力し、その後に中かっこで囲まれた初期化リストを入力します。</span><span class="sxs-lookup"><span data-stu-id="7d915-114">Type the keyword `With`, followed by an initialization list in braces.</span></span>  
  
     `Dim student1 As New Student With { <initialization list> }`  
  
3. <span data-ttu-id="7d915-115">初期化の一覧に、初期化する各プロパティを含め、初期値を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="7d915-115">In the initialization list, include each property that you want to initialize and assign an initial value to it.</span></span> <span data-ttu-id="7d915-116">プロパティの名前の前にピリオドが付きます。</span><span class="sxs-lookup"><span data-stu-id="7d915-116">The name of the property is preceded by a period.</span></span>  
  
     [!code-vb[VbVbalrObjectInit#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#21)]  
  
     <span data-ttu-id="7d915-117">クラスの1つ以上のメンバーを初期化できます。</span><span class="sxs-lookup"><span data-stu-id="7d915-117">You can initialize one or more members of the class.</span></span>  
  
4. <span data-ttu-id="7d915-118">または、クラスの新しいインスタンスを宣言し、そのインスタンスに値を割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="7d915-118">Alternatively, you can declare a new instance of the class and then assign a value to it.</span></span> <span data-ttu-id="7d915-119">最初に、`Student`のインスタンスを宣言します。</span><span class="sxs-lookup"><span data-stu-id="7d915-119">First, declare an instance of `Student`:</span></span>  
  
     `Dim student2 As Student`  
  
5. <span data-ttu-id="7d915-120">通常の方法で `Student` のインスタンスの作成を開始します。</span><span class="sxs-lookup"><span data-stu-id="7d915-120">Begin the creation of an instance of `Student` in the normal way.</span></span>  
  
     `Dim student2 As Student = New Student`  
  
6. <span data-ttu-id="7d915-121">「`With`」と入力し、オブジェクト初期化子を入力して、新しいインスタンスの1つ以上のメンバーを初期化します。</span><span class="sxs-lookup"><span data-stu-id="7d915-121">Type `With` and then an object initializer to initialize one or more members of the new instance.</span></span>  
  
     [!code-vb[VbVbalrObjectInit#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#22)]  
  
7. <span data-ttu-id="7d915-122">`As Student`を省略すると、前の手順で定義を簡略化できます。</span><span class="sxs-lookup"><span data-stu-id="7d915-122">You can simplify the definition in the previous step by omitting `As Student`.</span></span> <span data-ttu-id="7d915-123">これを行うと、コンパイラは、ローカル型推論を使用して、`student3` が `Student` のインスタンスであると判断します。</span><span class="sxs-lookup"><span data-stu-id="7d915-123">If you do this, the compiler determines that `student3` is an instance of `Student` by using local type inference.</span></span>  
  
     [!code-vb[VbVbalrObjectInit#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#23)]  
  
     <span data-ttu-id="7d915-124">詳細については、「[ローカル型の推論](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d915-124">For more information, see [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d915-125">参照</span><span class="sxs-lookup"><span data-stu-id="7d915-125">See also</span></span>

- [<span data-ttu-id="7d915-126">ローカル型の推論</span><span class="sxs-lookup"><span data-stu-id="7d915-126">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="7d915-127">方法: 項目のリストを作成する</span><span class="sxs-lookup"><span data-stu-id="7d915-127">How to: Create a List of Items</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)
- [<span data-ttu-id="7d915-128">オブジェクト初期化子 : 名前付きの型と匿名型</span><span class="sxs-lookup"><span data-stu-id="7d915-128">Object Initializers: Named and Anonymous Types</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [<span data-ttu-id="7d915-129">匿名型</span><span class="sxs-lookup"><span data-stu-id="7d915-129">Anonymous Types</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
