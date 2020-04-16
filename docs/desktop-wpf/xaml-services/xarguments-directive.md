---
title: x:Arguments ディレクティブ
ms.date: 03/30/2017
helpviewer_keywords:
- x:Arguments directive [XAML Services]
- Arguments directive in XAML [XAML Services]
- XAML [XAML Services], x:Arguments directive
ms.assetid: 87cc10b0-b610-4025-b6b0-ab27ca27c92e
ms.openlocfilehash: 5ec6e192688e1065ea847db6c175ad9da0e743fe
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432834"
---
# <a name="xarguments-directive"></a><span data-ttu-id="37462-102">x:Arguments ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="37462-102">x:Arguments Directive</span></span>

<span data-ttu-id="37462-103">XAML でのパラメーターなしのコンストラクター オブジェクト要素宣言、またはファクトリ メソッド オブジェクト宣言の構築引数をパッケージ化します。</span><span class="sxs-lookup"><span data-stu-id="37462-103">Packages construction arguments for a non-parameterless constructor object element declaration in XAML, or for a factory method object declaration.</span></span>

## <a name="xaml-element-usage-nonparameterless-constructor"></a><span data-ttu-id="37462-104">XAML 要素の使用方法 (非パラメーターなしのコンストラクター)</span><span class="sxs-lookup"><span data-stu-id="37462-104">XAML Element Usage (Nonparameterless constructor)</span></span>

```xaml
<object ...>
  <x:Arguments>
    oneOrMoreObjectElements
  </x:Arguments>
</object>
```

## <a name="xaml-element-usage-factory-method"></a><span data-ttu-id="37462-105">XAML 要素の使用方法 (ファクトリ メソッド)</span><span class="sxs-lookup"><span data-stu-id="37462-105">XAML Element Usage (factory method)</span></span>

```xaml
<object x:FactoryMethod="methodName"...>
  <x:Arguments>
    oneOrMoreObjectElements
  </x:Arguments>
</object>
```

## <a name="xaml-values"></a><span data-ttu-id="37462-106">XAML 値</span><span class="sxs-lookup"><span data-stu-id="37462-106">XAML Values</span></span>

|||
|-|-|
|`oneOrMoreObjectElements`|<span data-ttu-id="37462-107">バッキング非パラメーターのコンストラクターまたはファクトリ メソッドに渡す引数を指定する 1 つ以上のオブジェクト要素。</span><span class="sxs-lookup"><span data-stu-id="37462-107">One or more object elements that specify arguments to be passed to the backing non-parameterless constructor or factory method.</span></span><br /><br /> <span data-ttu-id="37462-108">一般的な使用方法は、オブジェクト要素内の初期化テキストを使用して、実際の引数値を指定することです。</span><span class="sxs-lookup"><span data-stu-id="37462-108">Typical usage is to use initialization text within the object elements to specify the actual argument values.</span></span> <span data-ttu-id="37462-109">「例」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="37462-109">See Examples section.</span></span><br /><br /> <span data-ttu-id="37462-110">要素の順序は重要です。</span><span class="sxs-lookup"><span data-stu-id="37462-110">The order of the elements is significant.</span></span> <span data-ttu-id="37462-111">XAML 型は、バッキング コンストラクターまたはファクトリ メソッドのオーバーロードの型と型の順序と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="37462-111">The XAML types in order must match the types and type order of the backing constructor or factory method overload.</span></span>|
|`methodName`|<span data-ttu-id="37462-112">引数`x:Arguments`を処理するファクトリ メソッドの名前。</span><span class="sxs-lookup"><span data-stu-id="37462-112">The name of the factory method that should process any `x:Arguments` arguments.</span></span>|

## <a name="dependencies"></a><span data-ttu-id="37462-113">依存関係</span><span class="sxs-lookup"><span data-stu-id="37462-113">Dependencies</span></span>

<span data-ttu-id="37462-114">`x:FactoryMethod`適用される範囲と動作を`x:Arguments`変更できます。</span><span class="sxs-lookup"><span data-stu-id="37462-114">`x:FactoryMethod` can modify the scope and behavior where `x:Arguments` applies.</span></span>

<span data-ttu-id="37462-115">no`x:FactoryMethod`を指定すると`x:Arguments`、バッキング コンストラクターの代替 (既定以外の) シグネチャに適用されます。</span><span class="sxs-lookup"><span data-stu-id="37462-115">If no `x:FactoryMethod` is specified, `x:Arguments` applies to alternate (non-default) signatures of the backing constructors.</span></span>

<span data-ttu-id="37462-116">指定`x:FactoryMethod`した場合は`x:Arguments`、名前付きメソッドのオーバーロードに適用されます。</span><span class="sxs-lookup"><span data-stu-id="37462-116">If `x:FactoryMethod` is specified, `x:Arguments` applies to an overload of the named method.</span></span>

## <a name="remarks"></a><span data-ttu-id="37462-117">解説</span><span class="sxs-lookup"><span data-stu-id="37462-117">Remarks</span></span>

<span data-ttu-id="37462-118">XAML 2006 では、初期化テキストを使用して既定以外の初期化をサポートできます。</span><span class="sxs-lookup"><span data-stu-id="37462-118">XAML 2006 can support non-default initialization through initialization text.</span></span> <span data-ttu-id="37462-119">しかし、初期化テキスト構築技術の実用化は限られている。</span><span class="sxs-lookup"><span data-stu-id="37462-119">However, the practical application of an initialization text construction technique is limited.</span></span> <span data-ttu-id="37462-120">初期化テキストは単一のテキスト文字列として扱われます。したがって、カスタム情報項目と文字列からのカスタム区切り記号を解析できる構築動作に対して型コンバーターが定義されていない限り、単一のパラメーター初期化の機能を追加するだけです。</span><span class="sxs-lookup"><span data-stu-id="37462-120">Initialization text is treated as a single text string; therefore, it only adds capability for a single parameter initialization unless a type converter is defined for the construction behavior that can parse custom information items and custom delimiters from the string.</span></span> <span data-ttu-id="37462-121">また、オブジェクト ロジックへのテキスト文字列は、実際の文字列以外のプリミティブを処理するための、指定された XAML パーサーのネイティブな既定の型コンバーターである可能性があります。</span><span class="sxs-lookup"><span data-stu-id="37462-121">Also, the text string to object logic is potentially a given XAML parser's native default type converter for handling primitives other than a true string.</span></span>

<span data-ttu-id="37462-122">XAML`x:Arguments`の使用法は、一般的な意味でのプロパティ要素の使用ではありません。</span><span class="sxs-lookup"><span data-stu-id="37462-122">The `x:Arguments` XAML usage is not property element usage in the typical sense, because the directive markup does not reference the containing object element's type.</span></span> <span data-ttu-id="37462-123">これは、マークアップが子コンテンツの既定以外の範囲`x:Code`として解釈される要素がマークされている場合など、他のディレクティブに似たものです。</span><span class="sxs-lookup"><span data-stu-id="37462-123">It is more akin to other directives such as `x:Code` where the element demarks a range in which the markup should be interpreted as other than the default for child contents.</span></span> <span data-ttu-id="37462-124">この場合、各オブジェクト要素の XAML 型は、使用`x:Arguments`法で参照しようとしている特定のコンストラクター ファクトリ メソッド シグネチャを決定するために XAML パーサーによって使用される引数の型に関する情報を伝達します。</span><span class="sxs-lookup"><span data-stu-id="37462-124">In this case, the XAML type of each object element communicates information about the argument types, which is used by XAML parsers to determine which specific constructor factory method signature an `x:Arguments` usage is attempting to reference.</span></span>

<span data-ttu-id="37462-125">`x:Arguments`オブジェクト要素が構築される場合は、オブジェクト要素の他のプロパティ要素、コンテンツ、内部テキスト、または初期化文字列の前に置く必要があります。</span><span class="sxs-lookup"><span data-stu-id="37462-125">`x:Arguments` for an object element being constructed must precede any other property elements, content, inner text, or initialization strings of the object element.</span></span> <span data-ttu-id="37462-126">内部`x:Arguments`のオブジェクト要素には、その XAML 型とそのバッキング コンストラクターまたはファクトリ メソッドで許可されている属性と初期化文字列を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="37462-126">The object elements within `x:Arguments` can include attributes and initialization strings, as permitted by that XAML type and its backing constructor or factory method.</span></span> <span data-ttu-id="37462-127">オブジェクトまたは引数の場合、確立されたプレフィックス マッピングを参照することで、既定の XAML 名前空間の外部にあるカスタム XAML 型または XAML 型を指定できます。</span><span class="sxs-lookup"><span data-stu-id="37462-127">For either the object or the arguments, you can specify custom XAML types or XAML types that are otherwise outside the default XAML namespace by referencing established prefix mappings.</span></span>

<span data-ttu-id="37462-128">XAML プロセッサは、次のガイドラインを使用して、 で`x:Arguments`指定した引数を使用してオブジェクトを構築する方法を決定します。</span><span class="sxs-lookup"><span data-stu-id="37462-128">XAML processors use the following guidelines to determine how the arguments specified in `x:Arguments` should be used to construct an object.</span></span> <span data-ttu-id="37462-129">指定`x:FactoryMethod`した場合、情報は指定された`x:FactoryMethod`情報と比較されます (の値`x:FactoryMethod`はメソッド名であり、名前付きメソッドはオーバーロードを持つことができます)。</span><span class="sxs-lookup"><span data-stu-id="37462-129">If `x:FactoryMethod` is specified, information is compared to the specified `x:FactoryMethod` (note that the value of `x:FactoryMethod` is the method name, and the named method can have overloads.</span></span> <span data-ttu-id="37462-130">指定`x:FactoryMethod`しない場合、情報はオブジェクトのすべてのパブリック コンストラクター オーバーロードのセットと比較されます。</span><span class="sxs-lookup"><span data-stu-id="37462-130">If `x:FactoryMethod` is not specified, information is compared to the set of all public constructor overloads of the object.</span></span> <span data-ttu-id="37462-131">次に、XAML 処理ロジックはパラメーターの数を比較し、一致するアリティを持つオーバーロードを選択します。</span><span class="sxs-lookup"><span data-stu-id="37462-131">XAML processing logic then compares the number of parameters and selects the overload with matching arity.</span></span> <span data-ttu-id="37462-132">複数の一致がある場合、XAML プロセッサは、指定されたオブジェクト要素の XAML 型に基づいてパラメーターの型を比較する必要があります。</span><span class="sxs-lookup"><span data-stu-id="37462-132">If there is more than one match, the XAML processor should compare the types of the parameters based on the XAML types of the provided object elements.</span></span> <span data-ttu-id="37462-133">一致が複数ある場合、XAML プロセッサの動作は未定義です。</span><span class="sxs-lookup"><span data-stu-id="37462-133">If there is still more than one match, the XAML processor behavior is undefined.</span></span> <span data-ttu-id="37462-134">が`x:FactoryMethod`指定されているが、メソッドを解決できない場合、XAML プロセッサは例外をスローする必要があります。</span><span class="sxs-lookup"><span data-stu-id="37462-134">If a `x:FactoryMethod` is specified but the method cannot be resolved, a XAML processor should throw an exception.</span></span>

<span data-ttu-id="37462-135">XAML 属性の`<x:Arguments>string</x:Arguments>`使用は技術的に可能です。</span><span class="sxs-lookup"><span data-stu-id="37462-135">A XAML attribute usage `<x:Arguments>string</x:Arguments>` is technically possible.</span></span> <span data-ttu-id="37462-136">ただし、初期化テキストと型コンバーターを使用して実行できる機能以外の機能は提供されません。</span><span class="sxs-lookup"><span data-stu-id="37462-136">However, this provides no capabilities beyond what could be done otherwise through initialization text and type converters, and using this syntax is not the design intention of the XAML 2009 factory method features.</span></span>

## <a name="examples"></a><span data-ttu-id="37462-137">例</span><span class="sxs-lookup"><span data-stu-id="37462-137">Examples</span></span>

<span data-ttu-id="37462-138">次の例では、パラメーターなしのコンストラクター シグネチャを示し、そのシグネチャ`x:Arguments`にアクセスする XAML の使用方法を示します。</span><span class="sxs-lookup"><span data-stu-id="37462-138">The following example shows a non-parameterless constructor signature, then the XAML usage of `x:Arguments` that accesses that signature.</span></span>

```csharp
public class Food {
  private string _name;
  private Int32 _calories;
  public Food(string name, Int32 calories) {
      _name=name;
      _calories=calories;
  }
}
```

```xaml
<my:Food>
  <x:Arguments>
      <x:String>Apple</x:String>
      <x:Int32>150</x:Int32>
  </x:Arguments>
</my:Food>
```

<span data-ttu-id="37462-139">次の例は、ターゲット ファクトリ メソッドシグネチャを示し、`x:Arguments`そのシグネチャにアクセスする XAML の使用方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="37462-139">The following example shows a target factory method signature, then the XAML usage of `x:Arguments` that accesses that signature.</span></span>

```csharp
public Food TryLookupFood(string name)
{
switch (name) {
  case "Apple": return new Food("Apple",150);
  case "Chocolate": return new Food("Chocolate",200);
  case "Cheese": return new Food("Cheese", 450);
  default: {return new Food(name,0);
}
}
```

```xaml
<my:Food x:FactoryMethod="TryLookupFood">
  <x:Arguments>
      <x:String>Apple</x:String>
  </x:Arguments>
</my:Food>
```

## <a name="see-also"></a><span data-ttu-id="37462-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="37462-140">See also</span></span>

- [<span data-ttu-id="37462-141">.NET XAML サービスで使用するカスタム型の定義</span><span class="sxs-lookup"><span data-stu-id="37462-141">Defining Custom Types for Use with .NET XAML Services</span></span>](define-custom-types.md)
- [<span data-ttu-id="37462-142">XAML の概要 (WPF)</span><span class="sxs-lookup"><span data-stu-id="37462-142">XAML Overview (WPF)</span></span>](../fundamentals/xaml.md)
