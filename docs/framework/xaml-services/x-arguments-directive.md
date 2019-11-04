---
title: x:Arguments ディレクティブ
ms.date: 03/30/2017
helpviewer_keywords:
- x:Arguments directive [XAML Services]
- Arguments directive in XAML [XAML Services]
- XAML [XAML Services], x:Arguments directive
ms.assetid: 87cc10b0-b610-4025-b6b0-ab27ca27c92e
ms.openlocfilehash: 338286b417c78b7cceeb30188e888928a15607cd
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458655"
---
# <a name="xarguments-directive"></a><span data-ttu-id="7691f-102">x:Arguments ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="7691f-102">x:Arguments Directive</span></span>
<span data-ttu-id="7691f-103">XAML でのパラメーターなしのコンストラクターオブジェクト要素の宣言またはファクトリメソッドオブジェクトの宣言に対する構築引数をパッケージ化します。</span><span class="sxs-lookup"><span data-stu-id="7691f-103">Packages construction arguments for a non-parameterless constructor object element declaration in XAML, or for a factory method object declaration.</span></span>  
  
## <a name="xaml-element-usage-nonparameterless-constructor"></a><span data-ttu-id="7691f-104">XAML 要素の使用法 (パラメーターなしのコンストラクター)</span><span class="sxs-lookup"><span data-stu-id="7691f-104">XAML Element Usage (Nonparameterless constructor)</span></span>  
  
```xaml  
<object ...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-element-usage-factory-method"></a><span data-ttu-id="7691f-105">XAML 要素の使用法 (ファクトリメソッド)</span><span class="sxs-lookup"><span data-stu-id="7691f-105">XAML Element Usage (factory method)</span></span>  
  
```xaml  
<object x:FactoryMethod="methodName"...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="7691f-106">XAML 値</span><span class="sxs-lookup"><span data-stu-id="7691f-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`oneOrMoreObjectElements`|<span data-ttu-id="7691f-107">バッキングでないパラメーターなしのコンストラクターまたはファクトリメソッドに渡される引数を指定する1つ以上のオブジェクト要素。</span><span class="sxs-lookup"><span data-stu-id="7691f-107">One or more object elements that specify arguments to be passed to the backing non-parameterless constructor or factory method.</span></span><br /><br /> <span data-ttu-id="7691f-108">一般的な使用方法は、オブジェクト要素内で初期化テキストを使用して、実際の引数値を指定することです。</span><span class="sxs-lookup"><span data-stu-id="7691f-108">Typical usage is to use initialization text within the object elements to specify the actual argument values.</span></span> <span data-ttu-id="7691f-109">「例」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7691f-109">See Examples section.</span></span><br /><br /> <span data-ttu-id="7691f-110">要素の順序は重要です。</span><span class="sxs-lookup"><span data-stu-id="7691f-110">The order of the elements is significant.</span></span> <span data-ttu-id="7691f-111">順序の XAML 型は、バッキングコンストラクターまたはファクトリメソッドのオーバーロードの型および型の順序と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7691f-111">The XAML types in order must match the types and type order of the backing constructor or factory method overload.</span></span>|  
|`methodName`|<span data-ttu-id="7691f-112">`x:Arguments` の引数を処理するファクトリメソッドの名前。</span><span class="sxs-lookup"><span data-stu-id="7691f-112">The name of the factory method that should process any `x:Arguments` arguments.</span></span>|  
  
## <a name="dependencies"></a><span data-ttu-id="7691f-113">依存関係</span><span class="sxs-lookup"><span data-stu-id="7691f-113">Dependencies</span></span>  
 <span data-ttu-id="7691f-114">`x:Arguments` 適用されるスコープと動作を変更 `x:FactoryMethod` ことができます。</span><span class="sxs-lookup"><span data-stu-id="7691f-114">`x:FactoryMethod` can modify the scope and behavior where `x:Arguments` applies.</span></span>  
  
 <span data-ttu-id="7691f-115">`x:FactoryMethod` が指定されていない場合、`x:Arguments` バッキングコンストラクターの別の (既定ではない) シグネチャに適用されます。</span><span class="sxs-lookup"><span data-stu-id="7691f-115">If no `x:FactoryMethod` is specified, `x:Arguments` applies to alternate (non-default) signatures of the backing constructors.</span></span>  
  
 <span data-ttu-id="7691f-116">`x:FactoryMethod` が指定されている場合、`x:Arguments` は名前付きメソッドのオーバーロードに適用されます。</span><span class="sxs-lookup"><span data-stu-id="7691f-116">If `x:FactoryMethod` is specified, `x:Arguments` applies to an overload of the named method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7691f-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="7691f-117">Remarks</span></span>  
 <span data-ttu-id="7691f-118">XAML 2006 では、初期化テキストによる既定以外の初期化をサポートできます。</span><span class="sxs-lookup"><span data-stu-id="7691f-118">XAML 2006 can support non-default initialization through initialization text.</span></span> <span data-ttu-id="7691f-119">ただし、初期化テキストの構築手法の実際の応用は限られています。</span><span class="sxs-lookup"><span data-stu-id="7691f-119">However, the practical application of an initialization text construction technique is limited.</span></span> <span data-ttu-id="7691f-120">初期化テキストは1つのテキスト文字列として扱われます。したがって、カスタム情報項目やカスタムの区切り記号を文字列から解析できる構築動作に対して型コンバーターが定義されていない限り、1つのパラメーター初期化の機能が追加されるだけです。</span><span class="sxs-lookup"><span data-stu-id="7691f-120">Initialization text is treated as a single text string; therefore, it only adds capability for a single parameter initialization unless a type converter is defined for the construction behavior that can parse custom information items and custom delimiters from the string.</span></span> <span data-ttu-id="7691f-121">また、オブジェクトロジックへのテキスト文字列は、実際の文字列以外のプリミティブを処理するために、特定の XAML パーサーのネイティブの既定の型コンバーターである可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7691f-121">Also, the text string to object logic is potentially a given XAML parser's native default type converter for handling primitives other than a true string.</span></span>  
  
 <span data-ttu-id="7691f-122">XAML の使用法は、一般的な意味ではプロパティ要素の使用法ではありません。ディレクティブマークアップは、格納するオブジェクトの型を参照しないためです。 `x:Arguments`</span><span class="sxs-lookup"><span data-stu-id="7691f-122">The `x:Arguments` XAML usage is not property element usage in the typical sense, because the directive markup does not reference the containing object element's type.</span></span> <span data-ttu-id="7691f-123">これは `x:Code` のような他のディレクティブに似ています。要素は、マークアップを子コンテンツの既定値以外として解釈する必要がある範囲を指定します。</span><span class="sxs-lookup"><span data-stu-id="7691f-123">It is more akin to other directives such as `x:Code` where the element demarks a range in which the markup should be interpreted as other than the default for child contents.</span></span> <span data-ttu-id="7691f-124">この場合、各オブジェクト要素の XAML 型は、引数の型に関する情報を伝えます。これは、XAML パーサーによって使用され、`x:Arguments` 使用法が参照しようとしている特定のコンストラクターファクトリメソッドシグネチャを判別します。</span><span class="sxs-lookup"><span data-stu-id="7691f-124">In this case, the XAML type of each object element communicates information about the argument types, which is used by XAML parsers to determine which specific constructor factory method signature an `x:Arguments` usage is attempting to reference.</span></span>  
  
 <span data-ttu-id="7691f-125">構築されるオブジェクト要素の `x:Arguments` は、オブジェクト要素の他のプロパティ要素、コンテンツ、内部テキスト、または初期化文字列の前に記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7691f-125">`x:Arguments` for an object element being constructed must precede any other property elements, content, inner text, or initialization strings of the object element.</span></span> <span data-ttu-id="7691f-126">`x:Arguments` 内のオブジェクト要素には、その XAML 型およびそのバッキングコンストラクターまたはファクトリメソッドで許可されている属性と初期化文字列を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="7691f-126">The object elements within `x:Arguments` can include attributes and initialization strings, as permitted by that XAML type and its backing constructor or factory method.</span></span> <span data-ttu-id="7691f-127">オブジェクトまたは引数のいずれかに対して、確立されたプレフィックスマッピングを参照することによって、既定の XAML 名前空間の外部にあるカスタム XAML 型または XAML 型を指定できます。</span><span class="sxs-lookup"><span data-stu-id="7691f-127">For either the object or the arguments, you can specify custom XAML types or XAML types that are otherwise outside the default XAML namespace by referencing established prefix mappings.</span></span>  
  
 <span data-ttu-id="7691f-128">XAML プロセッサは、次のガイドラインを使用して、`x:Arguments` で指定された引数を使用してオブジェクトを構築する方法を決定します。</span><span class="sxs-lookup"><span data-stu-id="7691f-128">XAML processors use the following guidelines to determine how the arguments specified in `x:Arguments` should be used to construct an object.</span></span> <span data-ttu-id="7691f-129">`x:FactoryMethod` が指定されている場合、情報は指定した `x:FactoryMethod` と比較されます (`x:FactoryMethod` の値がメソッド名であり、名前付きメソッドにオーバーロードがあることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="7691f-129">If `x:FactoryMethod` is specified, information is compared to the specified `x:FactoryMethod` (note that the value of `x:FactoryMethod` is the method name, and the named method can have overloads.</span></span> <span data-ttu-id="7691f-130">`x:FactoryMethod` が指定されていない場合、情報はオブジェクトのすべてのパブリックコンストラクターのオーバーロードのセットと比較されます。</span><span class="sxs-lookup"><span data-stu-id="7691f-130">If `x:FactoryMethod` is not specified, information is compared to the set of all public constructor overloads of the object.</span></span> <span data-ttu-id="7691f-131">次に、XAML 処理ロジックは、パラメーターの数を比較し、一致するアリティを持つオーバーロードを選択します。</span><span class="sxs-lookup"><span data-stu-id="7691f-131">XAML processing logic then compares the number of parameters and selects the overload with matching arity.</span></span> <span data-ttu-id="7691f-132">複数の一致がある場合、XAML プロセッサは、指定されたオブジェクト要素の XAML 型に基づいて、パラメーターの型を比較する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7691f-132">If there is more than one match, the XAML processor should compare the types of the parameters based on the XAML types of the provided object elements.</span></span> <span data-ttu-id="7691f-133">一致するものが1つ以上ある場合、XAML プロセッサの動作は未定義です。</span><span class="sxs-lookup"><span data-stu-id="7691f-133">If there is still more than one match, the XAML processor behavior is undefined.</span></span> <span data-ttu-id="7691f-134">`x:FactoryMethod` が指定されていても、メソッドを解決できない場合、XAML プロセッサは例外をスローする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7691f-134">If a `x:FactoryMethod` is specified but the method cannot be resolved, a XAML processor should throw an exception.</span></span>  
  
 <span data-ttu-id="7691f-135">XAML 属性の使用 `<x:Arguments>string</x:Arguments>` は、技術的には可能です。</span><span class="sxs-lookup"><span data-stu-id="7691f-135">A XAML attribute usage `<x:Arguments>string</x:Arguments>` is technically possible.</span></span> <span data-ttu-id="7691f-136">ただし、これは初期化テキストと型コンバーターを使用して実行できない機能を提供するものではなく、この構文を使用することは、XAML 2009 ファクトリメソッド機能の設計目的ではありません。</span><span class="sxs-lookup"><span data-stu-id="7691f-136">However, this provides no capabilities beyond what could be done otherwise through initialization text and type converters, and using this syntax is not the design intention of the XAML 2009 factory method features.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="7691f-137">使用例</span><span class="sxs-lookup"><span data-stu-id="7691f-137">Examples</span></span>  
 <span data-ttu-id="7691f-138">次の例では、パラメーターなしのコンストラクターシグネチャを示し、そのシグネチャにアクセスする `x:Arguments` の XAML 使用方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7691f-138">The following example shows a non-parameterless constructor signature, then the XAML usage of `x:Arguments` that accesses that signature.</span></span>  
  
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
  
 <span data-ttu-id="7691f-139">次の例では、ターゲットファクトリメソッドシグネチャを示し、その署名にアクセスする `x:Arguments` の XAML 使用方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7691f-139">The following example shows a target factory method signature, then the XAML usage of `x:Arguments` that accesses that signature.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7691f-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="7691f-140">See also</span></span>

- [<span data-ttu-id="7691f-141">.NET Framework XAML サービスで使用するためのカスタム型の定義</span><span class="sxs-lookup"><span data-stu-id="7691f-141">Defining Custom Types for Use with .NET Framework XAML Services</span></span>](defining-custom-types-for-use-with-net-framework-xaml-services.md)
- [<span data-ttu-id="7691f-142">XAML の概要 (WPF)</span><span class="sxs-lookup"><span data-stu-id="7691f-142">XAML Overview (WPF)</span></span>](../../desktop-wpf/fundamentals/xaml.md)
