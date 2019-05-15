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
ms.openlocfilehash: 541fe9f176a6210372b58753254692142f086992
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2019
ms.locfileid: "65589824"
---
# <a name="value-types-and-reference-types"></a><span data-ttu-id="8128e-102">値型と参照型</span><span class="sxs-lookup"><span data-stu-id="8128e-102">Value Types and Reference Types</span></span>
<span data-ttu-id="8128e-103">Visual basic でのデータ型は、分類に基づいて実装されます。</span><span class="sxs-lookup"><span data-stu-id="8128e-103">In Visual Basic, data types are implemented based on their classification.</span></span> <span data-ttu-id="8128e-104">Visual Basic のデータ型は、特定の型の変数が独自のデータまたはデータへのポインターを格納するかどうかに基づいて分類できます。</span><span class="sxs-lookup"><span data-stu-id="8128e-104">The Visual Basic data types can be classified according to whether a variable of a particular type stores its own data or a pointer to the data.</span></span> <span data-ttu-id="8128e-105">独自のデータを格納する場合は、*値の型*別の場所はメモリ内のデータへのポインターを保持する場合、*参照型*。</span><span class="sxs-lookup"><span data-stu-id="8128e-105">If it stores its own data it is a *value type*; if it holds a pointer to data elsewhere in memory it is a *reference type*.</span></span>  
  
## <a name="value-types"></a><span data-ttu-id="8128e-106">値型</span><span class="sxs-lookup"><span data-stu-id="8128e-106">Value Types</span></span>  
 <span data-ttu-id="8128e-107">データ型は、*値の型*独自のメモリ割り当て内のデータを保持している場合。</span><span class="sxs-lookup"><span data-stu-id="8128e-107">A data type is a *value type* if it holds the data within its own memory allocation.</span></span> <span data-ttu-id="8128e-108">値の型を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="8128e-108">Value types include the following:</span></span>  
  
- <span data-ttu-id="8128e-109">すべての数値データ型</span><span class="sxs-lookup"><span data-stu-id="8128e-109">All numeric data types</span></span>  
  
- <span data-ttu-id="8128e-110">`Boolean`、 `Char`、および `Date`</span><span class="sxs-lookup"><span data-stu-id="8128e-110">`Boolean`, `Char`, and `Date`</span></span>  
  
- <span data-ttu-id="8128e-111">そのメンバーが参照型の場合でも、すべての構造</span><span class="sxs-lookup"><span data-stu-id="8128e-111">All structures, even if their members are reference types</span></span>  
  
- <span data-ttu-id="8128e-112">列挙型では、その基になる型は常にため`SByte`、 `Short`、 `Integer`、 `Long`、 `Byte`、 `UShort`、 `UInteger`、または `ULong`</span><span class="sxs-lookup"><span data-stu-id="8128e-112">Enumerations, since their underlying type is always `SByte`, `Short`, `Integer`, `Long`, `Byte`, `UShort`, `UInteger`, or `ULong`</span></span>  
  
 <span data-ttu-id="8128e-113">すべての構造体は参照型のメンバーが含まれている場合でも、値型です。</span><span class="sxs-lookup"><span data-stu-id="8128e-113">Every structure is a value type, even if it contains reference type members.</span></span> <span data-ttu-id="8128e-114">このため、値などの型`Char`と`Integer`.NET Framework の構造体によって実装されます。</span><span class="sxs-lookup"><span data-stu-id="8128e-114">For this reason, value types such as `Char` and `Integer` are implemented by .NET Framework structures.</span></span>  
  
 <span data-ttu-id="8128e-115">たとえば、予約済みキーワードを使用して値の型を宣言する`Decimal`します。</span><span class="sxs-lookup"><span data-stu-id="8128e-115">You can declare a value type by using the reserved keyword, for example, `Decimal`.</span></span> <span data-ttu-id="8128e-116">使用することも、`New`値型を初期化するキーワード。</span><span class="sxs-lookup"><span data-stu-id="8128e-116">You can also use the `New` keyword to initialize a value type.</span></span> <span data-ttu-id="8128e-117">これは、型パラメーターを受け取るコンス トラクターがある場合に特に便利です。</span><span class="sxs-lookup"><span data-stu-id="8128e-117">This is especially useful if the type has a constructor that takes parameters.</span></span> <span data-ttu-id="8128e-118">この例は、<xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29>コンス トラクターは、新しいビルド`Decimal`指定した部分からの値。</span><span class="sxs-lookup"><span data-stu-id="8128e-118">An example of this is the <xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29> constructor, which builds a new `Decimal` value from the supplied parts.</span></span>  
  
## <a name="reference-types"></a><span data-ttu-id="8128e-119">参照型</span><span class="sxs-lookup"><span data-stu-id="8128e-119">Reference Types</span></span>  
 <span data-ttu-id="8128e-120">A*参照型*データを保持する別のメモリ位置へのポインターが含まれています。</span><span class="sxs-lookup"><span data-stu-id="8128e-120">A *reference type* contains a pointer to another memory location that holds the data.</span></span> <span data-ttu-id="8128e-121">参照型を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="8128e-121">Reference types include the following:</span></span>  
  
- `String`  
  
- <span data-ttu-id="8128e-122">その要素が値型の場合でも、すべての配列</span><span class="sxs-lookup"><span data-stu-id="8128e-122">All arrays, even if their elements are value types</span></span>  
  
- <span data-ttu-id="8128e-123">などのクラス型します。 <xref:System.Windows.Forms.Form></span><span class="sxs-lookup"><span data-stu-id="8128e-123">Class types, such as <xref:System.Windows.Forms.Form></span></span>  
  
- <span data-ttu-id="8128e-124">デリゲート</span><span class="sxs-lookup"><span data-stu-id="8128e-124">Delegates</span></span>  
  
 <span data-ttu-id="8128e-125">クラスは、*参照型*します。</span><span class="sxs-lookup"><span data-stu-id="8128e-125">A class is a *reference type*.</span></span> <span data-ttu-id="8128e-126">参照型など、このため、`Object`と`String`は .NET Framework のクラスでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="8128e-126">For this reason, reference types such as `Object` and `String` are supported by .NET Framework classes.</span></span> <span data-ttu-id="8128e-127">場合でも、そのメンバーが値型は、すべての配列が参照型であるに注意してください。</span><span class="sxs-lookup"><span data-stu-id="8128e-127">Note that every array is a reference type, even if its members are value types.</span></span>  
  
 <span data-ttu-id="8128e-128">使用する必要がありますすべての参照型は、基になる .NET Framework クラスを表すため、 [New 演算子](../../../../visual-basic/language-reference/operators/new-operator.md)初期化するときに、キーワード。</span><span class="sxs-lookup"><span data-stu-id="8128e-128">Since every reference type represents an underlying .NET Framework class, you must use the [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md) keyword when you initialize it.</span></span> <span data-ttu-id="8128e-129">次のステートメントでは、配列を初期化します。</span><span class="sxs-lookup"><span data-stu-id="8128e-129">The following statement initializes an array.</span></span>  
  
```  
Dim totals() As Single = New Single(8) {}  
```  
  
## <a name="elements-that-are-not-types"></a><span data-ttu-id="8128e-130">型ではない要素</span><span class="sxs-lookup"><span data-stu-id="8128e-130">Elements That Are Not Types</span></span>  
 <span data-ttu-id="8128e-131">これらのいずれかとして宣言された要素のデータ型を指定できないため、次のプログラミング要素は、型とは見なされません。</span><span class="sxs-lookup"><span data-stu-id="8128e-131">The following programming elements do not qualify as types, because you cannot specify any of them as a data type for a declared element:</span></span>  
  
- <span data-ttu-id="8128e-132">名前空間</span><span class="sxs-lookup"><span data-stu-id="8128e-132">Namespaces</span></span>  
  
- <span data-ttu-id="8128e-133">モジュール</span><span class="sxs-lookup"><span data-stu-id="8128e-133">Modules</span></span>  
  
- <span data-ttu-id="8128e-134">イベント</span><span class="sxs-lookup"><span data-stu-id="8128e-134">Events</span></span>  
  
- <span data-ttu-id="8128e-135">プロパティやプロシージャ</span><span class="sxs-lookup"><span data-stu-id="8128e-135">Properties and procedures</span></span>  
  
- <span data-ttu-id="8128e-136">変数、定数、およびフィールド</span><span class="sxs-lookup"><span data-stu-id="8128e-136">Variables, constants, and fields</span></span>  
  
## <a name="working-with-the-object-data-type"></a><span data-ttu-id="8128e-137">オブジェクトのデータ型の操作</span><span class="sxs-lookup"><span data-stu-id="8128e-137">Working with the Object Data Type</span></span>  
 <span data-ttu-id="8128e-138">変数に参照型または値型のいずれかを割り当てることができます、`Object`データ型。</span><span class="sxs-lookup"><span data-stu-id="8128e-138">You can assign either a reference type or a value type to a variable of the `Object` data type.</span></span> <span data-ttu-id="8128e-139">`Object`変数は常に、データそのものではない、データへのポインターを保持します。</span><span class="sxs-lookup"><span data-stu-id="8128e-139">An `Object` variable always holds a pointer to the data, never the data itself.</span></span> <span data-ttu-id="8128e-140">ただし、値の型を割り当てた場合、`Object`変数、その場合と同様、独自のデータを保持します。</span><span class="sxs-lookup"><span data-stu-id="8128e-140">However, if you assign a value type to an `Object` variable, it behaves as if it holds its own data.</span></span> <span data-ttu-id="8128e-141">詳細については、次を参照してください。 [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md)します。</span><span class="sxs-lookup"><span data-stu-id="8128e-141">For more information, see [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md).</span></span>  
  
 <span data-ttu-id="8128e-142">かどうかを見つけることができます、`Object`に渡すことによって変数が参照型または値型として機能する、<xref:Microsoft.VisualBasic.Information.IsReference%2A>メソッドで、<xref:Microsoft.VisualBasic.Information>のクラス、<xref:Microsoft.VisualBasic?displayProperty=nameWithType>名前空間。</span><span class="sxs-lookup"><span data-stu-id="8128e-142">You can find out whether an `Object` variable is acting as a reference type or a value type by passing it to the <xref:Microsoft.VisualBasic.Information.IsReference%2A> method in the <xref:Microsoft.VisualBasic.Information> class of the <xref:Microsoft.VisualBasic?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="8128e-143"><xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=nameWithType> 返します`True`場合のコンテンツ、`Object`変数は参照型を表します。</span><span class="sxs-lookup"><span data-stu-id="8128e-143"><xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=nameWithType> returns `True` if the content of the `Object` variable represents a reference type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8128e-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="8128e-144">See also</span></span>

- [<span data-ttu-id="8128e-145">null 許容値型</span><span class="sxs-lookup"><span data-stu-id="8128e-145">Nullable Value Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [<span data-ttu-id="8128e-146">Visual Basic における型変換</span><span class="sxs-lookup"><span data-stu-id="8128e-146">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="8128e-147">Structure ステートメント</span><span class="sxs-lookup"><span data-stu-id="8128e-147">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="8128e-148">データ型の有効な使用方法</span><span class="sxs-lookup"><span data-stu-id="8128e-148">Efficient Use of Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [<span data-ttu-id="8128e-149">Object 型</span><span class="sxs-lookup"><span data-stu-id="8128e-149">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="8128e-150">データの種類</span><span class="sxs-lookup"><span data-stu-id="8128e-150">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
