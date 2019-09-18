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
ms.openlocfilehash: a2a960870d368e57272b3368e69eb38ebbe2ba5d
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053714"
---
# <a name="xtypearguments-directive"></a><span data-ttu-id="05d5a-102">x:TypeArguments ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="05d5a-102">x:TypeArguments Directive</span></span>
<span data-ttu-id="05d5a-103">ジェネリックの制約型引数をジェネリック型のコンストラクターに渡します。</span><span class="sxs-lookup"><span data-stu-id="05d5a-103">Passes constraining type arguments of a generic to the constructor of the generic type.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="05d5a-104">XAML 属性の使用方法</span><span class="sxs-lookup"><span data-stu-id="05d5a-104">XAML Attribute Usage</span></span>  
  
```xaml  
<object x:TypeArguments="typeString" .../>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="05d5a-105">XAML 値</span><span class="sxs-lookup"><span data-stu-id="05d5a-105">XAML Values</span></span>  
  
|||  
|-|-|  
|`object`|<span data-ttu-id="05d5a-106">CLR ジェネリック型によってサポートされる XAML 型のオブジェクト要素宣言。</span><span class="sxs-lookup"><span data-stu-id="05d5a-106">An object element declaration of a XAML type, which is backed by a CLR generic type.</span></span> <span data-ttu-id="05d5a-107">が`object`既定の xaml 名前空間からではない xaml 型を参照し`object`ている場合、は、 `object`が存在する場合に xaml 名前空間を示すプレフィックスを必要とします。</span><span class="sxs-lookup"><span data-stu-id="05d5a-107">If `object` refers to a XAML type that is not from the default XAML namespace, `object` requires a prefix to indicate the XAML namespace where `object` exists.</span></span>|  
|`typeString`|<span data-ttu-id="05d5a-108">1つ以上の XAML 型名を文字列として宣言する文字列。この文字列は、CLR ジェネリック型の型引数を提供します。</span><span class="sxs-lookup"><span data-stu-id="05d5a-108">A string that declares one or more XAML type names as strings, which supplies the type arguments for the CLR generic type.</span></span> <span data-ttu-id="05d5a-109">追加の構文ノートについては、「解説」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="05d5a-109">See Remarks for additional syntax notes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="05d5a-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="05d5a-110">Remarks</span></span>  
 <span data-ttu-id="05d5a-111">ほとんどの場合、 `typeString`文字列の情報項目として使用される XAML 型にはプレフィックスが付きます。</span><span class="sxs-lookup"><span data-stu-id="05d5a-111">In most cases, the XAML types that are used as an information item in a `typeString` string are prefixed.</span></span> <span data-ttu-id="05d5a-112">Clr ジェネリック制約の一般的な型 (や<xref:System.Int32> <xref:System.String>など) は、clr 基底クラスライブラリから取得されます。</span><span class="sxs-lookup"><span data-stu-id="05d5a-112">Typical types of CLR generic constraints (for example, <xref:System.Int32> and <xref:System.String>) come from CLR base class libraries.</span></span> <span data-ttu-id="05d5a-113">これらのライブラリは、フレームワーク固有の一般的な既定の XAML 名前空間にマップされないため、XAML の使用にはプレフィックスマッピングが必要です。</span><span class="sxs-lookup"><span data-stu-id="05d5a-113">Those libraries are not mapped to typical framework-specific default XAML namespaces, and therefore, require a prefix mapping for XAML usage.</span></span>  
  
 <span data-ttu-id="05d5a-114">複数の XAML 型名を指定するには、コンマ区切り記号を使用します。</span><span class="sxs-lookup"><span data-stu-id="05d5a-114">You can specify more than one XAML type name by using a comma delimiter.</span></span>  
  
 <span data-ttu-id="05d5a-115">ジェネリック制約自体がジェネリック型を使用する場合は、入れ子になった制約型の引数をかっこ () で囲むことができます。</span><span class="sxs-lookup"><span data-stu-id="05d5a-115">If the generic constraints themselves use generic types, the nested constraint type arguments can be contained by parentheses ().</span></span>  
  
 <span data-ttu-id="05d5a-116">この定義は .NET Framework XAML `x:TypeArguments`サービスと CLR バッキングの使用に固有であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="05d5a-116">Note that this definition of `x:TypeArguments` is specific to .NET Framework XAML Services and using CLR backing.</span></span> <span data-ttu-id="05d5a-117">言語レベルの定義については、 [ \[\] 「5.3.11」セクション](https://go.microsoft.com/fwlink/?LinkId=114525)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="05d5a-117">A language-level definition can be found in [\[MS-XAML\] Section 5.3.11](https://go.microsoft.com/fwlink/?LinkId=114525).</span></span>  
  
## <a name="usage-examples"></a><span data-ttu-id="05d5a-118">使用例</span><span class="sxs-lookup"><span data-stu-id="05d5a-118">Usage Examples</span></span>  
 <span data-ttu-id="05d5a-119">これらの例では、次の XAML 名前空間定義が宣言されているものとします。</span><span class="sxs-lookup"><span data-stu-id="05d5a-119">For these examples, assume that the following XAML namespace definitions are declared:</span></span>  
  
```xaml  
xmlns:sys="clr-namespace:System;assembly=mscorlib"  
xmlns:scg="clr-namespace:System.Collections.Generic;assembly=mscorlib"  
```  
  
### <a name="liststring"></a><span data-ttu-id="05d5a-120">リスト\<文字列 ></span><span class="sxs-lookup"><span data-stu-id="05d5a-120">List\<String></span></span>  
 <span data-ttu-id="05d5a-121">`<scg:List x:TypeArguments="sys:String" ...>`<xref:System.String>型引数を<xref:System.Collections.Generic.List%601>使用して新しいをインスタンス化します。</span><span class="sxs-lookup"><span data-stu-id="05d5a-121">`<scg:List x:TypeArguments="sys:String" ...>` instantiates a new <xref:System.Collections.Generic.List%601> with a <xref:System.String> type argument.</span></span>  
  
### <a name="dictionarystringstring"></a><span data-ttu-id="05d5a-122">ディクショナリ\<文字列、文字列 ></span><span class="sxs-lookup"><span data-stu-id="05d5a-122">Dictionary\<String,String></span></span>  
 <span data-ttu-id="05d5a-123">`<scg:Dictionary x:TypeArguments="sys:String,sys:String" ...>`2つ<xref:System.Collections.Generic.Dictionary%602> <xref:System.String>の型引数を使用して、新しいをインスタンス化します。</span><span class="sxs-lookup"><span data-stu-id="05d5a-123">`<scg:Dictionary x:TypeArguments="sys:String,sys:String" ...>` instantiates a new <xref:System.Collections.Generic.Dictionary%602> with two <xref:System.String> type arguments.</span></span>  
  
### <a name="queuekeyvaluepairstringstring"></a><span data-ttu-id="05d5a-124">Queue < KeyValuePair\<string、string > ></span><span class="sxs-lookup"><span data-stu-id="05d5a-124">Queue<KeyValuePair\<String,String>></span></span>  
 <span data-ttu-id="05d5a-125">`<scg:Queue x:TypeArguments="scg:KeyValuePair(sys:String,sys:String)" ...>`内部制約型<xref:System.Collections.Generic.Queue%601>引数<xref:System.Collections.Generic.KeyValuePair%602> <xref:System.String> と<xref:System.String>を使用して、の制約を持つ新しいをインスタンス化します。</span><span class="sxs-lookup"><span data-stu-id="05d5a-125">`<scg:Queue x:TypeArguments="scg:KeyValuePair(sys:String,sys:String)" ...>` instantiates a new <xref:System.Collections.Generic.Queue%601> that has a constraint of <xref:System.Collections.Generic.KeyValuePair%602> with the inner constraint type arguments <xref:System.String> and <xref:System.String>.</span></span>  
  
## <a name="xaml-2006-and-wpf-generic-xaml-usages"></a><span data-ttu-id="05d5a-126">XAML 2006 と WPF 汎用 XAML の使用</span><span class="sxs-lookup"><span data-stu-id="05d5a-126">XAML 2006 and WPF Generic XAML Usages</span></span>  
 <span data-ttu-id="05d5a-127">Xaml 2006 の使用、および WPF アプリケーションで使用される xaml では、一般的に xaml `x:TypeArguments`からのジェネリック型の使用に関して次の制限があります。</span><span class="sxs-lookup"><span data-stu-id="05d5a-127">For XAML 2006 usage, and XAML that is used for WPF applications, the following restrictions exist for `x:TypeArguments` and generic type usages from XAML in general:</span></span>  
  
- <span data-ttu-id="05d5a-128">ジェネリック型を参照する汎用 XAML 使用をサポートできるのは、XAML ファイルのルート要素だけです。</span><span class="sxs-lookup"><span data-stu-id="05d5a-128">Only the root element of a XAML file can support a generic XAML usage that references a generic type.</span></span>  
  
- <span data-ttu-id="05d5a-129">ルート要素は、少なくとも1つの型引数を持つジェネリック型にマップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="05d5a-129">The root element must map to a generic type with at least one type argument.</span></span> <span data-ttu-id="05d5a-130">たとえば、の<xref:System.Windows.Navigation.PageFunction%601>ようになります。</span><span class="sxs-lookup"><span data-stu-id="05d5a-130">An example is <xref:System.Windows.Navigation.PageFunction%601>.</span></span> <span data-ttu-id="05d5a-131">ページ関数は、WPF の XAML 汎用使用サポートの主要なシナリオです。</span><span class="sxs-lookup"><span data-stu-id="05d5a-131">The page functions are the primary scenario for XAML generic usage support in WPF.</span></span>  
  
- <span data-ttu-id="05d5a-132">ジェネリックのルート要素 XAML オブジェクト要素も、を使用して`x:Class`部分クラスを宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="05d5a-132">The root element XAML object element for the generic must also declare a partial class using `x:Class`.</span></span> <span data-ttu-id="05d5a-133">これは、WPF ビルドアクションを定義する場合にも当てはまります。</span><span class="sxs-lookup"><span data-stu-id="05d5a-133">This is true even if defining a WPF build action.</span></span>  
  
- <span data-ttu-id="05d5a-134">`x:TypeArguments`入れ子になったジェネリック制約を参照することはできません。</span><span class="sxs-lookup"><span data-stu-id="05d5a-134">`x:TypeArguments` cannot reference nested generic constraints.</span></span>  
  
## <a name="xaml-2009-or-xaml-2006-with-no-wpf-30-or-wpf-35-dependency"></a><span data-ttu-id="05d5a-135">WPF 3.0 または WPF 3.5 依存関係のない XAML 2009 または XAML 2006</span><span class="sxs-lookup"><span data-stu-id="05d5a-135">XAML 2009 or XAML 2006 with No WPF 3.0 or WPF 3.5 Dependency</span></span>  
 <span data-ttu-id="05d5a-136">Xaml 2006 または XAML 2009 の xaml サービスでは、一般的な XAML の使用に関する WPF 関連の制限は緩やかに .NET Framework ます。</span><span class="sxs-lookup"><span data-stu-id="05d5a-136">In .NET Framework XAML Services for either XAML 2006 or XAML 2009, the WPF-related restrictions on generic XAML usage are relaxed.</span></span> <span data-ttu-id="05d5a-137">バッキング型システムおよびオブジェクトモデルがサポートできる XAML マークアップ内の任意の位置で、ジェネリックオブジェクト要素をインスタンス化できます。</span><span class="sxs-lookup"><span data-stu-id="05d5a-137">You can instantiate a generic object element at any position in XAML markup that the backing type system and object model can support.</span></span>  
  
 <span data-ttu-id="05d5a-138">CLR 基本型をマップして共通言語プリミティブの XAML 型を取得するのではなく、XAML 2009 を使用する場合は、 `typeString`[共通の Xaml 言語プリミティブの組み込み型](built-in-types-for-common-xaml-language-primitives.md)を内の情報項目として使用できます。</span><span class="sxs-lookup"><span data-stu-id="05d5a-138">If you use XAML 2009 instead of mapping the CLR base types to obtain XAML types for common language primitives, you can use [Built-in Types for Common XAML Language Primitives](built-in-types-for-common-xaml-language-primitives.md) as information items in a `typeString`.</span></span> <span data-ttu-id="05d5a-139">たとえば、次のように宣言できます (プレフィックスの割り当ては表示されませんが、x は xaml 言語2009の xaml 言語の xaml 名前空間です)。</span><span class="sxs-lookup"><span data-stu-id="05d5a-139">For example, you could declare the following (prefix mappings not shown, but x is the XAML language XAML namespace for XAML 2009):</span></span>  
  
```xaml  
<my:BusinessObject x:TypeArguments="x:String,x:Int32"/>  
```  
  
 <span data-ttu-id="05d5a-140">WPF で .NET Framework 4 を対象とする場合は、xaml 2009 の機能を`x:TypeArguments`と共に使用できますが、ルース xaml (マークアップコンパイルされていない xaml) に対してのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="05d5a-140">In WPF and when targeting .NET Framework 4, you can use XAML 2009 features together with `x:TypeArguments` but only for loose XAML (XAML that is not markup-compiled).</span></span> <span data-ttu-id="05d5a-141">WPF 向けにマークアップ コンパイルされた XAML、および XAML の BAML 形式は、現在、XAML 2009 のキーワードと機能をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="05d5a-141">Markup-compiled XAML for WPF and the BAML form of XAML do not currently support the XAML 2009 keywords and features.</span></span> <span data-ttu-id="05d5a-142">XAML をマークアップする必要がある場合は、「XAML 2006 および WPF 汎用 XAML の使用」セクションに記載されている制限事項に従って操作する必要があります。</span><span class="sxs-lookup"><span data-stu-id="05d5a-142">If you need to markup compile the XAML, you must operate under the restrictions noted in the "XAML 2006 and WPF Generic XAML Usages" section.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05d5a-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="05d5a-143">See also</span></span>

- [<span data-ttu-id="05d5a-144">x:Class ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="05d5a-144">x:Class Directive</span></span>](x-class-directive.md)
- [<span data-ttu-id="05d5a-145">x:Type マークアップ拡張機能</span><span class="sxs-lookup"><span data-stu-id="05d5a-145">x:Type Markup Extension</span></span>](x-type-markup-extension.md)
- [<span data-ttu-id="05d5a-146">共通の XAML 言語プリミティブの組み込み型</span><span class="sxs-lookup"><span data-stu-id="05d5a-146">Built-in Types for Common XAML Language Primitives</span></span>](built-in-types-for-common-xaml-language-primitives.md)
- [<span data-ttu-id="05d5a-147">XAML のジェネリック</span><span class="sxs-lookup"><span data-stu-id="05d5a-147">Generics in XAML</span></span>](generics-in-xaml.md)
