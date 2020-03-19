---
title: クラス、構造体、およびインターフェイスの名前
ms.date: 10/22/2008
helpviewer_keywords:
- type names, guidelines
- classes [.NET Framework], names
- enumerations [.NET Framework], names
- names [.NET Framework], interfaces
- common type names
- names [.NET Framework], type names
- names [.NET Framework], classes
- interfaces [.NET Framework], names
- generic type parameters
ms.assetid: 87a4b0da-ed64-43b1-ac43-968576c444ce
ms.openlocfilehash: 2c528348c0e84037a80df9797c56f03b51c73adc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401239"
---
# <a name="names-of-classes-structs-and-interfaces"></a><span data-ttu-id="a2448-102">クラス、構造体、およびインターフェイスの名前</span><span class="sxs-lookup"><span data-stu-id="a2448-102">Names of Classes, Structs, and Interfaces</span></span>
<span data-ttu-id="a2448-103">次の命名規則は、一般的な型の命名に適用されます。</span><span class="sxs-lookup"><span data-stu-id="a2448-103">The naming guidelines that follow apply to general type naming.</span></span>

 <span data-ttu-id="a2448-104">クラスや構造体に、PascalCasing を使用して、名詞または名詞句を使用して✔️します。</span><span class="sxs-lookup"><span data-stu-id="a2448-104">✔️ DO name classes and structs with nouns or noun phrases, using PascalCasing.</span></span>

 <span data-ttu-id="a2448-105">これにより、型名とメソッドが動詞句で指定されているのが区別されます。</span><span class="sxs-lookup"><span data-stu-id="a2448-105">This distinguishes type names from methods, which are named with verb phrases.</span></span>

 <span data-ttu-id="a2448-106">✔️は、形容詞句、または名詞や名詞句を使用してインタフェースに名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="a2448-106">✔️ DO name interfaces with adjective phrases, or occasionally with nouns or noun phrases.</span></span>

 <span data-ttu-id="a2448-107">名詞や名詞句はめったに使用されず、型がインターフェイスではなく抽象クラスであるべきであることを示している場合があります。</span><span class="sxs-lookup"><span data-stu-id="a2448-107">Nouns and noun phrases should be used rarely and they might indicate that the type should be an abstract class, and not an interface.</span></span>

 <span data-ttu-id="a2448-108">❌クラス名にプレフィックス ("C"など) を付けないでください。</span><span class="sxs-lookup"><span data-stu-id="a2448-108">❌ DO NOT give class names a prefix (e.g., "C").</span></span>

 <span data-ttu-id="a2448-109">✔️ CONSIDER 基底クラスの名前で派生クラスの名前を終了します。</span><span class="sxs-lookup"><span data-stu-id="a2448-109">✔️ CONSIDER ending the name of derived classes with the name of the base class.</span></span>

 <span data-ttu-id="a2448-110">これは非常に読みやすく、関係を明確に説明します。</span><span class="sxs-lookup"><span data-stu-id="a2448-110">This is very readable and explains the relationship clearly.</span></span> <span data-ttu-id="a2448-111">コードの例としては`ArgumentOutOfRangeException`、`Exception`の一種である、 と`SerializableAttribute`の一種である`Attribute`、 が挙げられます。</span><span class="sxs-lookup"><span data-stu-id="a2448-111">Some examples of this in code are: `ArgumentOutOfRangeException`, which is a kind of `Exception`, and `SerializableAttribute`, which is a kind of `Attribute`.</span></span> <span data-ttu-id="a2448-112">しかし、このガイドラインを適用する際には、合理的な判断を下す必要があります。たとえば、`Button`クラスは一種の`Control`イベントですが`Control`、その名前には表示されません。</span><span class="sxs-lookup"><span data-stu-id="a2448-112">However, it is important to use reasonable judgment in applying this guideline; for example, the `Button` class is a kind of `Control` event, although `Control` doesn’t appear in its name.</span></span>

 <span data-ttu-id="a2448-113">型がインターフェイスであることを示すために、DO プレフィックスインターフェイス名を I という文字で✔️します。</span><span class="sxs-lookup"><span data-stu-id="a2448-113">✔️ DO prefix interface names with the letter I, to indicate that the type is an interface.</span></span>

 <span data-ttu-id="a2448-114">例えば、(`IComponent`名詞)、(`ICustomAttributeProvider`名詞句)、および`IPersistable`(形容詞)は適切なインタフェース名である。</span><span class="sxs-lookup"><span data-stu-id="a2448-114">For example, `IComponent` (descriptive noun), `ICustomAttributeProvider` (noun phrase), and `IPersistable` (adjective) are appropriate interface names.</span></span> <span data-ttu-id="a2448-115">他の型名と同様に、省略形は避けてください。</span><span class="sxs-lookup"><span data-stu-id="a2448-115">As with other type names, avoid abbreviations.</span></span>

 <span data-ttu-id="a2448-116">✔️は、クラスがインターフェイスの標準実装である class-interface ペアを定義する場合、インターフェイス名の "I" プレフィックスだけが名前を異なることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a2448-116">✔️ DO ensure that the names differ only by the "I" prefix on the interface name when you are defining a class–interface pair where the class is a standard implementation of the interface.</span></span>

## <a name="names-of-generic-type-parameters"></a><span data-ttu-id="a2448-117">ジェネリック型パラメーターの名前</span><span class="sxs-lookup"><span data-stu-id="a2448-117">Names of Generic Type Parameters</span></span>
 <span data-ttu-id="a2448-118">ジェネリックは .NET Framework 2.0 に追加されました。</span><span class="sxs-lookup"><span data-stu-id="a2448-118">Generics were added to .NET Framework 2.0.</span></span> <span data-ttu-id="a2448-119">この機能は、*型パラメーター*と呼ばれる新しい種類の識別子を導入しました。</span><span class="sxs-lookup"><span data-stu-id="a2448-119">The feature introduced a new kind of identifier called *type parameter*.</span></span>

 <span data-ttu-id="a2448-120">✔️は、単一文字の名前が完全にわかりやすい名前であり、わかりやすい名前が値を追加しない限り、ジェネリック型パラメーターにわかりやすい名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="a2448-120">✔️ DO name generic type parameters with descriptive names unless a single-letter name is completely self-explanatory and a descriptive name would not add value.</span></span>

 <span data-ttu-id="a2448-121">✔️ 1`T`文字の型パラメーターを持つ型の型パラメーター名として使用することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="a2448-121">✔️ CONSIDER using `T` as the type parameter name for types with one single-letter type parameter.</span></span>

```csharp
public int IComparer<T> { ... }
public delegate bool Predicate<T>(T item);
public struct Nullable<T> where T:struct { ... }
```

 <span data-ttu-id="a2448-122">✔️ DO プレフィックスの説明型`T`パラメーター名に.</span><span class="sxs-lookup"><span data-stu-id="a2448-122">✔️ DO prefix descriptive type parameter names with `T`.</span></span>

```csharp
public interface ISessionChannel<TSession> where TSession : ISession {
    TSession Session { get; }
}
```

 <span data-ttu-id="a2448-123">✔️ CONSIDER は、パラメーターの名前の型パラメーターに配置される制約を示します。</span><span class="sxs-lookup"><span data-stu-id="a2448-123">✔️ CONSIDER indicating constraints placed on a type parameter in the name of the parameter.</span></span>

 <span data-ttu-id="a2448-124">たとえば、制約された`ISession`パラメーターは 、 という`TSession`名前になることがあります。</span><span class="sxs-lookup"><span data-stu-id="a2448-124">For example, a parameter constrained to `ISession` might be called `TSession`.</span></span>

## <a name="names-of-common-types"></a><span data-ttu-id="a2448-125">共通型の名前</span><span class="sxs-lookup"><span data-stu-id="a2448-125">Names of Common Types</span></span>
 <span data-ttu-id="a2448-126">✔️は、特定の .NET Framework 型から派生した型に名前を付ける場合、または特定の .NET Framework 型を実装する場合に、次の表で説明されているガイドラインに従います。</span><span class="sxs-lookup"><span data-stu-id="a2448-126">✔️ DO follow the guidelines described in the following table when naming types derived from or implementing certain .NET Framework types.</span></span>

|<span data-ttu-id="a2448-127">基本型</span><span class="sxs-lookup"><span data-stu-id="a2448-127">Base Type</span></span>|<span data-ttu-id="a2448-128">派生/実装型ガイドライン</span><span class="sxs-lookup"><span data-stu-id="a2448-128">Derived/Implementing Type Guideline</span></span>|
|---------------|------------------------------------------|
|`System.Attribute`|<span data-ttu-id="a2448-129">✔️は、カスタム属性クラスの名前に接尾辞 "Attribute" を追加します。</span><span class="sxs-lookup"><span data-stu-id="a2448-129">✔️ DO add the suffix "Attribute" to names of custom attribute classes.</span></span>|
|`System.Delegate`|<span data-ttu-id="a2448-130">イベントで使用されるデリゲートの名前にサフィックス "EventHandler" を追加✔️。</span><span class="sxs-lookup"><span data-stu-id="a2448-130">✔️ DO add the suffix "EventHandler" to names of delegates that are used in events.</span></span><br /><br /> <span data-ttu-id="a2448-131">✔️は、イベント ハンドラとして使用されるデリゲート以外のデリゲートの名前にサフィックス "Callback" を追加します。</span><span class="sxs-lookup"><span data-stu-id="a2448-131">✔️ DO add the suffix "Callback" to names of delegates other than those used as event handlers.</span></span><br /><br /> <span data-ttu-id="a2448-132">❌デリゲートに "Delegate" というサフィックスを追加しないでください。</span><span class="sxs-lookup"><span data-stu-id="a2448-132">❌ DO NOT add the suffix "Delegate" to a delegate.</span></span>|
|`System.EventArgs`|<span data-ttu-id="a2448-133">✔️は、サフィックス "EventArgs" を追加します。</span><span class="sxs-lookup"><span data-stu-id="a2448-133">✔️ DO add the suffix "EventArgs."</span></span>|
|`System.Enum`|<span data-ttu-id="a2448-134">❌このクラスから派生しないでください。代わりに、使用する言語でサポートされているキーワードを使用します。たとえば、C# では、キーワードを`enum`使用します。</span><span class="sxs-lookup"><span data-stu-id="a2448-134">❌ DO NOT derive from this class; use the keyword supported by your language instead; for example, in C#, use the `enum` keyword.</span></span><br /><br /> <span data-ttu-id="a2448-135">❌"列挙" または "フラグ" というサフィックスを追加しないでください。</span><span class="sxs-lookup"><span data-stu-id="a2448-135">❌ DO NOT add the suffix "Enum" or "Flag."</span></span>|
|`System.Exception`|<span data-ttu-id="a2448-136">✔️ DO は、"例外" というサフィックスを追加します。</span><span class="sxs-lookup"><span data-stu-id="a2448-136">✔️ DO add the suffix "Exception."</span></span>|
|`IDictionary` <br /> `IDictionary<TKey,TValue>`|<span data-ttu-id="a2448-137">✔️は、"辞書" というサフィックスを追加します。</span><span class="sxs-lookup"><span data-stu-id="a2448-137">✔️ DO add the suffix "Dictionary."</span></span> <span data-ttu-id="a2448-138">これは`IDictionary`特定の種類のコレクションですが、このガイドラインは、次に示す一般的なコレクションのガイドラインよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="a2448-138">Note that `IDictionary` is a specific type of collection, but this guideline takes precedence over the more general collections guideline that follows.</span></span>|
|`IEnumerable` <br /> `ICollection` <br /> `IList` <br /> `IEnumerable<T>` <br /> `ICollection<T>` <br /> `IList<T>`|<span data-ttu-id="a2448-139">✔️は、"コレクション" というサフィックスを追加します。</span><span class="sxs-lookup"><span data-stu-id="a2448-139">✔️ DO add the suffix "Collection."</span></span>|
|`System.IO.Stream`|<span data-ttu-id="a2448-140">✔️は、サフィックス"Stream"を追加します。</span><span class="sxs-lookup"><span data-stu-id="a2448-140">✔️ DO add the suffix "Stream."</span></span>|
|`CodeAccessPermission IPermission`|<span data-ttu-id="a2448-141">✔️は、"アクセス許可" というサフィックスを追加します。</span><span class="sxs-lookup"><span data-stu-id="a2448-141">✔️ DO add the suffix "Permission."</span></span>|

## <a name="naming-enumerations"></a><span data-ttu-id="a2448-142">列挙体の名前付け</span><span class="sxs-lookup"><span data-stu-id="a2448-142">Naming Enumerations</span></span>
 <span data-ttu-id="a2448-143">列挙型の名前 (enum) は、一般に、標準の型の名前付け規則 (PascalCasing など) に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2448-143">Names of enumeration types (also called enums) in general should follow the standard type-naming rules (PascalCasing, etc.).</span></span> <span data-ttu-id="a2448-144">ただし、列挙型に特に適用される追加のガイドラインがあります。</span><span class="sxs-lookup"><span data-stu-id="a2448-144">However, there are additional guidelines that apply specifically to enums.</span></span>

 <span data-ttu-id="a2448-145">✔️値がビット フィールドでない限り、列挙型には単数型名を使用します。</span><span class="sxs-lookup"><span data-stu-id="a2448-145">✔️ DO use a singular type name for an enumeration unless its values are bit fields.</span></span>

 <span data-ttu-id="a2448-146">✔️ DO では、値としてビット フィールドを持つ列挙体に複数形の型名を使用します。</span><span class="sxs-lookup"><span data-stu-id="a2448-146">✔️ DO use a plural type name for an enumeration with bit fields as values, also called flags enum.</span></span>

 <span data-ttu-id="a2448-147">❌列挙型名に "Enum" サフィックスを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="a2448-147">❌ DO NOT use an "Enum" suffix in enum type names.</span></span>

 <span data-ttu-id="a2448-148">❌列挙型名に "フラグ" または "フラグ" サフィックスを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="a2448-148">❌ DO NOT use "Flag" or "Flags" suffixes in enum type names.</span></span>

 <span data-ttu-id="a2448-149">❌列挙値名にプレフィックスを使用しないでください (たとえば、ADO 列挙型の "ad" やリッチ テキストの列挙型の場合は "rtf" など)。</span><span class="sxs-lookup"><span data-stu-id="a2448-149">❌ DO NOT use a prefix on enumeration value names (e.g., "ad" for ADO enums, "rtf" for rich text enums, etc.).</span></span>

 <span data-ttu-id="a2448-150">*2005年、2009年©マイクロソフト株式会社。すべての権利が予約されています。*</span><span class="sxs-lookup"><span data-stu-id="a2448-150">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="a2448-151">*2008 年 10 月 22 日に Microsoft Windows Development シリーズの一部として、Addison-Wesley Professional によって発行された、Krzysztof Cwalina および Brad Abrams による「[Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)」 (フレームワーク デザイン ガイドライン: 再利用可能な .NET ライブラリの規則、用法、パターン、第 2 版) から Pearson Education, Inc. の許可を得て再印刷されています。*</span><span class="sxs-lookup"><span data-stu-id="a2448-151">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="a2448-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="a2448-152">See also</span></span>

- [<span data-ttu-id="a2448-153">フレームワーク デザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="a2448-153">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="a2448-154">名前付けのガイドライン</span><span class="sxs-lookup"><span data-stu-id="a2448-154">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
