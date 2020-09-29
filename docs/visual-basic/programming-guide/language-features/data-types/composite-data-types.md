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
ms.openlocfilehash: 842b74aa7cc99c8196fdfb1eb6c976d9e72a4fa4
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "91077164"
---
# <a name="composite-data-types-visual-basic"></a><span data-ttu-id="57d0c-102">複合データ型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="57d0c-102">Composite Data Types (Visual Basic)</span></span>

<span data-ttu-id="57d0c-103">Visual Basic で用意されている基本データ型に加え、さまざまな型の項目を組み合わせて、構造体、配列、クラスなどの "*複合データ型*" を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="57d0c-103">In addition to the elementary data types Visual Basic supplies, you can also assemble items of different types to create *composite data types* such as structures, arrays, and classes.</span></span> <span data-ttu-id="57d0c-104">複合データ型は、基本型および他の複合型から構築できます。</span><span class="sxs-lookup"><span data-stu-id="57d0c-104">You can build composite data types from elementary types and from other composite types.</span></span> <span data-ttu-id="57d0c-105">たとえば、構造体要素の配列、または配列メンバーを含む構造体を定義できます。</span><span class="sxs-lookup"><span data-stu-id="57d0c-105">For example, you can define an array of structure elements, or a structure with array members.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="57d0c-106">データの種類</span><span class="sxs-lookup"><span data-stu-id="57d0c-106">Data Types</span></span>  

 <span data-ttu-id="57d0c-107">複合型は、その構成要素いずれかのデータ型とは異なります。</span><span class="sxs-lookup"><span data-stu-id="57d0c-107">A composite type is different from the data type of any of its components.</span></span> <span data-ttu-id="57d0c-108">たとえば、`Integer` 要素の配列は `Integer` データ型ではありません。</span><span class="sxs-lookup"><span data-stu-id="57d0c-108">For example, an array of `Integer` elements is not of the `Integer` data type.</span></span>  
  
 <span data-ttu-id="57d0c-109">通常、配列のデータ型は、必要に応じて、要素の型、かっこ、およびコンマを使用して表されます。</span><span class="sxs-lookup"><span data-stu-id="57d0c-109">An array data type is normally represented using the element type, parentheses, and commas as necessary.</span></span> <span data-ttu-id="57d0c-110">たとえば、`String` 要素の 1 次元配列は `String()` と表され、`Boolean` 要素の 2 次元配列は `Boolean(,)` と表されます。</span><span class="sxs-lookup"><span data-stu-id="57d0c-110">For example, a one-dimensional array of `String` elements is represented as `String()`, and a two-dimensional array of `Boolean` elements is represented as `Boolean(,)`.</span></span>  
  
## <a name="structure-types"></a><span data-ttu-id="57d0c-111">構造体型</span><span class="sxs-lookup"><span data-stu-id="57d0c-111">Structure Types</span></span>  

 <span data-ttu-id="57d0c-112">すべての構造体に対応する 1 つのデータ型はありません。</span><span class="sxs-lookup"><span data-stu-id="57d0c-112">There is no single data type comprising all structures.</span></span> <span data-ttu-id="57d0c-113">2 つの構造体で同じ要素が同じ順序で定義されている場合でも、構造体のそれぞれの定義は一意のデータ型を表します。</span><span class="sxs-lookup"><span data-stu-id="57d0c-113">Instead, each definition of a structure represents a unique data type, even if two structures define identical elements in the same order.</span></span> <span data-ttu-id="57d0c-114">ただし、同じ構造体の複数のインスタンスを作成した場合、Visual Basic では、それらが同じデータ型と見なされます。</span><span class="sxs-lookup"><span data-stu-id="57d0c-114">However, if you create two or more instances of the same structure, Visual Basic considers them to be of the same data type.</span></span>  
  
## <a name="tuples"></a><span data-ttu-id="57d0c-115">タプル</span><span class="sxs-lookup"><span data-stu-id="57d0c-115">Tuples</span></span>

<span data-ttu-id="57d0c-116">タプルは、型が事前定義された複数のフィールドを含む軽量の構造体です。</span><span class="sxs-lookup"><span data-stu-id="57d0c-116">A tuple is a lightweight structure that contains two or more fields whose types are predefined.</span></span> <span data-ttu-id="57d0c-117">タプルは Visual Basic 2017 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="57d0c-117">Tuples are supported starting with Visual Basic 2017.</span></span> <span data-ttu-id="57d0c-118">タプルは、1 回のメソッド呼び出しで複数の値を返す際に最もよく使用されます。参照によって引数を渡したり、返されたフィールドをより重いクラスまたは構造体にパッケージ化したりする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="57d0c-118">Tuples are most commonly used to return multiple values from a single method call without having to pass arguments by reference or packaging the returned fields in a more heavy-weight class or structure.</span></span> <span data-ttu-id="57d0c-119">タプルの詳細については、「[タプル](tuples.md)」のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="57d0c-119">See the [Tuples](tuples.md) topic for more information on tuples.</span></span>

## <a name="array-types"></a><span data-ttu-id="57d0c-120">配列型</span><span class="sxs-lookup"><span data-stu-id="57d0c-120">Array Types</span></span>  

 <span data-ttu-id="57d0c-121">すべての配列に対応する 1 つのデータ型はありません。</span><span class="sxs-lookup"><span data-stu-id="57d0c-121">There is no single data type comprising all arrays.</span></span> <span data-ttu-id="57d0c-122">配列の特定のインスタンスのデータ型は、次によって決まります。</span><span class="sxs-lookup"><span data-stu-id="57d0c-122">The data type of a particular instance of an array is determined by the following:</span></span>  
  
- <span data-ttu-id="57d0c-123">配列であるという事実</span><span class="sxs-lookup"><span data-stu-id="57d0c-123">The fact of being an array</span></span>  
  
- <span data-ttu-id="57d0c-124">配列のランク (次元数)</span><span class="sxs-lookup"><span data-stu-id="57d0c-124">The rank (number of dimensions) of the array</span></span>  
  
- <span data-ttu-id="57d0c-125">配列の要素型</span><span class="sxs-lookup"><span data-stu-id="57d0c-125">The element type of the array</span></span>  
  
 <span data-ttu-id="57d0c-126">特に、所定のディメンションの長さは、インスタンスのデータ型には含まれません。</span><span class="sxs-lookup"><span data-stu-id="57d0c-126">In particular, the length of a given dimension is not part of the instance's data type.</span></span> <span data-ttu-id="57d0c-127">次の例を使って説明します。</span><span class="sxs-lookup"><span data-stu-id="57d0c-127">The following example illustrates this.</span></span>  
  
```vb  
Dim arrayA( ) As Byte = New Byte(12) {}  
Dim arrayB( ) As Byte = New Byte(100) {}  
Dim arrayC( ) As Short = New Short(100) {}  
Dim arrayD( , ) As Short  
Dim arrayE( , ) As Short = New Short(4, 10) {}  
```  
  
 <span data-ttu-id="57d0c-128">前の例で、配列変数 `arrayA` および `arrayB` は、別の長さに初期化されていますが、同じデータ型 (`Byte()`) と見なされます。</span><span class="sxs-lookup"><span data-stu-id="57d0c-128">In the preceding example, array variables `arrayA` and `arrayB` are considered to be of the same data type — `Byte()` — even though they are initialized to different lengths.</span></span> <span data-ttu-id="57d0c-129">変数 `arrayB` および `arrayC` は、要素の型が異なるため、同じ型ではありません。</span><span class="sxs-lookup"><span data-stu-id="57d0c-129">Variables `arrayB` and `arrayC` are not of the same type because their element types are different.</span></span> <span data-ttu-id="57d0c-130">変数 `arrayC` および `arrayD` は、ランクが異なるため、同じ型ではありません。</span><span class="sxs-lookup"><span data-stu-id="57d0c-130">Variables `arrayC` and `arrayD` are not of the same type because their ranks are different.</span></span> <span data-ttu-id="57d0c-131">変数 `arrayD` および `arrayE` は、ランクと要素の型が同じであるため同じ型 (`Short(,)`) です。ただし、`arrayD` はまだ初期化されていません。</span><span class="sxs-lookup"><span data-stu-id="57d0c-131">Variables `arrayD` and `arrayE` have the same type — `Short(,)` — because their ranks and element types are the same, even though `arrayD` is not yet initialized.</span></span>  
  
 <span data-ttu-id="57d0c-132">配列の詳細については、「[配列](../arrays/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="57d0c-132">For more information on arrays, see [Arrays](../arrays/index.md).</span></span>  
  
## <a name="class-types"></a><span data-ttu-id="57d0c-133">クラスの種類</span><span class="sxs-lookup"><span data-stu-id="57d0c-133">Class Types</span></span>  

 <span data-ttu-id="57d0c-134">すべてのクラスに対応する 1 つのデータ型はありません。</span><span class="sxs-lookup"><span data-stu-id="57d0c-134">There is no single data type comprising all classes.</span></span> <span data-ttu-id="57d0c-135">1 つのクラスは別のクラスを継承できますが、それぞれは個別のデータ型です。</span><span class="sxs-lookup"><span data-stu-id="57d0c-135">Although one class can inherit from another class, each is a separate data type.</span></span> <span data-ttu-id="57d0c-136">同じクラスの複数のインスタンスは同じデータ型です。</span><span class="sxs-lookup"><span data-stu-id="57d0c-136">Multiple instances of the same class are of the same data type.</span></span> <span data-ttu-id="57d0c-137">あるクラス インスタンス変数を別のクラス インスタンス変数に代入すると、データ型が同じになるだけでなく、メモリ内の同じクラス インスタンスを参照します。</span><span class="sxs-lookup"><span data-stu-id="57d0c-137">If you assign one class instance variable to another, not only do they have the same data type, they point to the same class instance in memory.</span></span>  
  
 <span data-ttu-id="57d0c-138">クラスの詳細については、[オブジェクトとクラス](../objects-and-classes/index.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="57d0c-138">For more information on classes, see [Objects and Classes](../objects-and-classes/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57d0c-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="57d0c-139">See also</span></span>

- [<span data-ttu-id="57d0c-140">データの種類</span><span class="sxs-lookup"><span data-stu-id="57d0c-140">Data Types</span></span>](index.md)
- [<span data-ttu-id="57d0c-141">基本データ型</span><span class="sxs-lookup"><span data-stu-id="57d0c-141">Elementary Data Types</span></span>](elementary-data-types.md)
- [<span data-ttu-id="57d0c-142">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="57d0c-142">Generic Types in Visual Basic</span></span>](generic-types.md)
- [<span data-ttu-id="57d0c-143">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="57d0c-143">Value Types and Reference Types</span></span>](value-types-and-reference-types.md)
- [<span data-ttu-id="57d0c-144">Visual Basic における型変換</span><span class="sxs-lookup"><span data-stu-id="57d0c-144">Type Conversions in Visual Basic</span></span>](type-conversions.md)
- [<span data-ttu-id="57d0c-145">構造体</span><span class="sxs-lookup"><span data-stu-id="57d0c-145">Structures</span></span>](structures.md)
- [<span data-ttu-id="57d0c-146">トラブルシューティング (データ型)</span><span class="sxs-lookup"><span data-stu-id="57d0c-146">Troubleshooting Data Types</span></span>](troubleshooting-data-types.md)
- [<span data-ttu-id="57d0c-147">方法: 変数内で複数の値を保持する</span><span class="sxs-lookup"><span data-stu-id="57d0c-147">How to: Hold More Than One Value in a Variable</span></span>](how-to-hold-more-than-one-value-in-a-variable.md)
