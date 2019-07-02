---
title: 値型と参照型
ms.date: 07/20/2015
helpviewer_keywords:
- reference data types [Visual Basic]
- reference types [Visual Basic]
- value types [Visual Basic]
- value data types [Visual Basic]
- types [Visual Basic]
- data types [Visual Basic], value types
- data types [Visual Basic], reference types
ms.assetid: fc82ce15-5a40-4c5c-a1e1-a556830e7391
ms.openlocfilehash: f25caec43b7118b7b64db1b14516b0c5ea80f4f6
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2019
ms.locfileid: "67504882"
---
# <a name="value-types-and-reference-types"></a><span data-ttu-id="99688-102">値型と参照型</span><span class="sxs-lookup"><span data-stu-id="99688-102">Value Types and Reference Types</span></span>
<span data-ttu-id="99688-103">Visual Basic における型の 2 種類があります。 参照型と値の型。</span><span class="sxs-lookup"><span data-stu-id="99688-103">There are two kinds of types in Visual Basic: reference types and value types.</span></span> <span data-ttu-id="99688-104">参照型の変数はデータ (オブジェクト) への参照を格納するのに対して、値型の変数はデータを直接格納します。</span><span class="sxs-lookup"><span data-stu-id="99688-104">Variables of reference types store references to their data (objects), while variables of value types directly contain their data.</span></span> <span data-ttu-id="99688-105">参照型の場合、2 つの変数が同じオブジェクトを参照できるため、ある変数に対する演算によって、他の変数が参照しているオブジェクトが影響を受ける可能性があります。</span><span class="sxs-lookup"><span data-stu-id="99688-105">With reference types, two variables can reference the same object; therefore, operations on one variable can affect the object referenced by the other variable.</span></span> <span data-ttu-id="99688-106">各変数が独自のデータのコピーを値型の場合とに影響を与えるもう 1 つの変数に対する操作のことはできません (の場合を除く、 [ByRef パラメーター修飾子](../../../language-reference/modifiers/byref.md))。</span><span class="sxs-lookup"><span data-stu-id="99688-106">With value types, each variable has its own copy of the data, and it is not possible for operations on one variable to affect the other (except in the case of the [ByRef modifier on parameters](../../../language-reference/modifiers/byref.md)).</span></span>
  
## <a name="value-types"></a><span data-ttu-id="99688-107">値型</span><span class="sxs-lookup"><span data-stu-id="99688-107">Value Types</span></span>  
 <span data-ttu-id="99688-108">データ型は、*値の型*独自のメモリ割り当て内のデータを保持している場合。</span><span class="sxs-lookup"><span data-stu-id="99688-108">A data type is a *value type* if it holds the data within its own memory allocation.</span></span> <span data-ttu-id="99688-109">値の型を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="99688-109">Value types include the following:</span></span>  
  
- <span data-ttu-id="99688-110">すべての数値データ型</span><span class="sxs-lookup"><span data-stu-id="99688-110">All numeric data types</span></span>  
  
- <span data-ttu-id="99688-111">`Boolean`、 `Char`、および `Date`</span><span class="sxs-lookup"><span data-stu-id="99688-111">`Boolean`, `Char`, and `Date`</span></span>  
  
- <span data-ttu-id="99688-112">そのメンバーが参照型の場合でも、すべての構造</span><span class="sxs-lookup"><span data-stu-id="99688-112">All structures, even if their members are reference types</span></span>  
  
- <span data-ttu-id="99688-113">列挙型では、その基になる型は常にため`SByte`、 `Short`、 `Integer`、 `Long`、 `Byte`、 `UShort`、 `UInteger`、または `ULong`</span><span class="sxs-lookup"><span data-stu-id="99688-113">Enumerations, since their underlying type is always `SByte`, `Short`, `Integer`, `Long`, `Byte`, `UShort`, `UInteger`, or `ULong`</span></span>  
  
 <span data-ttu-id="99688-114">すべての構造体は参照型のメンバーが含まれている場合でも、値型です。</span><span class="sxs-lookup"><span data-stu-id="99688-114">Every structure is a value type, even if it contains reference type members.</span></span> <span data-ttu-id="99688-115">このため、値などの型`Char`と`Integer`.NET Framework の構造体によって実装されます。</span><span class="sxs-lookup"><span data-stu-id="99688-115">For this reason, value types such as `Char` and `Integer` are implemented by .NET Framework structures.</span></span>  
  
 <span data-ttu-id="99688-116">たとえば、予約済みキーワードを使用して値の型を宣言する`Decimal`します。</span><span class="sxs-lookup"><span data-stu-id="99688-116">You can declare a value type by using the reserved keyword, for example, `Decimal`.</span></span> <span data-ttu-id="99688-117">使用することも、`New`値型を初期化するキーワード。</span><span class="sxs-lookup"><span data-stu-id="99688-117">You can also use the `New` keyword to initialize a value type.</span></span> <span data-ttu-id="99688-118">これは、型パラメーターを受け取るコンス トラクターがある場合に特に便利です。</span><span class="sxs-lookup"><span data-stu-id="99688-118">This is especially useful if the type has a constructor that takes parameters.</span></span> <span data-ttu-id="99688-119">この例は、<xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29>コンス トラクターは、新しいビルド`Decimal`指定した部分からの値。</span><span class="sxs-lookup"><span data-stu-id="99688-119">An example of this is the <xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29> constructor, which builds a new `Decimal` value from the supplied parts.</span></span>  
  
## <a name="reference-types"></a><span data-ttu-id="99688-120">参照型</span><span class="sxs-lookup"><span data-stu-id="99688-120">Reference Types</span></span>  
 <span data-ttu-id="99688-121">A*参照型*データへの参照を格納します。</span><span class="sxs-lookup"><span data-stu-id="99688-121">A *reference type* stores a reference to its data.</span></span> <span data-ttu-id="99688-122">参照型を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="99688-122">Reference types include the following:</span></span>  
  
- `String`  
  
- <span data-ttu-id="99688-123">その要素が値型の場合でも、すべての配列</span><span class="sxs-lookup"><span data-stu-id="99688-123">All arrays, even if their elements are value types</span></span>  
  
- <span data-ttu-id="99688-124">などのクラス型します。 <xref:System.Windows.Forms.Form></span><span class="sxs-lookup"><span data-stu-id="99688-124">Class types, such as <xref:System.Windows.Forms.Form></span></span>  
  
- <span data-ttu-id="99688-125">デリゲート</span><span class="sxs-lookup"><span data-stu-id="99688-125">Delegates</span></span>  
  
 <span data-ttu-id="99688-126">クラスは、*参照型*します。</span><span class="sxs-lookup"><span data-stu-id="99688-126">A class is a *reference type*.</span></span> <span data-ttu-id="99688-127">場合でも、そのメンバーが値型は、すべての配列が参照型であるに注意してください。</span><span class="sxs-lookup"><span data-stu-id="99688-127">Note that every array is a reference type, even if its members are value types.</span></span>  
  
 <span data-ttu-id="99688-128">使用する必要がありますすべての参照型は、基になる .NET Framework クラスを表すため、 [New 演算子](../../../../visual-basic/language-reference/operators/new-operator.md)初期化するときに、キーワード。</span><span class="sxs-lookup"><span data-stu-id="99688-128">Since every reference type represents an underlying .NET Framework class, you must use the [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md) keyword when you initialize it.</span></span> <span data-ttu-id="99688-129">次のステートメントでは、配列を初期化します。</span><span class="sxs-lookup"><span data-stu-id="99688-129">The following statement initializes an array.</span></span>  
  
```  
Dim totals() As Single = New Single(8) {}  
```  
  
## <a name="elements-that-are-not-types"></a><span data-ttu-id="99688-130">型ではない要素</span><span class="sxs-lookup"><span data-stu-id="99688-130">Elements That Are Not Types</span></span>  
 <span data-ttu-id="99688-131">これらのいずれかとして宣言された要素のデータ型を指定できないため、次のプログラミング要素は、型とは見なされません。</span><span class="sxs-lookup"><span data-stu-id="99688-131">The following programming elements do not qualify as types, because you cannot specify any of them as a data type for a declared element:</span></span>  
  
- <span data-ttu-id="99688-132">名前空間</span><span class="sxs-lookup"><span data-stu-id="99688-132">Namespaces</span></span>  
  
- <span data-ttu-id="99688-133">モジュール</span><span class="sxs-lookup"><span data-stu-id="99688-133">Modules</span></span>  
  
- <span data-ttu-id="99688-134">イベント</span><span class="sxs-lookup"><span data-stu-id="99688-134">Events</span></span>  
  
- <span data-ttu-id="99688-135">プロパティやプロシージャ</span><span class="sxs-lookup"><span data-stu-id="99688-135">Properties and procedures</span></span>  
  
- <span data-ttu-id="99688-136">変数、定数、およびフィールド</span><span class="sxs-lookup"><span data-stu-id="99688-136">Variables, constants, and fields</span></span>  
  
## <a name="working-with-the-object-data-type"></a><span data-ttu-id="99688-137">オブジェクトのデータ型の操作</span><span class="sxs-lookup"><span data-stu-id="99688-137">Working with the Object Data Type</span></span>  
 <span data-ttu-id="99688-138">変数に参照型または値型のいずれかを割り当てることができます、`Object`データ型。</span><span class="sxs-lookup"><span data-stu-id="99688-138">You can assign either a reference type or a value type to a variable of the `Object` data type.</span></span> <span data-ttu-id="99688-139">`Object`変数は常に、データ自体ではない、データへの参照を保持します。</span><span class="sxs-lookup"><span data-stu-id="99688-139">An `Object` variable always holds a reference to the data, never the data itself.</span></span> <span data-ttu-id="99688-140">ただし、値の型を割り当てた場合、`Object`変数、その場合と同様、独自のデータを保持します。</span><span class="sxs-lookup"><span data-stu-id="99688-140">However, if you assign a value type to an `Object` variable, it behaves as if it holds its own data.</span></span> <span data-ttu-id="99688-141">詳細については、次を参照してください。 [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md)します。</span><span class="sxs-lookup"><span data-stu-id="99688-141">For more information, see [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md).</span></span>  
  
 <span data-ttu-id="99688-142">かどうかを見つけることができます、`Object`に渡すことによって変数が参照型または値型として機能する、<xref:Microsoft.VisualBasic.Information.IsReference%2A>メソッドで、<xref:Microsoft.VisualBasic.Information>のクラス、<xref:Microsoft.VisualBasic?displayProperty=nameWithType>名前空間。</span><span class="sxs-lookup"><span data-stu-id="99688-142">You can find out whether an `Object` variable is acting as a reference type or a value type by passing it to the <xref:Microsoft.VisualBasic.Information.IsReference%2A> method in the <xref:Microsoft.VisualBasic.Information> class of the <xref:Microsoft.VisualBasic?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="99688-143"><xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=nameWithType> 返します`True`場合のコンテンツ、`Object`変数は参照型を表します。</span><span class="sxs-lookup"><span data-stu-id="99688-143"><xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=nameWithType> returns `True` if the content of the `Object` variable represents a reference type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99688-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="99688-144">See also</span></span>

- [<span data-ttu-id="99688-145">null 許容値型</span><span class="sxs-lookup"><span data-stu-id="99688-145">Nullable Value Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [<span data-ttu-id="99688-146">Visual Basic における型変換</span><span class="sxs-lookup"><span data-stu-id="99688-146">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="99688-147">Structure ステートメント</span><span class="sxs-lookup"><span data-stu-id="99688-147">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="99688-148">データ型の有効な使用方法</span><span class="sxs-lookup"><span data-stu-id="99688-148">Efficient Use of Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [<span data-ttu-id="99688-149">Object 型</span><span class="sxs-lookup"><span data-stu-id="99688-149">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="99688-150">データの種類</span><span class="sxs-lookup"><span data-stu-id="99688-150">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
