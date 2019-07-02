---
title: 破壊的変更を評価する - .NET Core
description: .NET Core が開発者のために .NET バージョンをまたいで互換性を維持するために試行している方法について説明します。
author: rpetrusha
ms.author: ronpet
ms.date: 06/10/2019
ms.openlocfilehash: b58edd9ff0bd56b12b861162cc92d484a3b36c8b
ms.sourcegitcommit: a970268118ea61ce14207e0916e17243546a491f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/21/2019
ms.locfileid: "67307551"
---
# <a name="evaluate-breaking-changes-in-net-core"></a><span data-ttu-id="ac296-103">.NET Core の破壊的変更を評価する</span><span class="sxs-lookup"><span data-stu-id="ac296-103">Evaluate breaking changes in .NET Core</span></span>

<span data-ttu-id="ac296-104">.NET は、その歴史を通じて、バージョンからバージョンへ、.NET のさまざまなフレーバー間で高いレベルの互換性を維持しようと試行してきました。</span><span class="sxs-lookup"><span data-stu-id="ac296-104">Throughout its history, .NET has attempted to maintain a high level of compatibility from version to version and across flavors of .NET.</span></span> <span data-ttu-id="ac296-105">これは .NET Core でも引き続き同様の状況です。</span><span class="sxs-lookup"><span data-stu-id="ac296-105">This continues to be true for .NET Core.</span></span> <span data-ttu-id="ac296-106">.NET Core は、.NET Framework から独立した新しいテクノロジと見なすことができますが、.NET Core が .NET Framework から逸脱する能力を制限する主な要因が 2 つあります。</span><span class="sxs-lookup"><span data-stu-id="ac296-106">Although .NET Core can be considered as a new technology that is independent of the .NET Framework, two major factors limit the ability of .NET Core to diverge from .NET Framework:</span></span>

- <span data-ttu-id="ac296-107">開発者の多くは、.NET Framework アプリケーションをもともと開発していたか、現在も開発を続けています。</span><span class="sxs-lookup"><span data-stu-id="ac296-107">A large number of developers either originally developed or continue to develop .NET Framework applications.</span></span> <span data-ttu-id="ac296-108">.NET の実装間には一貫した動作が期待されます。</span><span class="sxs-lookup"><span data-stu-id="ac296-108">They expect consistent behavior across .NET implementations.</span></span>

- <span data-ttu-id="ac296-109">.NET Standard ライブラリ プロジェクトを使用すると、開発者は .NET Core と .NET Framework で共有される共通の API をターゲットとするライブラリを作成できます。</span><span class="sxs-lookup"><span data-stu-id="ac296-109">.NET Standard library projects allow developers to create libraries that target common APIs shared by .NET Core and .NET Framework.</span></span> <span data-ttu-id="ac296-110">開発者は、.NET Core アプリケーションで使用されるライブラリが、.NET Framework アプリケーションで使用される同じライブラリと同じように動作するはずであると期待します。</span><span class="sxs-lookup"><span data-stu-id="ac296-110">Developers expect that a library used in a .NET Core application should behave identically to the same library used in a .NET Framework application.</span></span>

<span data-ttu-id="ac296-111">.NET 実装間の互換性と共に、開発者は .NET Core バージョン間の高いレベルの互換性を期待しています。</span><span class="sxs-lookup"><span data-stu-id="ac296-111">Along with compatibility across .NET implementations, developers expect a high level of compatibility across .NET Core versions.</span></span> <span data-ttu-id="ac296-112">特に、以前のバージョンの .NET Core 用に書かれたコードは、新しいバージョンの .NET Core でもシームレスに動作するはずです。</span><span class="sxs-lookup"><span data-stu-id="ac296-112">In particular, code written for an earlier version of .NET Core should run seamlessly on a later version of .NET Core.</span></span> <span data-ttu-id="ac296-113">実際、多くの開発者は、新しくリリースされたバージョンの .NET Core にある新しい API が、それらの API が導入されたプレリリース バージョンとも互換性があると期待します。</span><span class="sxs-lookup"><span data-stu-id="ac296-113">In fact, many developers expect that the new APIs found in newly released versions of .NET Core should also be compatible with the pre-release versions in which those APIs were introduced.</span></span>

<span data-ttu-id="ac296-114">この記事では、互換性の変更 (つまり破壊的変更) のカテゴリと、.NET チームがこれらの各カテゴリの変更をどのように評価するかについて説明します。</span><span class="sxs-lookup"><span data-stu-id="ac296-114">This article outlines the categories of compatibility changes (or breaking changes) and the way in which the .NET team evaluates changes in each of these categories.</span></span> <span data-ttu-id="ac296-115">既存の API の動作を変更する [dotnet/corefx](https://github.com/dotnet/corefx) GitHub リポジトリで、プル要求を開く開発者の場合、考えられる破壊的変更に .NET チームがどのように対処しているかを理解することは特に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ac296-115">Understanding how the .NET team approaches possible breaking changes is particularly helpful for developers who are opening pull requests in the [dotnet/corefx](https://github.com/dotnet/corefx) GitHub repository that modify the behavior of existing APIs.</span></span>

> [!NOTE]
> <span data-ttu-id="ac296-116">バイナリ互換性や下位互換性などの互換性カテゴリの定義については、「[Breaking change categories (破壊的変更のカテゴリ)](categories.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac296-116">For a definition of compatibility categories, such as binary compatibility and backward compatibility, see [Breaking change categories](categories.md).</span></span>

<span data-ttu-id="ac296-117">次のセクションでは、.NET Core API に加えられた変更のカテゴリと、アプリケーションの互換性に与える影響について説明します。</span><span class="sxs-lookup"><span data-stu-id="ac296-117">The following sections describes the categories of changes made to .NET Core APIs and their impact on application compatibility.</span></span> <span data-ttu-id="ac296-118">✔️ アイコンは、特定の種類の変更が許可されることを示し、❌ は許可されないことを示し、❓ は許可される場合と許可されない場合がある変更を示します。</span><span class="sxs-lookup"><span data-stu-id="ac296-118">The ✔️ icon indicates that a particular kind of change is allowed, ❌ indicates that it is disallowed, and  ❓ indicates a change that may or may not be allowed.</span></span> <span data-ttu-id="ac296-119">この最後のカテゴリの変更には、以前の動作の予測可能性、明確性、一貫性の程度の判断と評価が必要です。</span><span class="sxs-lookup"><span data-stu-id="ac296-119">Changes in this last category require judgment and an evaluation of how predictable, obvious, and consistent the previous behavior was.</span></span>

> [!NOTE]
> <span data-ttu-id="ac296-120">.NET Core ライブラリの変更がどのように評価されるかのガイドとして利用できるだけでなく、ライブラリ開発者はこれらの基準を使用して、複数の .NET の実装とバージョンをターゲットとするライブラリの変更を評価することもできます。</span><span class="sxs-lookup"><span data-stu-id="ac296-120">In addition to serving as a guide to how changes to .NET Core libraries are evaluated, library developers can also use these criteria to evaluate changes to their libraries that target multiple .NET implementations and versions.</span></span>

## <a name="modifications-to-the-public-contract"></a><span data-ttu-id="ac296-121">パブリック コントラクトの変更</span><span class="sxs-lookup"><span data-stu-id="ac296-121">Modifications to the public contract</span></span>

<span data-ttu-id="ac296-122">このカテゴリの変更によって、型のパブリック セキュリティが "*変わります*"。</span><span class="sxs-lookup"><span data-stu-id="ac296-122">Changes in this category *modify* the public surface area of a type.</span></span> <span data-ttu-id="ac296-123">このカテゴリの変更のほとんどは、"*後方互換性*" に違反しているため、許可されません (以前のバージョンの API で開発されたアプリケーションが新しいバージョン上で再コンパイルすることなく実行できること)。</span><span class="sxs-lookup"><span data-stu-id="ac296-123">Most of the changes in this category are disallowed since they violate *backwards compatibility* (the ability of an application that was developed with a previous version of an API to execute without recompilation on a later version).</span></span>

### <a name="types"></a><span data-ttu-id="ac296-124">型</span><span class="sxs-lookup"><span data-stu-id="ac296-124">Types</span></span>

- <span data-ttu-id="ac296-125">**✔️ インターフェイスが既に基本データ型で実装されている場合に、型からインターフェイスの実装を削除する**</span><span class="sxs-lookup"><span data-stu-id="ac296-125">**✔️ Removing an interface implementation from a type when the interface is already implemented by a base type**</span></span>

- <span data-ttu-id="ac296-126">**❓ 型への新しいインターフェイス実装を追加する**</span><span class="sxs-lookup"><span data-stu-id="ac296-126">**❓ Adding a new interface implementation to a type**</span></span>

  <span data-ttu-id="ac296-127">既存のクライアントに悪影響を及ぼさないため、これは許容できる変更です。</span><span class="sxs-lookup"><span data-stu-id="ac296-127">This is an acceptable change because it does not adversely affect existing clients.</span></span> <span data-ttu-id="ac296-128">新しい実装が許容できる状態を維持するには、型に対するすべての変更が、ここで定義された許容可能な変更の境界内で機能する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac296-128">Any changes to the type must work within the boundaries of acceptable changes defined here for the new implementation to remain acceptable.</span></span> <span data-ttu-id="ac296-129">下位レベルでは消費できないコードやデータを生成するデザイナーやシリアライザーの能力に直接影響するインターフェイスを追加する場合は、細心の注意が必要です。</span><span class="sxs-lookup"><span data-stu-id="ac296-129">Extreme caution is necessary when adding interfaces that directly affect the ability of a designer or serializer to generate code or data that cannot be consumed down-level.</span></span> <span data-ttu-id="ac296-130">たとえば、<xref:System.Runtime.Serialization.ISerializable> インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="ac296-130">An example is the <xref:System.Runtime.Serialization.ISerializable> interface.</span></span>

- <span data-ttu-id="ac296-131">**❓ 新しい基底クラスの導入**</span><span class="sxs-lookup"><span data-stu-id="ac296-131">**❓ Introducing a new base class**</span></span>

  <span data-ttu-id="ac296-132">新しい [abstract](../../csharp/language-reference/keywords/abstract.md) メンバーを導入しない場合、または既存の型のセマンティクスまたは動作を変更しない場合は、既存の 2 つの型の間の階層に型を導入できます。</span><span class="sxs-lookup"><span data-stu-id="ac296-132">A type can be introduced into an hierarchy between two existing types if it doesn't introduce any new [abstract](../../csharp/language-reference/keywords/abstract.md) members or change the semantics or behavior of existing types.</span></span> <span data-ttu-id="ac296-133">たとえば、.NET Framework 2.0 では、<xref:System.Data.Common.DbConnection> クラスが <xref:System.Data.SqlClient.SqlConnection> の新しい基底クラスになりました。これは、以前は直接 <xref:System.ComponentModel.Component> から派生していました。</span><span class="sxs-lookup"><span data-stu-id="ac296-133">For example, in .NET Framework 2.0, the <xref:System.Data.Common.DbConnection> class became a new base class for <xref:System.Data.SqlClient.SqlConnection>, which had previously derived directly from <xref:System.ComponentModel.Component>.</span></span>

- <span data-ttu-id="ac296-134">**✔️ あるアセンブリから別のアセンブリに型を移動する**</span><span class="sxs-lookup"><span data-stu-id="ac296-134">**✔️ Moving a type from one assembly to another**</span></span>

  <span data-ttu-id="ac296-135">"*以前の*" アセンブリは、新しいアセンブリを指す <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute> でマークする必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="ac296-135">Note that the *old* assembly must be marked with the <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute> that points to the new assembly.</span></span>

- <span data-ttu-id="ac296-136">**✔️ [構造体](../../csharp/language-reference/keywords/struct.md)型を `readonly struct` 型に変更する**</span><span class="sxs-lookup"><span data-stu-id="ac296-136">**✔️ Changing a [struct](../../csharp/language-reference/keywords/struct.md) type to a `readonly struct` type**</span></span>

  <span data-ttu-id="ac296-137">`readonly struct` 型を `struct` 型に変更することはできないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="ac296-137">Note that changing a `readonly struct` type to a `struct` type is not allowed.</span></span>
  
- <span data-ttu-id="ac296-138">**✔️ "*アクセス可能な*" (パブリックまたは保護された) コンストラクターがない場合に[シールド](../../csharp/language-reference/keywords/sealed.md)または[抽象](../../csharp/language-reference/keywords/abstract.md)キーワードを型に追加する**</span><span class="sxs-lookup"><span data-stu-id="ac296-138">**✔️ Adding the [sealed](../../csharp/language-reference/keywords/sealed.md) or [abstract](../../csharp/language-reference/keywords/abstract.md) keyword to a type when there are no *accessible* (public or protected) constructors**</span></span>

- <span data-ttu-id="ac296-139">**✔️ 型の可視性を拡張する**</span><span class="sxs-lookup"><span data-stu-id="ac296-139">**✔️ Expanding the visibility of a type**</span></span>

- <span data-ttu-id="ac296-140">**❌ 型の名前空間または名前を変更する**</span><span class="sxs-lookup"><span data-stu-id="ac296-140">**❌ Changing the namespace or name of a type**</span></span>

- <span data-ttu-id="ac296-141">**❌ パブリック型の名前変更または削除**</span><span class="sxs-lookup"><span data-stu-id="ac296-141">**❌ Renaming or removing a public type**</span></span>

   <span data-ttu-id="ac296-142">これで、名前が変更された、または削除された型を使用するすべてのコードは互換性がなくなります。</span><span class="sxs-lookup"><span data-stu-id="ac296-142">This breaks all code that uses the renamed or removed type.</span></span>

- <span data-ttu-id="ac296-143">**❌ 列挙型の基になる型を変更する**</span><span class="sxs-lookup"><span data-stu-id="ac296-143">**❌ Changing the underlying type of an enumeration**</span></span>

   <span data-ttu-id="ac296-144">これは、コンパイル時と動作の破壊的変更であり、属性の引数が解析できなくなる可能性があるバイナリの破壊的変更もあります。</span><span class="sxs-lookup"><span data-stu-id="ac296-144">This is a compile-time and behavioral breaking change as well as a binary breaking change that can make attribute arguments unparsable.</span></span>

- <span data-ttu-id="ac296-145">**❌ 以前はアンシールドだった型をシールする**</span><span class="sxs-lookup"><span data-stu-id="ac296-145">**❌ Sealing a type that was previously unsealed**</span></span>

- <span data-ttu-id="ac296-146">**❌ インターフェイスの一連の基本データ型にインターフェイスを追加する**</span><span class="sxs-lookup"><span data-stu-id="ac296-146">**❌ Adding an interface to the set of base types of an interface**</span></span>

   <span data-ttu-id="ac296-147">あるインターフェイスが以前は実装していなかったインターフェイスを実装すると、そのインターフェイスの元のバージョンを実装していたすべての型は互換性がなくなります。</span><span class="sxs-lookup"><span data-stu-id="ac296-147">If an interface implements an interface that it previously did not implement, all types that implemented the original version of the interface are broken.</span></span>

- <span data-ttu-id="ac296-148">**❓ 一連の基底クラスからクラスを削除する、または実装済みの一連のインターフェイスからインターフェイスを削除する**</span><span class="sxs-lookup"><span data-stu-id="ac296-148">**❓ Removing a class from the set of base classes or an interface from the set of implemented interfaces**</span></span>

  <span data-ttu-id="ac296-149">インターフェイス削除の規則には 1 つの例外があります。削除したインターフェイスから派生するインターフェイスの実装を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="ac296-149">There is one exception to the rule for interface removal: you can add the implementation of an interface that derives from the removed interface.</span></span> <span data-ttu-id="ac296-150">たとえば、型またはインターフェイスが <xref:System.ComponentModel.IComponent> を実装し、それが <xref:System.IDisposable> を実装している場合は、<xref:System.IDisposable> を削除できます。</span><span class="sxs-lookup"><span data-stu-id="ac296-150">For example, you can remove <xref:System.IDisposable> if the type or interface now implements <xref:System.ComponentModel.IComponent>, which implements <xref:System.IDisposable>.</span></span>

- <span data-ttu-id="ac296-151">**❌ `readonly struct` 型を[構造体](../../csharp/language-reference/keywords/struct.md)型に変更する**</span><span class="sxs-lookup"><span data-stu-id="ac296-151">**❌ Changing a `readonly struct` type to a [struct](../../csharp/language-reference/keywords/struct.md) type**</span></span>

  <span data-ttu-id="ac296-152">`struct` 型から `readonly struct` 型への変更は許可されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="ac296-152">Note that the change of a `struct` type to a `readonly struct` type is allowed.</span></span>

- <span data-ttu-id="ac296-153">**❌ [構造体](../../csharp/language-reference/keywords/struct.md)型を `ref struct` 型に、またはその逆に変更する**</span><span class="sxs-lookup"><span data-stu-id="ac296-153">**❌ Changing a [struct](../../csharp/language-reference/keywords/struct.md) type to a `ref struct` type, and vice versa**</span></span>

- <span data-ttu-id="ac296-154">**❌ 型の可視性を下げる**</span><span class="sxs-lookup"><span data-stu-id="ac296-154">**❌ Reducing the visibility of a type**</span></span>

   <span data-ttu-id="ac296-155">ただし、型の可視性を上げることは許可されています。</span><span class="sxs-lookup"><span data-stu-id="ac296-155">However, increasing the visibility of a type is allowed.</span></span>

### <a name="members"></a><span data-ttu-id="ac296-156">メンバー</span><span class="sxs-lookup"><span data-stu-id="ac296-156">Members</span></span>

- <span data-ttu-id="ac296-157">**✔️ [仮想](../../csharp/language-reference/keywords/sealed.md)ではないメンバーの可視性を拡張する**</span><span class="sxs-lookup"><span data-stu-id="ac296-157">**✔️ Expanding the visibility of a member that is not [virtual](../../csharp/language-reference/keywords/sealed.md)**</span></span>

- <span data-ttu-id="ac296-158">**✔️ "*アクセス可能な*" (パブリックまたは保護された) コンストラクターを持たない、または型が[シールされている](../../csharp/language-reference/keywords/sealed.md)パブリック型に抽象メンバーを追加する**</span><span class="sxs-lookup"><span data-stu-id="ac296-158">**✔️ Adding an abstract member to a public type that has no *accessible* (public or protected) constructors, or the type is [sealed](../../csharp/language-reference/keywords/sealed.md)**</span></span>

  <span data-ttu-id="ac296-159">ただし、アクセス可能な (パブリックまたは保護された) コンストラクターを持ち、`sealed` ではない型に抽象メンバーを追加することは許可されていません。</span><span class="sxs-lookup"><span data-stu-id="ac296-159">However, adding an abstract member to a type that has accessible (public or protected) constructors and is not `sealed` is not allowed.</span></span>

- <span data-ttu-id="ac296-160">**✔️ 型にアクセス可能な (パブリックまたは保護された) コンストラクターがない、または型が[シールされている](../../csharp/language-reference/keywords/sealed.md)場合に、[保護された](../../csharp/language-reference/keywords/protected.md)メンバーの可視性を制限する**</span><span class="sxs-lookup"><span data-stu-id="ac296-160">**✔️ Restricting the visibility of a [protected](../../csharp/language-reference/keywords/protected.md) member when the type has no accessible (public or protected) constructors, or the type is [sealed](../../csharp/language-reference/keywords/sealed.md)**</span></span>

- <span data-ttu-id="ac296-161">**✔️ 削除された型より上位の層のクラスにメンバーを移動する**</span><span class="sxs-lookup"><span data-stu-id="ac296-161">**✔️ Moving a member into a class higher in the hierarchy than the type from which it was removed**</span></span>

- <span data-ttu-id="ac296-162">**✔️ オーバーライドの追加または削除**</span><span class="sxs-lookup"><span data-stu-id="ac296-162">**✔️ Adding or removing an override**</span></span>

  <span data-ttu-id="ac296-163">オーバーライドを導入すると、[ベース](../../csharp/language-reference/keywords/base.md)を呼び出すときに以前のコンシューマーでオーバーライドがスキップされる可能性があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="ac296-163">Note that introducing an override might cause previous consumers to skip over the override when calling [base](../../csharp/language-reference/keywords/base.md).</span></span>

- <span data-ttu-id="ac296-164">**✔️ 以前にクラスにコンストラクターがなかった場合に、既定の (パラメーターなしの) コンストラクターと共に、クラスにコンストラクターを追加する**</span><span class="sxs-lookup"><span data-stu-id="ac296-164">**✔️ Adding a constructor to a class, along with a default (parameterless) constructor if the class previously had no constructors**</span></span>

   <span data-ttu-id="ac296-165">ただし、既定のコンストラクターを "*追加することなく*" 以前にコンストラクターがなかったクラスにコンストラクターを追加することは許可されていません。</span><span class="sxs-lookup"><span data-stu-id="ac296-165">However, adding a constructor to a class that previously had no constructors *without* adding the default constructor is not allowed.</span></span>

- <span data-ttu-id="ac296-166">**✔️ メンバーを[抽象](../../csharp/language-reference/keywords/abstract.md)から[仮想](../../csharp/language-reference/keywords/virtual.md)に変更する**</span><span class="sxs-lookup"><span data-stu-id="ac296-166">**✔️ Changing a member from [abstract](../../csharp/language-reference/keywords/abstract.md) to [virtual](../../csharp/language-reference/keywords/virtual.md)**</span></span>

- <span data-ttu-id="ac296-167">**✔️ 戻り値を `ref readonly` から `ref` に変更する (仮想メソッドまたはインターフェイスを除く)**</span><span class="sxs-lookup"><span data-stu-id="ac296-167">**✔️ Changing from a `ref readonly` to a `ref` return value (except for virtual methods or interfaces)**</span></span>

- <span data-ttu-id="ac296-168">**✔️ フィールドの静的な型が可変値型ではない場合に、フィールドから[読み取り専用](../../csharp/language-reference/keywords/readonly.md)を削除する**</span><span class="sxs-lookup"><span data-stu-id="ac296-168">**✔️ Removing [readonly](../../csharp/language-reference/keywords/readonly.md) from a field, unless the static type of the field is a mutable value type**</span></span>

- <span data-ttu-id="ac296-169">**✔️ 以前定義されていなかった新しいイベントを呼び出す**</span><span class="sxs-lookup"><span data-stu-id="ac296-169">**✔️ Calling a new event that wasn't previously defined**</span></span>

- <span data-ttu-id="ac296-170">**❓ 新しいインスタンス フィールドを型に追加する**</span><span class="sxs-lookup"><span data-stu-id="ac296-170">**❓ Adding a new instance field to a type**</span></span>

   <span data-ttu-id="ac296-171">この変更はシリアル化に影響があります。</span><span class="sxs-lookup"><span data-stu-id="ac296-171">This change impacts serialization.</span></span>

- <span data-ttu-id="ac296-172">**❌ パブリック メンバーまたはパラメーターの名前変更または削除**</span><span class="sxs-lookup"><span data-stu-id="ac296-172">**❌ Renaming or removing a public member or parameter**</span></span>

   <span data-ttu-id="ac296-173">これで、名前が変更された、または削除されたメンバーまたはパラメーターを使用するすべてのコードは互換性がなくなります。</span><span class="sxs-lookup"><span data-stu-id="ac296-173">This breaks all code that uses the renamed or removed member, or parameter.</span></span>

   <span data-ttu-id="ac296-174">これには、列挙型メンバーの名前変更または削除だけでなく、プロパティからのゲッターまたはセッターの削除または名前変更も含まれることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="ac296-174">Note that this includes removing or renaming a getter or setter from a property, as well as renaming or removing enumeration members.</span></span>

- <span data-ttu-id="ac296-175">**❌ インターフェイスにメンバーを追加する**</span><span class="sxs-lookup"><span data-stu-id="ac296-175">**❌ Adding a member to an interface**</span></span>

- <span data-ttu-id="ac296-176">**❌ パブリック定数または列挙型メンバーの値を変更する**</span><span class="sxs-lookup"><span data-stu-id="ac296-176">**❌ Changing the value of a public constant or enumeration member**</span></span>

- <span data-ttu-id="ac296-177">**❌ プロパティ、フィールド、パラメーター、または戻り値の型を変更する**</span><span class="sxs-lookup"><span data-stu-id="ac296-177">**❌ Changing the type of a property, field, parameter, or return value**</span></span>

- <span data-ttu-id="ac296-178">**❌ パラメーターの順序の追加、削除、または変更**</span><span class="sxs-lookup"><span data-stu-id="ac296-178">**❌ Adding, removing, or changing the order of parameters**</span></span>

- <span data-ttu-id="ac296-179">**❌ [in](../../csharp/language-reference/keywords/in.md)、[out](../../csharp/language-reference/keywords/out.md)、または [ref](../../csharp/language-reference/keywords/ref.md) キーワードをパラメーターに追加または削除する**</span><span class="sxs-lookup"><span data-stu-id="ac296-179">**❌ Adding or removing the [in](../../csharp/language-reference/keywords/in.md), [out](../../csharp/language-reference/keywords/out.md) , or [ref](../../csharp/language-reference/keywords/ref.md) keyword from a parameter**</span></span>

- <span data-ttu-id="ac296-180">**❌ パラメーター名を変更する (大文字と小文字の変更も含む)**</span><span class="sxs-lookup"><span data-stu-id="ac296-180">**❌ Renaming a parameter (including changing its case)**</span></span>

  <span data-ttu-id="ac296-181">これは 2 つの理由で破壊的と見なされます。</span><span class="sxs-lookup"><span data-stu-id="ac296-181">This is considered breaking for two reasons:</span></span>
  
  - <span data-ttu-id="ac296-182">これは、Visual Basic の遅延バインディング機能や C# の[動的](../../csharp/language-reference/keywords/dynamic.md)など、遅延バインディングのシナリオの互換性がなくなります。</span><span class="sxs-lookup"><span data-stu-id="ac296-182">It breaks late-bound scenarios such as the late binding feature in Visual Basic and [dynamic](../../csharp/language-reference/keywords/dynamic.md) in C#.</span></span>
  
  - <span data-ttu-id="ac296-183">開発者が[名前付き引数](../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md#named-arguments)を使用すると、[ソースの互換性](categories.md#source-compatibility)がなくなります。</span><span class="sxs-lookup"><span data-stu-id="ac296-183">It breaks [source compatibility](categories.md#source-compatibility) when developers use [named arguments](../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md#named-arguments).</span></span>

- <span data-ttu-id="ac296-184">**❌ `ref` の戻り値から `ref readonly` の戻り値に変更する**</span><span class="sxs-lookup"><span data-stu-id="ac296-184">**❌ Changing from a `ref` return value to a `ref readonly` return value**</span></span>

- <span data-ttu-id="ac296-185">**❌ 仮想メソッドまたはインターフェイス上で戻り値を `ref readonly` から `ref` に変更する**</span><span class="sxs-lookup"><span data-stu-id="ac296-185">**❌️ Changing from a `ref readonly` to a `ref` return value on a virtual method or interface**</span></span>

- <span data-ttu-id="ac296-186">**❌ メンバーから[抽象](../../csharp/language-reference/keywords/abstract.md)を追加または削除する**</span><span class="sxs-lookup"><span data-stu-id="ac296-186">**❌ Adding or removing [abstract](../../csharp/language-reference/keywords/abstract.md) from a member**</span></span>

- <span data-ttu-id="ac296-187">**❌ メンバーから[仮想](../../csharp/language-reference/keywords/virtual.md)キーワードを削除する**</span><span class="sxs-lookup"><span data-stu-id="ac296-187">**❌ Removing the [virtual](../../csharp/language-reference/keywords/virtual.md) keyword from a member**</span></span>

  <span data-ttu-id="ac296-188">C# コンパイラでは [callvirt](<xref:System.Reflection.Emit.OpCodes.Callvirt>) 中間言語 (IL) 命令を発行して非仮想メソッドを呼び出す傾向があるので (`callvirt` は null チェックを行いますが、通常の呼び出しでは行われません)、多くの場合、これは破壊的変更ではありませんが、この動作はいくつかの理由で一定ではありません。</span><span class="sxs-lookup"><span data-stu-id="ac296-188">While this often is not a breaking change because the C# compiler tends to emit [callvirt](<xref:System.Reflection.Emit.OpCodes.Callvirt>) Intermediate Language (IL) instructions to call non-virtual methods (`callvirt` performs a null check, while a normal call doesn't), this behavior is not invariable for several reasons:</span></span>
  - <span data-ttu-id="ac296-189">.NET がターゲットにしている言語は C# だけではありません。</span><span class="sxs-lookup"><span data-stu-id="ac296-189">C# is not the only language that .NET targets.</span></span>
  
  - <span data-ttu-id="ac296-190">ターゲット メソッドが非仮想で、おそらく null ではない場合 ([?. null 反映演算子](../../csharp/language-reference/operators/member-access-operators.md#null-conditional-operators--and-)を介してアクセスされるメソッドなど) は常に、C# コンパイラでは `callvirt` を通常の呼び出しに最適化しようとします。</span><span class="sxs-lookup"><span data-stu-id="ac296-190">The C# compiler increasingly tries to optimize `callvirt` to a normal call whenever the target method is non-virtual and is probably not null (such as a method accessed through the [?. null propagation operator](../../csharp/language-reference/operators/member-access-operators.md#null-conditional-operators--and-)).</span></span>
  
  <span data-ttu-id="ac296-191">メソッドを仮想化することは、多くの場合、コンシューマー コードから最終的に非仮想的に呼び出されることを示します。</span><span class="sxs-lookup"><span data-stu-id="ac296-191">Making a method virtual means that the consumer code would often end up calling it non-virtually.</span></span>

- <span data-ttu-id="ac296-192">**❌ メンバーに[仮想](../../csharp/language-reference/keywords/virtual.md)キーワードを追加する**</span><span class="sxs-lookup"><span data-stu-id="ac296-192">**❌ Adding the [virtual](../../csharp/language-reference/keywords/virtual.md) keyword to a member**</span></span>

- <span data-ttu-id="ac296-193">**❌ 仮想メンバーを抽象化する**</span><span class="sxs-lookup"><span data-stu-id="ac296-193">**❌ Making a virtual member abstract**</span></span>

  <span data-ttu-id="ac296-194">[仮想メンバー](../../csharp/language-reference/keywords/virtual.md)には、派生クラスによってオーバーライド "*できる*" メソッド実装が用意されています。</span><span class="sxs-lookup"><span data-stu-id="ac296-194">A [virtual member](../../csharp/language-reference/keywords/virtual.md) provides a method implementation that *can be* overridden by a derived class.</span></span> <span data-ttu-id="ac296-195">[抽象メンバー](../../csharp/language-reference/keywords/abstract.md)には実装がないのでオーバーライドする "*必要があります*"。</span><span class="sxs-lookup"><span data-stu-id="ac296-195">An [abstract member](../../csharp/language-reference/keywords/abstract.md) provides no implementation and *must be* overridden.</span></span>

- <span data-ttu-id="ac296-196">**❌ アクセス可能な (パブリックまたは保護された) コンストラクターを持ち、[シール](../../csharp/language-reference/keywords/sealed.md)されていないパブリック型に抽象メンバーを追加する**</span><span class="sxs-lookup"><span data-stu-id="ac296-196">**❌ Adding an abstract member to a public type that has accessible (public or protected) constructors and that is not [sealed](../../csharp/language-reference/keywords/sealed.md)**</span></span>

- <span data-ttu-id="ac296-197">**❌ メンバーに[静的](../../csharp/language-reference/keywords/static.md)キーワードを追加または削除する**</span><span class="sxs-lookup"><span data-stu-id="ac296-197">**❌ Adding or removing the [static](../../csharp/language-reference/keywords/static.md) keyword from a member**</span></span>

- <span data-ttu-id="ac296-198">**❌ 既存のオーバーロードを排除し、異なる動作を定義するオーバーロードを追加する**</span><span class="sxs-lookup"><span data-stu-id="ac296-198">**❌ Adding an overload that precludes an existing overload and defines a different behavior**</span></span>

  <span data-ttu-id="ac296-199">これで、以前の過負荷にバインドされていた既存のクライアントは互換性がなくなります。</span><span class="sxs-lookup"><span data-stu-id="ac296-199">This breaks existing clients that were bound to the previous overload.</span></span> <span data-ttu-id="ac296-200">たとえば、クラスに <xref:System.UInt32> を受け取る単一バージョンのメソッドがある場合、既存のコンシューマーは <xref:System.Int32> 値を渡すときにそのオーバーロードに正常にバインドします。</span><span class="sxs-lookup"><span data-stu-id="ac296-200">For example, if a class has a single version of a method that accepts a <xref:System.UInt32>, an existing consumer will successfully bind to that overload when passing a <xref:System.Int32> value.</span></span> <span data-ttu-id="ac296-201">ただし、<xref:System.Int32> を受け取るオーバーロードを追加した場合、再コンパイル時または遅延バインディングの使用時に、コンパイラでは新しいオーバーロードにバインドされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="ac296-201">However, if you add an overload that accepts an <xref:System.Int32>, when recompiling or using late-binding, the compiler now binds to the new overload.</span></span> <span data-ttu-id="ac296-202">異なる動作結果になる場合、これは破壊的変更です。</span><span class="sxs-lookup"><span data-stu-id="ac296-202">If different behavior results, this is a breaking change.</span></span>

- <span data-ttu-id="ac296-203">**❌ 既定のコンストラクターを追加することなく以前にコンストラクターがなかったクラスにコンストラクターを追加する**</span><span class="sxs-lookup"><span data-stu-id="ac296-203">**❌ Adding a constructor to a class that previously had no constructor without adding the default constructor**</span></span>

- <span data-ttu-id="ac296-204">**❌️ フィールドに[読み取り専用](../../csharp/language-reference/keywords/readonly.md)を追加する**</span><span class="sxs-lookup"><span data-stu-id="ac296-204">**❌️ Adding [readonly](../../csharp/language-reference/keywords/readonly.md) to a field**</span></span>

- <span data-ttu-id="ac296-205">**❌ メンバーの可視性を下げる**</span><span class="sxs-lookup"><span data-stu-id="ac296-205">**❌ Reducing the visibility of a member**</span></span>

   <span data-ttu-id="ac296-206">これには、"*アクセス可能な*" (パブリックまたは保護された) コンストラクターを持ち、型が[シールド](../../csharp/language-reference/keywords/sealed.md)では "*ない*" 場合に、[保護された](../../csharp/language-reference/keywords/protected.md)メンバーの可視性を下げることも含まれます。</span><span class="sxs-lookup"><span data-stu-id="ac296-206">This includes reducing the visibility of a [protected](../../csharp/language-reference/keywords/protected.md) member when there are *accessible* (public or protected) constructors and the type is *not* [sealed](../../csharp/language-reference/keywords/sealed.md).</span></span> <span data-ttu-id="ac296-207">そうでない場合は、保護されたメンバーの可視性を下げることができます。</span><span class="sxs-lookup"><span data-stu-id="ac296-207">If this is not the case, reducing the visibility of a protected member is allowed.</span></span>

   <span data-ttu-id="ac296-208">メンバーの可視性を上げることは許可されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="ac296-208">Note that increasing the visibility of a member is allowed.</span></span>

- <span data-ttu-id="ac296-209">**❌ メンバーの型を変更する**</span><span class="sxs-lookup"><span data-stu-id="ac296-209">**❌ Changing the type of a member**</span></span>

   <span data-ttu-id="ac296-210">メソッドの戻り値、プロパティまたはフィールドの型は変更できません。</span><span class="sxs-lookup"><span data-stu-id="ac296-210">The return value of a method or the type of a property or field cannot be modified.</span></span> <span data-ttu-id="ac296-211">たとえば、<xref:System.Object> を返すメソッドのシグネチャを <xref:System.String> を返すように変更することはできません。その逆も同様です。</span><span class="sxs-lookup"><span data-stu-id="ac296-211">For example, the signature of a method that returns an <xref:System.Object> cannot be changed to return a <xref:System.String>, or vice versa.</span></span>

- <span data-ttu-id="ac296-212">**❌ 以前は状態がなかった構造体にフィールドを追加する**</span><span class="sxs-lookup"><span data-stu-id="ac296-212">**❌ Adding a field to a struct that previously had no state**</span></span>

  <span data-ttu-id="ac296-213">限定代入規則では、変数型がステートレス構造体である限り、未初期化変数の使用が許可されます。</span><span class="sxs-lookup"><span data-stu-id="ac296-213">Definite assignment rules allow the use of uninitialized variables so long as the variable type is a stateless struct.</span></span> <span data-ttu-id="ac296-214">構造体がステートフルになると、コードは未初期化データになる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ac296-214">If the struct is made stateful, code could end up with uninitialized data.</span></span> <span data-ttu-id="ac296-215">これは、ソースの破壊的変更とバイナリの破壊的変更の両方になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ac296-215">This is both potentially a source breaking and a binary breaking change.</span></span>

- <span data-ttu-id="ac296-216">**❌ 以前に発生したことのない既存のイベントを発生させる**</span><span class="sxs-lookup"><span data-stu-id="ac296-216">**❌ Firing an existing event when it was never fired before**</span></span>

## <a name="behavioral-changes"></a><span data-ttu-id="ac296-217">動作の変更</span><span class="sxs-lookup"><span data-stu-id="ac296-217">Behavioral changes</span></span>

### <a name="assemblies"></a><span data-ttu-id="ac296-218">アセンブリ</span><span class="sxs-lookup"><span data-stu-id="ac296-218">Assemblies</span></span>

- <span data-ttu-id="ac296-219">**✔️ 同じプラットフォームがまだサポートされているときにアセンブリを移植可能にする**</span><span class="sxs-lookup"><span data-stu-id="ac296-219">**✔️ Making an assembly portable when the same platforms are still supported**</span></span>

- <span data-ttu-id="ac296-220">**❌ アセンブリの名前を変更する**</span><span class="sxs-lookup"><span data-stu-id="ac296-220">**❌ Changing the name of an assembly**</span></span>
- <span data-ttu-id="ac296-221">**❌ アセンブリの公開キーを変更する**</span><span class="sxs-lookup"><span data-stu-id="ac296-221">**❌ Changing the public key of an assembly**</span></span>

### <a name="properties-fields-parameters-and-return-values"></a><span data-ttu-id="ac296-222">プロパティ、フィールド、パラメーター、および戻り値</span><span class="sxs-lookup"><span data-stu-id="ac296-222">Properties, fields, parameters, and return values</span></span>

- <span data-ttu-id="ac296-223">**✔️ プロパティ、フィールド、戻り値、または [out](../../csharp/language-reference/keywords/out-parameter-modifier.md) パラメーターの値を派生型に変更する**</span><span class="sxs-lookup"><span data-stu-id="ac296-223">**✔️ Changing the value of a property, field, return value, or [out](../../csharp/language-reference/keywords/out-parameter-modifier.md) parameter to a more derived type**</span></span>

  <span data-ttu-id="ac296-224">たとえば、型 <xref:System.Object> を返すメソッドからは <xref:System.String> インスタンスが返される可能性があります</span><span class="sxs-lookup"><span data-stu-id="ac296-224">For example, a method that returns a type of <xref:System.Object> can return a <xref:System.String> instance.</span></span> <span data-ttu-id="ac296-225">(ただし、メソッドのシグネチャは変更できません)。</span><span class="sxs-lookup"><span data-stu-id="ac296-225">(However, the method signature cannot change.)</span></span>

- <span data-ttu-id="ac296-226">**✔️ メンバーが[仮想](../../csharp/language-reference/keywords/virtual.md)ではない場合、プロパティまたはパラメーターに許容される値の範囲を広げる**</span><span class="sxs-lookup"><span data-stu-id="ac296-226">**✔️ Increasing the range of accepted values for a property or parameter if the member is not [virtual](../../csharp/language-reference/keywords/virtual.md)**</span></span>

  <span data-ttu-id="ac296-227">メソッドに渡すことができるか、メンバーから返される値の範囲は拡張できますが、パラメーターまたはメンバー型は拡張できません。</span><span class="sxs-lookup"><span data-stu-id="ac296-227">Note that while the range of values that can be passed to the method or are returned by the member can expand, the parameter or member type cannot.</span></span> <span data-ttu-id="ac296-228">たとえば、メソッドに渡される値は 0-124 から 0-255 に拡張できますが、パラメーターの型を <xref:System.Byte> から <xref:System.Int32> に変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="ac296-228">For example, while the values passed to a method can expand from 0-124 to 0-255, the parameter type cannot change from <xref:System.Byte> to <xref:System.Int32>.</span></span>

- <span data-ttu-id="ac296-229">**❌ メンバーが[仮想](../../csharp/language-reference/keywords/virtual.md)の場合、プロパティまたはパラメーターに許容される値の範囲を広げる**</span><span class="sxs-lookup"><span data-stu-id="ac296-229">**❌ Increasing the range of accepted values for a property or parameter if the member is [virtual](../../csharp/language-reference/keywords/virtual.md)**</span></span>

   <span data-ttu-id="ac296-230">この変更で、既存のオーバーライドされたメンバーは互換性がなくなり、値の拡張された範囲に対しては正しく機能しなくなります。</span><span class="sxs-lookup"><span data-stu-id="ac296-230">This change breaks existing overridden members, which will not function correctly for the extended range of values.</span></span>

- <span data-ttu-id="ac296-231">**❌ プロパティまたはパラメーターの許容される値の範囲を狭める**</span><span class="sxs-lookup"><span data-stu-id="ac296-231">**❌ Decreasing the range of accepted values for a property or parameter**</span></span>

- <span data-ttu-id="ac296-232">**❌ プロパティ、フィールド、戻り値、または [out](../../csharp/language-reference/keywords/out-parameter-modifier.md) パラメーターの戻り値の範囲を広げる**</span><span class="sxs-lookup"><span data-stu-id="ac296-232">**❌ Increasing the range of returned values for a property, field, return value, or [out](../../csharp/language-reference/keywords/out-parameter-modifier.md) parameter**</span></span>

- <span data-ttu-id="ac296-233">**❌ プロパティ、フィールド、メソッドの戻り値、または [out](../../csharp/language-reference/keywords/out-parameter-modifier.md) パラメーターの戻り値を変更する**</span><span class="sxs-lookup"><span data-stu-id="ac296-233">**❌ Changing the returned values for a property, field, method return value, or [out](../../csharp/language-reference/keywords/out-parameter-modifier.md) parameter**</span></span>

- <span data-ttu-id="ac296-234">**❌ プロパティ、フィールド、またはパラメーターの既定値を変更する**</span><span class="sxs-lookup"><span data-stu-id="ac296-234">**❌ Changing the default value of a property, field, or parameter**</span></span>

- <span data-ttu-id="ac296-235">**❌ 数値の戻り値の有効桁数を変更する**</span><span class="sxs-lookup"><span data-stu-id="ac296-235">**❌ Changing the precision of a numeric return value**</span></span>

- <span data-ttu-id="ac296-236">**❓ 入力の解析と新しい例外のスローの変更 (解析の動作がドキュメントで指定されていない場合でも)**</span><span class="sxs-lookup"><span data-stu-id="ac296-236">**❓ A change in the parsing of input and throwing new exceptions (even if parsing behavior is not specified in the documentation**</span></span>

### <a name="exceptions"></a><span data-ttu-id="ac296-237">例外</span><span class="sxs-lookup"><span data-stu-id="ac296-237">Exceptions</span></span>

- <span data-ttu-id="ac296-238">**✔️ 既存の例外ではなく派生した例外をスローする**</span><span class="sxs-lookup"><span data-stu-id="ac296-238">**✔️ Throwing a more derived exception than an existing exception**</span></span>

  <span data-ttu-id="ac296-239">新しい例外は既存の例外のサブクラスなので、以前の例外処理コードは引き続き例外を処理します。</span><span class="sxs-lookup"><span data-stu-id="ac296-239">Because the new exception is a subclass of an existing exception, previous exception handling code continues to handle the exception.</span></span> <span data-ttu-id="ac296-240">たとえば、.NET Framework 4 では、カルチャが見つからなかった場合、カルチャの作成および取得メソッドは <xref:System.ArgumentException> ではなく <xref:System.Globalization.CultureNotFoundException> をスローするようになりました。</span><span class="sxs-lookup"><span data-stu-id="ac296-240">For example, in .NET Framework 4, culture creation and retrieval methods began to throw a <xref:System.Globalization.CultureNotFoundException> instead of an <xref:System.ArgumentException> if the culture could not be found.</span></span> <span data-ttu-id="ac296-241"><xref:System.Globalization.CultureNotFoundException> は <xref:System.ArgumentException> から派生しているので、これは許容される変更です。</span><span class="sxs-lookup"><span data-stu-id="ac296-241">Because <xref:System.Globalization.CultureNotFoundException> derives from <xref:System.ArgumentException>, this is an acceptable change.</span></span>

- <span data-ttu-id="ac296-242">**✔️ <xref:System.NotSupportedException>、<xref:System.NotImplementedException>、<xref:System.NullReferenceException> よりも具体的な例外をスローする**</span><span class="sxs-lookup"><span data-stu-id="ac296-242">**✔️ Throwing a more specific exception than <xref:System.NotSupportedException>, <xref:System.NotImplementedException>, <xref:System.NullReferenceException>**</span></span>

- <span data-ttu-id="ac296-243">**✔️ 回復不能と見なされる例外をスローする**</span><span class="sxs-lookup"><span data-stu-id="ac296-243">**✔️ Throwing an exception that is considered unrecoverable**</span></span>

  <span data-ttu-id="ac296-244">おそらく、回復不能な例外はキャッチされませんが、代わりに高レベルの catch-all ハンドラーによって処理されます。</span><span class="sxs-lookup"><span data-stu-id="ac296-244">Unrecoverable exceptions should not be caught but instead should be handled by a high-level catch-all handler.</span></span> <span data-ttu-id="ac296-245">そのため、これらの明示的な例外をキャッチするコードをユーザーが持つことは期待されません。</span><span class="sxs-lookup"><span data-stu-id="ac296-245">Therefore, users are not expected to have code that catches these explicit exceptions.</span></span> <span data-ttu-id="ac296-246">回復不能な例外は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ac296-246">The unrecoverable exceptions are:</span></span>

  - <xref:System.AccessViolationException>
  - <xref:System.ExecutionEngineException>
  - <xref:System.Runtime.InteropServices.SEHException>
  - <xref:System.StackOverflowException>

- <span data-ttu-id="ac296-247">**✔️ 新しいコード パスで新しい例外をスローする**</span><span class="sxs-lookup"><span data-stu-id="ac296-247">**✔️ Throwing a new exception in a new code path**</span></span>

  <span data-ttu-id="ac296-248">例外は、新しいパラメーター値または状態で実行される新しいコードパスにのみ適用されます。これは、以前のバージョンをターゲットとする既存のコードでは実行できません。</span><span class="sxs-lookup"><span data-stu-id="ac296-248">The exception must apply only to a new code-path which is executed with new parameter values or state, and that can't be executed by existing code that targets the previous version.</span></span>

- <span data-ttu-id="ac296-249">**✔️ より堅牢な動作または新しいシナリオを有効にするために例外を削除する**</span><span class="sxs-lookup"><span data-stu-id="ac296-249">**✔️ Removing an exception to enable more robust behavior or new scenarios**</span></span>

  <span data-ttu-id="ac296-250">たとえば、以前は正の値のみを処理し、それ以外の場合は<xref:System.ArgumentOutOfRangeException> をスローする `Divide` メソッドは、例外をスローせずに負の値と正の値の両方をサポートするように変更できます。</span><span class="sxs-lookup"><span data-stu-id="ac296-250">For example, a `Divide` method that previously only handled positive values and threw an <xref:System.ArgumentOutOfRangeException> otherwise can be changed to support both negative and positive values without throwing an exception.</span></span>

- <span data-ttu-id="ac296-251">**✔️ エラー メッセージのテキストを変更する**</span><span class="sxs-lookup"><span data-stu-id="ac296-251">**✔️ Changing the text of an error message**</span></span>

  <span data-ttu-id="ac296-252">開発者は、エラー メッセージのテキストに頼るべきではありません。これはユーザーのカルチャに基づいて変わることもあります。</span><span class="sxs-lookup"><span data-stu-id="ac296-252">Developers should not rely on the text of error messages, which also change based on the user's culture.</span></span>

- <span data-ttu-id="ac296-253">**❌ 上記以外の場合に例外をスローする**</span><span class="sxs-lookup"><span data-stu-id="ac296-253">**❌ Throwing an exception in any other case not listed above**</span></span>

- <span data-ttu-id="ac296-254">**❌ 上記以外の場合の例外を削除する**</span><span class="sxs-lookup"><span data-stu-id="ac296-254">**❌ Removing an exception in any other case not listed above**</span></span>

### <a name="attributes"></a><span data-ttu-id="ac296-255">属性</span><span class="sxs-lookup"><span data-stu-id="ac296-255">Attributes</span></span>

- <span data-ttu-id="ac296-256">**✔️ 観測可能 "*ではない*" 属性の値を変更する**</span><span class="sxs-lookup"><span data-stu-id="ac296-256">**✔️ Changing the value of an attribute that is *not* observable**</span></span>

- <span data-ttu-id="ac296-257">**❌ 観測可能 "*である*" 属性の値を変更する**</span><span class="sxs-lookup"><span data-stu-id="ac296-257">**❌ Changing the value of an attribute that *is* observable**</span></span>

- <span data-ttu-id="ac296-258">**❓ 属性を削除する**</span><span class="sxs-lookup"><span data-stu-id="ac296-258">**❓ Removing an attribute**</span></span>

  <span data-ttu-id="ac296-259">ほとんどの場合、属性 (<xref:System.NonSerializedAttribute> など) を削除することは破壊的変更です。</span><span class="sxs-lookup"><span data-stu-id="ac296-259">In most cases, removing an attribute (such as <xref:System.NonSerializedAttribute>) is a breaking change.</span></span>

## <a name="platform-support"></a><span data-ttu-id="ac296-260">プラットフォームのサポート</span><span class="sxs-lookup"><span data-stu-id="ac296-260">Platform support</span></span>

- <span data-ttu-id="ac296-261">**✔️ 以前はサポートされていなかったプラットフォーム上の操作をサポートする**</span><span class="sxs-lookup"><span data-stu-id="ac296-261">**✔️ Supporting an operation on a platform that was previously not supported**</span></span>

- <span data-ttu-id="ac296-262">**❌ 以前にプラットフォームでサポートされていた操作に対して、特定のサービス パックのサポートを停止する、または必須にする**</span><span class="sxs-lookup"><span data-stu-id="ac296-262">**❌ Not supporting or now requiring a specific service pack for an operation that was previously supported on a platform**</span></span>

## <a name="internal-implementation-changes"></a><span data-ttu-id="ac296-263">内部的な実装の変更</span><span class="sxs-lookup"><span data-stu-id="ac296-263">Internal implementation changes</span></span>

- <span data-ttu-id="ac296-264">**❓ 内部型のセキュリティを変更する**</span><span class="sxs-lookup"><span data-stu-id="ac296-264">**❓ Changing the surface area of an internal type**</span></span>

   <span data-ttu-id="ac296-265">このような変更は一般に許可されていますが、非公開のリフレクションは互換性がなくなります。</span><span class="sxs-lookup"><span data-stu-id="ac296-265">Such changes are generally allowed, although they break private reflection.</span></span> <span data-ttu-id="ac296-266">一般的なサードパーティ製ライブラリや多数の開発者が内部 API に依存している場合など、状況によってはこのような変更が許容されないことがあります。</span><span class="sxs-lookup"><span data-stu-id="ac296-266">In some cases, where popular third-party libraries or a large number of developers depend on the internal APIs, such changes may not be allowed.</span></span>

- <span data-ttu-id="ac296-267">**❓ メンバーの内部的な実装を変更する**</span><span class="sxs-lookup"><span data-stu-id="ac296-267">**❓ Changing the internal implementation of a member**</span></span>

  <span data-ttu-id="ac296-268">このような変更は一般に許可されていますが、非公開のリフレクションは互換性がなくなります。</span><span class="sxs-lookup"><span data-stu-id="ac296-268">These changes are generally allowed, although they break private reflection.</span></span> <span data-ttu-id="ac296-269">顧客コードが非公開のリフレクションに頻繁に依存している場合や、変更によって意図しない副作用が生じる場合など、状況によってはこのような変更が許容されないことがあります。</span><span class="sxs-lookup"><span data-stu-id="ac296-269">In some cases, where customer code frequently depends on private reflection or where the change introduces unintended side effects, these changes may not be allowed.</span></span>

- <span data-ttu-id="ac296-270">**✔️ 操作のパフォーマンスを向上させる**</span><span class="sxs-lookup"><span data-stu-id="ac296-270">**✔️ Improving the performance of an operation**</span></span>

   <span data-ttu-id="ac296-271">操作のパフォーマンスを変更する機能は不可欠ですが、そのような変更により、現在の操作速度に依存するコードと互換性がなくなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ac296-271">The ability to modify the performance of an operation is essential, but such changes can break code that relies upon the current speed of an operation.</span></span> <span data-ttu-id="ac296-272">これは、非同期操作のタイミングに依存するコードに特に当てはまります。</span><span class="sxs-lookup"><span data-stu-id="ac296-272">This is particularly true of code that depends on the timing of asynchronous operations.</span></span> <span data-ttu-id="ac296-273">パフォーマンスの変更は、該当する API の他の動作には影響しないことに注意してください。それ以外の場合は、破壊的変更になります。</span><span class="sxs-lookup"><span data-stu-id="ac296-273">Note that the performance change should have no effect on other behavior of the API in question; otherwise, the change will be breaking.</span></span>

- <span data-ttu-id="ac296-274">**✔️ 間接的に (そして多くの場合は低下するように) 操作のパフォーマンスを変更する**</span><span class="sxs-lookup"><span data-stu-id="ac296-274">**✔️ Indirectly (and often adversely) changing the performance of an operation**</span></span>

  <span data-ttu-id="ac296-275">該当する変更が他の何らかの理由で破壊的と分類されていない場合、これは許容されます。</span><span class="sxs-lookup"><span data-stu-id="ac296-275">If the change in question is not categorized as breaking for some other reason, this is acceptable.</span></span> <span data-ttu-id="ac296-276">多くの場合、余分な操作を含む可能性があるアクション、または新しい機能を追加するアクションを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac296-276">Often, actions need to be taken that may include extra operations or that add new functionality.</span></span> <span data-ttu-id="ac296-277">これはほとんど常にパフォーマンスに影響しますが、該当する API を想定どおりに機能させるためには不可欠なことがあります。</span><span class="sxs-lookup"><span data-stu-id="ac296-277">This will almost always affect performance but may be essential to make the API in question function as expected.</span></span>

- <span data-ttu-id="ac296-278">**❌ 同期 API から非同期に変更する (およびその逆)**</span><span class="sxs-lookup"><span data-stu-id="ac296-278">**❌ Changing a synchronous API to asynchronous (and vice versa)**</span></span>

## <a name="code-changes"></a><span data-ttu-id="ac296-279">コードの変更</span><span class="sxs-lookup"><span data-stu-id="ac296-279">Code changes</span></span>

- <span data-ttu-id="ac296-280">**✔️ パラメーターに [params](../../csharp/language-reference/keywords/params.md) を追加する**</span><span class="sxs-lookup"><span data-stu-id="ac296-280">**✔️ Adding [params](../../csharp/language-reference/keywords/params.md) to a parameter**</span></span>

- <span data-ttu-id="ac296-281">**❌ [構造体](../../csharp/language-reference/keywords/struct.md)を[クラス](../../csharp/language-reference/keywords/class.md)に変更する (およびその逆)**</span><span class="sxs-lookup"><span data-stu-id="ac296-281">**❌ Changing a [struct](../../csharp/language-reference/keywords/struct.md) to a [class](../../csharp/language-reference/keywords/class.md) and vice versa**</span></span>

- <span data-ttu-id="ac296-282">**❌ [チェック済み](../../csharp/language-reference/keywords/virtual.md)キーワードをコード ブロックに追加する**</span><span class="sxs-lookup"><span data-stu-id="ac296-282">**❌ Adding the [checked](../../csharp/language-reference/keywords/virtual.md) keyword to a code block**</span></span>

   <span data-ttu-id="ac296-283">この変更により、以前に実行されたコードから <xref:System.OverflowException> がスローされることがあるため、許容されません。</span><span class="sxs-lookup"><span data-stu-id="ac296-283">This change may cause code that previously executed to throw an <xref:System.OverflowException> and is unacceptable.</span></span>

- <span data-ttu-id="ac296-284">**❌ パラメーターから [params](../../csharp/language-reference/keywords/params.md) を削除する**</span><span class="sxs-lookup"><span data-stu-id="ac296-284">**❌ Removing [params](../../csharp/language-reference/keywords/params.md) from a parameter**</span></span>

- <span data-ttu-id="ac296-285">**❌ イベントの発生順序を変更する**</span><span class="sxs-lookup"><span data-stu-id="ac296-285">**❌ Changing the order in which events are fired**</span></span>

  <span data-ttu-id="ac296-286">開発者はイベントが同じ順序で発生すると合理的に想定する可能性があります。開発者のコードはイベントが発生する順序に依存していることがよくあります。</span><span class="sxs-lookup"><span data-stu-id="ac296-286">Developers can reasonably expect events to fire in the same order, and developer code frequently depends on the order in which events are fired.</span></span>

- <span data-ttu-id="ac296-287">**❌ 特定のアクションに基づくイベントの発生を削除する**</span><span class="sxs-lookup"><span data-stu-id="ac296-287">**❌ Removing the raising of an event on a given action**</span></span>

- <span data-ttu-id="ac296-288">**❌ 指定されたイベントが呼び出される回数を変更する**</span><span class="sxs-lookup"><span data-stu-id="ac296-288">**❌ Changing the number of times given events are called**</span></span>

- <span data-ttu-id="ac296-289">**❌ 列挙型に <xref:System.FlagsAttribute> を追加する**</span><span class="sxs-lookup"><span data-stu-id="ac296-289">**❌ Adding the <xref:System.FlagsAttribute> to an enumeration type**</span></span>
