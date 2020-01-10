---
title: 列挙型デザイン
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- type design guidelines, enumerations
- simple enumerations
- enumerations [.NET Framework], design guidelines
- class library design guidelines [.NET Framework], enumerations
- flags enumerations
ms.assetid: dd53c952-9d9a-4736-86ff-9540e815d545
ms.openlocfilehash: 130e9b4e7f8d7076d1dc3f21f51dc07a68799bbe
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709453"
---
# <a name="enum-design"></a><span data-ttu-id="1b272-102">列挙型デザイン</span><span class="sxs-lookup"><span data-stu-id="1b272-102">Enum Design</span></span>

<span data-ttu-id="1b272-103">列挙型は、特別な種類の値型です。</span><span class="sxs-lookup"><span data-stu-id="1b272-103">Enums are a special kind of value type.</span></span> <span data-ttu-id="1b272-104">列挙型には、単純な列挙型とフラグ列挙型の2種類があります。</span><span class="sxs-lookup"><span data-stu-id="1b272-104">There are two kinds of enums: simple enums and flag enums.</span></span>

<span data-ttu-id="1b272-105">単純な列挙型は、選択の小さな閉じられたセットを表します。</span><span class="sxs-lookup"><span data-stu-id="1b272-105">Simple enums represent small closed sets of choices.</span></span> <span data-ttu-id="1b272-106">単純な列挙型の一般的な例としては、一連の色があります。</span><span class="sxs-lookup"><span data-stu-id="1b272-106">A common example of the simple enum is a set of colors.</span></span>

<span data-ttu-id="1b272-107">フラグ列挙型は、列挙値のビットごとの演算をサポートするように設計されています。</span><span class="sxs-lookup"><span data-stu-id="1b272-107">Flag enums are designed to support bitwise operations on the enum values.</span></span> <span data-ttu-id="1b272-108">Flags 列挙型の一般的な例として、オプションの一覧があります。</span><span class="sxs-lookup"><span data-stu-id="1b272-108">A common example of the flags enum is a list of options.</span></span>

<span data-ttu-id="1b272-109">**✓ DO** を厳密に型パラメーター、プロパティ、列挙型を使用し、戻り値のセットを表す値です。</span><span class="sxs-lookup"><span data-stu-id="1b272-109">**✓ DO** use an enum to strongly type parameters, properties, and return values that represent sets of values.</span></span>

<span data-ttu-id="1b272-110">**✓ DO** 列挙型を静的な定数の代わりに使用をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1b272-110">**✓ DO** favor using an enum instead of static constants.</span></span>

<span data-ttu-id="1b272-111">**X DO NOT** (など、オペレーティング システムのバージョン、友人などの名前)、開いているセットの列挙型を使用します。</span><span class="sxs-lookup"><span data-stu-id="1b272-111">**X DO NOT** use an enum for open sets (such as the operating system version, names of your friends, etc.).</span></span>

<span data-ttu-id="1b272-112">**X DO NOT** 将来使用するためのものでは予約されている列挙値を提供します。</span><span class="sxs-lookup"><span data-stu-id="1b272-112">**X DO NOT** provide reserved enum values that are intended for future use.</span></span>

<span data-ttu-id="1b272-113">後の段階で、既存の列挙に値をいつでも追加できます。</span><span class="sxs-lookup"><span data-stu-id="1b272-113">You can always simply add values to the existing enum at a later stage.</span></span> <span data-ttu-id="1b272-114">列挙型に値を追加する方法の詳細については、「[列挙型への値の追加](#add_value)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1b272-114">See [Adding Values to Enums](#add_value) for more details on adding values to enums.</span></span> <span data-ttu-id="1b272-115">予約済みの値は、実際の値のセットを汚染するだけで、ユーザーエラーにつながる傾向があります。</span><span class="sxs-lookup"><span data-stu-id="1b272-115">Reserved values just pollute the set of real values and tend to lead to user errors.</span></span>

<span data-ttu-id="1b272-116">**X AVOID** 1 つだけの値を持つ列挙型を公開することです。</span><span class="sxs-lookup"><span data-stu-id="1b272-116">**X AVOID** publicly exposing enums with only one value.</span></span>

<span data-ttu-id="1b272-117">C Api の将来の拡張性を確保するための一般的な方法は、メソッドシグネチャに予約済みのパラメーターを追加することです。</span><span class="sxs-lookup"><span data-stu-id="1b272-117">A common practice for ensuring future extensibility of C APIs is to add reserved parameters to method signatures.</span></span> <span data-ttu-id="1b272-118">このような予約済みのパラメーターは、単一の既定値を持つ列挙型として表すことができます。</span><span class="sxs-lookup"><span data-stu-id="1b272-118">Such reserved parameters can be expressed as enums with a single default value.</span></span> <span data-ttu-id="1b272-119">これは、マネージ Api では実行できません。</span><span class="sxs-lookup"><span data-stu-id="1b272-119">This should not be done in managed APIs.</span></span> <span data-ttu-id="1b272-120">メソッドのオーバーロードでは、将来のリリースでパラメーターを追加できます。</span><span class="sxs-lookup"><span data-stu-id="1b272-120">Method overloading allows adding parameters in future releases.</span></span>

<span data-ttu-id="1b272-121">**X DO NOT** enum で sentinel 値が含まれます。</span><span class="sxs-lookup"><span data-stu-id="1b272-121">**X DO NOT** include sentinel values in enums.</span></span>

<span data-ttu-id="1b272-122">Framework 開発者にとっては便利な場合もありますが、sentinel 値はフレームワークのユーザーにとって混乱を招くことがあります。</span><span class="sxs-lookup"><span data-stu-id="1b272-122">Although they are sometimes helpful to framework developers, sentinel values are confusing to users of the framework.</span></span> <span data-ttu-id="1b272-123">列挙型によって表されるセットの値の1つではなく、列挙型の状態を追跡するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="1b272-123">They are used to track the state of the enum rather than being one of the values from the set represented by the enum.</span></span>

<span data-ttu-id="1b272-124">**✓ DO** 単純な列挙型のゼロの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="1b272-124">**✓ DO** provide a value of zero on simple enums.</span></span>

<span data-ttu-id="1b272-125">"None" のような値を呼び出すことを検討してください。</span><span class="sxs-lookup"><span data-stu-id="1b272-125">Consider calling the value something like "None."</span></span> <span data-ttu-id="1b272-126">このような値がこの特定の列挙型に適していない場合は、列挙型の最も一般的な既定値に0の基になる値を代入する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1b272-126">If such a value is not appropriate for this particular enum, the most common default value for the enum should be assigned the underlying value of zero.</span></span>

<span data-ttu-id="1b272-127">**✓ CONSIDER** を使用して<xref:System.Int32>(ほとんどのプログラミング言語の既定値) enum の基になる型として、次のいずれかが当てはまる場合を除き、します。</span><span class="sxs-lookup"><span data-stu-id="1b272-127">**✓ CONSIDER** using <xref:System.Int32> (the default in most programming languages) as the underlying type of an enum unless any of the following is true:</span></span>

- <span data-ttu-id="1b272-128">列挙型はフラグの列挙型であり、32を超えるフラグがあるか、または今後さらに多くなることが予想されます。</span><span class="sxs-lookup"><span data-stu-id="1b272-128">The enum is a flags enum and you have more than 32 flags, or expect to have more in the future.</span></span>

- <span data-ttu-id="1b272-129">基になる型は、異なるサイズの列挙型を必要とするアンマネージコードとの相互運用性を容易にするために、<xref:System.Int32> とは異なる必要があります。</span><span class="sxs-lookup"><span data-stu-id="1b272-129">The underlying type needs to be different than <xref:System.Int32> for easier interoperability with unmanaged code expecting different-size enums.</span></span>

- <span data-ttu-id="1b272-130">基になる型が小さいと、スペースが大幅に節約されます。</span><span class="sxs-lookup"><span data-stu-id="1b272-130">A smaller underlying type would result in substantial savings in space.</span></span> <span data-ttu-id="1b272-131">列挙型が主に制御フローの引数として使用されることが予想される場合、サイズの違いはほとんどありません。</span><span class="sxs-lookup"><span data-stu-id="1b272-131">If you expect the enum to be used mainly as an argument for flow of control, the size makes little difference.</span></span> <span data-ttu-id="1b272-132">次の場合、サイズを節約することが重要になります。</span><span class="sxs-lookup"><span data-stu-id="1b272-132">The size savings might be significant if:</span></span>

  - <span data-ttu-id="1b272-133">非常に頻繁にインスタンス化される構造体またはクラスのフィールドとして列挙型を使用することを想定しています。</span><span class="sxs-lookup"><span data-stu-id="1b272-133">You expect the enum to be used as a field in a very frequently instantiated structure or class.</span></span>

  - <span data-ttu-id="1b272-134">ユーザーは、大規模な配列または列挙型インスタンスのコレクションを作成することを想定しています。</span><span class="sxs-lookup"><span data-stu-id="1b272-134">You expect users to create large arrays or collections of the enum instances.</span></span>

  - <span data-ttu-id="1b272-135">列挙型の多数のインスタンスをシリアル化することを想定しています。</span><span class="sxs-lookup"><span data-stu-id="1b272-135">You expect a large number of instances of the enum to be serialized.</span></span>

<span data-ttu-id="1b272-136">メモリ内での使用については、マネージオブジェクトが常に `DWORD`に配置されていることに注意してください。したがって、インスタンス全体のサイズは常に `DWORD`に切り上げられるため、より小さな列挙型をパックするためには、インスタンス内に複数の列挙型またはその他の小さな構造体が効果的に必要です。</span><span class="sxs-lookup"><span data-stu-id="1b272-136">For in-memory usage, be aware that managed objects are always `DWORD`-aligned, so you effectively need multiple enums or other small structures in an instance to pack a smaller enum with in order to make a difference, because the total instance size is always going to be rounded up to a `DWORD`.</span></span>

<span data-ttu-id="1b272-137">**✓ DO** フラグの列挙型には複数形の名詞または名詞句と単数形の名詞または名詞句と単純な列挙型の名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="1b272-137">**✓ DO** name flag enums with plural nouns or noun phrases and simple enums with singular nouns or noun phrases.</span></span>

<span data-ttu-id="1b272-138">**X DO NOT** 拡張<xref:System.Enum?displayProperty=nameWithType>直接です。</span><span class="sxs-lookup"><span data-stu-id="1b272-138">**X DO NOT** extend <xref:System.Enum?displayProperty=nameWithType> directly.</span></span>

<span data-ttu-id="1b272-139"><xref:System.Enum?displayProperty=nameWithType> は、ユーザー定義の列挙を作成するために CLR によって使用される特殊な型です。</span><span class="sxs-lookup"><span data-stu-id="1b272-139"><xref:System.Enum?displayProperty=nameWithType> is a special type used by the CLR to create user-defined enumerations.</span></span> <span data-ttu-id="1b272-140">ほとんどのプログラミング言語には、この機能にアクセスできるプログラミング要素が用意されています。</span><span class="sxs-lookup"><span data-stu-id="1b272-140">Most programming languages provide a programming element that gives you access to this functionality.</span></span> <span data-ttu-id="1b272-141">たとえば、 C#の `enum` キーワードを使用して、列挙型を定義します。</span><span class="sxs-lookup"><span data-stu-id="1b272-141">For example, in C# the `enum` keyword is used to define an enumeration.</span></span>

<a name="design"></a>

### <a name="designing-flag-enums"></a><span data-ttu-id="1b272-142">フラグ列挙型のデザイン</span><span class="sxs-lookup"><span data-stu-id="1b272-142">Designing Flag Enums</span></span>

<span data-ttu-id="1b272-143">**✓ DO** 適用、<xref:System.FlagsAttribute?displayProperty=nameWithType>フラグ列挙体にします。</span><span class="sxs-lookup"><span data-stu-id="1b272-143">**✓ DO** apply the <xref:System.FlagsAttribute?displayProperty=nameWithType> to flag enums.</span></span> <span data-ttu-id="1b272-144">単純な列挙型にはこの属性を適用しないでください。</span><span class="sxs-lookup"><span data-stu-id="1b272-144">Do not apply this attribute to simple enums.</span></span>

<span data-ttu-id="1b272-145">**✓ DO** フラグ列挙値に 2 の累乗を使用して、自由に組み合わせてことができます、ビットごとの OR 演算を使用しているためです。</span><span class="sxs-lookup"><span data-stu-id="1b272-145">**✓ DO** use powers of two for the flag enum values so they can be freely combined using the bitwise OR operation.</span></span>

<span data-ttu-id="1b272-146">**✓ CONSIDER** フラグの組み合わせを使用してよくの特別な enum 値を提供します。</span><span class="sxs-lookup"><span data-stu-id="1b272-146">**✓ CONSIDER** providing special enum values for commonly used combinations of flags.</span></span>

<span data-ttu-id="1b272-147">ビットごとの演算は高度な概念であり、単純なタスクには必要ありません。</span><span class="sxs-lookup"><span data-stu-id="1b272-147">Bitwise operations are an advanced concept and should not be required for simple tasks.</span></span> <span data-ttu-id="1b272-148">このような特殊な値の例としては、<xref:System.IO.FileAccess.ReadWrite> があります。</span><span class="sxs-lookup"><span data-stu-id="1b272-148"><xref:System.IO.FileAccess.ReadWrite> is an example of such a special value.</span></span>

<span data-ttu-id="1b272-149">**X AVOID** 特定の値の組み合わせは有効なフラグ列挙型を作成します。</span><span class="sxs-lookup"><span data-stu-id="1b272-149">**X AVOID** creating flag enums where certain combinations of values are invalid.</span></span>

<span data-ttu-id="1b272-150">**X AVOID** 値が「すべてのフラグをクリアする」を表し、次のガイドラインで規定された方法、適切に名前がない限り、列挙型値ゼロのフラグを使用しています。</span><span class="sxs-lookup"><span data-stu-id="1b272-150">**X AVOID** using flag enum values of zero unless the value represents "all flags are cleared" and is named appropriately, as prescribed by the next guideline.</span></span>

<span data-ttu-id="1b272-151">**✓ DO** フラグ列挙型のゼロ値の名前を付けます`None`です。</span><span class="sxs-lookup"><span data-stu-id="1b272-151">**✓ DO** name the zero value of flag enums `None`.</span></span> <span data-ttu-id="1b272-152">フラグの列挙型の場合、値は常に "すべてのフラグがクリアされている" ことを意味します。</span><span class="sxs-lookup"><span data-stu-id="1b272-152">For a flag enum, the value must always mean "all flags are cleared."</span></span>

<a name="add_value"></a>

### <a name="adding-value-to-enums"></a><span data-ttu-id="1b272-153">列挙型への値の追加</span><span class="sxs-lookup"><span data-stu-id="1b272-153">Adding Value to Enums</span></span>

<span data-ttu-id="1b272-154">列挙型に値を追加する必要があることを既に確認しています。</span><span class="sxs-lookup"><span data-stu-id="1b272-154">It is very common to discover that you need to add values to an enum after you have already shipped it.</span></span> <span data-ttu-id="1b272-155">新しく追加された値が既存の API から返された場合、アプリケーションの互換性の問題が発生する可能性があります。これは、正しく記述されていないアプリケーションが新しい値を正しく処理できない可能性があるためです。</span><span class="sxs-lookup"><span data-stu-id="1b272-155">There is a potential application compatibility problem when the newly added value is returned from an existing API, because poorly written applications might not handle the new value correctly.</span></span>

<span data-ttu-id="1b272-156">**✓ CONSIDER** 小さい互換性上のリスクに関係なく、列挙型に値を追加します。</span><span class="sxs-lookup"><span data-stu-id="1b272-156">**✓ CONSIDER** adding values to enums, despite a small compatibility risk.</span></span>

<span data-ttu-id="1b272-157">列挙型への追加によって発生するアプリケーションの非互換性に関する実際のデータがある場合は、新しい値と古い値を返す新しい API を追加し、古い API を廃止することを検討してください。これにより、古い値だけが返されます。</span><span class="sxs-lookup"><span data-stu-id="1b272-157">If you have real data about application incompatibilities caused by additions to an enum, consider adding a new API that returns the new and old values, and deprecate the old API, which should continue returning just the old values.</span></span> <span data-ttu-id="1b272-158">これにより、既存のアプリケーションに互換性があることが保証されます。</span><span class="sxs-lookup"><span data-stu-id="1b272-158">This will ensure that your existing applications remain compatible.</span></span>

<span data-ttu-id="1b272-159">*©2005、2009 Microsoft Corporation の部分。すべての権限が予約されています。*</span><span class="sxs-lookup"><span data-stu-id="1b272-159">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

<span data-ttu-id="1b272-160">*2008 年 10 月 22 日に Microsoft Windows Development シリーズの一部として、Addison-Wesley Professional によって発行された、Krzysztof Cwalina および Brad Abrams による「[Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)」 (フレームワーク デザイン ガイドライン: 再利用可能な .NET ライブラリの規則、用法、パターン、第 2 版) から Pearson Education, Inc. の許可を得て再印刷されています。*</span><span class="sxs-lookup"><span data-stu-id="1b272-160">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="1b272-161">関連項目</span><span class="sxs-lookup"><span data-stu-id="1b272-161">See also</span></span>

- [<span data-ttu-id="1b272-162">型デザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="1b272-162">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)
- [<span data-ttu-id="1b272-163">フレームワーク デザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="1b272-163">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
