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
author: KrzysztofCwalina
ms.openlocfilehash: 36e1f62ab1b236d48a55f7c255ed406cc0efa488
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64615247"
---
# <a name="enum-design"></a><span data-ttu-id="1d48b-102">列挙型デザイン</span><span class="sxs-lookup"><span data-stu-id="1d48b-102">Enum Design</span></span>
<span data-ttu-id="1d48b-103">列挙は、特殊な値の型です。</span><span class="sxs-lookup"><span data-stu-id="1d48b-103">Enums are a special kind of value type.</span></span> <span data-ttu-id="1d48b-104">列挙型の 2 種類があります。 単純な列挙型、およびフラグの列挙型。</span><span class="sxs-lookup"><span data-stu-id="1d48b-104">There are two kinds of enums: simple enums and flag enums.</span></span>  
  
 <span data-ttu-id="1d48b-105">単純な列挙型では、選択肢の小規模の閉じたセットを表します。</span><span class="sxs-lookup"><span data-stu-id="1d48b-105">Simple enums represent small closed sets of choices.</span></span> <span data-ttu-id="1d48b-106">単純な列挙型の一般的な例は、色のセットです。</span><span class="sxs-lookup"><span data-stu-id="1d48b-106">A common example of the simple enum is a set of colors.</span></span>  
  
 <span data-ttu-id="1d48b-107">フラグ列挙型は、列挙値のビットごとの演算をサポートするために設計されています。</span><span class="sxs-lookup"><span data-stu-id="1d48b-107">Flag enums are designed to support bitwise operations on the enum values.</span></span> <span data-ttu-id="1d48b-108">フラグ列挙型の一般的な例では、オプションの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="1d48b-108">A common example of the flags enum is a list of options.</span></span>  
  
 <span data-ttu-id="1d48b-109">**✓ DO** を厳密に型パラメーター、プロパティ、列挙型を使用し、戻り値のセットを表す値です。</span><span class="sxs-lookup"><span data-stu-id="1d48b-109">**✓ DO** use an enum to strongly type parameters, properties, and return values that represent sets of values.</span></span>  
  
 <span data-ttu-id="1d48b-110">**✓ DO** 列挙型を静的な定数の代わりに使用をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1d48b-110">**✓ DO** favor using an enum instead of static constants.</span></span>  
  
 <span data-ttu-id="1d48b-111">**X DO NOT** (など、オペレーティング システムのバージョン、友人などの名前)、開いているセットの列挙型を使用します。</span><span class="sxs-lookup"><span data-stu-id="1d48b-111">**X DO NOT** use an enum for open sets (such as the operating system version, names of your friends, etc.).</span></span>  
  
 <span data-ttu-id="1d48b-112">**X DO NOT** 将来使用するためのものでは予約されている列挙値を提供します。</span><span class="sxs-lookup"><span data-stu-id="1d48b-112">**X DO NOT** provide reserved enum values that are intended for future use.</span></span>  
  
 <span data-ttu-id="1d48b-113">後の段階で既存の列挙体を単純に常に値を追加できます。</span><span class="sxs-lookup"><span data-stu-id="1d48b-113">You can always simply add values to the existing enum at a later stage.</span></span> <span data-ttu-id="1d48b-114">参照してください[列挙型に値を追加する](#add_value)列挙型に値を追加する方法の詳細についてはします。</span><span class="sxs-lookup"><span data-stu-id="1d48b-114">See [Adding Values to Enums](#add_value) for more details on adding values to enums.</span></span> <span data-ttu-id="1d48b-115">予約済みの値は煩雑に実際の値のセットをユーザー エラーが発生する傾向がありますだけです。</span><span class="sxs-lookup"><span data-stu-id="1d48b-115">Reserved values just pollute the set of real values and tend to lead to user errors.</span></span>  
  
 <span data-ttu-id="1d48b-116">**X AVOID** 1 つだけの値を持つ列挙型を公開することです。</span><span class="sxs-lookup"><span data-stu-id="1d48b-116">**X AVOID** publicly exposing enums with only one value.</span></span>  
  
 <span data-ttu-id="1d48b-117">C Api の将来の拡張性を確保するための一般的な方法では、メソッド シグネチャに予約済みのパラメーターを追加します。</span><span class="sxs-lookup"><span data-stu-id="1d48b-117">A common practice for ensuring future extensibility of C APIs is to add reserved parameters to method signatures.</span></span> <span data-ttu-id="1d48b-118">このような予約済みのパラメーターは、1 つの既定値を持つ列挙型として表現できます。</span><span class="sxs-lookup"><span data-stu-id="1d48b-118">Such reserved parameters can be expressed as enums with a single default value.</span></span> <span data-ttu-id="1d48b-119">これは、マネージ Api で実行する必要がありますされません。</span><span class="sxs-lookup"><span data-stu-id="1d48b-119">This should not be done in managed APIs.</span></span> <span data-ttu-id="1d48b-120">メソッドのオーバー ロードでは、パラメーターは今後のリリースを追加できます。</span><span class="sxs-lookup"><span data-stu-id="1d48b-120">Method overloading allows adding parameters in future releases.</span></span>  
  
 <span data-ttu-id="1d48b-121">**X DO NOT** enum で sentinel 値が含まれます。</span><span class="sxs-lookup"><span data-stu-id="1d48b-121">**X DO NOT** include sentinel values in enums.</span></span>  
  
 <span data-ttu-id="1d48b-122">フレームワークの開発者に役立つことがあります、sentinel 値は、フレームワークのユーザーが混乱します。</span><span class="sxs-lookup"><span data-stu-id="1d48b-122">Although they are sometimes helpful to framework developers, sentinel values are confusing to users of the framework.</span></span> <span data-ttu-id="1d48b-123">列挙型で表されるセットから値のいずれかの中ではなく、列挙型の状態を追跡するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="1d48b-123">They are used to track the state of the enum rather than being one of the values from the set represented by the enum.</span></span>  
  
 <span data-ttu-id="1d48b-124">**✓ DO** 単純な列挙型のゼロの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="1d48b-124">**✓ DO** provide a value of zero on simple enums.</span></span>  
  
 <span data-ttu-id="1d48b-125">値を"None"のように呼び出すことを検討してください。</span><span class="sxs-lookup"><span data-stu-id="1d48b-125">Consider calling the value something like "None."</span></span> <span data-ttu-id="1d48b-126">このような値がこの特定の列挙型に対して適切でない場合、列挙型の最も一般的な既定値は、基になる値の 0 割り当てする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1d48b-126">If such a value is not appropriate for this particular enum, the most common default value for the enum should be assigned the underlying value of zero.</span></span>  
  
 <span data-ttu-id="1d48b-127">**✓ CONSIDER** を使用して<xref:System.Int32>(ほとんどのプログラミング言語の既定値) enum の基になる型として、次のいずれかが当てはまる場合を除き、します。</span><span class="sxs-lookup"><span data-stu-id="1d48b-127">**✓ CONSIDER** using <xref:System.Int32> (the default in most programming languages) as the underlying type of an enum unless any of the following is true:</span></span>  
  
- <span data-ttu-id="1d48b-128">列挙型はフラグ列挙体を 32 を超えるのフラグが設定されてしたりするは詳細は、将来の予想されます。</span><span class="sxs-lookup"><span data-stu-id="1d48b-128">The enum is a flags enum and you have more than 32 flags, or expect to have more in the future.</span></span>  
  
- <span data-ttu-id="1d48b-129">基になる型が異なる必要があります<xref:System.Int32>のサイズの異なる列挙型を指定してください。 アンマネージ コードと相互運用を簡単にします。</span><span class="sxs-lookup"><span data-stu-id="1d48b-129">The underlying type needs to be different than <xref:System.Int32> for easier interoperability with unmanaged code expecting different-size enums.</span></span>  
  
- <span data-ttu-id="1d48b-130">小さな基になる型は、スペースで大幅に削減になります。</span><span class="sxs-lookup"><span data-stu-id="1d48b-130">A smaller underlying type would result in substantial savings in space.</span></span> <span data-ttu-id="1d48b-131">列挙型の制御フローの引数として主に使用する場合は、ほとんど違いは、サイズ。</span><span class="sxs-lookup"><span data-stu-id="1d48b-131">If you expect the enum to be used mainly as an argument for flow of control, the size makes little difference.</span></span> <span data-ttu-id="1d48b-132">サイズ削減量がかなり大きくなる場合。</span><span class="sxs-lookup"><span data-stu-id="1d48b-132">The size savings might be significant if:</span></span>  
  
    - <span data-ttu-id="1d48b-133">非常に頻繁にインスタンス化された構造体またはクラス内のフィールドとして使用される列挙型を期待します。</span><span class="sxs-lookup"><span data-stu-id="1d48b-133">You expect the enum to be used as a field in a very frequently instantiated structure or class.</span></span>  
  
    - <span data-ttu-id="1d48b-134">大きな配列または列挙型のインスタンスのコレクションを作成するユーザーを必要とします。</span><span class="sxs-lookup"><span data-stu-id="1d48b-134">You expect users to create large arrays or collections of the enum instances.</span></span>  
  
    - <span data-ttu-id="1d48b-135">シリアル化する列挙型のインスタンスの数が多いはずです。</span><span class="sxs-lookup"><span data-stu-id="1d48b-135">You expect a large number of instances of the enum to be serialized.</span></span>  
  
 <span data-ttu-id="1d48b-136">インメモリ使用量にマネージ オブジェクトが常には注意してください`DWORD`-配置するため、複数の列挙型、または合計インスタンス サイズは常にあるために、差別化する、するためを持つ小規模な列挙型をパックするインスタンスでの他の小規模な構造を効果的に必要四捨五入されますへ、`DWORD`します。</span><span class="sxs-lookup"><span data-stu-id="1d48b-136">For in-memory usage, be aware that managed objects are always `DWORD`-aligned, so you effectively need multiple enums or other small structures in an instance to pack a smaller enum with in order to make a difference, because the total instance size is always going to be rounded up to a `DWORD`.</span></span>  
  
 <span data-ttu-id="1d48b-137">**✓ DO** フラグの列挙型には複数形の名詞または名詞句と単数形の名詞または名詞句と単純な列挙型の名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="1d48b-137">**✓ DO** name flag enums with plural nouns or noun phrases and simple enums with singular nouns or noun phrases.</span></span>  
  
 <span data-ttu-id="1d48b-138">**X DO NOT** 拡張<xref:System.Enum?displayProperty=nameWithType>直接です。</span><span class="sxs-lookup"><span data-stu-id="1d48b-138">**X DO NOT** extend <xref:System.Enum?displayProperty=nameWithType> directly.</span></span>  
  
 <span data-ttu-id="1d48b-139"><xref:System.Enum?displayProperty=nameWithType> 特殊な種類、CLR によって列挙型のユーザー定義の作成に使用します。</span><span class="sxs-lookup"><span data-stu-id="1d48b-139"><xref:System.Enum?displayProperty=nameWithType> is a special type used by the CLR to create user-defined enumerations.</span></span> <span data-ttu-id="1d48b-140">ほとんどのプログラミング言語では、この機能にアクセスを提供するプログラミング要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="1d48b-140">Most programming languages provide a programming element that gives you access to this functionality.</span></span> <span data-ttu-id="1d48b-141">C# などの`enum`列挙体を定義するキーワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="1d48b-141">For example, in C# the `enum` keyword is used to define an enumeration.</span></span>  
  
<a name="design"></a>   
### <a name="designing-flag-enums"></a><span data-ttu-id="1d48b-142">フラグ列挙型の設計</span><span class="sxs-lookup"><span data-stu-id="1d48b-142">Designing Flag Enums</span></span>  
 <span data-ttu-id="1d48b-143">**✓ DO** 適用、<xref:System.FlagsAttribute?displayProperty=nameWithType>フラグ列挙体にします。</span><span class="sxs-lookup"><span data-stu-id="1d48b-143">**✓ DO** apply the <xref:System.FlagsAttribute?displayProperty=nameWithType> to flag enums.</span></span> <span data-ttu-id="1d48b-144">単純な列挙型にはこの属性は適用されません。</span><span class="sxs-lookup"><span data-stu-id="1d48b-144">Do not apply this attribute to simple enums.</span></span>  
  
 <span data-ttu-id="1d48b-145">**✓ DO** フラグ列挙値に 2 の累乗を使用して、自由に組み合わせてことができます、ビットごとの OR 演算を使用しているためです。</span><span class="sxs-lookup"><span data-stu-id="1d48b-145">**✓ DO** use powers of two for the flag enum values so they can be freely combined using the bitwise OR operation.</span></span>  
  
 <span data-ttu-id="1d48b-146">**✓ CONSIDER** フラグの組み合わせを使用してよくの特別な enum 値を提供します。</span><span class="sxs-lookup"><span data-stu-id="1d48b-146">**✓ CONSIDER** providing special enum values for commonly used combinations of flags.</span></span>  
  
 <span data-ttu-id="1d48b-147">ビットごとの演算は、高度な概念し、は単純な作業は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="1d48b-147">Bitwise operations are an advanced concept and should not be required for simple tasks.</span></span> <span data-ttu-id="1d48b-148"><xref:System.IO.FileAccess.ReadWrite> このような特殊な値の例に示します。</span><span class="sxs-lookup"><span data-stu-id="1d48b-148"><xref:System.IO.FileAccess.ReadWrite> is an example of such a special value.</span></span>  
  
 <span data-ttu-id="1d48b-149">**X AVOID** 特定の値の組み合わせは有効なフラグ列挙型を作成します。</span><span class="sxs-lookup"><span data-stu-id="1d48b-149">**X AVOID** creating flag enums where certain combinations of values are invalid.</span></span>  
  
 <span data-ttu-id="1d48b-150">**X AVOID** 値が「すべてのフラグをクリアする」を表し、次のガイドラインで規定された方法、適切に名前がない限り、列挙型値ゼロのフラグを使用しています。</span><span class="sxs-lookup"><span data-stu-id="1d48b-150">**X AVOID** using flag enum values of zero unless the value represents "all flags are cleared" and is named appropriately, as prescribed by the next guideline.</span></span>  
  
 <span data-ttu-id="1d48b-151">**✓ DO** フラグ列挙型のゼロ値の名前を付けます`None`です。</span><span class="sxs-lookup"><span data-stu-id="1d48b-151">**✓ DO** name the zero value of flag enums `None`.</span></span> <span data-ttu-id="1d48b-152">フラグ列挙型では、値必要がありますとは限りません"すべてのフラグがクリアされます"</span><span class="sxs-lookup"><span data-stu-id="1d48b-152">For a flag enum, the value must always mean "all flags are cleared."</span></span>  
  
<a name="add_value"></a>   
### <a name="adding-value-to-enums"></a><span data-ttu-id="1d48b-153">列挙型に値を追加</span><span class="sxs-lookup"><span data-stu-id="1d48b-153">Adding Value to Enums</span></span>  
 <span data-ttu-id="1d48b-154">既に配布した後に、列挙型に値を追加する必要があることを検出する非常に一般的です。</span><span class="sxs-lookup"><span data-stu-id="1d48b-154">It is very common to discover that you need to add values to an enum after you have already shipped it.</span></span> <span data-ttu-id="1d48b-155">潜在的なアプリケーション互換性問題を新しく追加された値が、既存の API から返されるためには適切に記述されたアプリケーションの新しい値を正しく処理されない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1d48b-155">There is a potential application compatibility problem when the newly added value is returned from an existing API, because poorly written applications might not handle the new value correctly.</span></span>  
  
 <span data-ttu-id="1d48b-156">**✓ CONSIDER** 小さい互換性上のリスクに関係なく、列挙型に値を追加します。</span><span class="sxs-lookup"><span data-stu-id="1d48b-156">**✓ CONSIDER** adding values to enums, despite a small compatibility risk.</span></span>  
  
 <span data-ttu-id="1d48b-157">列挙型への追加によるアプリケーション互換性に関する実際のデータがあれば、新旧の値を返す新しい API の追加を検討して、古い値だけを返すことは引き続き以前の API の廃止します。</span><span class="sxs-lookup"><span data-stu-id="1d48b-157">If you have real data about application incompatibilities caused by additions to an enum, consider adding a new API that returns the new and old values, and deprecate the old API, which should continue returning just the old values.</span></span> <span data-ttu-id="1d48b-158">これにより、既存のアプリケーションの互換性を保つことが保証されます。</span><span class="sxs-lookup"><span data-stu-id="1d48b-158">This will ensure that your existing applications remain compatible.</span></span>  
  
 <span data-ttu-id="1d48b-159">*Portions © 2005, 2009 Microsoft Corporation.All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="1d48b-159">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="1d48b-160">*Pearson Education, Inc. からのアクセス許可によって了承を得て転載[Framework デザイン ガイドライン。規則、手法、および再利用可能な .NET ライブラリの第 2 版のパターン](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)Krzysztof Cwalina、Brad 内容では、Microsoft Windows の開発シリーズの一部として、Addison-wesley Professional、2008 年 10 月 22日を公開します。*</span><span class="sxs-lookup"><span data-stu-id="1d48b-160">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d48b-161">関連項目</span><span class="sxs-lookup"><span data-stu-id="1d48b-161">See also</span></span>

- [<span data-ttu-id="1d48b-162">型デザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="1d48b-162">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)
- [<span data-ttu-id="1d48b-163">フレームワーク デザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="1d48b-163">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
