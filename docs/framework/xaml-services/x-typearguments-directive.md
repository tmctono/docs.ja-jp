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
ms.openlocfilehash: 79264687b3a031fcf02ce65a907c7f21e216fbc9
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64622763"
---
# <a name="xtypearguments-directive"></a><span data-ttu-id="6dd59-102">x:TypeArguments ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="6dd59-102">x:TypeArguments Directive</span></span>
<span data-ttu-id="6dd59-103">パスの制約は、ジェネリック型のコンス トラクターに汎用の引数を入力します。</span><span class="sxs-lookup"><span data-stu-id="6dd59-103">Passes constraining type arguments of a generic to the constructor of the generic type.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="6dd59-104">XAML 属性の使用方法</span><span class="sxs-lookup"><span data-stu-id="6dd59-104">XAML Attribute Usage</span></span>  
  
```xaml  
<object x:TypeArguments="typeString" .../>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="6dd59-105">XAML 値</span><span class="sxs-lookup"><span data-stu-id="6dd59-105">XAML Values</span></span>  
  
|||  
|-|-|  
|`object`|<span data-ttu-id="6dd59-106">CLR のジェネリック型によってサポートされる XAML 型のオブジェクト要素の宣言。</span><span class="sxs-lookup"><span data-stu-id="6dd59-106">An object element declaration of a XAML type, which is backed by a CLR generic type.</span></span> <span data-ttu-id="6dd59-107">場合`object`が既定の XAML 名前空間からされていない XAML 型を表して`object`を XAML 名前空間を示すためにプレフィックスが必要です、`object`存在します。</span><span class="sxs-lookup"><span data-stu-id="6dd59-107">If `object` refers to a XAML type that is not from the default XAML namespace, `object` requires a prefix to indicate the XAML namespace where `object` exists.</span></span>|  
|`typeString`|<span data-ttu-id="6dd59-108">1 つまたは複数の XAML を宣言する文字列は、CLR のジェネリック型の型引数を指定する文字列として名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="6dd59-108">A string that declares one or more XAML type names as strings, which supplies the type arguments for the CLR generic type.</span></span> <span data-ttu-id="6dd59-109">追加の構文のノートの「解説」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6dd59-109">See Remarks for additional syntax notes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6dd59-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="6dd59-110">Remarks</span></span>  
 <span data-ttu-id="6dd59-111">ほとんどの場合、情報の項目として使用される XAML 型を`typeString`文字列が付きます。</span><span class="sxs-lookup"><span data-stu-id="6dd59-111">In most cases, the XAML types that are used as an information item in a `typeString` string are prefixed.</span></span> <span data-ttu-id="6dd59-112">一般的な種類の CLR のジェネリック制約 (たとえば、<xref:System.Int32>と<xref:System.String>) CLR 基本クラス ライブラリから取得します。</span><span class="sxs-lookup"><span data-stu-id="6dd59-112">Typical types of CLR generic constraints (for example, <xref:System.Int32> and <xref:System.String>) come from CLR base class libraries.</span></span> <span data-ttu-id="6dd59-113">これらのライブラリでは、標準的なマップされたフレームワーク固有の既定の XAML 名前空間ではなく、そのため、XAML の使用状況のプレフィックスのマッピングが必要です。</span><span class="sxs-lookup"><span data-stu-id="6dd59-113">Those libraries are not mapped to typical framework-specific default XAML namespaces, and therefore, require a prefix mapping for XAML usage.</span></span>  
  
 <span data-ttu-id="6dd59-114">1 つ以上の XAML 型名を指定するには、コンマ区切り記号を使用します。</span><span class="sxs-lookup"><span data-stu-id="6dd59-114">You can specify more than one XAML type name by using a comma delimiter.</span></span>  
  
 <span data-ttu-id="6dd59-115">ジェネリック制約自体がジェネリック型を使用する場合は、かっこ () で入れ子になった制約の型引数を格納できます。</span><span class="sxs-lookup"><span data-stu-id="6dd59-115">If the generic constraints themselves use generic types, the nested constraint type arguments can be contained by parentheses ().</span></span>  
  
 <span data-ttu-id="6dd59-116">注意この定義の`x:TypeArguments`は .NET Framework XAML サービスに固有と CLR バッキングを使用します。</span><span class="sxs-lookup"><span data-stu-id="6dd59-116">Note that this definition of `x:TypeArguments` is specific to .NET Framework XAML Services and using CLR backing.</span></span> <span data-ttu-id="6dd59-117">言語レベルの定義が記載[ \[MS XAML\]セクション 5.3.11](https://go.microsoft.com/fwlink/?LinkId=114525)します。</span><span class="sxs-lookup"><span data-stu-id="6dd59-117">A language-level definition can be found in [\[MS-XAML\] Section 5.3.11](https://go.microsoft.com/fwlink/?LinkId=114525).</span></span>  
  
## <a name="usage-examples"></a><span data-ttu-id="6dd59-118">使用例</span><span class="sxs-lookup"><span data-stu-id="6dd59-118">Usage Examples</span></span>  
 <span data-ttu-id="6dd59-119">これらの例については、次の XAML 名前空間の定義が宣言されていることを想定します。</span><span class="sxs-lookup"><span data-stu-id="6dd59-119">For these examples, assume that the following XAML namespace definitions are declared:</span></span>  
  
```  
xmlns:sys="clr-namespace:System;assembly=mscorlib"  
xmlns:scg="clr-namespace:System.Collections.Generic;assembly=mscorlib"  
```  
  
### <a name="liststring"></a><span data-ttu-id="6dd59-120">リスト\<文字列 ></span><span class="sxs-lookup"><span data-stu-id="6dd59-120">List\<String></span></span>  
 <span data-ttu-id="6dd59-121">`<scg:List x:TypeArguments="sys:String" ...>` 新しいインスタンスを作成<xref:System.Collections.Generic.List%601>で、<xref:System.String>引数を入力します。</span><span class="sxs-lookup"><span data-stu-id="6dd59-121">`<scg:List x:TypeArguments="sys:String" ...>` instantiates a new <xref:System.Collections.Generic.List%601> with a <xref:System.String> type argument.</span></span>  
  
### <a name="dictionarystringstring"></a><span data-ttu-id="6dd59-122">ディクショナリ\<String, String ></span><span class="sxs-lookup"><span data-stu-id="6dd59-122">Dictionary\<String,String></span></span>  
 <span data-ttu-id="6dd59-123">`<scg:Dictionary x:TypeArguments="sys:String,sys:String" ...>` 新しいインスタンスを作成<xref:System.Collections.Generic.Dictionary%602>の 2 つ<xref:System.String>引数を入力します。</span><span class="sxs-lookup"><span data-stu-id="6dd59-123">`<scg:Dictionary x:TypeArguments="sys:String,sys:String" ...>` instantiates a new <xref:System.Collections.Generic.Dictionary%602> with two <xref:System.String> type arguments.</span></span>  
  
### <a name="queuekeyvaluepairstringstring"></a><span data-ttu-id="6dd59-124">キュー < KeyValuePair\<String, String >></span><span class="sxs-lookup"><span data-stu-id="6dd59-124">Queue<KeyValuePair\<String,String>></span></span>  
 <span data-ttu-id="6dd59-125">`<scg:Queue x:TypeArguments="scg:KeyValuePair(sys:String,sys:String)" ...>` 新しいインスタンスを作成<xref:System.Collections.Generic.Queue%601>の制約を持つ<xref:System.Collections.Generic.KeyValuePair%602>内部制約の型引数を持つ<xref:System.String>と<xref:System.String>します。</span><span class="sxs-lookup"><span data-stu-id="6dd59-125">`<scg:Queue x:TypeArguments="scg:KeyValuePair(sys:String,sys:String)" ...>` instantiates a new <xref:System.Collections.Generic.Queue%601> that has a constraint of <xref:System.Collections.Generic.KeyValuePair%602> with the inner constraint type arguments <xref:System.String> and <xref:System.String>.</span></span>  
  
## <a name="xaml-2006-and-wpf-generic-xaml-usages"></a><span data-ttu-id="6dd59-126">XAML 2006 および WPF XAML のジェネリックの使用法</span><span class="sxs-lookup"><span data-stu-id="6dd59-126">XAML 2006 and WPF Generic XAML Usages</span></span>  
 <span data-ttu-id="6dd59-127">XAML 2006 の使用状況、および XAML の WPF アプリケーションで使用する、次の制限の存在の`x:TypeArguments`および一般的な XAML のジェネリック型の使用状況。</span><span class="sxs-lookup"><span data-stu-id="6dd59-127">For XAML 2006 usage, and XAML that is used for WPF applications, the following restrictions exist for `x:TypeArguments` and generic type usages from XAML in general:</span></span>  
  
- <span data-ttu-id="6dd59-128">XAML ファイルのルート要素だけでは、ジェネリック型を参照する汎用的な XAML 使用量をサポートできます。</span><span class="sxs-lookup"><span data-stu-id="6dd59-128">Only the root element of a XAML file can support a generic XAML usage that references a generic type.</span></span>  
  
- <span data-ttu-id="6dd59-129">ルート要素は、少なくとも 1 つの型引数を持つジェネリック型にマップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6dd59-129">The root element must map to a generic type with at least one type argument.</span></span> <span data-ttu-id="6dd59-130">例としては、<xref:System.Windows.Navigation.PageFunction%601>します。</span><span class="sxs-lookup"><span data-stu-id="6dd59-130">An example is <xref:System.Windows.Navigation.PageFunction%601>.</span></span> <span data-ttu-id="6dd59-131">ページ関数は、WPF における XAML のジェネリックの使用法サポートの主なシナリオです。</span><span class="sxs-lookup"><span data-stu-id="6dd59-131">The page functions are the primary scenario for XAML generic usage support in WPF.</span></span>  
  
- <span data-ttu-id="6dd59-132">ジェネリックのルート要素の XAML オブジェクト要素が、部分クラスを使用して、宣言する必要がありますも`x:Class`します。</span><span class="sxs-lookup"><span data-stu-id="6dd59-132">The root element XAML object element for the generic must also declare a partial class using `x:Class`.</span></span> <span data-ttu-id="6dd59-133">これは、ビルド アクションを WPF を定義する場合でも当てはまります。</span><span class="sxs-lookup"><span data-stu-id="6dd59-133">This is true even if defining a WPF build action.</span></span>  
  
- <span data-ttu-id="6dd59-134">`x:TypeArguments` 入れ子になったジェネリック制約は参照できません。</span><span class="sxs-lookup"><span data-stu-id="6dd59-134">`x:TypeArguments` cannot reference nested generic constraints.</span></span>  
  
## <a name="xaml-2009-or-xaml-2006-with-no-wpf-30-or-wpf-35-dependency"></a><span data-ttu-id="6dd59-135">XAML 2009 または XAML 2006 なし、WPF 3.0 または 3.5 の WPF 依存関係</span><span class="sxs-lookup"><span data-stu-id="6dd59-135">XAML 2009 or XAML 2006 with No WPF 3.0 or WPF 3.5 Dependency</span></span>  
 <span data-ttu-id="6dd59-136">XAML 2006 または XAML 2009 のいずれかの .NET Framework XAML サービスでは、WPF に関連する XAML のジェネリックの使用法の制限が緩和されます。</span><span class="sxs-lookup"><span data-stu-id="6dd59-136">In .NET Framework XAML Services for either XAML 2006 or XAML 2009, the WPF-related restrictions on generic XAML usage are relaxed.</span></span> <span data-ttu-id="6dd59-137">バッキング型システムとオブジェクト モデルをサポートする XAML のマークアップ内の任意の位置にある汎用オブジェクトの要素をインスタンス化することができます。</span><span class="sxs-lookup"><span data-stu-id="6dd59-137">You can instantiate a generic object element at any position in XAML markup that the backing type system and object model can support.</span></span>  
  
 <span data-ttu-id="6dd59-138">XAML 2009 を使用する場合、CLR をマップする代わりに基本の共通言語プリミティブの XAML 型を取得する型、使用することができます[共通の XAML 言語プリミティブの組み込み型](built-in-types-for-common-xaml-language-primitives.md)内の情報項目として、`typeString`します。</span><span class="sxs-lookup"><span data-stu-id="6dd59-138">If you use XAML 2009 instead of mapping the CLR base types to obtain XAML types for common language primitives, you can use [Built-in Types for Common XAML Language Primitives](built-in-types-for-common-xaml-language-primitives.md) as information items in a `typeString`.</span></span> <span data-ttu-id="6dd59-139">たとえば、次を宣言できます (表示されませんが、プレフィックスのマッピングが、x は XAML 2009 の XAML 言語の XAML 名前空間)。</span><span class="sxs-lookup"><span data-stu-id="6dd59-139">For example, you could declare the following (prefix mappings not shown, but x is the XAML language XAML namespace for XAML 2009):</span></span>  
  
```xaml  
<my:BusinessObject x:TypeArguments="x:String,x:Int32"/>  
```  
  
 <span data-ttu-id="6dd59-140">対象とする場合と WPF で[!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]、と共に XAML 2009 の機能を使用する`x:TypeArguments`loose XAML (XAML マークアップ コンパイルされていない) に対してのみです。</span><span class="sxs-lookup"><span data-stu-id="6dd59-140">In WPF and when targeting [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], you can use XAML 2009 features together with `x:TypeArguments` but only for loose XAML (XAML that is not markup-compiled).</span></span> <span data-ttu-id="6dd59-141">WPF 向けにマークアップ コンパイルされた XAML、および XAML の BAML 形式は、現在、XAML 2009 のキーワードと機能をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="6dd59-141">Markup-compiled XAML for WPF and the BAML form of XAML do not currently support the XAML 2009 keywords and features.</span></span> <span data-ttu-id="6dd59-142">必要なマークアップをコンパイルする場合、XAML は、「XAML 2006 および WPF 汎用 XAML 使用法」セクションに記載されている制限で動作する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6dd59-142">If you need to markup compile the XAML, you must operate under the restrictions noted in the "XAML 2006 and WPF Generic XAML Usages" section.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6dd59-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="6dd59-143">See also</span></span>

- [<span data-ttu-id="6dd59-144">x:Class ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="6dd59-144">x:Class Directive</span></span>](x-class-directive.md)
- [<span data-ttu-id="6dd59-145">x:Type マークアップ拡張機能</span><span class="sxs-lookup"><span data-stu-id="6dd59-145">x:Type Markup Extension</span></span>](x-type-markup-extension.md)
- [<span data-ttu-id="6dd59-146">共通の XAML 言語プリミティブの組み込み型</span><span class="sxs-lookup"><span data-stu-id="6dd59-146">Built-in Types for Common XAML Language Primitives</span></span>](built-in-types-for-common-xaml-language-primitives.md)
- [<span data-ttu-id="6dd59-147">XAML のジェネリック</span><span class="sxs-lookup"><span data-stu-id="6dd59-147">Generics in XAML</span></span>](generics-in-xaml.md)
