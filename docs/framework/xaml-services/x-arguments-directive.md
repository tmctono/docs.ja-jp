---
title: x:Arguments ディレクティブ
ms.date: 03/30/2017
helpviewer_keywords:
- x:Arguments directive [XAML Services]
- Arguments directive in XAML [XAML Services]
- XAML [XAML Services], x:Arguments directive
ms.assetid: 87cc10b0-b610-4025-b6b0-ab27ca27c92e
ms.openlocfilehash: a87542513ffeeec7efc526d4218f921d1b7579a1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59184848"
---
# <a name="xarguments-directive"></a><span data-ttu-id="2101e-102">x:Arguments ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="2101e-102">x:Arguments Directive</span></span>
<span data-ttu-id="2101e-103">パッケージの構築の引数、XAML で既定以外のコンス トラクター オブジェクト要素の宣言またはファクトリ メソッドのオブジェクトの宣言。</span><span class="sxs-lookup"><span data-stu-id="2101e-103">Packages construction arguments for a non-default constructor object element declaration in XAML, or for a factory method object declaration.</span></span>  
  
## <a name="xaml-element-usage-nondefault-constructor"></a><span data-ttu-id="2101e-104">XAML 要素の使用 (既定以外のコンス トラクター)</span><span class="sxs-lookup"><span data-stu-id="2101e-104">XAML Element Usage (Nondefault constructor)</span></span>  
  
```  
<object ...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-element-usage-factory-method"></a><span data-ttu-id="2101e-105">XAML 要素の使用方法 (ファクトリ メソッド)</span><span class="sxs-lookup"><span data-stu-id="2101e-105">XAML Element Usage (factory method)</span></span>  
  
```  
<object x:FactoryMethod="methodName"...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="2101e-106">XAML 値</span><span class="sxs-lookup"><span data-stu-id="2101e-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`oneOrMoreObjectElements`|<span data-ttu-id="2101e-107">既定以外のバッキング コンス トラクターまたはファクトリ メソッドに渡される引数を指定する 1 つまたは複数のオブジェクト要素。</span><span class="sxs-lookup"><span data-stu-id="2101e-107">One or more object elements that specify arguments to be passed to the backing non-default constructor or factory method.</span></span><br /><br /> <span data-ttu-id="2101e-108">一般的な使用法では、実際の引数の値を指定するオブジェクトの要素内の初期化のテキストを使用します。</span><span class="sxs-lookup"><span data-stu-id="2101e-108">Typical usage is to use initialization text within the object elements to specify the actual argument values.</span></span> <span data-ttu-id="2101e-109">例のセクションをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2101e-109">See Examples section.</span></span><br /><br /> <span data-ttu-id="2101e-110">要素の順序は重要です。</span><span class="sxs-lookup"><span data-stu-id="2101e-110">The order of the elements is significant.</span></span> <span data-ttu-id="2101e-111">順序内の XAML 型は、型と一致する必要があり、バッキング コンス トラクターまたはファクトリ メソッドのオーバー ロードの順序を入力します。</span><span class="sxs-lookup"><span data-stu-id="2101e-111">The XAML types in order must match the types and type order of the backing constructor or factory method overload.</span></span>|  
|`methodName`|<span data-ttu-id="2101e-112">いずれかを処理するファクトリ メソッドの名前`x:Arguments`引数。</span><span class="sxs-lookup"><span data-stu-id="2101e-112">The name of the factory method that should process any `x:Arguments` arguments.</span></span>|  
  
## <a name="dependencies"></a><span data-ttu-id="2101e-113">依存関係</span><span class="sxs-lookup"><span data-stu-id="2101e-113">Dependencies</span></span>  
 <span data-ttu-id="2101e-114">`x:FactoryMethod` スコープと動作を変更することができます、`x:Arguments`適用されます。</span><span class="sxs-lookup"><span data-stu-id="2101e-114">`x:FactoryMethod` can modify the scope and behavior where `x:Arguments` applies.</span></span>  
  
 <span data-ttu-id="2101e-115">ない場合は`x:FactoryMethod`が指定されている`x:Arguments`バッキング コンス トラクターの代替 (既定値) の署名に適用されます。</span><span class="sxs-lookup"><span data-stu-id="2101e-115">If no `x:FactoryMethod` is specified, `x:Arguments` applies to alternate (non-default) signatures of the backing constructors.</span></span>  
  
 <span data-ttu-id="2101e-116">場合`x:FactoryMethod`が指定されている`x:Arguments`名前付きメソッドのオーバー ロードに適用されます。</span><span class="sxs-lookup"><span data-stu-id="2101e-116">If `x:FactoryMethod` is specified, `x:Arguments` applies to an overload of the named method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2101e-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="2101e-117">Remarks</span></span>  
 <span data-ttu-id="2101e-118">XAML 2006 では、初期化のテキストを既定以外の初期化をサポートできます。</span><span class="sxs-lookup"><span data-stu-id="2101e-118">XAML 2006 can support non-default initialization through initialization text.</span></span> <span data-ttu-id="2101e-119">ただし、初期化テキストの構築方法の実用的なアプリケーションは制限されます。</span><span class="sxs-lookup"><span data-stu-id="2101e-119">However, the practical application of an initialization text construction technique is limited.</span></span> <span data-ttu-id="2101e-120">初期化のテキストが 1 つのテキスト文字列として扱われますそのため、カスタム情報項目とカスタムの区切り記号文字列からを解析できる構築動作の型コンバーターが定義されていない場合、1 つのパラメーターの初期化の機能のみ追加します。</span><span class="sxs-lookup"><span data-stu-id="2101e-120">Initialization text is treated as a single text string; therefore, it only adds capability for a single parameter initialization unless a type converter is defined for the construction behavior that can parse custom information items and custom delimiters from the string.</span></span> <span data-ttu-id="2101e-121">また、オブジェクトのロジックをテキスト文字列は、true 文字列以外のプリミティブを処理するための指定された XAML パーサーのネイティブの既定の型コンバーターでは可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2101e-121">Also, the text string to object logic is potentially a given XAML parser's native default type converter for handling primitives other than a true string.</span></span>  
  
 <span data-ttu-id="2101e-122">`x:Arguments` XAML の使用は、の一般的な意味で、プロパティ要素の使用方法、ディレクティブのマークアップが格納オブジェクト要素の型を参照していないためです。</span><span class="sxs-lookup"><span data-stu-id="2101e-122">The `x:Arguments` XAML usage is not property element usage in the typical sense, because the directive markup does not reference the containing object element's type.</span></span> <span data-ttu-id="2101e-123">など他のディレクティブと酷似`x:Code`要素境界の既定の子の内容以外に、マークアップを解釈する必要がありますの範囲を定めます。</span><span class="sxs-lookup"><span data-stu-id="2101e-123">It is more akin to other directives such as `x:Code` where the element demarks a range in which the markup should be interpreted as other than the default for child contents.</span></span> <span data-ttu-id="2101e-124">ここでは、オブジェクトの各要素の XAML 型はどの特定のコンス トラクターのファクトリ メソッドのシグネチャを決定する XAML パーサーで使用される引数の型については、通信、`x:Arguments`参照しようとして使用します。</span><span class="sxs-lookup"><span data-stu-id="2101e-124">In this case, the XAML type of each object element communicates information about the argument types, which is used by XAML parsers to determine which specific constructor factory method signature an `x:Arguments` usage is attempting to reference.</span></span>  
  
 <span data-ttu-id="2101e-125">`x:Arguments` オブジェクト要素の構築される必要がありますの前に、その他のプロパティ要素、コンテンツ、内部テキ ストは、またはオブジェクトの要素の初期化の文字列。</span><span class="sxs-lookup"><span data-stu-id="2101e-125">`x:Arguments` for an object element being constructed must precede any other property elements, content, inner text, or initialization strings of the object element.</span></span> <span data-ttu-id="2101e-126">内のオブジェクト要素`x:Arguments`その XAML の型とそのバッキングのコンス トラクターまたはファクトリ メソッドで許可されているように、属性と初期化文字列を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="2101e-126">The object elements within `x:Arguments` can include attributes and initialization strings, as permitted by that XAML type and its backing constructor or factory method.</span></span> <span data-ttu-id="2101e-127">オブジェクトまたは引数のいずれかのカスタムの XAML 型または外部にあるそれ以外の場合、既定の XAML 名前空間によって確立されたプレフィックスのマッピングを参照する XAML 型を指定できます。</span><span class="sxs-lookup"><span data-stu-id="2101e-127">For either the object or the arguments, you can specify custom XAML types or XAML types that are otherwise outside the default XAML namespace by referencing established prefix mappings.</span></span>  
  
 <span data-ttu-id="2101e-128">XAML プロセッサに引数を指定する方法を決定する、次のガイドラインを使用して`x:Arguments`オブジェクトを構築するために使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2101e-128">XAML processors use the following guidelines to determine how the arguments specified in `x:Arguments` should be used to construct an object.</span></span> <span data-ttu-id="2101e-129">場合`x:FactoryMethod`を指定すると、情報と比較を指定した`x:FactoryMethod`(注意の値`x:FactoryMethod`メソッドの名前し、名前付きメソッドのオーバー ロードを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="2101e-129">If `x:FactoryMethod` is specified, information is compared to the specified `x:FactoryMethod` (note that the value of `x:FactoryMethod` is the method name, and the named method can have overloads.</span></span> <span data-ttu-id="2101e-130">場合`x:FactoryMethod`が指定されていない、情報は、オブジェクトのすべてのパブリック コンス トラクター オーバー ロードのセットと比較されます。</span><span class="sxs-lookup"><span data-stu-id="2101e-130">If `x:FactoryMethod` is not specified, information is compared to the set of all public constructor overloads of the object.</span></span> <span data-ttu-id="2101e-131">XAML 処理ロジックは、パラメーターの数を比較しと一致するアリティのオーバー ロードを選択します。</span><span class="sxs-lookup"><span data-stu-id="2101e-131">XAML processing logic then compares the number of parameters and selects the overload with matching arity.</span></span> <span data-ttu-id="2101e-132">1 つ以上の一致がある場合、XAML プロセッサは提供されたオブジェクトの要素の XAML 型に基づいてパラメーターの型と比較します。</span><span class="sxs-lookup"><span data-stu-id="2101e-132">If there is more than one match, the XAML processor should compare the types of the parameters based on the XAML types of the provided object elements.</span></span> <span data-ttu-id="2101e-133">複数の一致がある場合、XAML プロセッサの動作は未定義です。</span><span class="sxs-lookup"><span data-stu-id="2101e-133">If there is still more than one match, the XAML processor behavior is undefined.</span></span> <span data-ttu-id="2101e-134">場合、`x:FactoryMethod`が指定されて、メソッドは、解決することはできませんは、XAML プロセッサは、例外をスローする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2101e-134">If a `x:FactoryMethod` is specified but the method cannot be resolved, a XAML processor should throw an exception.</span></span>  
  
 <span data-ttu-id="2101e-135">XAML 属性の使用法`<x:Arguments>string</x:Arguments>`技術的に可能です。</span><span class="sxs-lookup"><span data-stu-id="2101e-135">A XAML attribute usage `<x:Arguments>string</x:Arguments>` is technically possible.</span></span> <span data-ttu-id="2101e-136">ただし、この初期化のテキストと型コンバーターを使ってそれ以外の場合と行うことが含まれない機能はありません、この構文を使用して、XAML 2009 のファクトリ メソッドの機能の目的で設計ではありません。</span><span class="sxs-lookup"><span data-stu-id="2101e-136">However, this provides no capabilities beyond what could be done otherwise through initialization text and type converters, and using this syntax is not the design intention of the XAML 2009 factory method features.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="2101e-137">使用例</span><span class="sxs-lookup"><span data-stu-id="2101e-137">Examples</span></span>  
 <span data-ttu-id="2101e-138">次の例では、署名、次の XAML の使用状況は、既定以外のコンス トラクターを示しています`x:Arguments`その署名にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="2101e-138">The following example shows a non-default constructor signature, then the XAML usage of `x:Arguments` that accesses that signature.</span></span>  
  
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
  
 <span data-ttu-id="2101e-139">次の例では、ターゲット ファクトリ メソッドのシグネチャを次の XAML の使用状況を示しています。`x:Arguments`その署名にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="2101e-139">The following example shows a target factory method signature, then the XAML usage of `x:Arguments` that accesses that signature.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2101e-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="2101e-140">See also</span></span>

- [<span data-ttu-id="2101e-141">.NET Framework XAML サービスで使用するためのカスタム型の定義</span><span class="sxs-lookup"><span data-stu-id="2101e-141">Defining Custom Types for Use with .NET Framework XAML Services</span></span>](defining-custom-types-for-use-with-net-framework-xaml-services.md)
- [<span data-ttu-id="2101e-142">XAML の概要 (WPF)</span><span class="sxs-lookup"><span data-stu-id="2101e-142">XAML Overview (WPF)</span></span>](../wpf/advanced/xaml-overview-wpf.md)
