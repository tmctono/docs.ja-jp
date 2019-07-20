---
title: x:Arguments ディレクティブ
ms.date: 03/30/2017
helpviewer_keywords:
- x:Arguments directive [XAML Services]
- Arguments directive in XAML [XAML Services]
- XAML [XAML Services], x:Arguments directive
ms.assetid: 87cc10b0-b610-4025-b6b0-ab27ca27c92e
ms.openlocfilehash: 5bcd629e306169c1f7a61a316d76203827a2d0fe
ms.sourcegitcommit: 30a83efb57c468da74e9e218de26cf88d3254597
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2019
ms.locfileid: "68364271"
---
# <a name="xarguments-directive"></a><span data-ttu-id="7179a-102">x:Arguments ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="7179a-102">x:Arguments Directive</span></span>
<span data-ttu-id="7179a-103">XAML でのパラメーターなしのコンストラクターオブジェクト要素の宣言またはファクトリメソッドオブジェクトの宣言に対する構築引数をパッケージ化します。</span><span class="sxs-lookup"><span data-stu-id="7179a-103">Packages construction arguments for a non-parameterless constructor object element declaration in XAML, or for a factory method object declaration.</span></span>  
  
## <a name="xaml-element-usage-nonparameterless-constructor"></a><span data-ttu-id="7179a-104">XAML 要素の使用法 (パラメーターなしのコンストラクター)</span><span class="sxs-lookup"><span data-stu-id="7179a-104">XAML Element Usage (Nonparameterless constructor)</span></span>  
  
```  
<object ...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-element-usage-factory-method"></a><span data-ttu-id="7179a-105">XAML 要素の使用法 (ファクトリメソッド)</span><span class="sxs-lookup"><span data-stu-id="7179a-105">XAML Element Usage (factory method)</span></span>  
  
```  
<object x:FactoryMethod="methodName"...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="7179a-106">XAML 値</span><span class="sxs-lookup"><span data-stu-id="7179a-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`oneOrMoreObjectElements`|<span data-ttu-id="7179a-107">バッキングでないパラメーターなしのコンストラクターまたはファクトリメソッドに渡される引数を指定する1つ以上のオブジェクト要素。</span><span class="sxs-lookup"><span data-stu-id="7179a-107">One or more object elements that specify arguments to be passed to the backing non-parameterless constructor or factory method.</span></span><br /><br /> <span data-ttu-id="7179a-108">一般的な使用方法は、オブジェクト要素内で初期化テキストを使用して、実際の引数値を指定することです。</span><span class="sxs-lookup"><span data-stu-id="7179a-108">Typical usage is to use initialization text within the object elements to specify the actual argument values.</span></span> <span data-ttu-id="7179a-109">「例」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7179a-109">See Examples section.</span></span><br /><br /> <span data-ttu-id="7179a-110">要素の順序は重要です。</span><span class="sxs-lookup"><span data-stu-id="7179a-110">The order of the elements is significant.</span></span> <span data-ttu-id="7179a-111">順序の XAML 型は、バッキングコンストラクターまたはファクトリメソッドのオーバーロードの型および型の順序と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7179a-111">The XAML types in order must match the types and type order of the backing constructor or factory method overload.</span></span>|  
|`methodName`|<span data-ttu-id="7179a-112">任意`x:Arguments`の引数を処理するファクトリメソッドの名前。</span><span class="sxs-lookup"><span data-stu-id="7179a-112">The name of the factory method that should process any `x:Arguments` arguments.</span></span>|  
  
## <a name="dependencies"></a><span data-ttu-id="7179a-113">依存関係</span><span class="sxs-lookup"><span data-stu-id="7179a-113">Dependencies</span></span>  
 <span data-ttu-id="7179a-114">`x:FactoryMethod`適用される`x:Arguments`スコープと動作を変更できます。</span><span class="sxs-lookup"><span data-stu-id="7179a-114">`x:FactoryMethod` can modify the scope and behavior where `x:Arguments` applies.</span></span>  
  
 <span data-ttu-id="7179a-115">が指定`x:FactoryMethod`されて`x:Arguments`いない場合、はバッキングコンストラクターの別の (既定ではない) シグネチャに適用されます。</span><span class="sxs-lookup"><span data-stu-id="7179a-115">If no `x:FactoryMethod` is specified, `x:Arguments` applies to alternate (non-default) signatures of the backing constructors.</span></span>  
  
 <span data-ttu-id="7179a-116">を`x:FactoryMethod`指定した`x:Arguments`場合、は名前付きメソッドのオーバーロードに適用されます。</span><span class="sxs-lookup"><span data-stu-id="7179a-116">If `x:FactoryMethod` is specified, `x:Arguments` applies to an overload of the named method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7179a-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="7179a-117">Remarks</span></span>  
 <span data-ttu-id="7179a-118">XAML 2006 では、初期化テキストによる既定以外の初期化をサポートできます。</span><span class="sxs-lookup"><span data-stu-id="7179a-118">XAML 2006 can support non-default initialization through initialization text.</span></span> <span data-ttu-id="7179a-119">ただし、初期化テキストの構築手法の実際の応用は限られています。</span><span class="sxs-lookup"><span data-stu-id="7179a-119">However, the practical application of an initialization text construction technique is limited.</span></span> <span data-ttu-id="7179a-120">初期化テキストは1つのテキスト文字列として扱われます。したがって、カスタム情報項目やカスタムの区切り記号を文字列から解析できる構築動作に対して型コンバーターが定義されていない限り、1つのパラメーター初期化の機能が追加されるだけです。</span><span class="sxs-lookup"><span data-stu-id="7179a-120">Initialization text is treated as a single text string; therefore, it only adds capability for a single parameter initialization unless a type converter is defined for the construction behavior that can parse custom information items and custom delimiters from the string.</span></span> <span data-ttu-id="7179a-121">また、オブジェクトロジックへのテキスト文字列は、実際の文字列以外のプリミティブを処理するために、特定の XAML パーサーのネイティブの既定の型コンバーターである可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7179a-121">Also, the text string to object logic is potentially a given XAML parser's native default type converter for handling primitives other than a true string.</span></span>  
  
 <span data-ttu-id="7179a-122">XAML `x:Arguments`の使用法は、一般的な意味ではプロパティ要素の使用法ではありません。これは、ディレクティブマークアップが、包含するオブジェクト要素の型を参照しないためです。</span><span class="sxs-lookup"><span data-stu-id="7179a-122">The `x:Arguments` XAML usage is not property element usage in the typical sense, because the directive markup does not reference the containing object element's type.</span></span> <span data-ttu-id="7179a-123">これは、要素が子コンテンツの既定`x:Code`値以外としてマークアップを解釈する必要がある範囲を要素がどのようにマークするかなど、他のディレクティブに似ています。</span><span class="sxs-lookup"><span data-stu-id="7179a-123">It is more akin to other directives such as `x:Code` where the element demarks a range in which the markup should be interpreted as other than the default for child contents.</span></span> <span data-ttu-id="7179a-124">この場合、各オブジェクト要素の xaml 型は、引数の型に関する情報を伝達します。これは、xaml パーサーによって使用され`x:Arguments` 、使用されている特定のコンストラクターファクトリメソッドシグネチャのうち、どのコンストラクターが参照しようとしているかを判断するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="7179a-124">In this case, the XAML type of each object element communicates information about the argument types, which is used by XAML parsers to determine which specific constructor factory method signature an `x:Arguments` usage is attempting to reference.</span></span>  
  
 <span data-ttu-id="7179a-125">`x:Arguments`構築するオブジェクト要素は、他のプロパティ要素、コンテンツ、内部テキスト、またはオブジェクト要素の初期化文字列の前に記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7179a-125">`x:Arguments` for an object element being constructed must precede any other property elements, content, inner text, or initialization strings of the object element.</span></span> <span data-ttu-id="7179a-126">内`x:Arguments`のオブジェクト要素には、その XAML 型およびそのバッキングコンストラクターまたはファクトリメソッドで許可されている属性と初期化文字列を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="7179a-126">The object elements within `x:Arguments` can include attributes and initialization strings, as permitted by that XAML type and its backing constructor or factory method.</span></span> <span data-ttu-id="7179a-127">オブジェクトまたは引数のいずれかに対して、確立されたプレフィックスマッピングを参照することによって、既定の XAML 名前空間の外部にあるカスタム XAML 型または XAML 型を指定できます。</span><span class="sxs-lookup"><span data-stu-id="7179a-127">For either the object or the arguments, you can specify custom XAML types or XAML types that are otherwise outside the default XAML namespace by referencing established prefix mappings.</span></span>  
  
 <span data-ttu-id="7179a-128">XAML プロセッサは、次のガイドラインを使用して、で`x:Arguments`指定された引数を使用してオブジェクトを構築する方法を決定します。</span><span class="sxs-lookup"><span data-stu-id="7179a-128">XAML processors use the following guidelines to determine how the arguments specified in `x:Arguments` should be used to construct an object.</span></span> <span data-ttu-id="7179a-129">を`x:FactoryMethod`指定した場合、情報は指定し`x:FactoryMethod`たと比較されます`x:FactoryMethod` (の値がメソッド名であり、名前付きメソッドにオーバーロードがあることに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="7179a-129">If `x:FactoryMethod` is specified, information is compared to the specified `x:FactoryMethod` (note that the value of `x:FactoryMethod` is the method name, and the named method can have overloads.</span></span> <span data-ttu-id="7179a-130">が`x:FactoryMethod`指定されていない場合、情報は、オブジェクトのすべてのパブリックコンストラクターのオーバーロードのセットと比較されます。</span><span class="sxs-lookup"><span data-stu-id="7179a-130">If `x:FactoryMethod` is not specified, information is compared to the set of all public constructor overloads of the object.</span></span> <span data-ttu-id="7179a-131">次に、XAML 処理ロジックは、パラメーターの数を比較し、一致するアリティを持つオーバーロードを選択します。</span><span class="sxs-lookup"><span data-stu-id="7179a-131">XAML processing logic then compares the number of parameters and selects the overload with matching arity.</span></span> <span data-ttu-id="7179a-132">複数の一致がある場合、XAML プロセッサは、指定されたオブジェクト要素の XAML 型に基づいて、パラメーターの型を比較する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7179a-132">If there is more than one match, the XAML processor should compare the types of the parameters based on the XAML types of the provided object elements.</span></span> <span data-ttu-id="7179a-133">一致するものが1つ以上ある場合、XAML プロセッサの動作は未定義です。</span><span class="sxs-lookup"><span data-stu-id="7179a-133">If there is still more than one match, the XAML processor behavior is undefined.</span></span> <span data-ttu-id="7179a-134">`x:FactoryMethod`が指定されていてもメソッドを解決できない場合、XAML プロセッサは例外をスローする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7179a-134">If a `x:FactoryMethod` is specified but the method cannot be resolved, a XAML processor should throw an exception.</span></span>  
  
 <span data-ttu-id="7179a-135">XAML 属性の使用`<x:Arguments>string</x:Arguments>`は技術的に可能です。</span><span class="sxs-lookup"><span data-stu-id="7179a-135">A XAML attribute usage `<x:Arguments>string</x:Arguments>` is technically possible.</span></span> <span data-ttu-id="7179a-136">ただし、これは初期化テキストと型コンバーターを使用して実行できない機能を提供するものではなく、この構文を使用することは、XAML 2009 ファクトリメソッド機能の設計目的ではありません。</span><span class="sxs-lookup"><span data-stu-id="7179a-136">However, this provides no capabilities beyond what could be done otherwise through initialization text and type converters, and using this syntax is not the design intention of the XAML 2009 factory method features.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="7179a-137">使用例</span><span class="sxs-lookup"><span data-stu-id="7179a-137">Examples</span></span>  
 <span data-ttu-id="7179a-138">次の例は、パラメーターなしのコンストラクターシグネチャを示し、そのシグネチャに`x:Arguments`アクセスするの XAML 使用方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="7179a-138">The following example shows a non-parameterless constructor signature, then the XAML usage of `x:Arguments` that accesses that signature.</span></span>  
  
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
  
 <span data-ttu-id="7179a-139">次の例では、ターゲットファクトリメソッドシグネチャを示し、その署名`x:Arguments`にアクセスするの XAML 使用方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7179a-139">The following example shows a target factory method signature, then the XAML usage of `x:Arguments` that accesses that signature.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7179a-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="7179a-140">See also</span></span>

- [<span data-ttu-id="7179a-141">.NET Framework XAML サービスで使用するためのカスタム型の定義</span><span class="sxs-lookup"><span data-stu-id="7179a-141">Defining Custom Types for Use with .NET Framework XAML Services</span></span>](defining-custom-types-for-use-with-net-framework-xaml-services.md)
- [<span data-ttu-id="7179a-142">XAML の概要 (WPF)</span><span class="sxs-lookup"><span data-stu-id="7179a-142">XAML Overview (WPF)</span></span>](../wpf/advanced/xaml-overview-wpf.md)
