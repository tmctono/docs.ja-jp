---
title: ランタイム ディレクティブ (rd.xml) 構成ファイル リファレンス
ms.date: 03/30/2017
ms.assetid: 8241523f-d8e1-4fb6-bf6a-b29bfe07b38a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7545e1d7079664fd8706bdddac2ff3c8ebc27c7f
ms.sourcegitcommit: 37616676fde89153f563a485fc6159fc57326fc2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/23/2019
ms.locfileid: "69988296"
---
# <a name="runtime-directives-rdxml-configuration-file-reference"></a><span data-ttu-id="5988c-102">ランタイム ディレクティブ (rd.xml) 構成ファイル リファレンス</span><span class="sxs-lookup"><span data-stu-id="5988c-102">Runtime Directives (rd.xml) Configuration File Reference</span></span>

<span data-ttu-id="5988c-103">ランタイム ディレクティブ (.rd.xml) ファイルは、指定されたプログラム要素をリフレクションに使用できるかどうかを示す XML 構成ファイルです。</span><span class="sxs-lookup"><span data-stu-id="5988c-103">A runtime directives (.rd.xml) file is an XML configuration file that specifies whether designated program elements are available for reflection.</span></span> <span data-ttu-id="5988c-104">ランタイム ディレクティブ ファイルの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="5988c-104">Here’s an example of a runtime directives file:</span></span>

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
  <Application>
    <Namespace Name="Contoso.Cloud.AppServices" Serialize="Required Public" />
    <Namespace Name="ContosoClient.ViewModels" Serialize="Required Public" />
    <Namespace Name="ContosoClient.DataModel" Serialize="Required Public" />
    <Namespace Name="Contoso.Reader.UtilityLib" Serialize="Required Public" />

    <Namespace Name="System.Collections.ObjectModel" >
      <TypeInstantiation Name="ObservableCollection"
            Arguments="ContosoClient.DataModel.ProductItem" Serialize="Public" />
      <TypeInstantiation Name="ReadOnlyObservableCollection"
            Arguments="ContosoClient.DataModel.ProductGroup" Serialize="Public" />
    </Namespace>
  </Application>
</Directives>
```

## <a name="the-structure-of-a-runtime-directives-file"></a><span data-ttu-id="5988c-105">ランタイム ディレクティブ ファイルの構造</span><span class="sxs-lookup"><span data-stu-id="5988c-105">The structure of a runtime directives file</span></span>

<span data-ttu-id="5988c-106">ランタイム ディレクティブ ファイルは `http://schemas.microsoft.com/netfx/2013/01/metadata` 名前空間を使用します。</span><span class="sxs-lookup"><span data-stu-id="5988c-106">The runtime directives file uses the `http://schemas.microsoft.com/netfx/2013/01/metadata` namespace.</span></span>

<span data-ttu-id="5988c-107">ルート要素は [Directives](../../../docs/framework/net-native/directives-element-net-native.md) 要素です。</span><span class="sxs-lookup"><span data-stu-id="5988c-107">The root element is the [Directives](../../../docs/framework/net-native/directives-element-net-native.md) element.</span></span> <span data-ttu-id="5988c-108">これには、次の構造に示すように、0 個以上の [Library](../../../docs/framework/net-native/library-element-net-native.md) 要素と 0 または 1 個の [Application](../../../docs/framework/net-native/application-element-net-native.md) 要素を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="5988c-108">It can contain zero or more [Library](../../../docs/framework/net-native/library-element-net-native.md) elements, and zero or one [Application](../../../docs/framework/net-native/application-element-net-native.md) element, as shown in the following structure.</span></span> <span data-ttu-id="5988c-109">[Application](../../../docs/framework/net-native/application-element-net-native.md) 要素の属性は、アプリケーション全体のランタイム リフレクション ポリシーを定義できるか、子要素のコンテナーとして機能できます。</span><span class="sxs-lookup"><span data-stu-id="5988c-109">The attributes of the [Application](../../../docs/framework/net-native/application-element-net-native.md) element can define application-wide runtime reflection policy, or it can serve as a container for child elements.</span></span> <span data-ttu-id="5988c-110">一方、[Library](../../../docs/framework/net-native/library-element-net-native.md) 要素は単にコンテナーです。</span><span class="sxs-lookup"><span data-stu-id="5988c-110">The [Library](../../../docs/framework/net-native/library-element-net-native.md) element, on the other hand, is simply a container.</span></span> <span data-ttu-id="5988c-111">[Application](../../../docs/framework/net-native/application-element-net-native.md) 要素と [Library](../../../docs/framework/net-native/library-element-net-native.md) 要素の子は、リフレクションで使用できる型、メソッド、フィールド、プロパティ、およびイベントを定義します。</span><span class="sxs-lookup"><span data-stu-id="5988c-111">The children of the [Application](../../../docs/framework/net-native/application-element-net-native.md) and [Library](../../../docs/framework/net-native/library-element-net-native.md) elements define the types, methods, fields, properties, and events that are available for reflection.</span></span>

<span data-ttu-id="5988c-112">参照情報については、次の構造から要素を選択するか、「[ランタイム ディレクティブ要素](../../../docs/framework/net-native/runtime-directive-elements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5988c-112">For reference information, choose elements from the following structure or see [Runtime Directive Elements](../../../docs/framework/net-native/runtime-directive-elements.md).</span></span> <span data-ttu-id="5988c-113">次の階層で、省略記号は再帰構造を示します。</span><span class="sxs-lookup"><span data-stu-id="5988c-113">In the following hierarchy, the ellipsis marks a recursive structure.</span></span> <span data-ttu-id="5988c-114">角かっこ内の情報は、その要素が省略可能または必須のいずれであるか、および使用される場合に許可されるインスタンスの数 (1 つまたは複数) を示します。</span><span class="sxs-lookup"><span data-stu-id="5988c-114">The information in brackets indicates whether that element is optional or required, and if it is used, how many instances (one or many) are allowed.</span></span>

<span data-ttu-id="5988c-115">[ディレクティブ](../../../docs/framework/net-native/directives-element-net-native.md)[1:1][アプリケーション](../../../docs/framework/net-native/application-element-net-native.md)[0:1][アセンブリ](../../../docs/framework/net-native/assembly-element-net-native.md)[0: m][名前空間](../../../docs/framework/net-native/namespace-element-net-native.md)[0: m]。</span><span class="sxs-lookup"><span data-stu-id="5988c-115">[Directives](../../../docs/framework/net-native/directives-element-net-native.md) [1:1] [Application](../../../docs/framework/net-native/application-element-net-native.md) [0:1] [Assembly](../../../docs/framework/net-native/assembly-element-net-native.md) [0:M] [Namespace](../../../docs/framework/net-native/namespace-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="5988c-116">.</span><span class="sxs-lookup"><span data-stu-id="5988c-116">.</span></span> <span data-ttu-id="5988c-117">.</span><span class="sxs-lookup"><span data-stu-id="5988c-117">.</span></span>
<span data-ttu-id="5988c-118">[型](../../../docs/framework/net-native/type-element-net-native.md)[0: M]。</span><span class="sxs-lookup"><span data-stu-id="5988c-118">[Type](../../../docs/framework/net-native/type-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="5988c-119">.</span><span class="sxs-lookup"><span data-stu-id="5988c-119">.</span></span> <span data-ttu-id="5988c-120">.</span><span class="sxs-lookup"><span data-stu-id="5988c-120">.</span></span>
<span data-ttu-id="5988c-121">[Typeinstantiation インスタンス化](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)(構築されたジェネリック型)[0: M]。</span><span class="sxs-lookup"><span data-stu-id="5988c-121">[TypeInstantiation](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) (constructed generic type) [0:M] .</span></span> <span data-ttu-id="5988c-122">.</span><span class="sxs-lookup"><span data-stu-id="5988c-122">.</span></span> <span data-ttu-id="5988c-123">.</span><span class="sxs-lookup"><span data-stu-id="5988c-123">.</span></span>
<span data-ttu-id="5988c-124">[名前空間](../../../docs/framework/net-native/namespace-element-net-native.md)[0: M][名前空間](../../../docs/framework/net-native/namespace-element-net-native.md)[0: M]。</span><span class="sxs-lookup"><span data-stu-id="5988c-124">[Namespace](../../../docs/framework/net-native/namespace-element-net-native.md) [0:M] [Namespace](../../../docs/framework/net-native/namespace-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="5988c-125">.</span><span class="sxs-lookup"><span data-stu-id="5988c-125">.</span></span> <span data-ttu-id="5988c-126">.</span><span class="sxs-lookup"><span data-stu-id="5988c-126">.</span></span>
<span data-ttu-id="5988c-127">[型](../../../docs/framework/net-native/type-element-net-native.md)[0: M]。</span><span class="sxs-lookup"><span data-stu-id="5988c-127">[Type](../../../docs/framework/net-native/type-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="5988c-128">.</span><span class="sxs-lookup"><span data-stu-id="5988c-128">.</span></span> <span data-ttu-id="5988c-129">.</span><span class="sxs-lookup"><span data-stu-id="5988c-129">.</span></span>
<span data-ttu-id="5988c-130">[Typeinstantiation インスタンス化](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)(構築されたジェネリック型)[0: M]。</span><span class="sxs-lookup"><span data-stu-id="5988c-130">[TypeInstantiation](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) (constructed generic type) [0:M] .</span></span> <span data-ttu-id="5988c-131">.</span><span class="sxs-lookup"><span data-stu-id="5988c-131">.</span></span> <span data-ttu-id="5988c-132">.</span><span class="sxs-lookup"><span data-stu-id="5988c-132">.</span></span>
<span data-ttu-id="5988c-133">[型](../../../docs/framework/net-native/type-element-net-native.md)[0: M][サブタイプ](../../../docs/framework/net-native/subtypes-element-net-native.md)(含んでいる型のサブクラス)O:1[型](../../../docs/framework/net-native/type-element-net-native.md)[0: M]。</span><span class="sxs-lookup"><span data-stu-id="5988c-133">[Type](../../../docs/framework/net-native/type-element-net-native.md) [0:M] [Subtypes](../../../docs/framework/net-native/subtypes-element-net-native.md) (subclasses of the containing type) [O:1] [Type](../../../docs/framework/net-native/type-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="5988c-134">.</span><span class="sxs-lookup"><span data-stu-id="5988c-134">.</span></span> <span data-ttu-id="5988c-135">.</span><span class="sxs-lookup"><span data-stu-id="5988c-135">.</span></span>
<span data-ttu-id="5988c-136">[Typeinstantiation インスタンス化](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)(構築されたジェネリック型)[0: M]。</span><span class="sxs-lookup"><span data-stu-id="5988c-136">[TypeInstantiation](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) (constructed generic type) [0:M] .</span></span> <span data-ttu-id="5988c-137">.</span><span class="sxs-lookup"><span data-stu-id="5988c-137">.</span></span> <span data-ttu-id="5988c-138">.</span><span class="sxs-lookup"><span data-stu-id="5988c-138">.</span></span>
<span data-ttu-id="5988c-139">[Attributeimplies](../../../docs/framework/net-native/attributeimplies-element-net-native.md)(包含する型は属性です)O:1[Genericparameter](../../../docs/framework/net-native/genericparameter-element-net-native.md)[0: M][メソッド](../../../docs/framework/net-native/method-element-net-native.md)[0: M][パラメーター](../../../docs/framework/net-native/parameter-element-net-native.md)[0: M][Typeparameter](../../../docs/framework/net-native/typeparameter-element-net-native.md)[0: M][Genericparameter](../../../docs/framework/net-native/genericparameter-element-net-native.md)[0: M][Methodinstantiation 化](../../../docs/framework/net-native/methodinstantiation-element-net-native.md)(構築されたジェネリックメソッド)[0: M][プロパティ](../../../docs/framework/net-native/property-element-net-native.md)[0: M][フィールド](../../../docs/framework/net-native/field-element-net-native.md)[0: M][イベント](../../../docs/framework/net-native/event-element-net-native.md)[0: M][Typeinstantiation インスタンス化](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)(構築されたジェネリック型)[0: M][型](../../../docs/framework/net-native/type-element-net-native.md)[0: M]。</span><span class="sxs-lookup"><span data-stu-id="5988c-139">[AttributeImplies](../../../docs/framework/net-native/attributeimplies-element-net-native.md) (containing type is an attribute) [O:1] [GenericParameter](../../../docs/framework/net-native/genericparameter-element-net-native.md) [0:M] [Method](../../../docs/framework/net-native/method-element-net-native.md) [0:M] [Parameter](../../../docs/framework/net-native/parameter-element-net-native.md) [0:M] [TypeParameter](../../../docs/framework/net-native/typeparameter-element-net-native.md) [0:M] [GenericParameter](../../../docs/framework/net-native/genericparameter-element-net-native.md) [0:M] [MethodInstantiation](../../../docs/framework/net-native/methodinstantiation-element-net-native.md) (constructed generic method) [0:M] [Property](../../../docs/framework/net-native/property-element-net-native.md) [0:M] [Field](../../../docs/framework/net-native/field-element-net-native.md) [0:M] [Event](../../../docs/framework/net-native/event-element-net-native.md) [0:M] [TypeInstantiation](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) (constructed generic type) [0:M] [Type](../../../docs/framework/net-native/type-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="5988c-140">.</span><span class="sxs-lookup"><span data-stu-id="5988c-140">.</span></span> <span data-ttu-id="5988c-141">.</span><span class="sxs-lookup"><span data-stu-id="5988c-141">.</span></span>
<span data-ttu-id="5988c-142">[Typeinstantiation インスタンス化](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)(構築されたジェネリック型)[0: M]。</span><span class="sxs-lookup"><span data-stu-id="5988c-142">[TypeInstantiation](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) (constructed generic type) [0:M] .</span></span> <span data-ttu-id="5988c-143">.</span><span class="sxs-lookup"><span data-stu-id="5988c-143">.</span></span> <span data-ttu-id="5988c-144">.</span><span class="sxs-lookup"><span data-stu-id="5988c-144">.</span></span>
<span data-ttu-id="5988c-145">[メソッド](../../../docs/framework/net-native/method-element-net-native.md)[0: M][パラメーター](../../../docs/framework/net-native/parameter-element-net-native.md)[0: M][Typeparameter](../../../docs/framework/net-native/typeparameter-element-net-native.md)[0: M][Genericparameter](../../../docs/framework/net-native/genericparameter-element-net-native.md)[0: M][Methodinstantiation 化](../../../docs/framework/net-native/methodinstantiation-element-net-native.md)(構築されたジェネリックメソッド)[0: M][プロパティ](../../../docs/framework/net-native/property-element-net-native.md)[0: M][フィールド](../../../docs/framework/net-native/field-element-net-native.md)[0: M][イベント](../../../docs/framework/net-native/event-element-net-native.md)[0: M][ライブラリ](../../../docs/framework/net-native/library-element-net-native.md)[0: M][アセンブリ](../../../docs/framework/net-native/assembly-element-net-native.md)[0: M][名前空間](../../../docs/framework/net-native/namespace-element-net-native.md)[0: M]。</span><span class="sxs-lookup"><span data-stu-id="5988c-145">[Method](../../../docs/framework/net-native/method-element-net-native.md) [0:M] [Parameter](../../../docs/framework/net-native/parameter-element-net-native.md) [0:M] [TypeParameter](../../../docs/framework/net-native/typeparameter-element-net-native.md) [0:M] [GenericParameter](../../../docs/framework/net-native/genericparameter-element-net-native.md) [0:M] [MethodInstantiation](../../../docs/framework/net-native/methodinstantiation-element-net-native.md) (constructed generic method) [0:M] [Property](../../../docs/framework/net-native/property-element-net-native.md) [0:M] [Field](../../../docs/framework/net-native/field-element-net-native.md) [0:M] [Event](../../../docs/framework/net-native/event-element-net-native.md) [0:M] [Library](../../../docs/framework/net-native/library-element-net-native.md) [0:M] [Assembly](../../../docs/framework/net-native/assembly-element-net-native.md) [0:M] [Namespace](../../../docs/framework/net-native/namespace-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="5988c-146">.</span><span class="sxs-lookup"><span data-stu-id="5988c-146">.</span></span> <span data-ttu-id="5988c-147">.</span><span class="sxs-lookup"><span data-stu-id="5988c-147">.</span></span>
<span data-ttu-id="5988c-148">[型](../../../docs/framework/net-native/type-element-net-native.md)[0: M]。</span><span class="sxs-lookup"><span data-stu-id="5988c-148">[Type](../../../docs/framework/net-native/type-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="5988c-149">.</span><span class="sxs-lookup"><span data-stu-id="5988c-149">.</span></span> <span data-ttu-id="5988c-150">.</span><span class="sxs-lookup"><span data-stu-id="5988c-150">.</span></span>
<span data-ttu-id="5988c-151">[Typeinstantiation インスタンス化](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)(構築されたジェネリック型)[0: M]。</span><span class="sxs-lookup"><span data-stu-id="5988c-151">[TypeInstantiation](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) (constructed generic type) [0:M] .</span></span> <span data-ttu-id="5988c-152">.</span><span class="sxs-lookup"><span data-stu-id="5988c-152">.</span></span> <span data-ttu-id="5988c-153">.</span><span class="sxs-lookup"><span data-stu-id="5988c-153">.</span></span>
<span data-ttu-id="5988c-154">[名前空間](../../../docs/framework/net-native/namespace-element-net-native.md)[0: M][名前空間](../../../docs/framework/net-native/namespace-element-net-native.md)[0: M]。</span><span class="sxs-lookup"><span data-stu-id="5988c-154">[Namespace](../../../docs/framework/net-native/namespace-element-net-native.md) [0:M] [Namespace](../../../docs/framework/net-native/namespace-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="5988c-155">.</span><span class="sxs-lookup"><span data-stu-id="5988c-155">.</span></span> <span data-ttu-id="5988c-156">.</span><span class="sxs-lookup"><span data-stu-id="5988c-156">.</span></span>
<span data-ttu-id="5988c-157">[型](../../../docs/framework/net-native/type-element-net-native.md)[0: M]。</span><span class="sxs-lookup"><span data-stu-id="5988c-157">[Type](../../../docs/framework/net-native/type-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="5988c-158">.</span><span class="sxs-lookup"><span data-stu-id="5988c-158">.</span></span> <span data-ttu-id="5988c-159">.</span><span class="sxs-lookup"><span data-stu-id="5988c-159">.</span></span>
<span data-ttu-id="5988c-160">[Typeinstantiation インスタンス化](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)(構築されたジェネリック型)[0: M]。</span><span class="sxs-lookup"><span data-stu-id="5988c-160">[TypeInstantiation](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) (constructed generic type) [0:M] .</span></span> <span data-ttu-id="5988c-161">.</span><span class="sxs-lookup"><span data-stu-id="5988c-161">.</span></span> <span data-ttu-id="5988c-162">.</span><span class="sxs-lookup"><span data-stu-id="5988c-162">.</span></span>
<span data-ttu-id="5988c-163">[型](../../../docs/framework/net-native/type-element-net-native.md)[0: M][サブタイプ](../../../docs/framework/net-native/subtypes-element-net-native.md)(含んでいる型のサブクラス)O:1[型](../../../docs/framework/net-native/type-element-net-native.md)[0: M]。</span><span class="sxs-lookup"><span data-stu-id="5988c-163">[Type](../../../docs/framework/net-native/type-element-net-native.md) [0:M] [Subtypes](../../../docs/framework/net-native/subtypes-element-net-native.md) (subclasses of the containing type) [O:1] [Type](../../../docs/framework/net-native/type-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="5988c-164">.</span><span class="sxs-lookup"><span data-stu-id="5988c-164">.</span></span> <span data-ttu-id="5988c-165">.</span><span class="sxs-lookup"><span data-stu-id="5988c-165">.</span></span>
<span data-ttu-id="5988c-166">[Typeinstantiation インスタンス化](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)(構築されたジェネリック型)[0: M]。</span><span class="sxs-lookup"><span data-stu-id="5988c-166">[TypeInstantiation](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) (constructed generic type) [0:M] .</span></span> <span data-ttu-id="5988c-167">.</span><span class="sxs-lookup"><span data-stu-id="5988c-167">.</span></span> <span data-ttu-id="5988c-168">.</span><span class="sxs-lookup"><span data-stu-id="5988c-168">.</span></span>
<span data-ttu-id="5988c-169">[Attributeimplies](../../../docs/framework/net-native/attributeimplies-element-net-native.md)(包含する型は属性です)O:1[Genericparameter](../../../docs/framework/net-native/genericparameter-element-net-native.md)[0: M][メソッド](../../../docs/framework/net-native/method-element-net-native.md)[0: M][Methodinstantiation 化](../../../docs/framework/net-native/methodinstantiation-element-net-native.md)(構築されたジェネリックメソッド)[0: M][プロパティ](../../../docs/framework/net-native/property-element-net-native.md)[0: M][フィールド](../../../docs/framework/net-native/field-element-net-native.md)[0: M][イベント](../../../docs/framework/net-native/event-element-net-native.md)[0: M][Typeinstantiation インスタンス化](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)(構築されたジェネリック型)[0: M][型](../../../docs/framework/net-native/type-element-net-native.md)[0: M]。</span><span class="sxs-lookup"><span data-stu-id="5988c-169">[AttributeImplies](../../../docs/framework/net-native/attributeimplies-element-net-native.md) (containing type is an attribute) [O:1] [GenericParameter](../../../docs/framework/net-native/genericparameter-element-net-native.md) [0:M] [Method](../../../docs/framework/net-native/method-element-net-native.md) [0:M] [MethodInstantiation](../../../docs/framework/net-native/methodinstantiation-element-net-native.md) (constructed generic method) [0:M] [Property](../../../docs/framework/net-native/property-element-net-native.md) [0:M] [Field](../../../docs/framework/net-native/field-element-net-native.md) [0:M] [Event](../../../docs/framework/net-native/event-element-net-native.md) [0:M] [TypeInstantiation](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) (constructed generic type) [0:M] [Type](../../../docs/framework/net-native/type-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="5988c-170">.</span><span class="sxs-lookup"><span data-stu-id="5988c-170">.</span></span> <span data-ttu-id="5988c-171">.</span><span class="sxs-lookup"><span data-stu-id="5988c-171">.</span></span>
<span data-ttu-id="5988c-172">[Typeinstantiation インスタンス化](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)(構築されたジェネリック型)[0: M]。</span><span class="sxs-lookup"><span data-stu-id="5988c-172">[TypeInstantiation](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) (constructed generic type) [0:M] .</span></span> <span data-ttu-id="5988c-173">.</span><span class="sxs-lookup"><span data-stu-id="5988c-173">.</span></span> <span data-ttu-id="5988c-174">.</span><span class="sxs-lookup"><span data-stu-id="5988c-174">.</span></span>
<span data-ttu-id="5988c-175">[メソッド](../../../docs/framework/net-native/method-element-net-native.md)[0: M][Methodinstantiation 化](../../../docs/framework/net-native/methodinstantiation-element-net-native.md)(構築されたジェネリックメソッド)[0: M][プロパティ](../../../docs/framework/net-native/property-element-net-native.md)[0: M][フィールド](../../../docs/framework/net-native/field-element-net-native.md)[0: M][イベント](../../../docs/framework/net-native/event-element-net-native.md)[0: M]</span><span class="sxs-lookup"><span data-stu-id="5988c-175">[Method](../../../docs/framework/net-native/method-element-net-native.md) [0:M] [MethodInstantiation](../../../docs/framework/net-native/methodinstantiation-element-net-native.md) (constructed generic method) [0:M] [Property](../../../docs/framework/net-native/property-element-net-native.md) [0:M] [Field](../../../docs/framework/net-native/field-element-net-native.md) [0:M] [Event](../../../docs/framework/net-native/event-element-net-native.md) [0:M]</span></span>

<span data-ttu-id="5988c-176">[Application](../../../docs/framework/net-native/application-element-net-native.md) 要素は属性を持たないか、「[ランタイム ディレクティブとポリシー](#Directives)」セクションで説明しているポリシー属性を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="5988c-176">The [Application](../../../docs/framework/net-native/application-element-net-native.md) element can have no attributes, or it can have the policy attributes discussed in the [Runtime directive and policy section](#Directives).</span></span>

<span data-ttu-id="5988c-177">[Library](../../../docs/framework/net-native/library-element-net-native.md) 要素は、ライブラリまたはアセンブリの名前をファイル拡張子なしで指定する、`Name` 属性 1 つを持ちます。</span><span class="sxs-lookup"><span data-stu-id="5988c-177">A [Library](../../../docs/framework/net-native/library-element-net-native.md) element has a single attribute, `Name`, that specifies the name of a library or assembly, without its file extension.</span></span> <span data-ttu-id="5988c-178">たとえば、次の [Library](../../../docs/framework/net-native/library-element-net-native.md) 要素は、Extensions.dll という名前のアセンブリに適用されます。</span><span class="sxs-lookup"><span data-stu-id="5988c-178">For example, the following [Library](../../../docs/framework/net-native/library-element-net-native.md) element applies to an assembly named Extensions.dll.</span></span>

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
  <Application>
     <!-- Child elements go here -->
  </Application>
  <Library Name="Extensions">
     <!-- Child elements go here -->
  </Library>
</Directives>
```

<a name="Directives"></a>

## <a name="runtime-directives-and-policy"></a><span data-ttu-id="5988c-179">ランタイム ディレクティブとポリシー</span><span class="sxs-lookup"><span data-stu-id="5988c-179">Runtime directives and policy</span></span>

<span data-ttu-id="5988c-180">[Application](../../../docs/framework/net-native/application-element-net-native.md) 要素自体と [Library](../../../docs/framework/net-native/library-element-net-native.md) 要素と [Application](../../../docs/framework/net-native/application-element-net-native.md) 要素の子要素はポリシーを表します。つまり、アプリがプログラム要素にリフレクションを適用できる方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="5988c-180">The [Application](../../../docs/framework/net-native/application-element-net-native.md) element itself and the child elements of the [Library](../../../docs/framework/net-native/library-element-net-native.md) and [Application](../../../docs/framework/net-native/application-element-net-native.md) elements express policy; that is, they define the way in which an app can apply reflection to a program element.</span></span> <span data-ttu-id="5988c-181">ポリシーの種類は要素の属性 (たとえば、`Serialize`) により定義されます。</span><span class="sxs-lookup"><span data-stu-id="5988c-181">The policy type is defined by an attribute of the element (for example, `Serialize`).</span></span> <span data-ttu-id="5988c-182">ポリシーの値は属性の値 (たとえば、`Serialize="Required"`) により定義されます。</span><span class="sxs-lookup"><span data-stu-id="5988c-182">The policy value is defined by the attribute’s value (for example, `Serialize="Required"`).</span></span>

<span data-ttu-id="5988c-183">要素の属性により指定されるすべてのポリシーは、そのポリシーの値を指定しないすべての子要素に適用されます。</span><span class="sxs-lookup"><span data-stu-id="5988c-183">Any policy specified by an attribute of an element applies to all child elements that don’t specify a value for that policy.</span></span> <span data-ttu-id="5988c-184">たとえば、[Type](../../../docs/framework/net-native/type-element-net-native.md) 要素で指定されたポリシーは、ポリシーが明示的に指定されていない、その要素に含まれる型とメンバーすべてに適用されます。</span><span class="sxs-lookup"><span data-stu-id="5988c-184">For example, if a policy is specified by a [Type](../../../docs/framework/net-native/type-element-net-native.md) element, that policy applies to all contained types and members for which a policy is not explicitly specified.</span></span>

<span data-ttu-id="5988c-185">[Application](../../../docs/framework/net-native/application-element-net-native.md)、[Assembly](../../../docs/framework/net-native/assembly-element-net-native.md)、[AttributeImplies](../../../docs/framework/net-native/attributeimplies-element-net-native.md)、[Namespace](../../../docs/framework/net-native/namespace-element-net-native.md)、[Subtypes](../../../docs/framework/net-native/subtypes-element-net-native.md)、および [Type](../../../docs/framework/net-native/type-element-net-native.md) 要素で表すことができるポリシーは、個々のメンバーについて ([Method](../../../docs/framework/net-native/method-element-net-native.md)、[Property](../../../docs/framework/net-native/property-element-net-native.md)、[Field](../../../docs/framework/net-native/field-element-net-native.md)、および [Event](../../../docs/framework/net-native/event-element-net-native.md) 要素で) 表すことができるポリシーとは異なります。</span><span class="sxs-lookup"><span data-stu-id="5988c-185">The policy that can be expressed by the [Application](../../../docs/framework/net-native/application-element-net-native.md), [Assembly](../../../docs/framework/net-native/assembly-element-net-native.md), [AttributeImplies](../../../docs/framework/net-native/attributeimplies-element-net-native.md), [Namespace](../../../docs/framework/net-native/namespace-element-net-native.md), [Subtypes](../../../docs/framework/net-native/subtypes-element-net-native.md), and [Type](../../../docs/framework/net-native/type-element-net-native.md) elements differs from the policy that can be expressed for individual members (by the [Method](../../../docs/framework/net-native/method-element-net-native.md), [Property](../../../docs/framework/net-native/property-element-net-native.md), [Field](../../../docs/framework/net-native/field-element-net-native.md), and [Event](../../../docs/framework/net-native/event-element-net-native.md) elements).</span></span>

### <a name="specifying-policy-for-assemblies-namespaces-and-types"></a><span data-ttu-id="5988c-186">アセンブリ、名前空間、型に対するポリシーの指定</span><span class="sxs-lookup"><span data-stu-id="5988c-186">Specifying policy for assemblies, namespaces, and types</span></span>

<span data-ttu-id="5988c-187">[Application](../../../docs/framework/net-native/application-element-net-native.md)、[Assembly](../../../docs/framework/net-native/assembly-element-net-native.md)、[AttributeImplies](../../../docs/framework/net-native/attributeimplies-element-net-native.md)、[Namespace](../../../docs/framework/net-native/namespace-element-net-native.md)、[Subtypes](../../../docs/framework/net-native/subtypes-element-net-native.md)、および [Type](../../../docs/framework/net-native/type-element-net-native.md) 要素は、次のポリシーの種類をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="5988c-187">The [Application](../../../docs/framework/net-native/application-element-net-native.md), [Assembly](../../../docs/framework/net-native/assembly-element-net-native.md), [AttributeImplies](../../../docs/framework/net-native/attributeimplies-element-net-native.md), [Namespace](../../../docs/framework/net-native/namespace-element-net-native.md), [Subtypes](../../../docs/framework/net-native/subtypes-element-net-native.md), and [Type](../../../docs/framework/net-native/type-element-net-native.md) elements support the following policy types:</span></span>

- <span data-ttu-id="5988c-188">`Activate`。</span><span class="sxs-lookup"><span data-stu-id="5988c-188">`Activate`.</span></span> <span data-ttu-id="5988c-189">コンストラクターへの実行時アクセスを制御して、インスタンスのアクティブ化を有効にします。</span><span class="sxs-lookup"><span data-stu-id="5988c-189">Controls runtime access to constructors, to enable activation of instances.</span></span>

- <span data-ttu-id="5988c-190">`Browse`。</span><span class="sxs-lookup"><span data-stu-id="5988c-190">`Browse`.</span></span> <span data-ttu-id="5988c-191">プログラム要素に関する情報の照会を制御しますが、実行時アクセスは有効にしません。</span><span class="sxs-lookup"><span data-stu-id="5988c-191">Controls querying for information about program elements but does not enable any runtime access.</span></span>

- <span data-ttu-id="5988c-192">`Dynamic`。</span><span class="sxs-lookup"><span data-stu-id="5988c-192">`Dynamic`.</span></span> <span data-ttu-id="5988c-193">コンストラクター、メソッド、フィールド、プロパティ、およびイベントを含むすべての型のメンバーへの実行時アクセスを制御して、動的プログラミングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="5988c-193">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>

- <span data-ttu-id="5988c-194">`Serialize`。</span><span class="sxs-lookup"><span data-stu-id="5988c-194">`Serialize`.</span></span> <span data-ttu-id="5988c-195">コンストラクター、フィールド、およびプロパティへの実行時アクセスを制御し、Newtonsoft の JSON シリアライザーなどのサードパーティ ライブラリによって型インスタンスをシリアル化および逆シリアル化できるようにします。</span><span class="sxs-lookup"><span data-stu-id="5988c-195">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and serialized by third-party libraries such as the Newtonsoft JSON serializer.</span></span>

- <span data-ttu-id="5988c-196">`DataContractSerializer`。</span><span class="sxs-lookup"><span data-stu-id="5988c-196">`DataContractSerializer`.</span></span> <span data-ttu-id="5988c-197"><xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> クラスを使用するシリアル化のポリシーを制御します。</span><span class="sxs-lookup"><span data-stu-id="5988c-197">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>

- <span data-ttu-id="5988c-198">`DataContractJsonSerializer`。</span><span class="sxs-lookup"><span data-stu-id="5988c-198">`DataContractJsonSerializer`.</span></span> <span data-ttu-id="5988c-199"><xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> クラスを使用する JSON シリアル化のポリシーを制御します。</span><span class="sxs-lookup"><span data-stu-id="5988c-199">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>

- <span data-ttu-id="5988c-200">`XmlSerializer`。</span><span class="sxs-lookup"><span data-stu-id="5988c-200">`XmlSerializer`.</span></span> <span data-ttu-id="5988c-201"><xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> クラスを使用する XML シリアル化のポリシーを制御します。</span><span class="sxs-lookup"><span data-stu-id="5988c-201">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>

- <span data-ttu-id="5988c-202">`MarshalObject`。</span><span class="sxs-lookup"><span data-stu-id="5988c-202">`MarshalObject`.</span></span> <span data-ttu-id="5988c-203">WinRT と COM に参照型をマーシャリングするためのポリシーを制御します。</span><span class="sxs-lookup"><span data-stu-id="5988c-203">Controls policy for marshaling reference types to WinRT and COM.</span></span>

- <span data-ttu-id="5988c-204">`MarshalDelegate`。</span><span class="sxs-lookup"><span data-stu-id="5988c-204">`MarshalDelegate`.</span></span> <span data-ttu-id="5988c-205">ネイティブ コードへの関数ポインターとしてデリゲート型をマーシャリングするためのポリシーを制御します。</span><span class="sxs-lookup"><span data-stu-id="5988c-205">Controls policy for marshaling delegate types as function pointers to native code.</span></span>

- <span data-ttu-id="5988c-206">`MarshalStructure` .</span><span class="sxs-lookup"><span data-stu-id="5988c-206">`MarshalStructure` .</span></span> <span data-ttu-id="5988c-207">ネイティブ コードに構造体をマーシャリングするためのポリシーを制御します。</span><span class="sxs-lookup"><span data-stu-id="5988c-207">Controls policy for marshaling structures to native code.</span></span>

<span data-ttu-id="5988c-208">これらのポリシーの種類に関連付けられている設定を次に示します。</span><span class="sxs-lookup"><span data-stu-id="5988c-208">The settings associated with these policy types are:</span></span>

- <span data-ttu-id="5988c-209">`All`。</span><span class="sxs-lookup"><span data-stu-id="5988c-209">`All`.</span></span> <span data-ttu-id="5988c-210">ツール チェーンが削除しないすべての型とメンバーに対するポリシーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="5988c-210">Enable the policy for all types and members that the tool chain does not remove.</span></span>

- <span data-ttu-id="5988c-211">`Auto`。</span><span class="sxs-lookup"><span data-stu-id="5988c-211">`Auto`.</span></span> <span data-ttu-id="5988c-212">既定の動作を使用します。</span><span class="sxs-lookup"><span data-stu-id="5988c-212">Use the default behavior.</span></span> <span data-ttu-id="5988c-213">(親要素などによってポリシーがオーバーライドされない限り、ポリシーを指定しないことは、そのポリシーを `Auto` に設定することと同じです。)</span><span class="sxs-lookup"><span data-stu-id="5988c-213">(Not specifying a policy is equivalent to setting that policy to `Auto` unless that policy is overridden, for example by a parent element.)</span></span>

- <span data-ttu-id="5988c-214">`Excluded`。</span><span class="sxs-lookup"><span data-stu-id="5988c-214">`Excluded`.</span></span> <span data-ttu-id="5988c-215">プログラム要素のポリシーを無効にします。</span><span class="sxs-lookup"><span data-stu-id="5988c-215">Disable the policy for the program element.</span></span>

- <span data-ttu-id="5988c-216">`Public`。</span><span class="sxs-lookup"><span data-stu-id="5988c-216">`Public`.</span></span> <span data-ttu-id="5988c-217">ツール チェーンがメンバーが不要なために削除すると判断した場合を除き、パブリック型またはメンバーのポリシーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="5988c-217">Enable the policy for public types or members unless the tool chain determines that the member is unnecessary and therefore removes it.</span></span> <span data-ttu-id="5988c-218">(後者の場合は、`Required Public` を使用して、メンバーが保持されており、リフレクション機能があることを確認する必要があります。)</span><span class="sxs-lookup"><span data-stu-id="5988c-218">(In the latter case, you must use `Required Public` to ensure that the member is kept and has reflection capabilities.)</span></span>

- <span data-ttu-id="5988c-219">`PublicAndInternal`。</span><span class="sxs-lookup"><span data-stu-id="5988c-219">`PublicAndInternal`.</span></span> <span data-ttu-id="5988c-220">パブリックおよび内部型またはメンバーがツール チェーンによって削除されていない場合、それらのポリシーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="5988c-220">Enable the policy for public and internal types or members if the tool chain doesn't remove them.</span></span>

- <span data-ttu-id="5988c-221">`Required Public`。</span><span class="sxs-lookup"><span data-stu-id="5988c-221">`Required Public`.</span></span> <span data-ttu-id="5988c-222">使用されているかどうかに関係なく、パブリック型とメンバーを保持し、それらのポリシーを有効にするためにツール チェーンを要求します。</span><span class="sxs-lookup"><span data-stu-id="5988c-222">Require the tool chain to keep public types and members whether or not they are used, and enable the policy for them.</span></span>

- <span data-ttu-id="5988c-223">`Required PublicAndInternal`。</span><span class="sxs-lookup"><span data-stu-id="5988c-223">`Required PublicAndInternal`.</span></span> <span data-ttu-id="5988c-224">使用されているかどうかに関係なく、パブリックおよび内部両方の型とメンバーを保持し、それらのポリシーを有効にするためにツール チェーンを要求します。</span><span class="sxs-lookup"><span data-stu-id="5988c-224">Require the tool chain to keep both public and internal types and members whether or not they are used, and enable the policy for them.</span></span>

- <span data-ttu-id="5988c-225">`Required All`。</span><span class="sxs-lookup"><span data-stu-id="5988c-225">`Required All`.</span></span> <span data-ttu-id="5988c-226">使用されているかどうかに関係なく、すべての型とメンバーを保持し、それらのポリシーを有効にするために、ツール チェーンを要求します。</span><span class="sxs-lookup"><span data-stu-id="5988c-226">Require the tool chain to keep all types and members whether or not they are used, and enable the policy for them.</span></span>

<span data-ttu-id="5988c-227">たとえば、次のランタイム ディレクティブ ファイルは、DataClasses.dll アセンブリ内のすべての型とメンバーのポリシーを定義します。</span><span class="sxs-lookup"><span data-stu-id="5988c-227">For example, the following runtime directives file defines policy for all types and members in the assembly DataClasses.dll.</span></span> <span data-ttu-id="5988c-228">これは、すべてのパブリック プロパティのシリアル化のリフレクションを有効にし、すべての型と型のメンバーの参照を有効にし、すべての型のアクティブ化を (`Dynamic` 属性により) 有効にして、すべてのパブリック型とメンバーのリフレクションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="5988c-228">It enables reflection for serialization of all public properties, enables browsing for all types and type members, enables activation for all types (because of the `Dynamic` attribute), and enables reflection for all public types and members.</span></span>

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
   <Application>
      <Assembly Name="DataClasses" Serialize="Required Public"
                Browse="All" Activate="PublicAndInternal"
                Dynamic="Public"  />
   </Application>
   <Library Name="UtilityLibrary">
     <!-- Child elements go here -->
   </Library>
</Directives>
```

### <a name="specifying-policy-for-members"></a><span data-ttu-id="5988c-229">メンバーのポリシーの指定</span><span class="sxs-lookup"><span data-stu-id="5988c-229">Specifying policy for members</span></span>

<span data-ttu-id="5988c-230">[Property](../../../docs/framework/net-native/property-element-net-native.md) 要素と [Field](../../../docs/framework/net-native/field-element-net-native.md) 要素は次のポリシーの種類をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="5988c-230">The [Property](../../../docs/framework/net-native/property-element-net-native.md) and [Field](../../../docs/framework/net-native/field-element-net-native.md) elements support the following policy types:</span></span>

- <span data-ttu-id="5988c-231">`Browse`: このメンバーに関する情報の照会を制御しますが、実行時アクセスは有効にしません。</span><span class="sxs-lookup"><span data-stu-id="5988c-231">`Browse` - Controls querying for information about this member but does not enable any runtime access.</span></span>

- <span data-ttu-id="5988c-232">`Dynamic`: コンストラクター、メソッド、フィールド、プロパティ、およびイベントを含むすべての型のメンバーへの実行時アクセスを制御して、動的プログラミングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="5988c-232">`Dynamic` - Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span> <span data-ttu-id="5988c-233">また、それを含む型に関する情報の照会も制御します。</span><span class="sxs-lookup"><span data-stu-id="5988c-233">Also controls querying for information about the containing type.</span></span>

- <span data-ttu-id="5988c-234">`Serialize`: メンバーへの実行時アクセスを制御し、Newtonsoft の JSON シリアライザーなどのライブラリによって型インスタンスをシリアル化および逆シリアル化できるようにします。</span><span class="sxs-lookup"><span data-stu-id="5988c-234">`Serialize` - Controls runtime access to the member to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span> <span data-ttu-id="5988c-235">このポリシーは、コンストラクター、フィールド、およびプロパティに適用できます。</span><span class="sxs-lookup"><span data-stu-id="5988c-235">This policy can be applied to constructors, fields, and properties.</span></span>

<span data-ttu-id="5988c-236">[Method](../../../docs/framework/net-native/method-element-net-native.md) 要素と [Event](../../../docs/framework/net-native/event-element-net-native.md) 要素は次のポリシーの種類をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="5988c-236">The [Method](../../../docs/framework/net-native/method-element-net-native.md) and [Event](../../../docs/framework/net-native/event-element-net-native.md) elements support the following policy types:</span></span>

- <span data-ttu-id="5988c-237">`Browse`: このメンバーに関する情報の照会を制御しますが、実行時アクセスは有効にしません。</span><span class="sxs-lookup"><span data-stu-id="5988c-237">`Browse` - Controls querying for information about this member but doesn’t enable any runtime access.</span></span>

- <span data-ttu-id="5988c-238">`Dynamic`: コンストラクター、メソッド、フィールド、プロパティ、およびイベントを含むすべての型のメンバーへの実行時アクセスを制御して、動的プログラミングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="5988c-238">`Dynamic` - Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span> <span data-ttu-id="5988c-239">また、それを含む型に関する情報の照会も制御します。</span><span class="sxs-lookup"><span data-stu-id="5988c-239">Also controls querying for information about the containing type.</span></span>

 <span data-ttu-id="5988c-240">これらのポリシーの種類に関連付けられている設定を次に示します。</span><span class="sxs-lookup"><span data-stu-id="5988c-240">The settings associated with these policy types are:</span></span>

- <span data-ttu-id="5988c-241">`Auto`: 既定の動作を使用します。</span><span class="sxs-lookup"><span data-stu-id="5988c-241">`Auto` - Use the default behavior.</span></span> <span data-ttu-id="5988c-242">(何かにオーバーライドされない限り、ポリシーを指定しないことは、そのポリシーを `Auto` に設定することと同じです。)</span><span class="sxs-lookup"><span data-stu-id="5988c-242">(Not specifying a policy is equivalent to setting that policy to `Auto` unless something overrides it.)</span></span>

- <span data-ttu-id="5988c-243">`Excluded`: メンバーのメタデータを含めません。</span><span class="sxs-lookup"><span data-stu-id="5988c-243">`Excluded` - Never include metadata for the member.</span></span>

- <span data-ttu-id="5988c-244">`Included`: 親型が出力に存在する場合、ポリシーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="5988c-244">`Included` - Enable the policy if the parent type is present in the output.</span></span>

- <span data-ttu-id="5988c-245">`Required`: このメンバーが未使用と見なされる場合でもこれを保持し、そのメンバーのポリシーを有効にするためにツール チェーンを要求します。</span><span class="sxs-lookup"><span data-stu-id="5988c-245">`Required` - Require the tool chain to keep this member even if appears to be unused, and enable policy for it.</span></span>

## <a name="runtime-directives-file-semantics"></a><span data-ttu-id="5988c-246">ランタイム ディレクティブ ファイルのセマンティクス</span><span class="sxs-lookup"><span data-stu-id="5988c-246">Runtime directives file semantics</span></span>

<span data-ttu-id="5988c-247">ポリシーは、上位レベルと下位レベルの要素両方に同時に定義できます。</span><span class="sxs-lookup"><span data-stu-id="5988c-247">Policy can be defined simultaneously for both higher-level and lower-level elements.</span></span> <span data-ttu-id="5988c-248">たとえば、アセンブリと、そのアセンブリに含まれる型の一部にポリシーを定義できます。</span><span class="sxs-lookup"><span data-stu-id="5988c-248">For example, policy can be defined for an assembly, and for some of the types contained in that assembly.</span></span> <span data-ttu-id="5988c-249">特定の下位レベル要素が表されていない場合、その親のポリシーを継承します。</span><span class="sxs-lookup"><span data-stu-id="5988c-249">If a particular lower-level element is not represented, it inherits the policy of its parent.</span></span> <span data-ttu-id="5988c-250">たとえば、`Assembly` 要素は存在するが `Type` 要素は存在しない場合、`Assembly` 要素で指定されるポリシーはアセンブリ内のすべての型に適用されます。</span><span class="sxs-lookup"><span data-stu-id="5988c-250">For example, if an `Assembly` element is present but `Type` elements are not, the policy specified in the `Assembly` element applies to each type in the assembly.</span></span> <span data-ttu-id="5988c-251">複数の要素が同じプログラム要素にポリシーを適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="5988c-251">Multiple elements can also apply policy to the same program element.</span></span> <span data-ttu-id="5988c-252">たとえば、個別の [Assembly](../../../docs/framework/net-native/assembly-element-net-native.md) 要素が、同じアセンブリの同じポリシー要素を別々に定義するとします。</span><span class="sxs-lookup"><span data-stu-id="5988c-252">For example, separate [Assembly](../../../docs/framework/net-native/assembly-element-net-native.md) elements might define the same policy element for the same assembly differently.</span></span> <span data-ttu-id="5988c-253">次のセクションで、このような場合に特定の型のポリシーがどのように解決されるかを説明します。</span><span class="sxs-lookup"><span data-stu-id="5988c-253">The following sections explain how the policy for a particular type is resolved in those cases.</span></span>

<span data-ttu-id="5988c-254">ジェネリック型またはメソッドの [Type](../../../docs/framework/net-native/type-element-net-native.md) 要素または [Method](../../../docs/framework/net-native/method-element-net-native.md) 要素は、独自のポリシーを持たないすべてのインスタンス化にそのポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="5988c-254">A [Type](../../../docs/framework/net-native/type-element-net-native.md) or [Method](../../../docs/framework/net-native/method-element-net-native.md) element of a generic type or method applies its policy to all instantiations that do not have their own policy.</span></span> <span data-ttu-id="5988c-255">たとえば、`Type` のポリシーを指定する <xref:System.Collections.Generic.List%601> 要素は、構築された特定のジェネリック型 (`List<Int32>` など) について `TypeInstantiation` 要素によってオーバーライドされない限り、そのジェネリック型のすべての構築されたインスタンスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="5988c-255">For example, a `Type` element that specifies policy for <xref:System.Collections.Generic.List%601> applies to all constructed instances of that generic type, unless it's overridden for a particular constructed generic type (such as a `List<Int32>`) by a `TypeInstantiation` element.</span></span> <span data-ttu-id="5988c-256">そうでない場合、要素は指定されたプログラム要素のポリシーを定義します。</span><span class="sxs-lookup"><span data-stu-id="5988c-256">Otherwise, elements define policy for the program element named.</span></span>

<span data-ttu-id="5988c-257">要素があいまいな場合、エンジンが一致を検索し、完全一致が見つかるとそれを使用します。</span><span class="sxs-lookup"><span data-stu-id="5988c-257">When an element is ambiguous, the engine looks for matches, and if it finds an exact match, it will use it.</span></span> <span data-ttu-id="5988c-258">複数の一致が見つかった場合は警告またはエラーになります。</span><span class="sxs-lookup"><span data-stu-id="5988c-258">If it finds multiple matches, there will be a warning or error.</span></span>

### <a name="if-two-directives-apply-policy-to-the-same-program-element"></a><span data-ttu-id="5988c-259">2 つのディレクティブが同じプログラム要素にポリシーを適用する場合</span><span class="sxs-lookup"><span data-stu-id="5988c-259">If two directives apply policy to the same program element</span></span>

<span data-ttu-id="5988c-260">別のランタイム ディレクティブ ファイルにある 2 つの要素が同じプログラム要素 (アセンブリや型など) の同じポリシーの種類を異なる値に設定しようとした場合、次のように競合が解決されます。</span><span class="sxs-lookup"><span data-stu-id="5988c-260">If two elements in different runtime directives files try to set the same policy type for the same program element (such as an assembly or type) to different values, the conflict is resolved as follows:</span></span>

1. <span data-ttu-id="5988c-261">`Excluded` 要素が存在する場合はこれが優先されます。</span><span class="sxs-lookup"><span data-stu-id="5988c-261">If the `Excluded` element is present, it has precedence.</span></span>

2. <span data-ttu-id="5988c-262">`Required` は `Required` 以外より優先されます。</span><span class="sxs-lookup"><span data-stu-id="5988c-262">`Required` has precedence over not `Required`.</span></span>

3. <span data-ttu-id="5988c-263">`All` は `PublicAndInternal` (`Public` より優先) より優先されされます。</span><span class="sxs-lookup"><span data-stu-id="5988c-263">`All` has precedence over `PublicAndInternal`, which has precedence over `Public`.</span></span>

4. <span data-ttu-id="5988c-264">明示的な設定はいずれも `Auto` より優先されます。</span><span class="sxs-lookup"><span data-stu-id="5988c-264">Any explicit setting has precedence over `Auto`.</span></span>

<span data-ttu-id="5988c-265">たとえば、1 つのプロジェクトに次の 2 つのランタイム ディレクティブ ファイルが含まれている場合、DataClasses.dll のシリアル化ポリシーは `Required Public` と `All` の両方に設定されます。</span><span class="sxs-lookup"><span data-stu-id="5988c-265">For example, if a single project includes the following two runtime directives files, the serialization policy for DataClasses.dll is set to both `Required Public` and `All`.</span></span> <span data-ttu-id="5988c-266">この場合、シリアル化ポリシーは `Required All` として解決されます。</span><span class="sxs-lookup"><span data-stu-id="5988c-266">In this case, the serialization policy would be resolved as `Required All`.</span></span>

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
   <Application>
      <Assembly Name="DataClasses" Serialize="Required Public"/>
   </Application>
   <Library Name="DataClasses">
      <!-- any other elements -->
   </Library>
</Directives>
```

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
   <Application>
      <Assembly Name="DataClasses" Serialize="All" />
   </Application>
   <Library Name="DataClasses">
      <!-- any other elements -->
   </Library>
</Directives>
```

<span data-ttu-id="5988c-267">ただし、1 つのランタイム ディレクティブ ファイル内の 2 つのディレクティブが同じプログラム要素に同じポリシーの種類を設定しようとした場合、XML スキーマ定義ツールからエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5988c-267">However, if two directives in a single runtime directives file try to set the same policy type for the same program element, the XML Scheme Definition tool displays an error message.</span></span>

### <a name="if-child-and-parent-elements-apply-the-same-policy-type"></a><span data-ttu-id="5988c-268">子要素と親要素が同じポリシーの種類を適用する場合</span><span class="sxs-lookup"><span data-stu-id="5988c-268">If child and parent elements apply the same policy type</span></span>

<span data-ttu-id="5988c-269">`Excluded` 設定を含め、子要素はその親要素をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="5988c-269">Child elements override their parent elements, including the `Excluded` setting.</span></span> <span data-ttu-id="5988c-270">オーバーライドは、`Auto` を指定する必要がある主な理由です。</span><span class="sxs-lookup"><span data-stu-id="5988c-270">Overriding is the main reason you would want to specify `Auto`.</span></span>

<span data-ttu-id="5988c-271">次の例では、`DataClasses` にはあるが `DataClasses.ViewModels` にはないものすべてのシリアル化ポリシー設定が `Required Public` になり、`DataClasses` と `DataClasses.ViewModels` の両方にあるものすべてのシリアル化ポリシー設定は `All` になります。</span><span class="sxs-lookup"><span data-stu-id="5988c-271">In the following example, the serialization policy setting for everything in `DataClasses` that’s not in `DataClasses.ViewModels` would be `Required Public`, and everything that's in both `DataClasses` and `DataClasses.ViewModels` would be `All`.</span></span>

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
   <Application>
      <Assembly Name="DataClasses" Serialize="Required Public" >
         <Namespace Name="DataClasses.ViewModels" Serialize="All" />
      </Assembly>
   </Application>
   <Library Name="DataClasses">
      <!-- any other elements -->
   </Library>
</Directives>
```

### <a name="if-open-generics-and-instantiated-elements-apply-the-same-policy-type"></a><span data-ttu-id="5988c-272">オープン ジェネリックとインスタンス化された要素が同じポリシーの種類を適用する場合</span><span class="sxs-lookup"><span data-stu-id="5988c-272">If open generics and instantiated elements apply the same policy type</span></span>

<span data-ttu-id="5988c-273">次の例では、`Dictionary<int,int>` には、特に `Browse` ポリシーを割り当てる理由がエンジンにある場合にのみ、`Browse` ポリシーが割り当てられます (通常は、これが既定の動作です)。それ以外の <xref:System.Collections.Generic.Dictionary%602> のすべてのインスタンス化では、そのメンバーのすべてが参照可能になります。</span><span class="sxs-lookup"><span data-stu-id="5988c-273">In the following example, `Dictionary<int,int>` is assigned the `Browse` policy only if the engine has another reason to give it the `Browse` policy (which would otherwise be the default behavior); every other instantiation of <xref:System.Collections.Generic.Dictionary%602> will have all of its members browsable.</span></span>

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
   <Application>
      <Assembly Name="DataClasses" Serialize="Required Public" >
         <Namespace Name="DataClasses.ViewModels" Serialize="All" />
      </Assembly>
      <Namespace Name="DataClasses.Generics" />
      <Type Name="Dictionary" Browse="All" />
      <TypeInstantiation Name="Dictionary"
                         Arguments="System.Int32,System.Int32" Browse="Auto" />
   </Application>
   <Library Name="DataClasses">
      <!-- any other elements -->
   </Library>
</Directives>
```

### <a name="how-policy-is-inferred"></a><span data-ttu-id="5988c-274">ポリシーの推論方法</span><span class="sxs-lookup"><span data-stu-id="5988c-274">How policy is inferred</span></span>

<span data-ttu-id="5988c-275">ポリシーの種類ごとに、そのポリシーの種類の存在が他の構造体にどう影響するかを決定する一連のルールが異なります。</span><span class="sxs-lookup"><span data-stu-id="5988c-275">Each policy type has a different set of rules that determine how the presence of that policy type affects other constructs.</span></span>

#### <a name="the-effect-of-browse-policy"></a><span data-ttu-id="5988c-276">Browse ポリシーの効果</span><span class="sxs-lookup"><span data-stu-id="5988c-276">The effect of Browse policy</span></span>

<span data-ttu-id="5988c-277">`Browse` ポリシーを型に適用すると、ポリシーが次のように変更されます。</span><span class="sxs-lookup"><span data-stu-id="5988c-277">Applying the `Browse` policy to a type involves the following policy changes:</span></span>

- <span data-ttu-id="5988c-278">型の基本型が `Browse` ポリシーでマークされます。</span><span class="sxs-lookup"><span data-stu-id="5988c-278">The base type of the type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="5988c-279">型がインスタンス化されたジェネリックである場合、インスタンス化されていないその型が `Browse` ポリシーでマークされます。</span><span class="sxs-lookup"><span data-stu-id="5988c-279">If the type is an instantiated generic, the uninstantiated version of the type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="5988c-280">型がデリゲートの場合、型の `Invoke` メソッドが `Dynamic` ポリシーでマークされます。</span><span class="sxs-lookup"><span data-stu-id="5988c-280">If the type is a delegate, the `Invoke` method on the type is marked with the `Dynamic` policy.</span></span>

- <span data-ttu-id="5988c-281">型の各インターフェイスが `Browse` ポリシーでマークされます。</span><span class="sxs-lookup"><span data-stu-id="5988c-281">Each interface of the type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="5988c-282">型に適用されている各属性の型が `Browse` ポリシーでマークされます。</span><span class="sxs-lookup"><span data-stu-id="5988c-282">The type of each attribute applied to the type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="5988c-283">型がジェネリックの場合、各制約型が `Browse` ポリシーでマークされます。</span><span class="sxs-lookup"><span data-stu-id="5988c-283">If the type is generic, each constraint type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="5988c-284">型がジェネリックの場合、その型のインスタンス化対象である型が `Browse` ポリシーでマークされます。</span><span class="sxs-lookup"><span data-stu-id="5988c-284">If the type is generic, the types over which the type is instantiated are marked with the `Browse` policy.</span></span>

<span data-ttu-id="5988c-285">メソッドに `Browse` ポリシーを適用すると、ポリシーが次のように変更されます。</span><span class="sxs-lookup"><span data-stu-id="5988c-285">Applying the `Browse` policy to a method involves the following policy changes:</span></span>

- <span data-ttu-id="5988c-286">メソッドの各パラメーター型が `Browse` ポリシーでマークされます。</span><span class="sxs-lookup"><span data-stu-id="5988c-286">Each parameter type of the method is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="5988c-287">メソッドの戻り型が `Browse` ポリシーでマークされます。</span><span class="sxs-lookup"><span data-stu-id="5988c-287">The return type of the method is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="5988c-288">メソッドを含む型が `Browse` ポリシーでマークされます。</span><span class="sxs-lookup"><span data-stu-id="5988c-288">The containing type of the method is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="5988c-289">メソッドがインスタンス化されたジェネリック メソッドである場合、インスタンス化されていないジェネリック メソッドが `Browse` ポリシーでマークされます。</span><span class="sxs-lookup"><span data-stu-id="5988c-289">If the method is an instantiated generic method, the uninstantiated generic method is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="5988c-290">メソッドに適用される各属性の型が `Browse` ポリシーでマークされます。</span><span class="sxs-lookup"><span data-stu-id="5988c-290">The type of each attribute applied to the method is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="5988c-291">メソッドがジェネリックの場合、各制約型が `Browse` ポリシーでマークされます。</span><span class="sxs-lookup"><span data-stu-id="5988c-291">If the method is generic, each constraint type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="5988c-292">メソッドがジェネリックの場合、そのメソッドのインスタンス化対象である型が `Browse` ポリシーでマークされます。</span><span class="sxs-lookup"><span data-stu-id="5988c-292">If the method is generic, the types over which the method is instantiated are marked with the `Browse` policy.</span></span>

<span data-ttu-id="5988c-293">フィールドに `Browse` ポリシーを適用すると、ポリシーが次のように変更されます。</span><span class="sxs-lookup"><span data-stu-id="5988c-293">Applying the `Browse` policy to a field involves the following policy changes:</span></span>

- <span data-ttu-id="5988c-294">フィールドに適用される各属性の型が `Browse` ポリシーでマークされます。</span><span class="sxs-lookup"><span data-stu-id="5988c-294">The type of each attribute applied to the field is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="5988c-295">フィールドの型が `Browse` ポリシーでマークされます。</span><span class="sxs-lookup"><span data-stu-id="5988c-295">The type of the field is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="5988c-296">フィールドが属する型が `Browse` ポリシーでマークされます。</span><span class="sxs-lookup"><span data-stu-id="5988c-296">The type to which the field belongs is marked with the `Browse` policy.</span></span>

#### <a name="the-effect-of-dynamic-policy"></a><span data-ttu-id="5988c-297">Dynamic ポリシーの効果</span><span class="sxs-lookup"><span data-stu-id="5988c-297">The effect of Dynamic policy</span></span>

<span data-ttu-id="5988c-298">`Dynamic` ポリシーを型に適用すると、ポリシーが次のように変更されます。</span><span class="sxs-lookup"><span data-stu-id="5988c-298">Applying the `Dynamic` policy to a type involves the following policy changes:</span></span>

- <span data-ttu-id="5988c-299">型の基本型が `Dynamic` ポリシーでマークされます。</span><span class="sxs-lookup"><span data-stu-id="5988c-299">The base type of the type is marked with the `Dynamic` policy.</span></span>

- <span data-ttu-id="5988c-300">型がインスタンス化されたジェネリックである場合、インスタンス化されていないその型が `Dynamic` ポリシーでマークされます。</span><span class="sxs-lookup"><span data-stu-id="5988c-300">If the type is an instantiated generic, the uninstantiated version of the type is marked with the `Dynamic` policy.</span></span>

- <span data-ttu-id="5988c-301">型がデリゲート型の場合、型の `Invoke` メソッドが `Dynamic` ポリシーでマークされます。</span><span class="sxs-lookup"><span data-stu-id="5988c-301">If the type is a delegate type, the `Invoke` method on the type is marked with the `Dynamic` policy.</span></span>

- <span data-ttu-id="5988c-302">型の各インターフェイスが `Browse` ポリシーでマークされます。</span><span class="sxs-lookup"><span data-stu-id="5988c-302">Each interface of the type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="5988c-303">型に適用されている各属性の型が `Browse` ポリシーでマークされます。</span><span class="sxs-lookup"><span data-stu-id="5988c-303">The type of each attribute applied to the type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="5988c-304">型がジェネリックの場合、各制約型が `Browse` ポリシーでマークされます。</span><span class="sxs-lookup"><span data-stu-id="5988c-304">If the type is generic, each constraint type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="5988c-305">型がジェネリックの場合、その型のインスタンス化対象である型が `Browse` ポリシーでマークされます。</span><span class="sxs-lookup"><span data-stu-id="5988c-305">If the type is generic, the types over which the type is instantiated are marked with the `Browse` policy.</span></span>

<span data-ttu-id="5988c-306">メソッドに `Dynamic` ポリシーを適用すると、ポリシーが次のように変更されます。</span><span class="sxs-lookup"><span data-stu-id="5988c-306">Applying the `Dynamic` policy to a method involves the following policy changes:</span></span>

- <span data-ttu-id="5988c-307">メソッドの各パラメーター型が `Browse` ポリシーでマークされます。</span><span class="sxs-lookup"><span data-stu-id="5988c-307">Each parameter type of the method is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="5988c-308">メソッドの戻り型が `Dynamic` ポリシーでマークされます。</span><span class="sxs-lookup"><span data-stu-id="5988c-308">The return type of the method is marked with the `Dynamic` policy.</span></span>

- <span data-ttu-id="5988c-309">メソッドを含む型が `Dynamic` ポリシーでマークされます。</span><span class="sxs-lookup"><span data-stu-id="5988c-309">The containing type of the method is marked with the `Dynamic` policy.</span></span>

- <span data-ttu-id="5988c-310">メソッドがインスタンス化されたジェネリック メソッドである場合、インスタンス化されていないジェネリック メソッドが `Browse` ポリシーでマークされます。</span><span class="sxs-lookup"><span data-stu-id="5988c-310">If the method is an instantiated generic method, the uninstantiated generic method is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="5988c-311">メソッドに適用される各属性の型が `Browse` ポリシーでマークされます。</span><span class="sxs-lookup"><span data-stu-id="5988c-311">The type of each attribute applied to the method is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="5988c-312">メソッドがジェネリックの場合、各制約型が `Browse` ポリシーでマークされます。</span><span class="sxs-lookup"><span data-stu-id="5988c-312">If the method is generic, each constraint type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="5988c-313">メソッドがジェネリックの場合、そのメソッドのインスタンス化対象である型が `Browse` ポリシーでマークされます。</span><span class="sxs-lookup"><span data-stu-id="5988c-313">If the method is generic, the types over which the method is instantiated are marked with the `Browse` policy.</span></span>

- <span data-ttu-id="5988c-314">メソッドを `MethodInfo.Invoke` により呼び出すことができ、<xref:System.Reflection.MethodInfo.CreateDelegate%2A?displayProperty=nameWithType> によりデリゲートの作成が可能になります。</span><span class="sxs-lookup"><span data-stu-id="5988c-314">The method can be invoked by `MethodInfo.Invoke`, and delegate creation becomes possible by <xref:System.Reflection.MethodInfo.CreateDelegate%2A?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="5988c-315">フィールドに `Dynamic` ポリシーを適用すると、ポリシーが次のように変更されます。</span><span class="sxs-lookup"><span data-stu-id="5988c-315">Applying the `Dynamic` policy to a field involves the following policy changes:</span></span>

- <span data-ttu-id="5988c-316">フィールドに適用される各属性の型が `Browse` ポリシーでマークされます。</span><span class="sxs-lookup"><span data-stu-id="5988c-316">The type of each attribute applied to the field is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="5988c-317">フィールドの型が `Dynamic` ポリシーでマークされます。</span><span class="sxs-lookup"><span data-stu-id="5988c-317">The type of the field is marked with the `Dynamic` policy.</span></span>

- <span data-ttu-id="5988c-318">フィールドが属する型が `Dynamic` ポリシーでマークされます。</span><span class="sxs-lookup"><span data-stu-id="5988c-318">The type to which the field belongs is marked with the `Dynamic` policy.</span></span>

#### <a name="the-effect-of-activation-policy"></a><span data-ttu-id="5988c-319">Activation ポリシーの効果</span><span class="sxs-lookup"><span data-stu-id="5988c-319">The effect of Activation policy</span></span>

<span data-ttu-id="5988c-320">型に Activation ポリシーを適用すると、ポリシーが次のように変更されます。</span><span class="sxs-lookup"><span data-stu-id="5988c-320">Applying the Activation policy to a type involves the following policy changes:</span></span>

- <span data-ttu-id="5988c-321">型がインスタンス化されたジェネリックである場合、インスタンス化されていないその型が `Browse` ポリシーでマークされます。</span><span class="sxs-lookup"><span data-stu-id="5988c-321">If the type is an instantiated generic, the uninstantiated version of the type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="5988c-322">型がデリゲート型の場合、型の `Invoke` メソッドが `Dynamic` ポリシーでマークされます。</span><span class="sxs-lookup"><span data-stu-id="5988c-322">If the type is a delegate type, the `Invoke` method on the type is marked with the `Dynamic` policy.</span></span>

- <span data-ttu-id="5988c-323">型のコンストラクターが `Activation` ポリシーでマークされます。</span><span class="sxs-lookup"><span data-stu-id="5988c-323">Constructors of the type are marked with the `Activation` policy.</span></span>

<span data-ttu-id="5988c-324">メソッドに `Activation` ポリシーを適用すると、ポリシーが次のように変更されます。</span><span class="sxs-lookup"><span data-stu-id="5988c-324">Applying the `Activation` policy to a method involves the following policy change:</span></span>

- <span data-ttu-id="5988c-325">コンストラクターを <xref:System.Reflection.ConstructorInfo.Invoke%2A?displayProperty=nameWithType> メソッドと <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> メソッドにより呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="5988c-325">The constructor can be invoked by the <xref:System.Reflection.ConstructorInfo.Invoke%2A?displayProperty=nameWithType> and <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="5988c-326">メソッドに関しては、`Activation` ポリシーはコンストラクターにのみ影響します。</span><span class="sxs-lookup"><span data-stu-id="5988c-326">For methods, the `Activation` policy affects constructors only.</span></span>

<span data-ttu-id="5988c-327">フィールドに `Activation` ポリシーを適用しても効果はありません。</span><span class="sxs-lookup"><span data-stu-id="5988c-327">Applying the `Activation` policy to a field has no effect.</span></span>

#### <a name="the-effect-of-serialize-policy"></a><span data-ttu-id="5988c-328">Serialize ポリシーの効果</span><span class="sxs-lookup"><span data-stu-id="5988c-328">The effect of Serialize policy</span></span>

<span data-ttu-id="5988c-329">`Serialize` ポリシーにより、一般的なリフレクション ベースのシリアライザーを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="5988c-329">The `Serialize` policy enables the use of common reflection-based serializers.</span></span> <span data-ttu-id="5988c-330">ただし、Microsoft では、Microsoft 以外のシリアライザーの正確なリフレクション アクセス パターンを認識していないため、このポリシーが常に効果的であるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="5988c-330">However, because the exact reflection access patterns of non-Microsoft serializers are not known to Microsoft, this policy may not be entirely effective.</span></span>

<span data-ttu-id="5988c-331">`Serialize` ポリシーを型に適用すると、ポリシーが次のように変更されます。</span><span class="sxs-lookup"><span data-stu-id="5988c-331">Applying the `Serialize` policy to a type involves the following policy changes:</span></span>

- <span data-ttu-id="5988c-332">型の基本型が `Serialize` ポリシーでマークされます。</span><span class="sxs-lookup"><span data-stu-id="5988c-332">The base type of the type is marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="5988c-333">型がインスタンス化されたジェネリックである場合、インスタンス化されていないその型が `Browse` ポリシーでマークされます。</span><span class="sxs-lookup"><span data-stu-id="5988c-333">If the type is an instantiated generic, the uninstantiated version of the type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="5988c-334">型がデリゲート型の場合、型の `Invoke` メソッドが `Dynamic` ポリシーでマークされます。</span><span class="sxs-lookup"><span data-stu-id="5988c-334">If the type is a delegate type, the `Invoke` method on the type is marked with the `Dynamic` policy.</span></span>

- <span data-ttu-id="5988c-335">型が列挙の場合、型の配列が `Serialize` ポリシーでマークされます。</span><span class="sxs-lookup"><span data-stu-id="5988c-335">If the type is an enumeration, an array of the type is marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="5988c-336">型が <xref:System.Collections.Generic.IEnumerable%601> を実装する場合、`T` が `Serialize` ポリシーでマークされます。</span><span class="sxs-lookup"><span data-stu-id="5988c-336">If the type implements <xref:System.Collections.Generic.IEnumerable%601>, `T` is marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="5988c-337">型が <xref:System.Collections.Generic.IEnumerable%601>、<xref:System.Collections.Generic.IList%601>、<xref:System.Collections.Generic.ICollection%601>、<xref:System.Collections.Generic.IReadOnlyCollection%601>、または <xref:System.Collections.Generic.IReadOnlyList%601> の場合、`T[]` と <xref:System.Collections.Generic.List%601> が `Serialize` ポリシーでマークされますが、インターフェイス型のメンバーは `Serialize` ポリシーでマークされません。</span><span class="sxs-lookup"><span data-stu-id="5988c-337">If the type is <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.Generic.IList%601>, <xref:System.Collections.Generic.ICollection%601>, <xref:System.Collections.Generic.IReadOnlyCollection%601>, or <xref:System.Collections.Generic.IReadOnlyList%601>, then `T[]` and <xref:System.Collections.Generic.List%601> marked with the `Serialize` policy., but no members of the interface type are marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="5988c-338">型が <xref:System.Collections.Generic.List%601> の場合、型のどのメンバーも `Serialize` ポリシーでマークされません。</span><span class="sxs-lookup"><span data-stu-id="5988c-338">If the type is <xref:System.Collections.Generic.List%601>, no members of the type are marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="5988c-339">型が <xref:System.Collections.Generic.IDictionary%602> の場合、<xref:System.Collections.Generic.Dictionary%602> が `Serialize` ポリシーでマークされます。</span><span class="sxs-lookup"><span data-stu-id="5988c-339">If the type is <xref:System.Collections.Generic.IDictionary%602>, <xref:System.Collections.Generic.Dictionary%602> is marked with the `Serialize` policy.</span></span> <span data-ttu-id="5988c-340">ただし、型のどのメンバーも `Serialize` ポリシーでマークされません。</span><span class="sxs-lookup"><span data-stu-id="5988c-340">but no members of the type are marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="5988c-341">型が <xref:System.Collections.Generic.Dictionary%602> の場合、型のどのメンバーも `Serialize` ポリシーでマークされません。</span><span class="sxs-lookup"><span data-stu-id="5988c-341">If the type is <xref:System.Collections.Generic.Dictionary%602>, no members of the type are marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="5988c-342">型が <xref:System.Collections.Generic.IDictionary%602> を実装している場合、`TKey` と `TValue` が `Serialize` ポリシーでマークされます。</span><span class="sxs-lookup"><span data-stu-id="5988c-342">If the type implements <xref:System.Collections.Generic.IDictionary%602>, `TKey` and `TValue` are marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="5988c-343">各コンストラクター、各プロパティ アクセサー、および各フィールドが `Serialize` ポリシーでマークされます。</span><span class="sxs-lookup"><span data-stu-id="5988c-343">Each constructor, each property accessor, and each field is marked with the `Serialize` policy.</span></span>

<span data-ttu-id="5988c-344">メソッドに `Serialize` ポリシーを適用すると、ポリシーが次のように変更されます。</span><span class="sxs-lookup"><span data-stu-id="5988c-344">Applying the `Serialize` policy to a method involves the following policy changes:</span></span>

- <span data-ttu-id="5988c-345">それを含む型が `Serialize` ポリシーでマークされます。</span><span class="sxs-lookup"><span data-stu-id="5988c-345">The containing type is marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="5988c-346">メソッドの戻り型が `Serialize` ポリシーでマークされます。</span><span class="sxs-lookup"><span data-stu-id="5988c-346">The return type of the method is marked with the `Serialize` policy.</span></span>

<span data-ttu-id="5988c-347">フィールドに `Serialize` ポリシーを適用すると、ポリシーが次のように変更されます。</span><span class="sxs-lookup"><span data-stu-id="5988c-347">Applying the `Serialize` policy to a field involves the following policy changes:</span></span>

- <span data-ttu-id="5988c-348">それを含む型が `Serialize` ポリシーでマークされます。</span><span class="sxs-lookup"><span data-stu-id="5988c-348">The containing type is marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="5988c-349">フィールドの型が `Serialize` ポリシーでマークされます。</span><span class="sxs-lookup"><span data-stu-id="5988c-349">The type of the field is marked with the `Serialize` policy.</span></span>

#### <a name="the-effect-of-xmlserializer-datacontractserializer-and-datacontractjsonserializer-policies"></a><span data-ttu-id="5988c-350">XmlSerializer、DataContractSerializer、DataContractJsonSerializer の各ポリシーの影響</span><span class="sxs-lookup"><span data-stu-id="5988c-350">The effect of XmlSerializer, DataContractSerializer, and DataContractJsonSerializer policies</span></span>

<span data-ttu-id="5988c-351">リフレクションベースのシリアライザーを対象とする<xref:System.Xml.Serialization.XmlSerializer> <xref:System.Runtime.Serialization.DataContractSerializer> <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>ポリシーとは異なり、、、およびの各ポリシーを使用して、.NET ネイティブツールチェーンで認識されているシリアライザーのセットを有効にします。 `Serialize`</span><span class="sxs-lookup"><span data-stu-id="5988c-351">Unlike the `Serialize` policy, which is intended for reflection-based serializers, the <xref:System.Xml.Serialization.XmlSerializer>, <xref:System.Runtime.Serialization.DataContractSerializer>, and <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> policies are used to enable a set of serializers that are known to the .NET Native tool chain.</span></span> <span data-ttu-id="5988c-352">これらのシリアライザーはリフレクションを使用して実装されるのではなく、実行時にシリアル化可能な型のセットが、リフレクション可能な型と同様の方法で決定されます。</span><span class="sxs-lookup"><span data-stu-id="5988c-352">These serializers are not implemented by using reflection, but the set of types that can be serialized at run time is determined in a similar manner as types that are reflectable.</span></span>

<span data-ttu-id="5988c-353">これらのポリシーのいずれかを型に適用すると、対応するシリアライザーで型をシリアル化できるようになります。</span><span class="sxs-lookup"><span data-stu-id="5988c-353">Applying one of these policies to a type enables the type to be serialized with the matching serializer.</span></span> <span data-ttu-id="5988c-354">また、シリアル化が必要であることをシリアル化エンジンが静的に決定できる、すべての型もシリアル化されます。</span><span class="sxs-lookup"><span data-stu-id="5988c-354">Also, any types that the serialization engine can statically determine as needing serialization will also be serializable.</span></span>

<span data-ttu-id="5988c-355">これらのポリシーは、メソッドとフィールドには影響しません。</span><span class="sxs-lookup"><span data-stu-id="5988c-355">These policies have no effect on methods or fields.</span></span>

<span data-ttu-id="5988c-356">詳細については、「[Windows ストア アプリの .NET ネイティブへの移行](../../../docs/framework/net-native/migrating-your-windows-store-app-to-net-native.md)」の「シリアライザーの違い」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5988c-356">For more information, see the "Differences in Serializers" section in [Migrating Your Windows Store App to .NET Native](../../../docs/framework/net-native/migrating-your-windows-store-app-to-net-native.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5988c-357">関連項目</span><span class="sxs-lookup"><span data-stu-id="5988c-357">See also</span></span>

- [<span data-ttu-id="5988c-358">ランタイム ディレクティブ要素</span><span class="sxs-lookup"><span data-stu-id="5988c-358">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)
- [<span data-ttu-id="5988c-359">リフレクションおよび .NET ネイティブ</span><span class="sxs-lookup"><span data-stu-id="5988c-359">Reflection and .NET Native</span></span>](../../../docs/framework/net-native/reflection-and-net-native.md)
