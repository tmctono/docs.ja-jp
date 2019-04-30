---
title: x:FactoryMethod ディレクティブ
ms.date: 03/30/2017
helpviewer_keywords:
- XAML. x:FactoryMethod directive [XAML Services]
- FactoryMethod directive in XAML [XAML Services]
- x:FactoryMethod directive [XAML Services]
ms.assetid: 829bcbdf-5318-4afb-9a03-c310e0d2f23d
ms.openlocfilehash: 8fff4d62e07bdfd4ecc27d2692c391251afdd6d5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61971835"
---
# <a name="xfactorymethod-directive"></a><span data-ttu-id="659e6-102">x:FactoryMethod ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="659e6-102">x:FactoryMethod Directive</span></span>
<span data-ttu-id="659e6-103">XAML プロセッサが、バッキング型を解決した後、オブジェクトを初期化するために使用するコンス トラクター以外の方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="659e6-103">Specifies a method other than a constructor that a XAML processor should use to initialize an object after resolving its backing type.</span></span>  
  
## <a name="xaml-attribute-usage-no-xarguments"></a><span data-ttu-id="659e6-104">XAML 属性使用状況、x: 引数なし</span><span class="sxs-lookup"><span data-stu-id="659e6-104">XAML Attribute Usage, no x:Arguments</span></span>  
  
```  
<object x:FactoryMethod="methodname"...>  
  ...  
</object>  
```  
  
## <a name="xaml-attribute-usage-xarguments-as-elements"></a><span data-ttu-id="659e6-105">XAML 属性使用状況、個の要素として X:arguments</span><span class="sxs-lookup"><span data-stu-id="659e6-105">XAML Attribute Usage, x:Arguments as Element(s)</span></span>  
  
```  
<object x:FactoryMethod="methodname"...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="659e6-106">XAML 値</span><span class="sxs-lookup"><span data-stu-id="659e6-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`methodname`|<span data-ttu-id="659e6-107">文字列のメソッド名として指定されたインスタンスを初期化するために XAML プロセッサが呼び出すメソッドの`object`します。</span><span class="sxs-lookup"><span data-stu-id="659e6-107">The string method name of a method that XAML processors call to initialize the instance specified as `object`.</span></span> <span data-ttu-id="659e6-108">「解説」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="659e6-108">See Remarks.</span></span>|  
|`oneOrMoreObjectElements`|<span data-ttu-id="659e6-109">ファクトリ メソッドのパラメーターを指定するオブジェクトのオブジェクトの要素の 1 つ以上</span><span class="sxs-lookup"><span data-stu-id="659e6-109">One or more object elements for objects that specify factory method parameters.</span></span> <span data-ttu-id="659e6-110">順序は重要です。ファクトリ メソッドに引数を渡す必要があります、順序のことを示します。</span><span class="sxs-lookup"><span data-stu-id="659e6-110">Order is significant; it signifies the order in which arguments should be passed to the factory method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="659e6-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="659e6-111">Remarks</span></span>  
 <span data-ttu-id="659e6-112">場合`methodname`インスタンス メソッドを修飾することもできません。</span><span class="sxs-lookup"><span data-stu-id="659e6-112">If `methodname` is an instance method, it cannot be qualified.</span></span>  
  
 <span data-ttu-id="659e6-113">ファクトリ メソッドとしての静的メソッドがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="659e6-113">Static methods as factory methods are supported.</span></span> <span data-ttu-id="659e6-114">場合`methodname`静的メソッドでは、`methodname`として提供されて、 *typeName*.*methodName*の組み合わせを*typeName*静的ファクトリ メソッドを定義するクラスの名前します。</span><span class="sxs-lookup"><span data-stu-id="659e6-114">If `methodname` is a static method, `methodname` is provided as a *typeName*.*methodName* combination, where *typeName* names the class that defines the static factory method.</span></span> <span data-ttu-id="659e6-115">*typeName*マップされた xmlns 内の型を参照している場合のプレフィックスで修飾することができます。</span><span class="sxs-lookup"><span data-stu-id="659e6-115">*typeName* can be prefix-qualified if referring to a type in a mapped xmlns.</span></span> <span data-ttu-id="659e6-116">*typeName*より異なる型を指定できます`typeof(object)`します。</span><span class="sxs-lookup"><span data-stu-id="659e6-116">*typeName* can be a different type than `typeof(object)`.</span></span>  
  
 <span data-ttu-id="659e6-117">ファクトリ メソッドは、関連するオブジェクトの要素をサポートする型の宣言されたパブリック メソッドである必要があります。</span><span class="sxs-lookup"><span data-stu-id="659e6-117">The factory method must be a declared public method of the type that backs the relevant object element.</span></span>  
  
 <span data-ttu-id="659e6-118">ファクトリ メソッドには、関連するオブジェクトに割り当てることができるインスタンスを返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="659e6-118">The factory method must return an instance that is assignable to the relevant object.</span></span> <span data-ttu-id="659e6-119">ファクトリ メソッドには null を返すことはありません。</span><span class="sxs-lookup"><span data-stu-id="659e6-119">Factory methods should never return null.</span></span>  
  
 <span data-ttu-id="659e6-120">`x:Arguments` ファクトリ メソッドのシグネチャに最適なものの原則で動作します。</span><span class="sxs-lookup"><span data-stu-id="659e6-120">`x:Arguments` operates on a principle of best match for signatures of factory methods.</span></span> <span data-ttu-id="659e6-121">一致するパラメーターの数を最初に評価します。</span><span class="sxs-lookup"><span data-stu-id="659e6-121">Matching evaluates the parameter count first.</span></span> <span data-ttu-id="659e6-122">パラメーターの数に一致する 1 つ以上の場合は、パラメーターの型は、評価と最適な一致を確認しが。</span><span class="sxs-lookup"><span data-stu-id="659e6-122">If there is more than one possible match for a parameter count, parameter type is then evaluated and best match is determined.</span></span> <span data-ttu-id="659e6-123">評価のこのフェーズの後にあいまいさが残る、XAML プロセッサの動作は未定義です。</span><span class="sxs-lookup"><span data-stu-id="659e6-123">If there is still ambiguity after this phase of evaluation, XAML processor behavior is undefined.</span></span>  
  
 <span data-ttu-id="659e6-124">`x:FactoryMethod`要素の使用方法で、一般的な意味では、プロパティ要素による使用できないためはディレクティブのマークアップは、親オブジェクト要素の型を参照していません。</span><span class="sxs-lookup"><span data-stu-id="659e6-124">The `x:FactoryMethod` element usage is not property element usage in the typical sense, because the directive markup does not reference the containing object element's type.</span></span> <span data-ttu-id="659e6-125">要素の使用方法は、属性の使用方法よりは一般的です。</span><span class="sxs-lookup"><span data-stu-id="659e6-125">It is expected that element usage is less common than attribute usage.</span></span> <span data-ttu-id="659e6-126">`x:Arguments` 組み合わせて (属性または要素のいずれかの使用法) を使用することができます`x:FactoryMethod`要素の使用方法が、これは具体的には表示されません、使用状況のセクションでします。</span><span class="sxs-lookup"><span data-stu-id="659e6-126">`x:Arguments` (either attribute or element usage) can be used along with `x:FactoryMethod` element usage, but this is not specifically shown in the Usage sections.</span></span>  
  
 <span data-ttu-id="659e6-127">`x:FactoryMethod` 要素には、他のすべてのプロパティ要素が前に指定する必要がありますのいずれかの必要があります前`x:Arguments`も、要素として提供されており、任意の初期化/コンテンツ/内部のテキストのテキストの前にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="659e6-127">`x:FactoryMethod` as an element must precede any other property elements, must precede any `x:Arguments` also provided as elements, and must precede any content/inner text/initialization text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="659e6-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="659e6-128">See also</span></span>

- [<span data-ttu-id="659e6-129">x:Arguments ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="659e6-129">x:Arguments Directive</span></span>](x-arguments-directive.md)
