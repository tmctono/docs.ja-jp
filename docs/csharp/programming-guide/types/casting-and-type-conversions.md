---
title: キャストと型変換 - C# プログラミング ガイド
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- type conversion [C#]
- data type conversion [C#]
- numeric conversions [C#]
- conversions [C#], type
- casting [C#]
- converting types [C#]
ms.assetid: 568df58a-d292-4b55-93ba-601578722878
ms.openlocfilehash: 19b4ec08cc8790df0e9a99204c0401b1b873eb20
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2019
ms.locfileid: "69588425"
---
# <a name="casting-and-type-conversions-c-programming-guide"></a><span data-ttu-id="a650c-102">キャストと型変換 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="a650c-102">Casting and type conversions (C# Programming Guide)</span></span>

<span data-ttu-id="a650c-103">C# はコンパイル時 (変数が宣言された後) に静的に型指定されるため、その型が変数の型に暗黙的に変換可能でない限り、再び宣言したり、別の型の値を代入したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="a650c-103">Because C# is statically-typed at compile time, after a variable is declared, it cannot be declared again or assigned a value of another type unless that type is implicitly convertible to the variable's type.</span></span> <span data-ttu-id="a650c-104">たとえば、`string` を `int` に暗黙的に変換することはできません。</span><span class="sxs-lookup"><span data-stu-id="a650c-104">For example, the `string` cannot be implicitly converted to `int`.</span></span> <span data-ttu-id="a650c-105">そのため、次のコードに示すように、`i` を `int` として宣言した後、"Hello" という文字列を代入することはできません。</span><span class="sxs-lookup"><span data-stu-id="a650c-105">Therefore, after you declare `i` as an `int`, you cannot assign the string "Hello" to it, as the following code shows:</span></span>
  
```csharp  
int i;  
i = "Hello"; // error CS0029: Cannot implicitly convert type 'string' to 'int'
```  
  
 <span data-ttu-id="a650c-106">しかし場合によっては、別の型の変数やメソッドのパラメーターに値をコピーする必要が生じることもあります。</span><span class="sxs-lookup"><span data-stu-id="a650c-106">However, you might sometimes need to copy a value into a variable or method parameter of another type.</span></span> <span data-ttu-id="a650c-107">たとえば、パラメーターが `double` として型指定されたメソッドに、整数の変数を渡す必要が生じることもあるでしょう。</span><span class="sxs-lookup"><span data-stu-id="a650c-107">For example, you might have an integer variable that you need to pass to a method whose parameter is typed as `double`.</span></span> <span data-ttu-id="a650c-108">また、クラス変数をインターフェイス型の変数に代入しなければならない場合もあるかもしれません。</span><span class="sxs-lookup"><span data-stu-id="a650c-108">Or you might need to assign a class variable to a variable of an interface type.</span></span> <span data-ttu-id="a650c-109">この種の操作は、*型変換*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="a650c-109">These kinds of operations are called *type conversions*.</span></span> <span data-ttu-id="a650c-110">C# では、次のような変換を実行できます。</span><span class="sxs-lookup"><span data-stu-id="a650c-110">In C#, you can perform the following kinds of conversions:</span></span>  
  
- <span data-ttu-id="a650c-111">**暗黙的な変換**: この変換はタイプ セーフであり、データが失われることはないため、特別な構文は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="a650c-111">**Implicit conversions**: No special syntax is required because the conversion is type safe and no data will be lost.</span></span> <span data-ttu-id="a650c-112">例としては、小さい整数型から大きい整数型への変換や、派生クラスから基底クラスへの変換が挙げられます。</span><span class="sxs-lookup"><span data-stu-id="a650c-112">Examples include conversions from smaller to larger integral types, and conversions from derived classes to base classes.</span></span>  
  
- <span data-ttu-id="a650c-113">**明示的な変換 (キャスト)** : 明示的な変換には、キャスト演算子が必要です。</span><span class="sxs-lookup"><span data-stu-id="a650c-113">**Explicit conversions (casts)**: Explicit conversions require a cast operator.</span></span> <span data-ttu-id="a650c-114">変換時に情報が失われる可能性がある場合や、その他の理由によって変換が成功しない可能性がある場合には、キャストが必要です。</span><span class="sxs-lookup"><span data-stu-id="a650c-114">Casting is required when information might be lost in the conversion, or when the conversion might not succeed for other reasons.</span></span>  <span data-ttu-id="a650c-115">典型的な例としては、より精度の低い型 (または、より範囲が狭い型) に数値を変換する場合や、基底クラスのインスタンスを派生クラスに変換する場合が挙げられます。</span><span class="sxs-lookup"><span data-stu-id="a650c-115">Typical examples include numeric conversion to a type that has less precision or a smaller range, and conversion of a base-class instance to a derived class.</span></span>  
  
- <span data-ttu-id="a650c-116">**ユーザー定義の変換**: ユーザー定義の変換は特殊なメソッドによって実行されます。これを定義することで、基本クラスと派生クラスの関係がないカスタム型間の明示的および暗黙的な変換が可能になります。</span><span class="sxs-lookup"><span data-stu-id="a650c-116">**User-defined conversions**: User-defined conversions are performed by special methods that you can define to enable explicit and implicit conversions between custom types that do not have a base class–derived class relationship.</span></span> <span data-ttu-id="a650c-117">詳細については、「[User-defined conversion operators](../../language-reference/operators/user-defined-conversion-operators.md)」(ユーザー定義の変換演算子) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a650c-117">For more information, see [User-defined conversion operators](../../language-reference/operators/user-defined-conversion-operators.md).</span></span>  
  
- <span data-ttu-id="a650c-118">**ヘルパー クラスを使用する変換**: 整数と <xref:System.DateTime?displayProperty=nameWithType> オブジェクトの間、16 進文字列とバイト配列の間など、互換性のない型の間で変換を行うには、<xref:System.BitConverter?displayProperty=nameWithType> クラス、<xref:System.Convert?displayProperty=nameWithType> クラス、および組み込み数値型の `Parse` メソッド (<xref:System.Int32.Parse%2A?displayProperty=nameWithType> など) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="a650c-118">**Conversions with helper classes**: To convert between non-compatible types, such as integers and <xref:System.DateTime?displayProperty=nameWithType> objects, or hexadecimal strings and byte arrays, you can use the <xref:System.BitConverter?displayProperty=nameWithType> class, the <xref:System.Convert?displayProperty=nameWithType> class, and the `Parse` methods of the built-in numeric types, such as <xref:System.Int32.Parse%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="a650c-119">詳細については、[方法:バイト配列を int に変換する](./how-to-convert-a-byte-array-to-an-int.md)」、「[方法: 文字列を数値に変換する](./how-to-convert-a-string-to-a-number.md)」、および「[方法: 16 進文字列と数値型の間で変換する](./how-to-convert-between-hexadecimal-strings-and-numeric-types.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a650c-119">For more information, see [How to: Convert a byte Array to an int](./how-to-convert-a-byte-array-to-an-int.md), [How to: Convert a String to a Number](./how-to-convert-a-string-to-a-number.md), and [How to: Convert Between Hexadecimal Strings and Numeric Types](./how-to-convert-between-hexadecimal-strings-and-numeric-types.md).</span></span>  
  
## <a name="implicit-conversions"></a><span data-ttu-id="a650c-120">暗黙の変換</span><span class="sxs-lookup"><span data-stu-id="a650c-120">Implicit conversions</span></span>

 <span data-ttu-id="a650c-121">組み込みの数値型の場合、格納される値を切り捨てたり丸めたりしなくても変数に収めることができるのであれば、暗黙的な変換を実行できます。</span><span class="sxs-lookup"><span data-stu-id="a650c-121">For built-in numeric types, an implicit conversion can be made when the value to be stored can fit into the variable without being truncated or rounded off.</span></span> <span data-ttu-id="a650c-122">整数型の場合、これは、ソースの型の範囲が、ターゲットの型の範囲の適切なサブセットであるという意味です。</span><span class="sxs-lookup"><span data-stu-id="a650c-122">For integral types, this means the range of the source type is a proper subset of the range for the target type.</span></span> <span data-ttu-id="a650c-123">たとえば、[long](../../language-reference/builtin-types/integral-numeric-types.md) 型の変数 (64 ビットの整数) は、[int](../../language-reference/builtin-types/integral-numeric-types.md) (32 ビットの整数) が格納できる任意の値を格納できます。</span><span class="sxs-lookup"><span data-stu-id="a650c-123">For example, a variable of type [long](../../language-reference/builtin-types/integral-numeric-types.md) (64-bit integer) can store any value that an [int](../../language-reference/builtin-types/integral-numeric-types.md) (32-bit integer) can store.</span></span> <span data-ttu-id="a650c-124">次の例の場合、コンパイラは右側の `num` の値を `bigNum` に代入する前に、この値を `long` 型へと暗黙的に変換します。</span><span class="sxs-lookup"><span data-stu-id="a650c-124">In the following example, the compiler implicitly converts the value of `num` on the right to a type `long` before assigning it to `bigNum`.</span></span>  
  
 [!code-csharp[csProgGuideTypes#34](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#34)]  
  
 <span data-ttu-id="a650c-125">暗黙的な数値変換をすべてまとめた一覧については、「[暗黙的な数値変換の一覧表](../../language-reference/keywords/implicit-numeric-conversions-table.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a650c-125">For a complete list of all implicit numeric conversions, see [Implicit Numeric Conversions Table](../../language-reference/keywords/implicit-numeric-conversions-table.md).</span></span>  
  
 <span data-ttu-id="a650c-126">参照型の場合は、特定のクラスから、その直接または間接的な基底クラスやインターフェイスに対して、常に暗黙的な変換が存在します。</span><span class="sxs-lookup"><span data-stu-id="a650c-126">For reference types, an implicit conversion always exists from a class to any one of its direct or indirect base classes or interfaces.</span></span> <span data-ttu-id="a650c-127">派生クラスには常に基底クラスのすべてのメンバーが含まれるため、特別な構文は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="a650c-127">No special syntax is necessary because a derived class always contains all the members of a base class.</span></span>  
  
```csharp
Derived d = new Derived();  
Base b = d; // Always OK.  
```  
  
## <a name="explicit-conversions"></a><span data-ttu-id="a650c-128">明示的な変換</span><span class="sxs-lookup"><span data-stu-id="a650c-128">Explicit conversions</span></span>

 <span data-ttu-id="a650c-129">変換によって情報が失われるリスクがある場合は、コンパイラで明示的な変換を実行する必要があります。これを*キャスト*と呼びます。</span><span class="sxs-lookup"><span data-stu-id="a650c-129">However, if a conversion cannot be made without a risk of losing information, the compiler requires that you perform an explicit conversion, which is called a *cast*.</span></span> <span data-ttu-id="a650c-130">キャストとは、変換を行う意図があることと、データ損失が発生する可能性があることを、コンパイラに明示的に知らせるための方法です。</span><span class="sxs-lookup"><span data-stu-id="a650c-130">A cast is a way of explicitly informing the compiler that you intend to make the conversion and that you are aware that data loss might occur.</span></span> <span data-ttu-id="a650c-131">キャストを実行するには、変換する値または変数の前に、キャストする型をかっこで囲んで指定します。</span><span class="sxs-lookup"><span data-stu-id="a650c-131">To perform a cast, specify the type that you are casting to in parentheses in front of the value or variable to be converted.</span></span> <span data-ttu-id="a650c-132">次のプログラでは、[double](../../language-reference/builtin-types/floating-point-numeric-types.md) を [int](../../language-reference/builtin-types/integral-numeric-types.md) にキャストしています。このプログラムは、キャストなしではコンパイルされません。</span><span class="sxs-lookup"><span data-stu-id="a650c-132">The following program casts a [double](../../language-reference/builtin-types/floating-point-numeric-types.md) to an [int](../../language-reference/builtin-types/integral-numeric-types.md). The program will not compile without the cast.</span></span>  
  
 [!code-csharp[csProgGuideTypes#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#2)]  
  
 <span data-ttu-id="a650c-133">許可される明示的数値変換の一覧については、「[明示的な数値変換の一覧表](../../language-reference/keywords/explicit-numeric-conversions-table.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a650c-133">For a list of the explicit numeric conversions that are allowed, see [Explicit Numeric Conversions Table](../../language-reference/keywords/explicit-numeric-conversions-table.md).</span></span>  
  
 <span data-ttu-id="a650c-134">参照型の場合は、基本型から派生型に変換する必要がある場合に、明示的なキャストが必要です。</span><span class="sxs-lookup"><span data-stu-id="a650c-134">For reference types, an explicit cast is required if you need to convert from a base type to a derived type:</span></span>  
  
```csharp  
// Create a new derived type.  
Giraffe g = new Giraffe();  
  
// Implicit conversion to base type is safe.  
Animal a = g;  
  
// Explicit conversion is required to cast back  
// to derived type. Note: This will compile but will  
// throw an exception at run time if the right-side  
// object is not in fact a Giraffe.  
Giraffe g2 = (Giraffe) a;  
```  
  
 <span data-ttu-id="a650c-135">参照型の間でキャスト操作を行っても、基になるオブジェクトの実行時の型は変わりません。そのオブジェクトへの参照として使用される値の型だけが変更されます。</span><span class="sxs-lookup"><span data-stu-id="a650c-135">A cast operation between reference types does not change the run-time type of the underlying object; it only changes the type of the value that is being used as a reference to that object.</span></span> <span data-ttu-id="a650c-136">詳細については、「[ポリモーフィズム](../classes-and-structs/polymorphism.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a650c-136">For more information, see [Polymorphism](../classes-and-structs/polymorphism.md).</span></span>  
  
## <a name="type-conversion-exceptions-at-run-time"></a><span data-ttu-id="a650c-137">実行時に発生する型変換の例外</span><span class="sxs-lookup"><span data-stu-id="a650c-137">Type conversion exceptions at run time</span></span>

 <span data-ttu-id="a650c-138">一部の参照型変換では、キャストが有効になるかどうかをコンパイラで判断できません。</span><span class="sxs-lookup"><span data-stu-id="a650c-138">In some reference type conversions, the compiler cannot determine whether a cast will be valid.</span></span> <span data-ttu-id="a650c-139">キャスト操作が正しくコンパイルされても、実行時に失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a650c-139">It is possible for a cast operation that compiles correctly to fail at run time.</span></span> <span data-ttu-id="a650c-140">次の例に示すように、型キャストが実行時に失敗すると、<xref:System.InvalidCastException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="a650c-140">As shown in the following example, a type cast that fails at run time will cause an <xref:System.InvalidCastException> to be thrown.</span></span>  
  
 [!code-csharp[csProgGuideTypes#41](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#41)]  
  
 <span data-ttu-id="a650c-141">C# では、キャストの実行前に互換性をテストできるよう、[is](../../language-reference/operators/type-testing-and-cast.md#is-operator) 演算子が提供されています。</span><span class="sxs-lookup"><span data-stu-id="a650c-141">C# provides the [is](../../language-reference/operators/type-testing-and-cast.md#is-operator) operator to enable you to test for compatibility before actually performing a cast.</span></span> <span data-ttu-id="a650c-142">詳しくは、「[方法: パターン マッチング、is 演算子、as 演算子を使用して安全にキャストする](../../how-to/safely-cast-using-pattern-matching-is-and-as-operators.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a650c-142">For more information, see [How to: safely cast using pattern matching and the as and is operators](../../how-to/safely-cast-using-pattern-matching-is-and-as-operators.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="a650c-143">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="a650c-143">C# language specification</span></span>

<span data-ttu-id="a650c-144">詳細については、[C# 言語仕様](~/_csharplang/spec/introduction.md)の[変換](~/_csharplang/spec/conversions.md)に関するセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a650c-144">For more information, see the [Conversions](~/_csharplang/spec/conversions.md) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a650c-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="a650c-145">See also</span></span>

- [<span data-ttu-id="a650c-146">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="a650c-146">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="a650c-147">型</span><span class="sxs-lookup"><span data-stu-id="a650c-147">Types</span></span>](./index.md)
- [<span data-ttu-id="a650c-148">() キャスト演算子</span><span class="sxs-lookup"><span data-stu-id="a650c-148">() cast operator</span></span>](../../language-reference/operators/type-testing-and-cast.md#cast-operator-)
- [<span data-ttu-id="a650c-149">ユーザー定義の変換演算子</span><span class="sxs-lookup"><span data-stu-id="a650c-149">User-defined conversion operators</span></span>](../../language-reference/operators/user-defined-conversion-operators.md)
- <span data-ttu-id="a650c-150">[一般的な型変換](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/yy580hbd(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="a650c-150">[Generalized Type Conversion](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/yy580hbd(v=vs.120))</span></span>
- [<span data-ttu-id="a650c-151">方法: 文字列を数値に変換する</span><span class="sxs-lookup"><span data-stu-id="a650c-151">How to: Convert a String to a Number</span></span>](./how-to-convert-a-string-to-a-number.md)
