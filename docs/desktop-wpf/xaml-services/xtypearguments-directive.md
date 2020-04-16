---
title: x:TypeArguments ディレクティブ
ms.date: 03/30/2017
f1_keywords:
- x:TypeArguments
- xTypeArguments
- TypeArguments
helpviewer_keywords:
- x:TypeArguments attribute [XAML Services]
- TypeArguments attribute in XAML [XAML Services]
- XAML [XAML Services], x:TypeArguments attribute
ms.assetid: 86561058-d393-4a44-b5c3-993a4513ea74
ms.openlocfilehash: 69da9329f140121b66c71d4cf2e99e9d14a1b207
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432630"
---
# <a name="xtypearguments-directive"></a><span data-ttu-id="be9a0-102">x:TypeArguments ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="be9a0-102">x:TypeArguments Directive</span></span>

<span data-ttu-id="be9a0-103">ジェネリック型の制約型引数をジェネリック型のコンストラクターに渡します。</span><span class="sxs-lookup"><span data-stu-id="be9a0-103">Passes constraining type arguments of a generic to the constructor of the generic type.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="be9a0-104">XAML 属性の使用方法</span><span class="sxs-lookup"><span data-stu-id="be9a0-104">XAML Attribute Usage</span></span>

```xaml
<object x:TypeArguments="typeString" .../>
```

## <a name="xaml-values"></a><span data-ttu-id="be9a0-105">XAML 値</span><span class="sxs-lookup"><span data-stu-id="be9a0-105">XAML Values</span></span>

|||
|-|-|
|`object`|<span data-ttu-id="be9a0-106">CLR ジェネリック型によってサポートされる XAML 型のオブジェクト要素宣言。</span><span class="sxs-lookup"><span data-stu-id="be9a0-106">An object element declaration of a XAML type, which is backed by a CLR generic type.</span></span> <span data-ttu-id="be9a0-107">既定`object`の XAML 名前空間からでない XAML 型を参照する`object`場合は、存在する XAML`object`名前空間を示すプレフィックスが必要です。</span><span class="sxs-lookup"><span data-stu-id="be9a0-107">If `object` refers to a XAML type that is not from the default XAML namespace, `object` requires a prefix to indicate the XAML namespace where `object` exists.</span></span>|
|`typeString`|<span data-ttu-id="be9a0-108">1 つ以上の XAML 型名を文字列として宣言する文字列。</span><span class="sxs-lookup"><span data-stu-id="be9a0-108">A string that declares one or more XAML type names as strings, which supplies the type arguments for the CLR generic type.</span></span> <span data-ttu-id="be9a0-109">構文に関するその他の注意事項については、「解説」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="be9a0-109">See Remarks for additional syntax notes.</span></span>|

## <a name="remarks"></a><span data-ttu-id="be9a0-110">解説</span><span class="sxs-lookup"><span data-stu-id="be9a0-110">Remarks</span></span>

<span data-ttu-id="be9a0-111">ほとんどの場合、`typeString`文字列内の情報項目として使用される XAML 型にはプレフィックスが付けられます。</span><span class="sxs-lookup"><span data-stu-id="be9a0-111">In most cases, the XAML types that are used as an information item in a `typeString` string are prefixed.</span></span> <span data-ttu-id="be9a0-112">CLR の一般的な制約 (たとえば<xref:System.Int32><xref:System.String>、 ) の型は、CLR 基本クラス ライブラリから取得されます。</span><span class="sxs-lookup"><span data-stu-id="be9a0-112">Typical types of CLR generic constraints (for example, <xref:System.Int32> and <xref:System.String>) come from CLR base class libraries.</span></span> <span data-ttu-id="be9a0-113">これらのライブラリは、フレームワーク固有の一般的な既定の XAML 名前空間にはマップされないため、XAML の使用に対するプレフィックス マッピングが必要です。</span><span class="sxs-lookup"><span data-stu-id="be9a0-113">Those libraries are not mapped to typical framework-specific default XAML namespaces, and therefore, require a prefix mapping for XAML usage.</span></span>

<span data-ttu-id="be9a0-114">コンマ区切り記号を使用して、複数の XAML 型名を指定できます。</span><span class="sxs-lookup"><span data-stu-id="be9a0-114">You can specify more than one XAML type name by using a comma delimiter.</span></span>

<span data-ttu-id="be9a0-115">ジェネリック制約自体がジェネリック型を使用する場合、入れ子になった制約型引数は括弧 () で囲むことができます。</span><span class="sxs-lookup"><span data-stu-id="be9a0-115">If the generic constraints themselves use generic types, the nested constraint type arguments can be contained by parentheses ().</span></span>

<span data-ttu-id="be9a0-116">この定義`x:TypeArguments`は.NET XAML サービスに固有で、CLR バッキングを使用していることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="be9a0-116">Note that this definition of `x:TypeArguments` is specific to .NET XAML Services and using CLR backing.</span></span> <span data-ttu-id="be9a0-117">言語レベルの定義は、 [ \[MS-XAML\]セクション 5.3.11](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10))にあります。</span><span class="sxs-lookup"><span data-stu-id="be9a0-117">A language-level definition can be found in [\[MS-XAML\] Section 5.3.11](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span></span>

## <a name="usage-examples"></a><span data-ttu-id="be9a0-118">使用例</span><span class="sxs-lookup"><span data-stu-id="be9a0-118">Usage Examples</span></span>

<span data-ttu-id="be9a0-119">これらの例では、次の XAML 名前空間定義が宣言されていると仮定します。</span><span class="sxs-lookup"><span data-stu-id="be9a0-119">For these examples, assume that the following XAML namespace definitions are declared:</span></span>

```xaml
xmlns:sys="clr-namespace:System;assembly=mscorlib"
xmlns:scg="clr-namespace:System.Collections.Generic;assembly=mscorlib"
```

### <a name="liststring"></a><span data-ttu-id="be9a0-120">リスト\<文字列></span><span class="sxs-lookup"><span data-stu-id="be9a0-120">List\<String></span></span>

<span data-ttu-id="be9a0-121">`<scg:List x:TypeArguments="sys:String" ...>`型引数を使用<xref:System.Collections.Generic.List%601>して<xref:System.String>new をインスタンス化します。</span><span class="sxs-lookup"><span data-stu-id="be9a0-121">`<scg:List x:TypeArguments="sys:String" ...>` instantiates a new <xref:System.Collections.Generic.List%601> with a <xref:System.String> type argument.</span></span>

### <a name="dictionarystringstring"></a><span data-ttu-id="be9a0-122">辞書\<文字列,文字列></span><span class="sxs-lookup"><span data-stu-id="be9a0-122">Dictionary\<String,String></span></span>

<span data-ttu-id="be9a0-123">`<scg:Dictionary x:TypeArguments="sys:String,sys:String" ...>`2 つの型<xref:System.Collections.Generic.Dictionary%602>引数を<xref:System.String>使用して new をインスタンス化します。</span><span class="sxs-lookup"><span data-stu-id="be9a0-123">`<scg:Dictionary x:TypeArguments="sys:String,sys:String" ...>` instantiates a new <xref:System.Collections.Generic.Dictionary%602> with two <xref:System.String> type arguments.</span></span>

### <a name="queuekeyvaluepairstringstring"></a><span data-ttu-id="be9a0-124">キュー<キー\<値ペア文字列,文字列>></span><span class="sxs-lookup"><span data-stu-id="be9a0-124">Queue<KeyValuePair\<String,String>></span></span>

<span data-ttu-id="be9a0-125">`<scg:Queue x:TypeArguments="scg:KeyValuePair(sys:String,sys:String)" ...>`内部制約型の<xref:System.Collections.Generic.Queue%601>引数<xref:System.Collections.Generic.KeyValuePair%602><xref:System.String>と での制約を持つ新しいを<xref:System.String>インスタンス化します。</span><span class="sxs-lookup"><span data-stu-id="be9a0-125">`<scg:Queue x:TypeArguments="scg:KeyValuePair(sys:String,sys:String)" ...>` instantiates a new <xref:System.Collections.Generic.Queue%601> that has a constraint of <xref:System.Collections.Generic.KeyValuePair%602> with the inner constraint type arguments <xref:System.String> and <xref:System.String>.</span></span>

## <a name="xaml-2006-and-wpf-generic-xaml-usages"></a><span data-ttu-id="be9a0-126">XAML 2006 および WPF の汎用 XAML の使用法</span><span class="sxs-lookup"><span data-stu-id="be9a0-126">XAML 2006 and WPF Generic XAML Usages</span></span>

<span data-ttu-id="be9a0-127">XAML 2006 の使用法および WPF アプリケーションで使用される XAML の場合`x:TypeArguments`、XAML でのジェネリック型の使用方法には次の制限事項と、一般的なジェネリック型の使用が適用されます。</span><span class="sxs-lookup"><span data-stu-id="be9a0-127">For XAML 2006 usage, and XAML that is used for WPF applications, the following restrictions exist for `x:TypeArguments` and generic type usages from XAML in general:</span></span>

- <span data-ttu-id="be9a0-128">ジェネリック型を参照する汎用 XAML の使用法をサポートできるのは、XAML ファイルのルート要素だけです。</span><span class="sxs-lookup"><span data-stu-id="be9a0-128">Only the root element of a XAML file can support a generic XAML usage that references a generic type.</span></span>

- <span data-ttu-id="be9a0-129">ルート要素は、少なくとも 1 つの型引数を持つジェネリック型にマップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="be9a0-129">The root element must map to a generic type with at least one type argument.</span></span> <span data-ttu-id="be9a0-130">たとえば <xref:System.Windows.Navigation.PageFunction%601> です。</span><span class="sxs-lookup"><span data-stu-id="be9a0-130">An example is <xref:System.Windows.Navigation.PageFunction%601>.</span></span> <span data-ttu-id="be9a0-131">ページ関数は、WPF での XAML 汎用の使用サポートの主なシナリオです。</span><span class="sxs-lookup"><span data-stu-id="be9a0-131">The page functions are the primary scenario for XAML generic usage support in WPF.</span></span>

- <span data-ttu-id="be9a0-132">ジェネリックのルート要素 XAML オブジェクト要素も、 を使用して`x:Class`部分クラスを宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="be9a0-132">The root element XAML object element for the generic must also declare a partial class using `x:Class`.</span></span> <span data-ttu-id="be9a0-133">これは、WPF ビルド アクションを定義する場合にも当てはまります。</span><span class="sxs-lookup"><span data-stu-id="be9a0-133">This is true even if defining a WPF build action.</span></span>

- <span data-ttu-id="be9a0-134">`x:TypeArguments`ネストされたジェネリック制約を参照できません。</span><span class="sxs-lookup"><span data-stu-id="be9a0-134">`x:TypeArguments` cannot reference nested generic constraints.</span></span>

## <a name="xaml-2009-or-xaml-2006-with-no-wpf-30-or-wpf-35-dependency"></a><span data-ttu-id="be9a0-135">WPF 3.0 または WPF 3.5 の依存関係がない XAML 2009 または XAML 2006</span><span class="sxs-lookup"><span data-stu-id="be9a0-135">XAML 2009 or XAML 2006 with No WPF 3.0 or WPF 3.5 Dependency</span></span>

<span data-ttu-id="be9a0-136">XAML 2006 または XAML 2009 の .NET XAML サービスでは、汎用 XAML の使用に関する WPF 関連の制限が緩和されました。</span><span class="sxs-lookup"><span data-stu-id="be9a0-136">In .NET XAML Services for either XAML 2006 or XAML 2009, the WPF-related restrictions on generic XAML usage are relaxed.</span></span> <span data-ttu-id="be9a0-137">XAML マークアップ内の任意の位置で、バッキング型システムとオブジェクト モデルでサポートできる汎用オブジェクト要素をインスタンス化できます。</span><span class="sxs-lookup"><span data-stu-id="be9a0-137">You can instantiate a generic object element at any position in XAML markup that the backing type system and object model can support.</span></span>

<span data-ttu-id="be9a0-138">共通言語プリミティブの XAML 型を取得するために CLR 基本型をマッピングする代わりに XAML 2009 を使用する場合は、[共通 XAML 言語プリミティブの組み込み型を](types-for-primitives.md)`typeString`情報項目として使用できます。</span><span class="sxs-lookup"><span data-stu-id="be9a0-138">If you use XAML 2009 instead of mapping the CLR base types to obtain XAML types for common language primitives, you can use [Built-in Types for Common XAML Language Primitives](types-for-primitives.md) as information items in a `typeString`.</span></span> <span data-ttu-id="be9a0-139">たとえば、次のように宣言できます (プレフィックス マッピングは表示されませんが、x は XAML 2009 の XAML 言語 XAML 名前空間です)。</span><span class="sxs-lookup"><span data-stu-id="be9a0-139">For example, you could declare the following (prefix mappings not shown, but x is the XAML language XAML namespace for XAML 2009):</span></span>

```xaml
<my:BusinessObject x:TypeArguments="x:String,x:Int32"/>
```

<span data-ttu-id="be9a0-140">WPF で 、.NET Framework 4 または .NET Core 3.0 以降を対象とする場合は、XAML `x:TypeArguments` 2009 の機能を緩い XAML (マークアップ コンパイルされていない XAML) と共に使用できます。</span><span class="sxs-lookup"><span data-stu-id="be9a0-140">In WPF and when targeting .NET Framework 4 or .NET Core 3.0 (or later), you can use XAML 2009 features together with `x:TypeArguments` but only for loose XAML (XAML that is not markup-compiled).</span></span> <span data-ttu-id="be9a0-141">WPF 向けにマークアップ コンパイルされた XAML、および XAML の BAML 形式は、現在、XAML 2009 のキーワードと機能をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="be9a0-141">Markup-compiled XAML for WPF and the BAML form of XAML do not currently support the XAML 2009 keywords and features.</span></span> <span data-ttu-id="be9a0-142">XAML をマークアップ コンパイルする必要がある場合は[、XAML 2006 および WPF 汎用 XAML の使用方法](#xaml-2006-and-wpf-generic-xaml-usages)に関するセクションに記載されている制限の下で操作する必要があります。</span><span class="sxs-lookup"><span data-stu-id="be9a0-142">If you need to markup compile the XAML, you must operate under the restrictions noted in the [XAML 2006 and WPF Generic XAML Usages](#xaml-2006-and-wpf-generic-xaml-usages) section.</span></span> <span data-ttu-id="be9a0-143">BAML は .NET フレームワークでのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="be9a0-143">BAML is only supported in .NET Framework.</span></span>

## <a name="see-also"></a><span data-ttu-id="be9a0-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="be9a0-144">See also</span></span>

- [<span data-ttu-id="be9a0-145">x:Class ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="be9a0-145">x:Class Directive</span></span>](xclass-directive.md)
- [<span data-ttu-id="be9a0-146">x:Type マークアップ拡張機能</span><span class="sxs-lookup"><span data-stu-id="be9a0-146">x:Type Markup Extension</span></span>](xtype-markup-extension.md)
- [<span data-ttu-id="be9a0-147">共通の XAML 言語プリミティブの組み込み型</span><span class="sxs-lookup"><span data-stu-id="be9a0-147">Built-in Types for Common XAML Language Primitives</span></span>](types-for-primitives.md)
- [<span data-ttu-id="be9a0-148">XAML のジェネリック</span><span class="sxs-lookup"><span data-stu-id="be9a0-148">Generics in XAML</span></span>](generics.md)
