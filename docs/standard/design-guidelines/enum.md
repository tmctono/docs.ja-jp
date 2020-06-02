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
ms.openlocfilehash: efdfcda95a67941f0fde5f7a96467af7dd374396
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2020
ms.locfileid: "84280141"
---
# <a name="enum-design"></a><span data-ttu-id="91d6d-102">列挙型デザイン</span><span class="sxs-lookup"><span data-stu-id="91d6d-102">Enum Design</span></span>

<span data-ttu-id="91d6d-103">列挙型は、特別な種類の値型です。</span><span class="sxs-lookup"><span data-stu-id="91d6d-103">Enums are a special kind of value type.</span></span> <span data-ttu-id="91d6d-104">列挙型には、単純な列挙型とフラグ列挙型の2種類があります。</span><span class="sxs-lookup"><span data-stu-id="91d6d-104">There are two kinds of enums: simple enums and flag enums.</span></span>

<span data-ttu-id="91d6d-105">単純な列挙型は、選択の小さな閉じられたセットを表します。</span><span class="sxs-lookup"><span data-stu-id="91d6d-105">Simple enums represent small closed sets of choices.</span></span> <span data-ttu-id="91d6d-106">単純な列挙型の一般的な例としては、一連の色があります。</span><span class="sxs-lookup"><span data-stu-id="91d6d-106">A common example of the simple enum is a set of colors.</span></span>

<span data-ttu-id="91d6d-107">フラグ列挙型は、列挙値のビットごとの演算をサポートするように設計されています。</span><span class="sxs-lookup"><span data-stu-id="91d6d-107">Flag enums are designed to support bitwise operations on the enum values.</span></span> <span data-ttu-id="91d6d-108">Flags 列挙型の一般的な例として、オプションの一覧があります。</span><span class="sxs-lookup"><span data-stu-id="91d6d-108">A common example of the flags enum is a list of options.</span></span>

<span data-ttu-id="91d6d-109">厳密に型指定されたパラメーター、プロパティ、および値のセットを表す戻り値には、列挙型を使用✔️ます。</span><span class="sxs-lookup"><span data-stu-id="91d6d-109">✔️ DO use an enum to strongly type parameters, properties, and return values that represent sets of values.</span></span>

<span data-ttu-id="91d6d-110">✔️は、静的な定数ではなく列挙型を使用するようにします。</span><span class="sxs-lookup"><span data-stu-id="91d6d-110">✔️ DO favor using an enum instead of static constants.</span></span>

<span data-ttu-id="91d6d-111">❌オープンセットには列挙型を使用しないでください (オペレーティングシステムのバージョン、友人の名前など)。</span><span class="sxs-lookup"><span data-stu-id="91d6d-111">❌ DO NOT use an enum for open sets (such as the operating system version, names of your friends, etc.).</span></span>

<span data-ttu-id="91d6d-112">❌将来使用するための予約済み列挙値を指定しないでください。</span><span class="sxs-lookup"><span data-stu-id="91d6d-112">❌ DO NOT provide reserved enum values that are intended for future use.</span></span>

<span data-ttu-id="91d6d-113">後の段階で、既存の列挙に値をいつでも追加できます。</span><span class="sxs-lookup"><span data-stu-id="91d6d-113">You can always simply add values to the existing enum at a later stage.</span></span> <span data-ttu-id="91d6d-114">列挙型に値を追加する方法の詳細については、「[列挙型への値の追加](#add_value)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="91d6d-114">See [Adding Values to Enums](#add_value) for more details on adding values to enums.</span></span> <span data-ttu-id="91d6d-115">予約済みの値は、実際の値のセットを汚染するだけで、ユーザーエラーにつながる傾向があります。</span><span class="sxs-lookup"><span data-stu-id="91d6d-115">Reserved values just pollute the set of real values and tend to lead to user errors.</span></span>

<span data-ttu-id="91d6d-116">❌1つの値のみを使用して enum を公開しないようにします。</span><span class="sxs-lookup"><span data-stu-id="91d6d-116">❌ AVOID publicly exposing enums with only one value.</span></span>

<span data-ttu-id="91d6d-117">C Api の将来の拡張性を確保するための一般的な方法は、メソッドシグネチャに予約済みのパラメーターを追加することです。</span><span class="sxs-lookup"><span data-stu-id="91d6d-117">A common practice for ensuring future extensibility of C APIs is to add reserved parameters to method signatures.</span></span> <span data-ttu-id="91d6d-118">このような予約済みのパラメーターは、単一の既定値を持つ列挙型として表すことができます。</span><span class="sxs-lookup"><span data-stu-id="91d6d-118">Such reserved parameters can be expressed as enums with a single default value.</span></span> <span data-ttu-id="91d6d-119">これは、マネージ Api では実行できません。</span><span class="sxs-lookup"><span data-stu-id="91d6d-119">This should not be done in managed APIs.</span></span> <span data-ttu-id="91d6d-120">メソッドのオーバーロードでは、将来のリリースでパラメーターを追加できます。</span><span class="sxs-lookup"><span data-stu-id="91d6d-120">Method overloading allows adding parameters in future releases.</span></span>

<span data-ttu-id="91d6d-121">❌列挙型には、sentinel 値を含めないでください。</span><span class="sxs-lookup"><span data-stu-id="91d6d-121">❌ DO NOT include sentinel values in enums.</span></span>

<span data-ttu-id="91d6d-122">Framework 開発者にとっては便利な場合もありますが、sentinel 値はフレームワークのユーザーにとって混乱を招くことがあります。</span><span class="sxs-lookup"><span data-stu-id="91d6d-122">Although they are sometimes helpful to framework developers, sentinel values are confusing to users of the framework.</span></span> <span data-ttu-id="91d6d-123">列挙型によって表されるセットの値の1つではなく、列挙型の状態を追跡するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="91d6d-123">They are used to track the state of the enum rather than being one of the values from the set represented by the enum.</span></span>

<span data-ttu-id="91d6d-124">単純な列挙型で値0を指定する✔️ます。</span><span class="sxs-lookup"><span data-stu-id="91d6d-124">✔️ DO provide a value of zero on simple enums.</span></span>

<span data-ttu-id="91d6d-125">"None" のような値を呼び出すことを検討してください。</span><span class="sxs-lookup"><span data-stu-id="91d6d-125">Consider calling the value something like "None."</span></span> <span data-ttu-id="91d6d-126">このような値がこの特定の列挙型に適していない場合は、列挙型の最も一般的な既定値に0の基になる値を代入する必要があります。</span><span class="sxs-lookup"><span data-stu-id="91d6d-126">If such a value is not appropriate for this particular enum, the most common default value for the enum should be assigned the underlying value of zero.</span></span>

<span data-ttu-id="91d6d-127"><xref:System.Int32>次のいずれかに該当しない場合は、列挙型の基になる型として (ほとんどのプログラミング言語で既定) を使用することを✔️してください。</span><span class="sxs-lookup"><span data-stu-id="91d6d-127">✔️ CONSIDER using <xref:System.Int32> (the default in most programming languages) as the underlying type of an enum unless any of the following is true:</span></span>

- <span data-ttu-id="91d6d-128">列挙型はフラグの列挙型であり、32を超えるフラグがあるか、または今後さらに多くなることが予想されます。</span><span class="sxs-lookup"><span data-stu-id="91d6d-128">The enum is a flags enum and you have more than 32 flags, or expect to have more in the future.</span></span>

- <span data-ttu-id="91d6d-129"><xref:System.Int32>異なるサイズの列挙型が必要なアンマネージコードとの相互運用性を容易にするために、基になる型はとは異なる必要があります。</span><span class="sxs-lookup"><span data-stu-id="91d6d-129">The underlying type needs to be different than <xref:System.Int32> for easier interoperability with unmanaged code expecting different-size enums.</span></span>

- <span data-ttu-id="91d6d-130">基になる型が小さいと、スペースが大幅に節約されます。</span><span class="sxs-lookup"><span data-stu-id="91d6d-130">A smaller underlying type would result in substantial savings in space.</span></span> <span data-ttu-id="91d6d-131">列挙型が主に制御フローの引数として使用されることが予想される場合、サイズの違いはほとんどありません。</span><span class="sxs-lookup"><span data-stu-id="91d6d-131">If you expect the enum to be used mainly as an argument for flow of control, the size makes little difference.</span></span> <span data-ttu-id="91d6d-132">次の場合、サイズを節約することが重要になります。</span><span class="sxs-lookup"><span data-stu-id="91d6d-132">The size savings might be significant if:</span></span>

  - <span data-ttu-id="91d6d-133">非常に頻繁にインスタンス化される構造体またはクラスのフィールドとして列挙型を使用することを想定しています。</span><span class="sxs-lookup"><span data-stu-id="91d6d-133">You expect the enum to be used as a field in a very frequently instantiated structure or class.</span></span>

  - <span data-ttu-id="91d6d-134">ユーザーは、大規模な配列または列挙型インスタンスのコレクションを作成することを想定しています。</span><span class="sxs-lookup"><span data-stu-id="91d6d-134">You expect users to create large arrays or collections of the enum instances.</span></span>

  - <span data-ttu-id="91d6d-135">列挙型の多数のインスタンスをシリアル化することを想定しています。</span><span class="sxs-lookup"><span data-stu-id="91d6d-135">You expect a large number of instances of the enum to be serialized.</span></span>

<span data-ttu-id="91d6d-136">メモリ内での使用については、マネージオブジェクトが常に固定されていることに注意してください。したがって、インスタンス `DWORD` 全体のサイズは常にに切り上げられるため、より小さな列挙型をパックするために、インスタンス内に複数の列挙型またはその他の小さな構造体を効果的に使用する必要があり `DWORD` ます。</span><span class="sxs-lookup"><span data-stu-id="91d6d-136">For in-memory usage, be aware that managed objects are always `DWORD`-aligned, so you effectively need multiple enums or other small structures in an instance to pack a smaller enum with in order to make a difference, because the total instance size is always going to be rounded up to a `DWORD`.</span></span>

<span data-ttu-id="91d6d-137">✔️は、複数形の名詞または名詞句を持つ列挙型と、単数形または名詞句を持つ単純な列挙型を使用します。</span><span class="sxs-lookup"><span data-stu-id="91d6d-137">✔️ DO name flag enums with plural nouns or noun phrases and simple enums with singular nouns or noun phrases.</span></span>

<span data-ttu-id="91d6d-138">❌を直接拡張しないで <xref:System.Enum?displayProperty=nameWithType> ください。</span><span class="sxs-lookup"><span data-stu-id="91d6d-138">❌ DO NOT extend <xref:System.Enum?displayProperty=nameWithType> directly.</span></span>

<span data-ttu-id="91d6d-139"><xref:System.Enum?displayProperty=nameWithType>は、ユーザー定義の列挙を作成するために CLR によって使用される特殊な型です。</span><span class="sxs-lookup"><span data-stu-id="91d6d-139"><xref:System.Enum?displayProperty=nameWithType> is a special type used by the CLR to create user-defined enumerations.</span></span> <span data-ttu-id="91d6d-140">ほとんどのプログラミング言語には、この機能にアクセスできるプログラミング要素が用意されています。</span><span class="sxs-lookup"><span data-stu-id="91d6d-140">Most programming languages provide a programming element that gives you access to this functionality.</span></span> <span data-ttu-id="91d6d-141">たとえば、C# では、 `enum` キーワードを使用して列挙型を定義します。</span><span class="sxs-lookup"><span data-stu-id="91d6d-141">For example, in C# the `enum` keyword is used to define an enumeration.</span></span>

<a name="design"></a>

### <a name="designing-flag-enums"></a><span data-ttu-id="91d6d-142">フラグ列挙型のデザイン</span><span class="sxs-lookup"><span data-stu-id="91d6d-142">Designing Flag Enums</span></span>

<span data-ttu-id="91d6d-143">✔️には、 <xref:System.FlagsAttribute?displayProperty=nameWithType> 列挙型にフラグを適用します。</span><span class="sxs-lookup"><span data-stu-id="91d6d-143">✔️ DO apply the <xref:System.FlagsAttribute?displayProperty=nameWithType> to flag enums.</span></span> <span data-ttu-id="91d6d-144">単純な列挙型にはこの属性を適用しないでください。</span><span class="sxs-lookup"><span data-stu-id="91d6d-144">Do not apply this attribute to simple enums.</span></span>

<span data-ttu-id="91d6d-145">フラグの列挙値には2の累乗を使用して、ビットごとの OR 演算を使用して自由に組み合わせることができるように✔️ます。</span><span class="sxs-lookup"><span data-stu-id="91d6d-145">✔️ DO use powers of two for the flag enum values so they can be freely combined using the bitwise OR operation.</span></span>

<span data-ttu-id="91d6d-146">一般的に使用されるフラグの組み合わせに対して特別な列挙値を指定することを✔️検討します。</span><span class="sxs-lookup"><span data-stu-id="91d6d-146">✔️ CONSIDER providing special enum values for commonly used combinations of flags.</span></span>

<span data-ttu-id="91d6d-147">ビットごとの演算は高度な概念であり、単純なタスクには必要ありません。</span><span class="sxs-lookup"><span data-stu-id="91d6d-147">Bitwise operations are an advanced concept and should not be required for simple tasks.</span></span> <span data-ttu-id="91d6d-148"><xref:System.IO.FileAccess.ReadWrite>このような特殊な値の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="91d6d-148"><xref:System.IO.FileAccess.ReadWrite> is an example of such a special value.</span></span>

<span data-ttu-id="91d6d-149">❌値の特定の組み合わせが無効な場合は、フラグの列挙型を作成しないようにします。</span><span class="sxs-lookup"><span data-stu-id="91d6d-149">❌ AVOID creating flag enums where certain combinations of values are invalid.</span></span>

<span data-ttu-id="91d6d-150">❌次のガイドラインで規定されているように、値が "すべてのフラグがクリアされています" を表し、適切な名前が付けられている場合を除き、フラグの列挙値0を使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="91d6d-150">❌ AVOID using flag enum values of zero unless the value represents "all flags are cleared" and is named appropriately, as prescribed by the next guideline.</span></span>

<span data-ttu-id="91d6d-151">✔️には、フラグの列挙型の0の値を指定 `None` します。</span><span class="sxs-lookup"><span data-stu-id="91d6d-151">✔️ DO name the zero value of flag enums `None`.</span></span> <span data-ttu-id="91d6d-152">フラグの列挙型の場合、値は常に "すべてのフラグがクリアされている" ことを意味します。</span><span class="sxs-lookup"><span data-stu-id="91d6d-152">For a flag enum, the value must always mean "all flags are cleared."</span></span>

<a name="add_value"></a>

### <a name="adding-value-to-enums"></a><span data-ttu-id="91d6d-153">列挙型への値の追加</span><span class="sxs-lookup"><span data-stu-id="91d6d-153">Adding Value to Enums</span></span>

<span data-ttu-id="91d6d-154">列挙型に値を追加する必要があることを既に確認しています。</span><span class="sxs-lookup"><span data-stu-id="91d6d-154">It is very common to discover that you need to add values to an enum after you have already shipped it.</span></span> <span data-ttu-id="91d6d-155">新しく追加された値が既存の API から返された場合、アプリケーションの互換性の問題が発生する可能性があります。これは、正しく記述されていないアプリケーションが新しい値を正しく処理できない可能性があるためです。</span><span class="sxs-lookup"><span data-stu-id="91d6d-155">There is a potential application compatibility problem when the newly added value is returned from an existing API, because poorly written applications might not handle the new value correctly.</span></span>

<span data-ttu-id="91d6d-156">互換性のリスクが小さいとしても、列挙値に値を追加することを検討✔️。</span><span class="sxs-lookup"><span data-stu-id="91d6d-156">✔️ CONSIDER adding values to enums, despite a small compatibility risk.</span></span>

<span data-ttu-id="91d6d-157">列挙型への追加によって発生するアプリケーションの非互換性に関する実際のデータがある場合は、新しい値と古い値を返す新しい API を追加し、古い API を廃止することを検討してください。これにより、古い値だけが返されます。</span><span class="sxs-lookup"><span data-stu-id="91d6d-157">If you have real data about application incompatibilities caused by additions to an enum, consider adding a new API that returns the new and old values, and deprecate the old API, which should continue returning just the old values.</span></span> <span data-ttu-id="91d6d-158">これにより、既存のアプリケーションに互換性があることが保証されます。</span><span class="sxs-lookup"><span data-stu-id="91d6d-158">This will ensure that your existing applications remain compatible.</span></span>

<span data-ttu-id="91d6d-159">*©2005、2009 Microsoft Corporation の部分。すべての権限が予約されています。*</span><span class="sxs-lookup"><span data-stu-id="91d6d-159">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

<span data-ttu-id="91d6d-160">*2008 年 10 月 22 日に Microsoft Windows Development シリーズの一部として、Addison-Wesley Professional によって発行された、Krzysztof Cwalina および Brad Abrams による「[Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)」 (フレームワーク デザイン ガイドライン: 再利用可能な .NET ライブラリの規則、用法、パターン、第 2 版) から Pearson Education, Inc. の許可を得て再印刷されています。*</span><span class="sxs-lookup"><span data-stu-id="91d6d-160">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="91d6d-161">関連項目</span><span class="sxs-lookup"><span data-stu-id="91d6d-161">See also</span></span>

- [<span data-ttu-id="91d6d-162">型デザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="91d6d-162">Type Design Guidelines</span></span>](type.md)
- [<span data-ttu-id="91d6d-163">フレームワークデザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="91d6d-163">Framework Design Guidelines</span></span>](index.md)
