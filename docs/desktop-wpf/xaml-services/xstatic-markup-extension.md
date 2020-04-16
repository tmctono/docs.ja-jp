---
title: x:Static のマークアップ拡張機能
ms.date: 03/30/2017
f1_keywords:
- StaticExtension
- xStatic
- x:Static
helpviewer_keywords:
- x:Static markup extension [XAML Services]
- Static markup extension in XAML [XAML Services]
- XAML [XAML Services], x:Static markup extension
ms.assetid: 056aee79-7cdd-434f-8174-dfc856cad343
ms.openlocfilehash: fb9ee6807135f17fd9e0c799533bba28b369ebe2
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2020
ms.locfileid: "81433266"
---
# <a name="xstatic-markup-extension"></a><span data-ttu-id="db317-102">x:Static のマークアップ拡張機能</span><span class="sxs-lookup"><span data-stu-id="db317-102">x:Static Markup Extension</span></span>

<span data-ttu-id="db317-103">共通言語仕様 (CLS) に準拠した方法で定義されている静的な値によるコード エンティティを参照します。</span><span class="sxs-lookup"><span data-stu-id="db317-103">References any static by-value code entity that is defined in a Common Language Specification (CLS)–compliant way.</span></span> <span data-ttu-id="db317-104">参照される静的プロパティを使用して、XAML でプロパティの値を提供できます。</span><span class="sxs-lookup"><span data-stu-id="db317-104">The static property that is referenced can be used to provide the value of a property in XAML.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="db317-105">XAML 属性の使用方法</span><span class="sxs-lookup"><span data-stu-id="db317-105">XAML Attribute Usage</span></span>

```xaml
<object property="{x:Static prefix:typeName.staticMemberName}" .../>
```

## <a name="xaml-values"></a><span data-ttu-id="db317-106">XAML 値</span><span class="sxs-lookup"><span data-stu-id="db317-106">XAML Values</span></span>

| | |
|-|-|
|`prefix`|<span data-ttu-id="db317-107">省略可能。</span><span class="sxs-lookup"><span data-stu-id="db317-107">Optional.</span></span> <span data-ttu-id="db317-108">マップされた既定以外の XAML 名前空間を参照するプレフィックス。</span><span class="sxs-lookup"><span data-stu-id="db317-108">A prefix that refers to a mapped, non-default XAML namespace.</span></span> <span data-ttu-id="db317-109">`prefix`は、既定の XAML 名前空間から取得した静的プロパティを参照することはほとんどありませんので、使用法で明示的に示されています。</span><span class="sxs-lookup"><span data-stu-id="db317-109">`prefix` is shown explicitly in the usage because you rarely reference static properties that come from a default XAML namespace.</span></span> <span data-ttu-id="db317-110">「解説」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="db317-110">See Remarks.</span></span>|
|`typeName`|<span data-ttu-id="db317-111">必須。</span><span class="sxs-lookup"><span data-stu-id="db317-111">Required.</span></span> <span data-ttu-id="db317-112">目的の静的メンバーを定義する型の名前。</span><span class="sxs-lookup"><span data-stu-id="db317-112">The name of the type that defines the desired static member.</span></span>|
|`staticMemberName`|<span data-ttu-id="db317-113">必須。</span><span class="sxs-lookup"><span data-stu-id="db317-113">Required.</span></span> <span data-ttu-id="db317-114">目的の静的値メンバー (定数、静的プロパティ、フィールド、または列挙値) の名前。</span><span class="sxs-lookup"><span data-stu-id="db317-114">The name of the desired static value member (a constant, a static property, a field, or an enumeration value).</span></span>|

## <a name="remarks"></a><span data-ttu-id="db317-115">解説</span><span class="sxs-lookup"><span data-stu-id="db317-115">Remarks</span></span>

<span data-ttu-id="db317-116">参照されるコード エンティティは、次のいずれかである必要があります。</span><span class="sxs-lookup"><span data-stu-id="db317-116">The code entity that is referenced must be one of the following:</span></span>

- <span data-ttu-id="db317-117">定数</span><span class="sxs-lookup"><span data-stu-id="db317-117">A constant</span></span>
- <span data-ttu-id="db317-118">静的プロパティ</span><span class="sxs-lookup"><span data-stu-id="db317-118">A static property</span></span>
- <span data-ttu-id="db317-119">フィールド</span><span class="sxs-lookup"><span data-stu-id="db317-119">A field</span></span>
- <span data-ttu-id="db317-120">列挙値</span><span class="sxs-lookup"><span data-stu-id="db317-120">An enumeration value</span></span>

<span data-ttu-id="db317-121">非静的プロパティなどの他のコード エンティティを指定すると、XAML がマークアップ コンパイルされた場合にコンパイル エラーが発生したり、XAML の読み込み時解析例外が発生します。</span><span class="sxs-lookup"><span data-stu-id="db317-121">Specifying any other code entity, such as a nonstatic property, causes a compile-time error if the XAML is markup compiled, or a XAML load-time parse exception.</span></span>

<span data-ttu-id="db317-122">現在の`x:Static`XAML ドキュメントの既定の XAML 名前空間にない静的フィールドまたはプロパティへの参照を作成できます。ただし、この場合はプレフィックスマッピングが必要です。</span><span class="sxs-lookup"><span data-stu-id="db317-122">You can make `x:Static` references to static fields or properties that are not in the default XAML namespace for the current XAML document; however, this requires a prefix mapping.</span></span> <span data-ttu-id="db317-123">XAML 名前空間は、ほとんどの場合、XAML ドキュメントのルート要素で定義されます。</span><span class="sxs-lookup"><span data-stu-id="db317-123">XAML namespaces are almost always defined on the root element of the XAML document.</span></span>

<span data-ttu-id="db317-124">静的プロパティの検索操作は、.NET XAML サービス、XAML リーダー、および XAML ライターが既定の XAML スキーマ コンテキストで実行しているときに実行できます。</span><span class="sxs-lookup"><span data-stu-id="db317-124">The lookup operations for static properties can be performed by .NET XAML Services and its XAML readers and XAML writers, when they are running with the default XAML schema context.</span></span> <span data-ttu-id="db317-125">この XAML スキーマ コンテキストでは、CLR リフレクションを使用して、オブジェクト グラフの構築に必要な静的な値を提供できます。</span><span class="sxs-lookup"><span data-stu-id="db317-125">This XAML schema context can use CLR reflection to provide the necessary static values for object graph construction.</span></span> <span data-ttu-id="db317-126">指定`typeName`するのは、実際には CLR 型名ではなく、XAML 型名ですが、既定の XAML スキーマ コンテキストを使用する場合や、既存のすべての CLR ベースの XAML 実装フレームワークを使用する場合は、基本的に同じ名前です。</span><span class="sxs-lookup"><span data-stu-id="db317-126">The `typeName` you specify is actually a XAML type name, not a CLR type name, although these are essentially the same name when using the default XAML schema context or when using all existing CLR-based XAML-implementing frameworks.</span></span>

<span data-ttu-id="db317-127">プロパティの値の型`x:Static`を直接参照しない場合は注意が必要です。</span><span class="sxs-lookup"><span data-stu-id="db317-127">Use caution when you make `x:Static` references that are not directly the type of a property's value.</span></span> <span data-ttu-id="db317-128">XAML 処理シーケンスでは、マークアップ拡張機能から提供された値は、追加の値変換を呼び出しません。</span><span class="sxs-lookup"><span data-stu-id="db317-128">In the XAML processing sequence, provided values from a markup extension do not invoke additional value conversion.</span></span> <span data-ttu-id="db317-129">これは、参照でテキスト文字列`x:Static`が作成され、テキスト文字列に基づく属性値の値の変換が通常、その特定のメンバーまたは戻り値の型のメンバー値に対して行われる場合でも当てはまります。</span><span class="sxs-lookup"><span data-stu-id="db317-129">This is true even if your `x:Static` reference creates a text string, and a value conversion for attribute values based on text string typically occurs either for that specific member or for any member values of the return type.</span></span>

<span data-ttu-id="db317-130">属性構文は、このマークアップ拡張機能で使用される最も一般的な構文です。</span><span class="sxs-lookup"><span data-stu-id="db317-130">Attribute syntax is the most common syntax used with this markup extension.</span></span> <span data-ttu-id="db317-131">`x:Static` 識別子文字列の後に設定される文字列トークンは、基になる <xref:System.Windows.Markup.StaticExtension.Member%2A> 拡張クラスの <xref:System.Windows.Markup.StaticExtension> 値として割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="db317-131">The string token provided after the `x:Static` identifier string is assigned as the <xref:System.Windows.Markup.StaticExtension.Member%2A> value of the underlying <xref:System.Windows.Markup.StaticExtension> extension class.</span></span>

<span data-ttu-id="db317-132">技術的に可能な XAML の使用方法は他に 2 つあります。</span><span class="sxs-lookup"><span data-stu-id="db317-132">There are two other XAML usages that are technically possible.</span></span> <span data-ttu-id="db317-133">ただし、これらの使用法は不必要に冗長であるため、あまり一般的ではありません。</span><span class="sxs-lookup"><span data-stu-id="db317-133">However, these usages are less common because they are unnecessarily verbose:</span></span>

01. <span data-ttu-id="db317-134">オブジェクト要素の構文。</span><span class="sxs-lookup"><span data-stu-id="db317-134">Object element syntax.</span></span>

    ```xaml
    <x:Static Member="prefix:typeName.staticMemberName" ... />
    ```

02. <span data-ttu-id="db317-135">初期化文字列に明示的な Member プロパティを持つ属性構文。</span><span class="sxs-lookup"><span data-stu-id="db317-135">Attribute syntax with explicit Member property for initialization string.</span></span>

    ```xaml
    <object property="{x:Static Member=prefix:typeName.staticMemberName}" ... />
    ```

<span data-ttu-id="db317-136">NET XAML サービスの実装では、このマークアップ拡張機能の処理は、クラスによって<xref:System.Windows.Markup.StaticExtension>定義されます。</span><span class="sxs-lookup"><span data-stu-id="db317-136">In .NET XAML Services implementation, the handling for this markup extension is defined by the <xref:System.Windows.Markup.StaticExtension> class.</span></span>

<span data-ttu-id="db317-137">`x:Static` はマークアップ拡張機能です。</span><span class="sxs-lookup"><span data-stu-id="db317-137">`x:Static` is a markup extension.</span></span> <span data-ttu-id="db317-138">XAML のすべてのマークアップ拡張機能は、`{`属性`}`構文で、 および 文字を使用します。</span><span class="sxs-lookup"><span data-stu-id="db317-138">All markup extensions in XAML use the `{` and `}` characters in their attribute syntax, which is the convention by which a XAML processor recognizes that a markup extension must provide a value.</span></span> <span data-ttu-id="db317-139">マークアップ拡張機能について詳しくは、「 [Markup Extensions for XAML Overview](markup-extensions-overview.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="db317-139">For more information about markup extensions, see [Markup Extensions for XAML Overview](markup-extensions-overview.md).</span></span>

## <a name="wpf-usage-notes"></a><span data-ttu-id="db317-140">WPF の使用上の注意</span><span class="sxs-lookup"><span data-stu-id="db317-140">WPF Usage Notes</span></span>

<span data-ttu-id="db317-141">WPF プログラミングに使用する既定の XAML 名前空間には、便利な静的プロパティが多く含まれていないため、便利な静的プロパティのほとんどでは、使用を容易にする型`{x:Static}`コンバーターなどのサポートがあります。</span><span class="sxs-lookup"><span data-stu-id="db317-141">The default XAML namespace you use for WPF programming does not contain many useful static properties, and most of the useful static properties have support such as type converters that facilitate the usage without requiring `{x:Static}` .</span></span> <span data-ttu-id="db317-142">静的プロパティの場合、次のいずれかに該当する場合は、XAML 名前空間のプレフィックスをマップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="db317-142">For static properties, you must map a prefix for a XAML namespace if one of the following is true:</span></span>

- <span data-ttu-id="db317-143">WPF に存在するが、WPF ( )`http://schemas.microsoft.com/winfx/2006/xaml/presentation`の既定の XAML 名前空間の一部ではない型を参照しています。</span><span class="sxs-lookup"><span data-stu-id="db317-143">You are referencing a type that exists in WPF but is not part of the default XAML namespace for WPF (`http://schemas.microsoft.com/winfx/2006/xaml/presentation`).</span></span> <span data-ttu-id="db317-144">これは、 を使用`x:Static`する場合にはかなり一般的なシナリオです。</span><span class="sxs-lookup"><span data-stu-id="db317-144">This is a fairly common scenario for using `x:Static`.</span></span> <span data-ttu-id="db317-145">たとえば、`x:Static`<xref:System>クラスの静的プロパティを参照するために、CLR 名前空間と mscorlib アセンブリに対する XAML 名前空間マッピングを持つ<xref:System.Environment>参照を使用できます。</span><span class="sxs-lookup"><span data-stu-id="db317-145">For example, you might use an `x:Static` reference with a XAML namespace mapping to the <xref:System> CLR namespace and mscorlib assembly in order to reference the static properties of the <xref:System.Environment> class.</span></span>

- <span data-ttu-id="db317-146">カスタム アセンブリから型を参照しています。</span><span class="sxs-lookup"><span data-stu-id="db317-146">You are referencing a type from a custom assembly.</span></span>

- <span data-ttu-id="db317-147">WPF アセンブリ内に存在する型を参照していますが、その型は、WPF の既定の XAML 名前空間の一部としてマップされていない CLR 名前空間内にあります。</span><span class="sxs-lookup"><span data-stu-id="db317-147">You are referencing a type that exists in a WPF assembly, but that type is within a CLR namespace that was not mapped to be part of the WPF default XAML namespace.</span></span> <span data-ttu-id="db317-148">CLR 名前空間の既定の XAML 名前空間へのマッピングは、さまざまな WPF アセンブリの定義によって実行されます (この概念の詳細については[、「XAML 名前空間と WPF XAML の名前空間マッピング](../../framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="db317-148">The mapping of CLR namespaces into the default XAML namespace for WPF is performed by definitions in the various WPF assemblies (for more information about this concept, see [XAML Namespaces and Namespace Mapping for WPF XAML](../../framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)).</span></span> <span data-ttu-id="db317-149">マップされていない CLR 名前空間は、CLR 名前空間が XAML 用ではないクラス定義の大部分で構成されている場合に存在する可能性があります<xref:System.Windows.Threading>。</span><span class="sxs-lookup"><span data-stu-id="db317-149">Non-mapped CLR namespaces can exist if that CLR namespace is composed mostly of class definitions that are not typically intended for XAML, such as <xref:System.Windows.Threading>.</span></span>

<span data-ttu-id="db317-150">WPF のプレフィックスと XAML 名前空間を使用する方法の詳細については、「 WPF XAML の[XAML 名前空間と名前空間マッピング](../../framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="db317-150">For more information on how to use prefixes and XAML namespaces for WPF, see [XAML Namespaces and Namespace Mapping for WPF XAML](../../framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="db317-151">関連項目</span><span class="sxs-lookup"><span data-stu-id="db317-151">See also</span></span>

- [<span data-ttu-id="db317-152">x:Type マークアップ拡張機能</span><span class="sxs-lookup"><span data-stu-id="db317-152">x:Type Markup Extension</span></span>](xtype-markup-extension.md)
- [<span data-ttu-id="db317-153">WPF から System.Xaml に移行した型</span><span class="sxs-lookup"><span data-stu-id="db317-153">Types Migrated from WPF to System.Xaml</span></span>](../../framework/wpf/advanced/types-migrated-from-wpf-to-system.md)
