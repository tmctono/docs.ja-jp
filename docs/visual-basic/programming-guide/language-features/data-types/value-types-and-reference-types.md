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
ms.openlocfilehash: 466bb5386235917705344d35c5141c8bf779218d
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582642"
---
# <a name="value-types-and-reference-types"></a><span data-ttu-id="37271-102">値型と参照型</span><span class="sxs-lookup"><span data-stu-id="37271-102">Value Types and Reference Types</span></span>
<span data-ttu-id="37271-103">Visual Basic には、参照型と値型という2種類の型があります。</span><span class="sxs-lookup"><span data-stu-id="37271-103">There are two kinds of types in Visual Basic: reference types and value types.</span></span> <span data-ttu-id="37271-104">参照型の変数はデータ (オブジェクト) への参照を格納するのに対して、値型の変数はデータを直接格納します。</span><span class="sxs-lookup"><span data-stu-id="37271-104">Variables of reference types store references to their data (objects), while variables of value types directly contain their data.</span></span> <span data-ttu-id="37271-105">参照型の場合、2 つの変数が同じオブジェクトを参照できるため、ある変数に対する演算によって、他の変数が参照しているオブジェクトが影響を受ける可能性があります。</span><span class="sxs-lookup"><span data-stu-id="37271-105">With reference types, two variables can reference the same object; therefore, operations on one variable can affect the object referenced by the other variable.</span></span> <span data-ttu-id="37271-106">値型の場合、各変数にはデータの独自のコピーがあり、一方の変数に対する操作がもう一方の変数に影響を与えることはできません ([パラメーターの ByRef 修飾子](../../../language-reference/modifiers/byref.md)の場合を除く)。</span><span class="sxs-lookup"><span data-stu-id="37271-106">With value types, each variable has its own copy of the data, and it is not possible for operations on one variable to affect the other (except in the case of the [ByRef modifier on parameters](../../../language-reference/modifiers/byref.md)).</span></span>
  
## <a name="value-types"></a><span data-ttu-id="37271-107">値型</span><span class="sxs-lookup"><span data-stu-id="37271-107">Value Types</span></span>  
 <span data-ttu-id="37271-108">データ型は、独自のメモリ割り当て内にデータを保持する場合は*値型*です。</span><span class="sxs-lookup"><span data-stu-id="37271-108">A data type is a *value type* if it holds the data within its own memory allocation.</span></span> <span data-ttu-id="37271-109">値の種類は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="37271-109">Value types include the following:</span></span>  
  
- <span data-ttu-id="37271-110">すべての数値データ型</span><span class="sxs-lookup"><span data-stu-id="37271-110">All numeric data types</span></span>  
  
- <span data-ttu-id="37271-111">`Boolean`、`Char`、および `Date`</span><span class="sxs-lookup"><span data-stu-id="37271-111">`Boolean`, `Char`, and `Date`</span></span>  
  
- <span data-ttu-id="37271-112">メンバーが参照型の場合でも、すべての構造体</span><span class="sxs-lookup"><span data-stu-id="37271-112">All structures, even if their members are reference types</span></span>  
  
- <span data-ttu-id="37271-113">列挙型。基になる型は常に `SByte`、`Short`、`Integer`、`Long`、`Byte`、`UShort`、`UInteger`、または `ULong`</span><span class="sxs-lookup"><span data-stu-id="37271-113">Enumerations, since their underlying type is always `SByte`, `Short`, `Integer`, `Long`, `Byte`, `UShort`, `UInteger`, or `ULong`</span></span>  
  
 <span data-ttu-id="37271-114">すべての構造体は、参照型のメンバーが含まれている場合でも、値型です。</span><span class="sxs-lookup"><span data-stu-id="37271-114">Every structure is a value type, even if it contains reference type members.</span></span> <span data-ttu-id="37271-115">このため、`Char` や `Integer` などの値型は .NET Framework 構造体によって実装されます。</span><span class="sxs-lookup"><span data-stu-id="37271-115">For this reason, value types such as `Char` and `Integer` are implemented by .NET Framework structures.</span></span>  
  
 <span data-ttu-id="37271-116">予約済みのキーワードを使用して値型を宣言できます (`Decimal` など)。</span><span class="sxs-lookup"><span data-stu-id="37271-116">You can declare a value type by using the reserved keyword, for example, `Decimal`.</span></span> <span data-ttu-id="37271-117">@No__t_0 キーワードを使用して値型を初期化することもできます。</span><span class="sxs-lookup"><span data-stu-id="37271-117">You can also use the `New` keyword to initialize a value type.</span></span> <span data-ttu-id="37271-118">これは、型にパラメーターを受け取るコンストラクターがある場合に特に便利です。</span><span class="sxs-lookup"><span data-stu-id="37271-118">This is especially useful if the type has a constructor that takes parameters.</span></span> <span data-ttu-id="37271-119">この例として、<xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29> コンストラクターがあります。このコンストラクターは、指定されたパーツから新しい `Decimal` 値を構築します。</span><span class="sxs-lookup"><span data-stu-id="37271-119">An example of this is the <xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29> constructor, which builds a new `Decimal` value from the supplied parts.</span></span>  
  
## <a name="reference-types"></a><span data-ttu-id="37271-120">参照型</span><span class="sxs-lookup"><span data-stu-id="37271-120">Reference Types</span></span>  
 <span data-ttu-id="37271-121">*参照型*は、そのデータへの参照を格納します。</span><span class="sxs-lookup"><span data-stu-id="37271-121">A *reference type* stores a reference to its data.</span></span> <span data-ttu-id="37271-122">参照型には、次のものがあります。</span><span class="sxs-lookup"><span data-stu-id="37271-122">Reference types include the following:</span></span>  
  
- `String`  
  
- <span data-ttu-id="37271-123">すべての配列 (要素が値型の場合でも)</span><span class="sxs-lookup"><span data-stu-id="37271-123">All arrays, even if their elements are value types</span></span>  
  
- <span data-ttu-id="37271-124">クラスの型 (<xref:System.Windows.Forms.Form> など)</span><span class="sxs-lookup"><span data-stu-id="37271-124">Class types, such as <xref:System.Windows.Forms.Form></span></span>  
  
- <span data-ttu-id="37271-125">デリゲート</span><span class="sxs-lookup"><span data-stu-id="37271-125">Delegates</span></span>  
  
 <span data-ttu-id="37271-126">クラスは*参照型*です。</span><span class="sxs-lookup"><span data-stu-id="37271-126">A class is a *reference type*.</span></span> <span data-ttu-id="37271-127">すべての配列が参照型であることに注意してください。これは、そのメンバーが値型の場合でも同様です。</span><span class="sxs-lookup"><span data-stu-id="37271-127">Note that every array is a reference type, even if its members are value types.</span></span>  
  
 <span data-ttu-id="37271-128">参照型はすべて、基になる .NET Framework クラスを表しているため、初期化時に [New 演算子](../../../../visual-basic/language-reference/operators/new-operator.md)キーワードを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="37271-128">Since every reference type represents an underlying .NET Framework class, you must use the [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md) keyword when you initialize it.</span></span> <span data-ttu-id="37271-129">次のステートメントは、配列を初期化します。</span><span class="sxs-lookup"><span data-stu-id="37271-129">The following statement initializes an array.</span></span>  
  
```vb  
Dim totals() As Single = New Single(8) {}  
```  
  
## <a name="elements-that-are-not-types"></a><span data-ttu-id="37271-130">型ではない要素</span><span class="sxs-lookup"><span data-stu-id="37271-130">Elements That Are Not Types</span></span>  
 <span data-ttu-id="37271-131">次のプログラミング要素は、宣言された要素のデータ型として指定できないため、型としては使用できません。</span><span class="sxs-lookup"><span data-stu-id="37271-131">The following programming elements do not qualify as types, because you cannot specify any of them as a data type for a declared element:</span></span>  
  
- <span data-ttu-id="37271-132">名前空間</span><span class="sxs-lookup"><span data-stu-id="37271-132">Namespaces</span></span>  
  
- <span data-ttu-id="37271-133">モジュール</span><span class="sxs-lookup"><span data-stu-id="37271-133">Modules</span></span>  
  
- <span data-ttu-id="37271-134">イベント</span><span class="sxs-lookup"><span data-stu-id="37271-134">Events</span></span>  
  
- <span data-ttu-id="37271-135">プロパティとプロシージャ</span><span class="sxs-lookup"><span data-stu-id="37271-135">Properties and procedures</span></span>  
  
- <span data-ttu-id="37271-136">変数、定数、およびフィールド</span><span class="sxs-lookup"><span data-stu-id="37271-136">Variables, constants, and fields</span></span>  
  
## <a name="working-with-the-object-data-type"></a><span data-ttu-id="37271-137">オブジェクトのデータ型の操作</span><span class="sxs-lookup"><span data-stu-id="37271-137">Working with the Object Data Type</span></span>  
 <span data-ttu-id="37271-138">@No__t_0 データ型の変数には、参照型または値型のいずれかを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="37271-138">You can assign either a reference type or a value type to a variable of the `Object` data type.</span></span> <span data-ttu-id="37271-139">@No__t_0 変数は、データ自体ではなく、常にデータへの参照を保持します。</span><span class="sxs-lookup"><span data-stu-id="37271-139">An `Object` variable always holds a reference to the data, never the data itself.</span></span> <span data-ttu-id="37271-140">ただし、`Object` 変数に値型を割り当てた場合は、それが独自のデータを保持しているかのように動作します。</span><span class="sxs-lookup"><span data-stu-id="37271-140">However, if you assign a value type to an `Object` variable, it behaves as if it holds its own data.</span></span> <span data-ttu-id="37271-141">詳細については、「 [Object データ型](../../../../visual-basic/language-reference/data-types/object-data-type.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37271-141">For more information, see [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md).</span></span>  
  
 <span data-ttu-id="37271-142">@No__t_0 変数が参照型または値型として機能しているかどうかを確認するには、<xref:Microsoft.VisualBasic?displayProperty=nameWithType> 名前空間の <xref:Microsoft.VisualBasic.Information> クラスの <xref:Microsoft.VisualBasic.Information.IsReference%2A> メソッドに渡します。</span><span class="sxs-lookup"><span data-stu-id="37271-142">You can find out whether an `Object` variable is acting as a reference type or a value type by passing it to the <xref:Microsoft.VisualBasic.Information.IsReference%2A> method in the <xref:Microsoft.VisualBasic.Information> class of the <xref:Microsoft.VisualBasic?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="37271-143">`Object` 変数の内容が参照型を表している場合、<xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=nameWithType> は `True` を返します。</span><span class="sxs-lookup"><span data-stu-id="37271-143"><xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=nameWithType> returns `True` if the content of the `Object` variable represents a reference type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37271-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="37271-144">See also</span></span>

- [<span data-ttu-id="37271-145">null 許容値型</span><span class="sxs-lookup"><span data-stu-id="37271-145">Nullable Value Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [<span data-ttu-id="37271-146">Visual Basic での型変換</span><span class="sxs-lookup"><span data-stu-id="37271-146">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="37271-147">Structure ステートメント</span><span class="sxs-lookup"><span data-stu-id="37271-147">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="37271-148">データ型の有効な使用方法</span><span class="sxs-lookup"><span data-stu-id="37271-148">Efficient Use of Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [<span data-ttu-id="37271-149">Object データ型</span><span class="sxs-lookup"><span data-stu-id="37271-149">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="37271-150">データの種類</span><span class="sxs-lookup"><span data-stu-id="37271-150">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
