---
title: 複合データ型 (Visual Basic)
ms.date: 04/25/2017
helpviewer_keywords:
- classes [Visual Basic], composite data types
- composite types [Visual Basic]
- composite data types [Visual Basic]
- data types [Visual Basic], composite
- arrays [Visual Basic], composite data types
- structures [Visual Basic], composite data types
- classes [Visual Basic], composite types
- types [Visual Basic], composite
ms.assetid: 62970f2e-52c0-4369-8963-613820f1f434
ms.openlocfilehash: 65ee23c59958eefb94c7ab0c6bef4a7e992a121c
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64601180"
---
# <a name="composite-data-types-visual-basic"></a><span data-ttu-id="7fb5d-102">複合データ型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7fb5d-102">Composite Data Types (Visual Basic)</span></span>
<span data-ttu-id="7fb5d-103">Visual Basic に用意されている基本データ型だけでなくを作成するさまざまな種類の項目をアセンブルすることができますも*複合データ型*構造体、配列、およびクラスなどです。</span><span class="sxs-lookup"><span data-stu-id="7fb5d-103">In addition to the elementary data types Visual Basic supplies, you can also assemble items of different types to create *composite data types* such as structures, arrays, and classes.</span></span> <span data-ttu-id="7fb5d-104">基本型およびその他の複合型からは、複合データ型を構築できます。</span><span class="sxs-lookup"><span data-stu-id="7fb5d-104">You can build composite data types from elementary types and from other composite types.</span></span> <span data-ttu-id="7fb5d-105">たとえば、配列のメンバーを持つ構造体または構造体の要素の配列を定義できます。</span><span class="sxs-lookup"><span data-stu-id="7fb5d-105">For example, you can define an array of structure elements, or a structure with array members.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="7fb5d-106">データの種類</span><span class="sxs-lookup"><span data-stu-id="7fb5d-106">Data Types</span></span>  
 <span data-ttu-id="7fb5d-107">複合型は、そのコンポーネントのいずれかのデータ型と異なります。</span><span class="sxs-lookup"><span data-stu-id="7fb5d-107">A composite type is different from the data type of any of its components.</span></span> <span data-ttu-id="7fb5d-108">たとえば、配列の`Integer`の要素ではありません、`Integer`データ型。</span><span class="sxs-lookup"><span data-stu-id="7fb5d-108">For example, an array of `Integer` elements is not of the `Integer` data type.</span></span>  
  
 <span data-ttu-id="7fb5d-109">配列のデータ型は、通常、必要に応じて、要素の型、かっこ、およびコンマを使用して表されます。</span><span class="sxs-lookup"><span data-stu-id="7fb5d-109">An array data type is normally represented using the element type, parentheses, and commas as necessary.</span></span> <span data-ttu-id="7fb5d-110">たとえば、1 次元配列`String`として表される要素`String()`との 2 次元配列`Boolean`として表される要素`Boolean(,)`。</span><span class="sxs-lookup"><span data-stu-id="7fb5d-110">For example, a one-dimensional array of `String` elements is represented as `String()`, and a two-dimensional array of `Boolean` elements is represented as `Boolean(,)`.</span></span>  
  
## <a name="structure-types"></a><span data-ttu-id="7fb5d-111">構造体の型</span><span class="sxs-lookup"><span data-stu-id="7fb5d-111">Structure Types</span></span>  
 <span data-ttu-id="7fb5d-112">すべての構造を構成する 1 つのデータ型はありません。</span><span class="sxs-lookup"><span data-stu-id="7fb5d-112">There is no single data type comprising all structures.</span></span> <span data-ttu-id="7fb5d-113">代わりに、場合でも、2 つの構造が同じ順序で同一の要素を定義、構造体の各定義は、一意のデータ型を表します。</span><span class="sxs-lookup"><span data-stu-id="7fb5d-113">Instead, each definition of a structure represents a unique data type, even if two structures define identical elements in the same order.</span></span> <span data-ttu-id="7fb5d-114">ただし、同じ構造の 2 つ以上のインスタンスを作成する場合は、Visual Basic は、同じデータ型のそれらと見なします。</span><span class="sxs-lookup"><span data-stu-id="7fb5d-114">However, if you create two or more instances of the same structure, Visual Basic considers them to be of the same data type.</span></span>  
  
## <a name="tuples"></a><span data-ttu-id="7fb5d-115">タプル</span><span class="sxs-lookup"><span data-stu-id="7fb5d-115">Tuples</span></span>

<span data-ttu-id="7fb5d-116">タプルは、定義済みの型を持つ 2 つ以上のフィールドを含む軽量な構造です。</span><span class="sxs-lookup"><span data-stu-id="7fb5d-116">A tuple is a lightweight structure that contains two or more fields whose types are predefined.</span></span> <span data-ttu-id="7fb5d-117">タプルは、Visual Basic 2017 以降ではサポートされています。</span><span class="sxs-lookup"><span data-stu-id="7fb5d-117">Tuples are supported starting with Visual Basic 2017.</span></span> <span data-ttu-id="7fb5d-118">タプルは、参照渡しで引数を渡さずにまたはよりヘビーウェイトなクラスまたは構造体で返されるフィールドをパッケージ化せず、1 つのメソッドの呼び出しから複数の値を返す最もよく使用されます。</span><span class="sxs-lookup"><span data-stu-id="7fb5d-118">Tuples are most commonly used to return multiple values from a single method call without having to pass arguments by reference or packaging the returned fields in a more heavy-weight class or structure.</span></span> <span data-ttu-id="7fb5d-119">参照してください、[組](tuples.md)タプルの詳細についてはトピック。</span><span class="sxs-lookup"><span data-stu-id="7fb5d-119">See the [Tuples](tuples.md) topic for more information on tuples.</span></span>

## <a name="array-types"></a><span data-ttu-id="7fb5d-120">配列型</span><span class="sxs-lookup"><span data-stu-id="7fb5d-120">Array Types</span></span>  
 <span data-ttu-id="7fb5d-121">すべてのアレイを構成する 1 つのデータ型はありません。</span><span class="sxs-lookup"><span data-stu-id="7fb5d-121">There is no single data type comprising all arrays.</span></span> <span data-ttu-id="7fb5d-122">配列の特定のインスタンスのデータ型は、次のように決定されます。</span><span class="sxs-lookup"><span data-stu-id="7fb5d-122">The data type of a particular instance of an array is determined by the following:</span></span>  
  
- <span data-ttu-id="7fb5d-123">配列であること</span><span class="sxs-lookup"><span data-stu-id="7fb5d-123">The fact of being an array</span></span>  
  
- <span data-ttu-id="7fb5d-124">配列のランク (次元数)</span><span class="sxs-lookup"><span data-stu-id="7fb5d-124">The rank (number of dimensions) of the array</span></span>  
  
- <span data-ttu-id="7fb5d-125">配列の要素型</span><span class="sxs-lookup"><span data-stu-id="7fb5d-125">The element type of the array</span></span>  
  
 <span data-ttu-id="7fb5d-126">具体的には、次元の長さはインスタンスのデータ型の一部ではありません。</span><span class="sxs-lookup"><span data-stu-id="7fb5d-126">In particular, the length of a given dimension is not part of the instance's data type.</span></span> <span data-ttu-id="7fb5d-127">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="7fb5d-127">The following example illustrates this.</span></span>  
  
```  
Dim arrayA( ) As Byte = New Byte(12) {}  
Dim arrayB( ) As Byte = New Byte(100) {}  
Dim arrayC( ) As Short = New Short(100) {}  
Dim arrayD( , ) As Short  
Dim arrayE( , ) As Short = New Short(4, 10) {}  
```  
  
 <span data-ttu-id="7fb5d-128">前の例では、配列変数`arrayA`と`arrayB`、同じデータ型と見なされます: `Byte()` -場合でも、異なる長さに初期化されます。</span><span class="sxs-lookup"><span data-stu-id="7fb5d-128">In the preceding example, array variables `arrayA` and `arrayB` are considered to be of the same data type — `Byte()` — even though they are initialized to different lengths.</span></span> <span data-ttu-id="7fb5d-129">変数`arrayB`と`arrayC`要素型が異なるために、同じ型のないです。</span><span class="sxs-lookup"><span data-stu-id="7fb5d-129">Variables `arrayB` and `arrayC` are not of the same type because their element types are different.</span></span> <span data-ttu-id="7fb5d-130">変数`arrayC`と`arrayD`ランクが異なるために、同じ型のないです。</span><span class="sxs-lookup"><span data-stu-id="7fb5d-130">Variables `arrayC` and `arrayD` are not of the same type because their ranks are different.</span></span> <span data-ttu-id="7fb5d-131">変数`arrayD`と`arrayE`同じ型である — `Short(,)` : ランクと要素の型が同じため、たとえ`arrayD`がまだ初期化されていません。</span><span class="sxs-lookup"><span data-stu-id="7fb5d-131">Variables `arrayD` and `arrayE` have the same type — `Short(,)` — because their ranks and element types are the same, even though `arrayD` is not yet initialized.</span></span>  
  
 <span data-ttu-id="7fb5d-132">配列の詳細については、次を参照してください。[配列](../../../../visual-basic/programming-guide/language-features/arrays/index.md)します。</span><span class="sxs-lookup"><span data-stu-id="7fb5d-132">For more information on arrays, see [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
## <a name="class-types"></a><span data-ttu-id="7fb5d-133">クラスの種類</span><span class="sxs-lookup"><span data-stu-id="7fb5d-133">Class Types</span></span>  
 <span data-ttu-id="7fb5d-134">すべてのクラスを構成する 1 つのデータ型はありません。</span><span class="sxs-lookup"><span data-stu-id="7fb5d-134">There is no single data type comprising all classes.</span></span> <span data-ttu-id="7fb5d-135">1 つのクラスは、別のクラスから継承できます、別のデータ型はそれぞれします。</span><span class="sxs-lookup"><span data-stu-id="7fb5d-135">Although one class can inherit from another class, each is a separate data type.</span></span> <span data-ttu-id="7fb5d-136">同じクラスの複数のインスタンスでは、同じデータ型です。</span><span class="sxs-lookup"><span data-stu-id="7fb5d-136">Multiple instances of the same class are of the same data type.</span></span> <span data-ttu-id="7fb5d-137">クラスのインスタンスの 1 つの変数を割り当てるには別に、同じデータ型がだけでなく、メモリ内と同じクラスのインスタンスを指すようにします。</span><span class="sxs-lookup"><span data-stu-id="7fb5d-137">If you assign one class instance variable to another, not only do they have the same data type, they point to the same class instance in memory.</span></span>  
  
 <span data-ttu-id="7fb5d-138">クラスの詳細については、次を参照してください。[オブジェクトとクラス](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)します。</span><span class="sxs-lookup"><span data-stu-id="7fb5d-138">For more information on classes, see [Objects and Classes](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fb5d-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="7fb5d-139">See also</span></span>

- [<span data-ttu-id="7fb5d-140">データの種類</span><span class="sxs-lookup"><span data-stu-id="7fb5d-140">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [<span data-ttu-id="7fb5d-141">基本データ型</span><span class="sxs-lookup"><span data-stu-id="7fb5d-141">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [<span data-ttu-id="7fb5d-142">Visual Basic におけるジェネリック型</span><span class="sxs-lookup"><span data-stu-id="7fb5d-142">Generic Types in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="7fb5d-143">値型と参照型</span><span class="sxs-lookup"><span data-stu-id="7fb5d-143">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [<span data-ttu-id="7fb5d-144">Visual Basic における型変換</span><span class="sxs-lookup"><span data-stu-id="7fb5d-144">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="7fb5d-145">構造体</span><span class="sxs-lookup"><span data-stu-id="7fb5d-145">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="7fb5d-146">トラブルシューティング (データ型)</span><span class="sxs-lookup"><span data-stu-id="7fb5d-146">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="7fb5d-147">方法: 変数内で複数の値を保持する</span><span class="sxs-lookup"><span data-stu-id="7fb5d-147">How to: Hold More Than One Value in a Variable</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-hold-more-than-one-value-in-a-variable.md)
