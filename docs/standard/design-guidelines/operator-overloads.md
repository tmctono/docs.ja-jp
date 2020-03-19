---
title: 演算子のオーバーロード
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- operators [.NET Framework], overloads
- names [.NET Framework], overloaded operators
- member design guidelines, operators
- overloaded operators
ms.assetid: 37585bf2-4c27-4dee-849a-af70e3338cc1
ms.openlocfilehash: 0999e94c8d77396b237522e89c51206ce1226718
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401221"
---
# <a name="operator-overloads"></a><span data-ttu-id="a5950-102">演算子のオーバーロード</span><span class="sxs-lookup"><span data-stu-id="a5950-102">Operator Overloads</span></span>
<span data-ttu-id="a5950-103">演算子のオーバーロードを使用すると、フレームワークの型は組み込みの言語プリミティブのように見えます。</span><span class="sxs-lookup"><span data-stu-id="a5950-103">Operator overloads allow framework types to appear as if they were built-in language primitives.</span></span>

 <span data-ttu-id="a5950-104">許可され、役立つ場合もありますが、演算子のオーバーロードは慎重に使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5950-104">Although allowed and useful in some situations, operator overloads should be used cautiously.</span></span> <span data-ttu-id="a5950-105">フレームワークの設計者が単純なメソッドである必要がある操作に演算子を使用し始めた場合など、演算子のオーバーロードが悪用されたケースが多くあります。</span><span class="sxs-lookup"><span data-stu-id="a5950-105">There are many cases in which operator overloading has been abused, such as when framework designers started to use operators for operations that should be simple methods.</span></span> <span data-ttu-id="a5950-106">次のガイドラインは、演算子のオーバーロードを使用するタイミングと方法を決定する際に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a5950-106">The following guidelines should help you decide when and how to use operator overloading.</span></span>

 <span data-ttu-id="a5950-107">❌プリミティブ (組み込み) 型のように感じる型を除き、演算子のオーバーロードを定義しないようにします。</span><span class="sxs-lookup"><span data-stu-id="a5950-107">❌ AVOID defining operator overloads, except in types that should feel like primitive (built-in) types.</span></span>

 <span data-ttu-id="a5950-108">✔️プリミティブ型のように感じる型で演算子のオーバーロードを定義することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="a5950-108">✔️ CONSIDER defining operator overloads in a type that should feel like a primitive type.</span></span>

 <span data-ttu-id="a5950-109">たとえば、<xref:System.String?displayProperty=nameWithType>を持`operator==`っていると`operator!=`定義されています。</span><span class="sxs-lookup"><span data-stu-id="a5950-109">For example, <xref:System.String?displayProperty=nameWithType> has `operator==` and `operator!=` defined.</span></span>

 <span data-ttu-id="a5950-110">✔️は、数値を表す構造体の演算子のオーバーロードを定義します<xref:System.Decimal?displayProperty=nameWithType>( など )。</span><span class="sxs-lookup"><span data-stu-id="a5950-110">✔️ DO define operator overloads in structs that represent numbers (such as <xref:System.Decimal?displayProperty=nameWithType>).</span></span>

 <span data-ttu-id="a5950-111">❌演算子のオーバーロードを定義するときにかわいいしないでください。</span><span class="sxs-lookup"><span data-stu-id="a5950-111">❌ DO NOT be cute when defining operator overloads.</span></span>

 <span data-ttu-id="a5950-112">演算子のオーバーロードは、操作の結果が何であるかがすぐにわかる場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="a5950-112">Operator overloading is useful in cases in which it is immediately obvious what the result of the operation will be.</span></span> <span data-ttu-id="a5950-113">たとえば、互<xref:System.DateTime>`DateTime`いに減算して<xref:System.TimeSpan>.</span><span class="sxs-lookup"><span data-stu-id="a5950-113">For example, it makes sense to be able to subtract one <xref:System.DateTime> from another `DateTime` and get a <xref:System.TimeSpan>.</span></span> <span data-ttu-id="a5950-114">ただし、論理共用体演算子を使用して 2 つのデータベース照会を共用するか、シフト演算子を使用してストリームに書き込むのは適切ではありません。</span><span class="sxs-lookup"><span data-stu-id="a5950-114">However, it is not appropriate to use the logical union operator to union two database queries, or to use the shift operator to write to a stream.</span></span>

 <span data-ttu-id="a5950-115">❌少なくとも 1 つのオペランドがオーバーロードを定義する型でない限り、演算子のオーバーロードを提供しないでください。</span><span class="sxs-lookup"><span data-stu-id="a5950-115">❌ DO NOT provide operator overloads unless at least one of the operands is of the type defining the overload.</span></span>

 <span data-ttu-id="a5950-116">✔️演算子を対称的にオーバーロードします。</span><span class="sxs-lookup"><span data-stu-id="a5950-116">✔️ DO overload operators in a symmetric fashion.</span></span>

 <span data-ttu-id="a5950-117">たとえば、`operator==`をオーバーロードする場合は、 もオーバーロードする`operator!=`必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5950-117">For example, if you overload the `operator==`, you should also overload the `operator!=`.</span></span> <span data-ttu-id="a5950-118">同様に、`operator<`をオーバーロードする場合は、 など`operator>`もオーバーロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5950-118">Similarly, if you overload the `operator<`, you should also overload the `operator>`, and so on.</span></span>

 <span data-ttu-id="a5950-119">✔️ CONSIDER オーバーロードされた各演算子に対応するフレンドリ名を持つメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="a5950-119">✔️ CONSIDER providing methods with friendly names that correspond to each overloaded operator.</span></span>

 <span data-ttu-id="a5950-120">多くの言語では、演算子のオーバーロードはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="a5950-120">Many languages do not support operator overloading.</span></span> <span data-ttu-id="a5950-121">このため、演算子をオーバーロードする型には、同等の機能を提供する適切なドメイン固有の名前を持つセカンダリ メソッドを含める方法をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a5950-121">For this reason, it is recommended that types that overload operators include a secondary method with an appropriate domain-specific name that provides equivalent functionality.</span></span>

 <span data-ttu-id="a5950-122">次の表に、演算子と対応するフレンドリ メソッド名の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="a5950-122">The following table contains a list of operators and the corresponding friendly method names.</span></span>

|<span data-ttu-id="a5950-123">C# 演算子記号</span><span class="sxs-lookup"><span data-stu-id="a5950-123">C# Operator Symbol</span></span>|<span data-ttu-id="a5950-124">メタデータ名</span><span class="sxs-lookup"><span data-stu-id="a5950-124">Metadata Name</span></span>|<span data-ttu-id="a5950-125">フレンドリ名</span><span class="sxs-lookup"><span data-stu-id="a5950-125">Friendly Name</span></span>|
|-------------------------|-------------------|-------------------|
|`N/A`|`op_Implicit`|`To<TypeName>/From<TypeName>`|
|`N/A`|`op_Explicit`|`To<TypeName>/From<TypeName>`|
|`+ (binary)`|`op_Addition`|`Add`|
|`- (binary)`|`op_Subtraction`|`Subtract`|
|`* (binary)`|`op_Multiply`|`Multiply`|
|`/`|`op_Division`|`Divide`|
|`%`|`op_Modulus`|`Mod or Remainder`|
|`^`|`op_ExclusiveOr`|`Xor`|
|`& (binary)`|`op_BitwiseAnd`|`BitwiseAnd`|
|<code>&#124;</code>|`op_BitwiseOr`|`BitwiseOr`|
|`&&`|`op_LogicalAnd`|`And`|
|<code>&#124;&#124;</code>|`op_LogicalOr`|`Or`|
|`=`|`op_Assign`|`Assign`|
|`<<`|`op_LeftShift`|`LeftShift`|
|`>>`|`op_RightShift`|`RightShift`|
|`N/A`|`op_SignedRightShift`|`SignedRightShift`|
|`N/A`|`op_UnsignedRightShift`|`UnsignedRightShift`|
|`==`|`op_Equality`|`Equals`|
|`!=`|`op_Inequality`|`Equals`|
|`>`|`op_GreaterThan`|`CompareTo`|
|`<`|`op_LessThan`|`CompareTo`|
|`>=`|`op_GreaterThanOrEqual`|`CompareTo`|
|`<=`|`op_LessThanOrEqual`|`CompareTo`|
|`*=`|`op_MultiplicationAssignment`|`Multiply`|
|`-=`|`op_SubtractionAssignment`|`Subtract`|
|`^=`|`op_ExclusiveOrAssignment`|`Xor`|
|`<<=`|`op_LeftShiftAssignment`|`LeftShift`|
|`%=`|`op_ModulusAssignment`|`Mod`|
|`+=`|`op_AdditionAssignment`|`Add`|
|`&=`|`op_BitwiseAndAssignment`|`BitwiseAnd`|
|<code>&#124;=</code>|`op_BitwiseOrAssignment`|`BitwiseOr`|
|`,`|`op_Comma`|`Comma`|
|`/=`|`op_DivisionAssignment`|`Divide`|
|`--`|`op_Decrement`|`Decrement`|
|`++`|`op_Increment`|`Increment`|
|`- (unary)`|`op_UnaryNegation`|`Negate`|
|`+ (unary)`|`op_UnaryPlus`|`Plus`|
|`~`|`op_OnesComplement`|`OnesComplement`|

### <a name="overloading-operator-"></a><span data-ttu-id="a5950-126">オーバーロード演算子 ==</span><span class="sxs-lookup"><span data-stu-id="a5950-126">Overloading Operator ==</span></span>
 <span data-ttu-id="a5950-127">オーバーロードは`operator ==`非常に複雑です。</span><span class="sxs-lookup"><span data-stu-id="a5950-127">Overloading `operator ==` is quite complicated.</span></span> <span data-ttu-id="a5950-128">演算子のセマンティクスは、 などの<xref:System.Object.Equals%2A?displayProperty=nameWithType>他のメンバーと互換性がある必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5950-128">The semantics of the operator need to be compatible with several other members, such as <xref:System.Object.Equals%2A?displayProperty=nameWithType>.</span></span>

### <a name="conversion-operators"></a><span data-ttu-id="a5950-129">変換演算子</span><span class="sxs-lookup"><span data-stu-id="a5950-129">Conversion Operators</span></span>
 <span data-ttu-id="a5950-130">変換演算子は、ある型から別の型への変換を可能にする単項演算子です。</span><span class="sxs-lookup"><span data-stu-id="a5950-130">Conversion operators are unary operators that allow conversion from one type to another.</span></span> <span data-ttu-id="a5950-131">演算子は、オペランドまたは戻り値の型で静的メンバーとして定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5950-131">The operators must be defined as static members on either the operand or the return type.</span></span> <span data-ttu-id="a5950-132">変換演算子には、暗黙的および明示的の 2 種類があります。</span><span class="sxs-lookup"><span data-stu-id="a5950-132">There are two types of conversion operators: implicit and explicit.</span></span>

 <span data-ttu-id="a5950-133">❌このような変換がエンド ユーザーによって明確に予期されない場合は、変換演算子を提供しないでください。</span><span class="sxs-lookup"><span data-stu-id="a5950-133">❌ DO NOT provide a conversion operator if such conversion is not clearly expected by the end users.</span></span>

 <span data-ttu-id="a5950-134">❌型のドメインの外部で変換演算子を定義しないでください。</span><span class="sxs-lookup"><span data-stu-id="a5950-134">❌ DO NOT define conversion operators outside of a type’s domain.</span></span>

 <span data-ttu-id="a5950-135">たとえば、 <xref:System.Int32>、、<xref:System.Double>および<xref:System.Decimal>は、すべて数値型<xref:System.DateTime>ですが、数値型は、そうではありません。</span><span class="sxs-lookup"><span data-stu-id="a5950-135">For example, <xref:System.Int32>, <xref:System.Double>, and <xref:System.Decimal> are all numeric types, whereas <xref:System.DateTime> is not.</span></span> <span data-ttu-id="a5950-136">したがって、 に`Double(long)`変換する変換演算子は必要`DateTime`ありません。</span><span class="sxs-lookup"><span data-stu-id="a5950-136">Therefore, there should be no conversion operator to convert a `Double(long)` to a `DateTime`.</span></span> <span data-ttu-id="a5950-137">このような場合はコンストラクタが好ましい。</span><span class="sxs-lookup"><span data-stu-id="a5950-137">A constructor is preferred in such a case.</span></span>

 <span data-ttu-id="a5950-138">❌変換が損失を生じやすい場合は、暗黙の変換演算子を提供しないでください。</span><span class="sxs-lookup"><span data-stu-id="a5950-138">❌ DO NOT provide an implicit conversion operator if the conversion is potentially lossy.</span></span>

 <span data-ttu-id="a5950-139">For example, there should not be an implicit conversion from `Double` to `Int32` because `Double` has a wider range than `Int32`.</span><span class="sxs-lookup"><span data-stu-id="a5950-139">For example, there should not be an implicit conversion from `Double` to `Int32` because `Double` has a wider range than `Int32`.</span></span> <span data-ttu-id="a5950-140">変換が損失を生じかなくても、明示的な変換演算子を指定できます。</span><span class="sxs-lookup"><span data-stu-id="a5950-140">An explicit conversion operator can be provided even if the conversion is potentially lossy.</span></span>

 <span data-ttu-id="a5950-141">❌暗黙的なキャストから例外をスローしないでください。</span><span class="sxs-lookup"><span data-stu-id="a5950-141">❌ DO NOT throw exceptions from implicit casts.</span></span>

 <span data-ttu-id="a5950-142">エンド ユーザーは、変換が行われていることに気づいていない可能性があるため、何が起こっているのかを理解することは非常に困難です。</span><span class="sxs-lookup"><span data-stu-id="a5950-142">It is very difficult for end users to understand what is happening, because they might not be aware that a conversion is taking place.</span></span>

 <span data-ttu-id="a5950-143">キャスト演算子を<xref:System.InvalidCastException?displayProperty=nameWithType>呼び出すと損失変換が発生し、演算子のコントラクトが損失変換を許可しない場合は、✔️ DO スローします。</span><span class="sxs-lookup"><span data-stu-id="a5950-143">✔️ DO throw <xref:System.InvalidCastException?displayProperty=nameWithType> if a call to a cast operator results in a lossy conversion and the contract of the operator does not allow lossy conversions.</span></span>

 <span data-ttu-id="a5950-144">*2005年、2009年©マイクロソフト株式会社。すべての権利が予約されています。*</span><span class="sxs-lookup"><span data-stu-id="a5950-144">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="a5950-145">*2008 年 10 月 22 日に Microsoft Windows Development シリーズの一部として、Addison-Wesley Professional によって発行された、Krzysztof Cwalina および Brad Abrams による「[Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)」 (フレームワーク デザイン ガイドライン: 再利用可能な .NET ライブラリの規則、用法、パターン、第 2 版) から Pearson Education, Inc. の許可を得て再印刷されています。*</span><span class="sxs-lookup"><span data-stu-id="a5950-145">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="a5950-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="a5950-146">See also</span></span>

- [<span data-ttu-id="a5950-147">メンバーのデザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="a5950-147">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)
- [<span data-ttu-id="a5950-148">フレームワーク デザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="a5950-148">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
