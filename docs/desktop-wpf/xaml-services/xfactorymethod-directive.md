---
title: x:FactoryMethod ディレクティブ
ms.date: 03/30/2017
helpviewer_keywords:
- XAML. x:FactoryMethod directive [XAML Services]
- FactoryMethod directive in XAML [XAML Services]
- x:FactoryMethod directive [XAML Services]
ms.assetid: 829bcbdf-5318-4afb-9a03-c310e0d2f23d
ms.openlocfilehash: 5e864b6f5d664b079036a5d915e2f6f81b83639f
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432786"
---
# <a name="xfactorymethod-directive"></a><span data-ttu-id="2a66e-102">x:FactoryMethod ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="2a66e-102">x:FactoryMethod Directive</span></span>
<span data-ttu-id="2a66e-103">XAML プロセッサがバッキング型を解決した後にオブジェクトを初期化するために使用するコンストラクター以外のメソッドを指定します。</span><span class="sxs-lookup"><span data-stu-id="2a66e-103">Specifies a method other than a constructor that a XAML processor should use to initialize an object after resolving its backing type.</span></span>  
  
## <a name="xaml-attribute-usage-no-xarguments"></a><span data-ttu-id="2a66e-104">XAML 属性の使用方法、x なし:引数</span><span class="sxs-lookup"><span data-stu-id="2a66e-104">XAML Attribute Usage, no x:Arguments</span></span>  
  
```xaml  
<object x:FactoryMethod="methodname"...>  
  ...  
</object>  
```  
  
## <a name="xaml-attribute-usage-xarguments-as-elements"></a><span data-ttu-id="2a66e-105">XAML 属性の使用方法、x: 要素としての引数</span><span class="sxs-lookup"><span data-stu-id="2a66e-105">XAML Attribute Usage, x:Arguments as Element(s)</span></span>  
  
```xaml  
<object x:FactoryMethod="methodname"...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="2a66e-106">XAML 値</span><span class="sxs-lookup"><span data-stu-id="2a66e-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`methodname`|<span data-ttu-id="2a66e-107">として`object`指定されたインスタンスを初期化するために XAML プロセッサが呼び出すメソッドの文字列メソッド名。</span><span class="sxs-lookup"><span data-stu-id="2a66e-107">The string method name of a method that XAML processors call to initialize the instance specified as `object`.</span></span> <span data-ttu-id="2a66e-108">「解説」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a66e-108">See Remarks.</span></span>|  
|`oneOrMoreObjectElements`|<span data-ttu-id="2a66e-109">ファクトリ メソッド のパラメーターを指定するオブジェクトの 1 つ以上のオブジェクト要素。</span><span class="sxs-lookup"><span data-stu-id="2a66e-109">One or more object elements for objects that specify factory method parameters.</span></span> <span data-ttu-id="2a66e-110">順序は重要です。これは、引数がファクトリメソッドに渡される順序を示します。</span><span class="sxs-lookup"><span data-stu-id="2a66e-110">Order is significant; it signifies the order in which arguments should be passed to the factory method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2a66e-111">解説</span><span class="sxs-lookup"><span data-stu-id="2a66e-111">Remarks</span></span>  
 <span data-ttu-id="2a66e-112">インスタンス`methodname`メソッドの場合、修飾できません。</span><span class="sxs-lookup"><span data-stu-id="2a66e-112">If `methodname` is an instance method, it cannot be qualified.</span></span>  
  
 <span data-ttu-id="2a66e-113">ファクトリ メソッドとしての静的メソッドがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="2a66e-113">Static methods as factory methods are supported.</span></span> <span data-ttu-id="2a66e-114">静的`methodname`メソッドの場合は、`methodname`静的ファクトリ メソッド`typeName.methodName`を定義する`typeName`クラスを名前を指定する組み合わせとして提供されます。</span><span class="sxs-lookup"><span data-stu-id="2a66e-114">If `methodname` is a static method, `methodname` is provided as a `typeName.methodName` combination, where `typeName` names the class that defines the static factory method.</span></span> <span data-ttu-id="2a66e-115">`typeName`マップされた xmlns 内の型を参照する場合は、プレフィックス修飾できます。</span><span class="sxs-lookup"><span data-stu-id="2a66e-115">`typeName` can be prefix-qualified if referring to a type in a mapped xmlns.</span></span> <span data-ttu-id="2a66e-116">`typeName`とは異なる型を`typeof(object)`指定できます。</span><span class="sxs-lookup"><span data-stu-id="2a66e-116">`typeName` can be a different type than `typeof(object)`.</span></span>  
  
 <span data-ttu-id="2a66e-117">ファクトリ メソッドは、関連するオブジェクト要素をバックする型の宣言済みのパブリック メソッドである必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a66e-117">The factory method must be a declared public method of the type that backs the relevant object element.</span></span>  
  
 <span data-ttu-id="2a66e-118">ファクトリ メソッドは、関連オブジェクトに割り当て可能なインスタンスを返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a66e-118">The factory method must return an instance that is assignable to the relevant object.</span></span> <span data-ttu-id="2a66e-119">ファクトリ メソッドは null を返しません。</span><span class="sxs-lookup"><span data-stu-id="2a66e-119">Factory methods should never return null.</span></span>  
  
 <span data-ttu-id="2a66e-120">`x:Arguments`ファクトリメソッドのシグネチャに最適な一致の原則に基づいて動作します。</span><span class="sxs-lookup"><span data-stu-id="2a66e-120">`x:Arguments` operates on a principle of best match for signatures of factory methods.</span></span> <span data-ttu-id="2a66e-121">一致は、最初にパラメーター数を評価します。</span><span class="sxs-lookup"><span data-stu-id="2a66e-121">Matching evaluates the parameter count first.</span></span> <span data-ttu-id="2a66e-122">パラメーター数に対して複数の一致が可能な場合、パラメーターの型が評価され、最適な一致が判別されます。</span><span class="sxs-lookup"><span data-stu-id="2a66e-122">If there is more than one possible match for a parameter count, parameter type is then evaluated and best match is determined.</span></span> <span data-ttu-id="2a66e-123">この評価フェーズの後にあいまいな状態が続く場合、XAML プロセッサの動作は未定義です。</span><span class="sxs-lookup"><span data-stu-id="2a66e-123">If there is still ambiguity after this phase of evaluation, XAML processor behavior is undefined.</span></span>  
  
 <span data-ttu-id="2a66e-124">ディレクティブ`x:FactoryMethod`マークアップは、含んでいるオブジェクト要素の型を参照しないため、要素の使用法は、一般的な意味でのプロパティ要素の使用ではありません。</span><span class="sxs-lookup"><span data-stu-id="2a66e-124">The `x:FactoryMethod` element usage is not property element usage in the typical sense, because the directive markup does not reference the containing object element's type.</span></span> <span data-ttu-id="2a66e-125">要素の使用は属性の使用よりも一般的ではないと予想されます。</span><span class="sxs-lookup"><span data-stu-id="2a66e-125">It is expected that element usage is less common than attribute usage.</span></span> <span data-ttu-id="2a66e-126">`x:Arguments`(属性または要素の使用法) は、要素`x:FactoryMethod`の使用方法と共に使用できますが、これは Usage セクションに特に示されていません。</span><span class="sxs-lookup"><span data-stu-id="2a66e-126">`x:Arguments` (either attribute or element usage) can be used along with `x:FactoryMethod` element usage, but this is not specifically shown in the Usage sections.</span></span>  
  
 <span data-ttu-id="2a66e-127">`x:FactoryMethod`要素は、他のプロパティ要素の前にする必要があり、要素`x:Arguments`としても指定される前に、コンテンツ/内部テキスト/初期化テキストの前にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a66e-127">`x:FactoryMethod` as an element must precede any other property elements, must precede any `x:Arguments` also provided as elements, and must precede any content/inner text/initialization text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a66e-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="2a66e-128">See also</span></span>

- [<span data-ttu-id="2a66e-129">x:Arguments ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="2a66e-129">x:Arguments Directive</span></span>](xarguments-directive.md)
