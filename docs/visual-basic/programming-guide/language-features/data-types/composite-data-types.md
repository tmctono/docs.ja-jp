---
title: 複合データ型
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
ms.openlocfilehash: 1c099c5082f1c4173a50c70998c99135c94821e6
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346376"
---
# <a name="composite-data-types-visual-basic"></a><span data-ttu-id="90421-102">複合データ型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="90421-102">Composite Data Types (Visual Basic)</span></span>
<span data-ttu-id="90421-103">Visual Basic の基本データ型に加えて、さまざまな型の項目をアセンブルして、構造体、配列、クラスなどの*複合データ型*を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="90421-103">In addition to the elementary data types Visual Basic supplies, you can also assemble items of different types to create *composite data types* such as structures, arrays, and classes.</span></span> <span data-ttu-id="90421-104">複合データ型は、基本型および他の複合型から構築できます。</span><span class="sxs-lookup"><span data-stu-id="90421-104">You can build composite data types from elementary types and from other composite types.</span></span> <span data-ttu-id="90421-105">たとえば、構造体要素の配列、または配列メンバーを持つ構造体を定義できます。</span><span class="sxs-lookup"><span data-stu-id="90421-105">For example, you can define an array of structure elements, or a structure with array members.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="90421-106">データ型</span><span class="sxs-lookup"><span data-stu-id="90421-106">Data Types</span></span>  
 <span data-ttu-id="90421-107">複合型は、そのコンポーネントのデータ型とは異なります。</span><span class="sxs-lookup"><span data-stu-id="90421-107">A composite type is different from the data type of any of its components.</span></span> <span data-ttu-id="90421-108">たとえば、`Integer` の要素の配列は、`Integer` データ型ではありません。</span><span class="sxs-lookup"><span data-stu-id="90421-108">For example, an array of `Integer` elements is not of the `Integer` data type.</span></span>  
  
 <span data-ttu-id="90421-109">通常、配列のデータ型は、要素の型、かっこ、およびコンマを使用して、必要に応じて表されます。</span><span class="sxs-lookup"><span data-stu-id="90421-109">An array data type is normally represented using the element type, parentheses, and commas as necessary.</span></span> <span data-ttu-id="90421-110">たとえば、`String` 要素の1次元配列は `String()`として表され、`Boolean` 要素の2次元配列は `Boolean(,)`として表されます。</span><span class="sxs-lookup"><span data-stu-id="90421-110">For example, a one-dimensional array of `String` elements is represented as `String()`, and a two-dimensional array of `Boolean` elements is represented as `Boolean(,)`.</span></span>  
  
## <a name="structure-types"></a><span data-ttu-id="90421-111">構造体の型</span><span class="sxs-lookup"><span data-stu-id="90421-111">Structure Types</span></span>  
 <span data-ttu-id="90421-112">すべての構造体を構成する1つのデータ型はありません。</span><span class="sxs-lookup"><span data-stu-id="90421-112">There is no single data type comprising all structures.</span></span> <span data-ttu-id="90421-113">2つの構造体が同じ順序で同じ要素を定義している場合でも、構造体の各定義は一意のデータ型を表します。</span><span class="sxs-lookup"><span data-stu-id="90421-113">Instead, each definition of a structure represents a unique data type, even if two structures define identical elements in the same order.</span></span> <span data-ttu-id="90421-114">ただし、同じ構造体の複数のインスタンスを作成した場合、Visual Basic はそれらを同じデータ型であると見なします。</span><span class="sxs-lookup"><span data-stu-id="90421-114">However, if you create two or more instances of the same structure, Visual Basic considers them to be of the same data type.</span></span>  
  
## <a name="tuples"></a><span data-ttu-id="90421-115">タプル</span><span class="sxs-lookup"><span data-stu-id="90421-115">Tuples</span></span>

<span data-ttu-id="90421-116">組は、型が事前定義されている 2 つ以上のフィールドを含む軽量の構造体です。</span><span class="sxs-lookup"><span data-stu-id="90421-116">A tuple is a lightweight structure that contains two or more fields whose types are predefined.</span></span> <span data-ttu-id="90421-117">タプルは Visual Basic 2017 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="90421-117">Tuples are supported starting with Visual Basic 2017.</span></span> <span data-ttu-id="90421-118">タプルは、1つのメソッド呼び出しから複数の値を返すために最も一般的に使用されます。参照によって引数を渡したり、返されたフィールドをより重いクラスまたは構造体にパッケージ化したりする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="90421-118">Tuples are most commonly used to return multiple values from a single method call without having to pass arguments by reference or packaging the returned fields in a more heavy-weight class or structure.</span></span> <span data-ttu-id="90421-119">組の詳細については、「[タプル](tuples.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="90421-119">See the [Tuples](tuples.md) topic for more information on tuples.</span></span>

## <a name="array-types"></a><span data-ttu-id="90421-120">配列型</span><span class="sxs-lookup"><span data-stu-id="90421-120">Array Types</span></span>  
 <span data-ttu-id="90421-121">すべての配列を構成する1つのデータ型はありません。</span><span class="sxs-lookup"><span data-stu-id="90421-121">There is no single data type comprising all arrays.</span></span> <span data-ttu-id="90421-122">配列の特定のインスタンスのデータ型は、次のように決定されます。</span><span class="sxs-lookup"><span data-stu-id="90421-122">The data type of a particular instance of an array is determined by the following:</span></span>  
  
- <span data-ttu-id="90421-123">配列であるという事実</span><span class="sxs-lookup"><span data-stu-id="90421-123">The fact of being an array</span></span>  
  
- <span data-ttu-id="90421-124">配列のランク (次元数)</span><span class="sxs-lookup"><span data-stu-id="90421-124">The rank (number of dimensions) of the array</span></span>  
  
- <span data-ttu-id="90421-125">配列の要素型。</span><span class="sxs-lookup"><span data-stu-id="90421-125">The element type of the array</span></span>  
  
 <span data-ttu-id="90421-126">特に、特定のディメンションの長さは、インスタンスのデータ型の一部ではありません。</span><span class="sxs-lookup"><span data-stu-id="90421-126">In particular, the length of a given dimension is not part of the instance's data type.</span></span> <span data-ttu-id="90421-127">これを次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="90421-127">The following example illustrates this.</span></span>  
  
```vb  
Dim arrayA( ) As Byte = New Byte(12) {}  
Dim arrayB( ) As Byte = New Byte(100) {}  
Dim arrayC( ) As Short = New Short(100) {}  
Dim arrayD( , ) As Short  
Dim arrayE( , ) As Short = New Short(4, 10) {}  
```  
  
 <span data-ttu-id="90421-128">前の例では、配列変数 `arrayA` と `arrayB` は、異なる長さに初期化されている場合でも、同じデータ型 (`Byte()`) と見なされます。</span><span class="sxs-lookup"><span data-stu-id="90421-128">In the preceding example, array variables `arrayA` and `arrayB` are considered to be of the same data type — `Byte()` — even though they are initialized to different lengths.</span></span> <span data-ttu-id="90421-129">`arrayB` と `arrayC` の変数は、要素の型が異なるため、同じ型ではありません。</span><span class="sxs-lookup"><span data-stu-id="90421-129">Variables `arrayB` and `arrayC` are not of the same type because their element types are different.</span></span> <span data-ttu-id="90421-130">`arrayC` と `arrayD` の変数は、ランクが異なるため、同じ型ではありません。</span><span class="sxs-lookup"><span data-stu-id="90421-130">Variables `arrayC` and `arrayD` are not of the same type because their ranks are different.</span></span> <span data-ttu-id="90421-131">`arrayD` がまだ初期化されていない場合でも、`arrayD` と `arrayE` 変数は同じ型 (`Short(,)`) を持ちます。</span><span class="sxs-lookup"><span data-stu-id="90421-131">Variables `arrayD` and `arrayE` have the same type — `Short(,)` — because their ranks and element types are the same, even though `arrayD` is not yet initialized.</span></span>  
  
 <span data-ttu-id="90421-132">配列の詳細については、「[配列](../../../../visual-basic/programming-guide/language-features/arrays/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="90421-132">For more information on arrays, see [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
## <a name="class-types"></a><span data-ttu-id="90421-133">クラスの種類</span><span class="sxs-lookup"><span data-stu-id="90421-133">Class Types</span></span>  
 <span data-ttu-id="90421-134">すべてのクラスを構成する1つのデータ型はありません。</span><span class="sxs-lookup"><span data-stu-id="90421-134">There is no single data type comprising all classes.</span></span> <span data-ttu-id="90421-135">1つのクラスは別のクラスから継承できますが、それぞれが個別のデータ型です。</span><span class="sxs-lookup"><span data-stu-id="90421-135">Although one class can inherit from another class, each is a separate data type.</span></span> <span data-ttu-id="90421-136">同じクラスの複数のインスタンスが同じデータ型です。</span><span class="sxs-lookup"><span data-stu-id="90421-136">Multiple instances of the same class are of the same data type.</span></span> <span data-ttu-id="90421-137">あるクラスインスタンス変数を別のクラスインスタンス変数に割り当てると、データ型が同じであるだけでなく、メモリ内の同じクラスインスタンスが参照されます。</span><span class="sxs-lookup"><span data-stu-id="90421-137">If you assign one class instance variable to another, not only do they have the same data type, they point to the same class instance in memory.</span></span>  
  
 <span data-ttu-id="90421-138">クラスの詳細については、「[オブジェクトとクラス](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="90421-138">For more information on classes, see [Objects and Classes](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90421-139">参照</span><span class="sxs-lookup"><span data-stu-id="90421-139">See also</span></span>

- [<span data-ttu-id="90421-140">データの種類</span><span class="sxs-lookup"><span data-stu-id="90421-140">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [<span data-ttu-id="90421-141">基本データ型</span><span class="sxs-lookup"><span data-stu-id="90421-141">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [<span data-ttu-id="90421-142">Visual Basic におけるジェネリック型</span><span class="sxs-lookup"><span data-stu-id="90421-142">Generic Types in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="90421-143">値型と参照型</span><span class="sxs-lookup"><span data-stu-id="90421-143">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [<span data-ttu-id="90421-144">Visual Basic での型変換</span><span class="sxs-lookup"><span data-stu-id="90421-144">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="90421-145">構造体</span><span class="sxs-lookup"><span data-stu-id="90421-145">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="90421-146">トラブルシューティング (データ型)</span><span class="sxs-lookup"><span data-stu-id="90421-146">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="90421-147">方法 : 変数内で複数の値を保持する</span><span class="sxs-lookup"><span data-stu-id="90421-147">How to: Hold More Than One Value in a Variable</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-hold-more-than-one-value-in-a-variable.md)
