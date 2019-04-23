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
ms.openlocfilehash: 3da2f6afc7e7ecf20c91f0badca38bc26083d3ae
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59295711"
---
# <a name="xstatic-markup-extension"></a><span data-ttu-id="25d0a-102">x:Static のマークアップ拡張機能</span><span class="sxs-lookup"><span data-stu-id="25d0a-102">x:Static Markup Extension</span></span>
<span data-ttu-id="25d0a-103">定義されている任意の静的な値をコード エンティティを参照、 [!INCLUDE[TLA#tla_cls](../../../includes/tlasharptla-cls-md.md)]– に準拠した方法。</span><span class="sxs-lookup"><span data-stu-id="25d0a-103">References any static by-value code entity that is defined in a [!INCLUDE[TLA#tla_cls](../../../includes/tlasharptla-cls-md.md)]–compliant way.</span></span> <span data-ttu-id="25d0a-104">XAML のプロパティの値を提供する、参照されている静的プロパティを使用できます。</span><span class="sxs-lookup"><span data-stu-id="25d0a-104">The static property that is referenced can be used to provide the value of a property in XAML.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="25d0a-105">XAML 属性の使用方法</span><span class="sxs-lookup"><span data-stu-id="25d0a-105">XAML Attribute Usage</span></span>  
  
```xaml  
<object property="{x:Static prefix:typeName.staticMemberName}" .../>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="25d0a-106">XAML 値</span><span class="sxs-lookup"><span data-stu-id="25d0a-106">XAML Values</span></span>  
  
| | |  
|-|-|  
|`prefix`|<span data-ttu-id="25d0a-107">任意。</span><span class="sxs-lookup"><span data-stu-id="25d0a-107">Optional.</span></span> <span data-ttu-id="25d0a-108">割り当てられた、既定以外の XAML 名前空間を参照するプレフィックス。</span><span class="sxs-lookup"><span data-stu-id="25d0a-108">A prefix that refers to a mapped, non-default XAML namespace.</span></span> <span data-ttu-id="25d0a-109">`prefix` 明示的に使用量のため表示から既定の XAML 名前空間を静的プロパティを参照することはほとんどありません。</span><span class="sxs-lookup"><span data-stu-id="25d0a-109">`prefix` is shown explicitly in the usage because you rarely reference static properties that come from a default XAML namespace.</span></span> <span data-ttu-id="25d0a-110">「解説」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="25d0a-110">See Remarks.</span></span>|  
|`typeName`|<span data-ttu-id="25d0a-111">必須。</span><span class="sxs-lookup"><span data-stu-id="25d0a-111">Required.</span></span> <span data-ttu-id="25d0a-112">必要な静的メンバーを定義する型の名前。</span><span class="sxs-lookup"><span data-stu-id="25d0a-112">The name of the type that defines the desired static member.</span></span>|  
|`staticMemberName`|<span data-ttu-id="25d0a-113">必須。</span><span class="sxs-lookup"><span data-stu-id="25d0a-113">Required.</span></span> <span data-ttu-id="25d0a-114">(定数、静的プロパティ、フィールド、または列挙値) の静的な値が必要なメンバーの名前。</span><span class="sxs-lookup"><span data-stu-id="25d0a-114">The name of the desired static value member (a constant, a static property, a field, or an enumeration value).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="25d0a-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="25d0a-115">Remarks</span></span>  

<span data-ttu-id="25d0a-116">参照されているコード エンティティは、次のいずれかである必要があります。</span><span class="sxs-lookup"><span data-stu-id="25d0a-116">The code entity that is referenced must be one of the following:</span></span>  
  
-   <span data-ttu-id="25d0a-117">定数</span><span class="sxs-lookup"><span data-stu-id="25d0a-117">A constant</span></span>  
-   <span data-ttu-id="25d0a-118">静的プロパティ</span><span class="sxs-lookup"><span data-stu-id="25d0a-118">A static property</span></span>  
-   <span data-ttu-id="25d0a-119">フィールド</span><span class="sxs-lookup"><span data-stu-id="25d0a-119">A field</span></span>  
-   <span data-ttu-id="25d0a-120">列挙値</span><span class="sxs-lookup"><span data-stu-id="25d0a-120">An enumeration value</span></span>

<span data-ttu-id="25d0a-121">非静的のプロパティなど、他のコード エンティティを指定すると、XAML がコンパイルされると、マークアップまたは XAML 読み込み時の解析の例外の場合は、コンパイル時エラーとします。</span><span class="sxs-lookup"><span data-stu-id="25d0a-121">Specifying any other code entity, such as a nonstatic property, causes a compile-time error if the XAML is markup compiled, or a XAML load-time parse exception.</span></span>  

<span data-ttu-id="25d0a-122">行うことができます`x:Static`静的フィールドまたは現在の XAML ドキュメントの既定の XAML 名前空間に属さないプロパティへの参照ただし、プレフィックスのマッピングが必要です。</span><span class="sxs-lookup"><span data-stu-id="25d0a-122">You can make `x:Static` references to static fields or properties that are not in the default XAML namespace for the current XAML document; however, this requires a prefix mapping.</span></span> <span data-ttu-id="25d0a-123">XAML 名前空間は、ほとんどの場合に、XAML ドキュメントのルート要素で定義されます。</span><span class="sxs-lookup"><span data-stu-id="25d0a-123">XAML namespaces are almost always defined on the root element of the XAML document.</span></span>  

<span data-ttu-id="25d0a-124">既定の XAML スキーマ コンテキストで実行されている場合、.NET Framework XAML サービスおよびその XAML リーダーと XAML ライターによって静的なプロパティの検索操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="25d0a-124">The lookup operations for static properties can be performed by .NET Framework XAML Services and its XAML readers and XAML writers, when they are running with the default XAML schema context.</span></span> <span data-ttu-id="25d0a-125">この XAML スキーマ コンテキストでは、CLR リフレクションを使用して、オブジェクト グラフの構築のために必要な静的な値を指定します。</span><span class="sxs-lookup"><span data-stu-id="25d0a-125">This XAML schema context can use CLR reflection to provide the necessary static values for object graph construction.</span></span> <span data-ttu-id="25d0a-126">`typeName`を指定する実際には XAML 型名を CLR 型名ではなく、これらは基本的に同じ名前、既定の XAML スキーマ コンテキストを使用する場合、または既存のすべての CLR ベース XAML 実装するフレームワークを使用する場合は。</span><span class="sxs-lookup"><span data-stu-id="25d0a-126">The `typeName` you specify is actually a XAML type name, not a CLR type name, although these are essentially the same name when using the default XAML schema context or when using all existing CLR-based XAML-implementing frameworks.</span></span>  

<span data-ttu-id="25d0a-127">行ったと注意して使用`x:Static`直接プロパティの値の型ではない参照をします。</span><span class="sxs-lookup"><span data-stu-id="25d0a-127">Use caution when you make `x:Static` references that are not directly the type of a property's value.</span></span> <span data-ttu-id="25d0a-128">XAML マークアップ拡張機能で指定した値のシーケンス処理を呼び出さないでください追加の値の変換。</span><span class="sxs-lookup"><span data-stu-id="25d0a-128">In the XAML processing sequence, provided values from a markup extension do not invoke additional value conversion.</span></span> <span data-ttu-id="25d0a-129">これは、true の場合でも、`x:Static`参照は、文字列を作成し、通常のテキスト文字列に基づく属性値の値の変換は、特定のメンバーまたは戻り値の型のメンバー値のいずれかに発生します。</span><span class="sxs-lookup"><span data-stu-id="25d0a-129">This is true even if your `x:Static` reference creates a text string, and a value conversion for attribute values based on text string typically occurs either for that specific member or for any member values of the return type.</span></span>  

<span data-ttu-id="25d0a-130">属性構文は、このマークアップ拡張機能で使用される最も一般的な構文です。</span><span class="sxs-lookup"><span data-stu-id="25d0a-130">Attribute syntax is the most common syntax used with this markup extension.</span></span> <span data-ttu-id="25d0a-131">`x:Static` 識別子文字列の後に設定される文字列トークンは、基になる <xref:System.Windows.Markup.StaticExtension.Member%2A> 拡張クラスの <xref:System.Windows.Markup.StaticExtension> 値として割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="25d0a-131">The string token provided after the `x:Static` identifier string is assigned as the <xref:System.Windows.Markup.StaticExtension.Member%2A> value of the underlying <xref:System.Windows.Markup.StaticExtension> extension class.</span></span>  

<span data-ttu-id="25d0a-132">技術的に可能なその他の 2 つの XAML 使用法があります。</span><span class="sxs-lookup"><span data-stu-id="25d0a-132">There are two other XAML usages that are technically possible.</span></span> <span data-ttu-id="25d0a-133">ただし、これらの使用方法は、不必要に詳細があまり一般的なは。</span><span class="sxs-lookup"><span data-stu-id="25d0a-133">However, these usages are less common because they are unnecessarily verbose:</span></span>  

1. <span data-ttu-id="25d0a-134">オブジェクト要素構文です。</span><span class="sxs-lookup"><span data-stu-id="25d0a-134">Object element syntax.</span></span>

    ```xaml
    <x:Static Member="prefix:typeName.staticMemberName" ... />
    ```

2. <span data-ttu-id="25d0a-135">初期化文字列の明示的なメンバー プロパティの構文を属性します。</span><span class="sxs-lookup"><span data-stu-id="25d0a-135">Attribute syntax with explicit Member property for initialization string.</span></span>

    ```xaml
    <object property="{x:Static Member=prefix:typeName.staticMemberName}" ... />
    ```

<span data-ttu-id="25d0a-136">このマークアップ拡張機能の処理がによって定義されている、.NET Framework XAML サービス実装、<xref:System.Windows.Markup.StaticExtension>クラス。</span><span class="sxs-lookup"><span data-stu-id="25d0a-136">In the .NET Framework XAML Services implementation, the handling for this markup extension is defined by the <xref:System.Windows.Markup.StaticExtension> class.</span></span>  

<span data-ttu-id="25d0a-137">`x:Static` はマークアップ拡張機能です。</span><span class="sxs-lookup"><span data-stu-id="25d0a-137">`x:Static` is a markup extension.</span></span> <span data-ttu-id="25d0a-138">XAML の使用中のすべてのマークアップ拡張機能、`{`と`}`マークアップ拡張機能が値を指定する必要がありますを XAML プロセッサが認識する規則は、それぞれの属性構文内の文字。</span><span class="sxs-lookup"><span data-stu-id="25d0a-138">All markup extensions in XAML use the `{` and `}` characters in their attribute syntax, which is the convention by which a XAML processor recognizes that a markup extension must provide a value.</span></span> <span data-ttu-id="25d0a-139">マークアップ拡張機能について詳しくは、「 [Markup Extensions for XAML Overview](markup-extensions-for-xaml-overview.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="25d0a-139">For more information about markup extensions, see [Markup Extensions for XAML Overview](markup-extensions-for-xaml-overview.md).</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="25d0a-140">WPF の使用上の注意</span><span class="sxs-lookup"><span data-stu-id="25d0a-140">WPF Usage Notes</span></span>  
 <span data-ttu-id="25d0a-141">WPF プログラミングで使用する既定の XAML 名前空間に多数の便利な静的プロパティが含まれていないと、便利な静的プロパティのほとんどはなどを必要とせず、使用状況を容易にする型コンバーターをサポート`{x:Static}`します。</span><span class="sxs-lookup"><span data-stu-id="25d0a-141">The default XAML namespace you use for WPF programming does not contain many useful static properties, and most of the useful static properties have support such as type converters that facilitate the usage without requiring `{x:Static}` .</span></span> <span data-ttu-id="25d0a-142">静的プロパティは、次のいずれかが true の場合、XAML 名前空間のプレフィックスをマップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="25d0a-142">For static properties, you must map a prefix for a XAML namespace if one of the following is true:</span></span>  
  
-   <span data-ttu-id="25d0a-143">WPF に存在しますが、WPF の既定の XAML 名前空間の一部でない型を参照している ([!INCLUDE[TLA#tla_wpfxmlnsv1](../../../includes/tlasharptla-wpfxmlnsv1-md.md)])。</span><span class="sxs-lookup"><span data-stu-id="25d0a-143">You are referencing a type that exists in WPF but is not part of the default XAML namespace for WPF ([!INCLUDE[TLA#tla_wpfxmlnsv1](../../../includes/tlasharptla-wpfxmlnsv1-md.md)]).</span></span> <span data-ttu-id="25d0a-144">これは、非常に一般的なシナリオを使用するため`x:Static`します。</span><span class="sxs-lookup"><span data-stu-id="25d0a-144">This is a fairly common scenario for using `x:Static`.</span></span> <span data-ttu-id="25d0a-145">たとえば、使用する場合があります、`x:Static`へのマッピングを XAML 名前空間を持つ参照、<xref:System>の静的プロパティを参照するには CLR 名前空間と mscorlib アセンブリ、<xref:System.Environment>クラス。</span><span class="sxs-lookup"><span data-stu-id="25d0a-145">For example, you might use an `x:Static` reference with a XAML namespace mapping to the <xref:System> CLR namespace and mscorlib assembly in order to reference the static properties of the <xref:System.Environment> class.</span></span>  
  
-   <span data-ttu-id="25d0a-146">カスタム アセンブリから型を参照しています。</span><span class="sxs-lookup"><span data-stu-id="25d0a-146">You are referencing a type from a custom assembly.</span></span>  
  
-   <span data-ttu-id="25d0a-147">その型が既定の WPF XAML 名前空間の一部としてマップされていませんでしたが CLR 名前空間は WPF アセンブリに存在する型を参照しています。</span><span class="sxs-lookup"><span data-stu-id="25d0a-147">You are referencing a type that exists in a WPF assembly, but that type is within a CLR namespace that was not mapped to be part of the WPF default XAML namespace.</span></span> <span data-ttu-id="25d0a-148">WPF の既定の XAML 名前空間に CLR 名前空間のマッピングは、さまざまな WPF アセンブリ内の定義によって実行されます (この概念の詳細については、次を参照してください。 [XAML 名前空間および WPF XAML の Namespace マッピング](../wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md))。</span><span class="sxs-lookup"><span data-stu-id="25d0a-148">The mapping of CLR namespaces into the default XAML namespace for WPF is performed by definitions in the various WPF assemblies (for more information about this concept, see [XAML Namespaces and Namespace Mapping for WPF XAML](../wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)).</span></span> <span data-ttu-id="25d0a-149">CLR 名前空間のマッピングされていないがその CLR 名前空間が、通常は想定されていません、XAML などのクラス定義のほとんどの場合で構成される場合に存在できる<xref:System.Windows.Threading>します。</span><span class="sxs-lookup"><span data-stu-id="25d0a-149">Non-mapped CLR namespaces can exist if that CLR namespace is composed mostly of class definitions that are not typically intended for XAML, such as <xref:System.Windows.Threading>.</span></span>  
  
 <span data-ttu-id="25d0a-150">WPF のプレフィックスと XAML 名前空間を使用する方法の詳細については、次を参照してください。 [XAML 名前空間および WPF XAML のマッピングの Namespace](../wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)します。</span><span class="sxs-lookup"><span data-stu-id="25d0a-150">For more information on how to use prefixes and XAML namespaces for WPF, see [XAML Namespaces and Namespace Mapping for WPF XAML](../wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25d0a-151">関連項目</span><span class="sxs-lookup"><span data-stu-id="25d0a-151">See also</span></span>

- [<span data-ttu-id="25d0a-152">x:Type マークアップ拡張機能</span><span class="sxs-lookup"><span data-stu-id="25d0a-152">x:Type Markup Extension</span></span>](x-type-markup-extension.md)
- [<span data-ttu-id="25d0a-153">WPF から System.Xaml に移行した型</span><span class="sxs-lookup"><span data-stu-id="25d0a-153">Types Migrated from WPF to System.Xaml</span></span>](types-migrated-from-wpf-to-system-xaml.md)
