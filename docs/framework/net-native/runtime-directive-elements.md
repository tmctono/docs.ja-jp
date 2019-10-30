---
title: ランタイム ディレクティブ要素
ms.date: 03/30/2017
ms.assetid: 3fe5848c-ecd7-4136-970b-8e48d250bde6
ms.openlocfilehash: c900516382c8e526a6b0021bb2b681486283f3ab
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128170"
---
# <a name="runtime-directive-elements"></a><span data-ttu-id="bb477-102">ランタイム ディレクティブ要素</span><span class="sxs-lookup"><span data-stu-id="bb477-102">Runtime Directive Elements</span></span>
<span data-ttu-id="bb477-103">ランタイム ディレクティブ (rd.xml) ファイル形式は、次のランタイム ディレクティブ要素をサポートします。</span><span class="sxs-lookup"><span data-stu-id="bb477-103">The runtime directives (rd.xml) file format supports the following runtime directive elements.</span></span> <span data-ttu-id="bb477-104">階層表現については、「[ランタイム ディレクティブ (rd.xml) 構成ファイル リファレンス](runtime-directives-rd-xml-configuration-file-reference.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb477-104">See [Runtime Directives (rd.xml) Configuration File Reference](runtime-directives-rd-xml-configuration-file-reference.md) for a hierarchical representation.</span></span>  
  
 [<span data-ttu-id="bb477-105">\<Application></span><span class="sxs-lookup"><span data-stu-id="bb477-105">\<Application></span></span>](application-element-net-native.md)  
 <span data-ttu-id="bb477-106">アプリで使用されるすべての型にランタイム リフレクション ポリシーを適用し、実行時にリフレクションに使用できるメタデータを持つアプリケーション全体の型と型のメンバーのコンテナーとして機能します。</span><span class="sxs-lookup"><span data-stu-id="bb477-106">Applies runtime reflection policy to all types used by the app, and serves as a container for application-wide types and type members whose metadata is available for reflection at run time.</span></span> <span data-ttu-id="bb477-107">これは、[\<Directives>](directives-element-net-native.md) 要素の子です。</span><span class="sxs-lookup"><span data-stu-id="bb477-107">This is a child of the [\<Directives>](directives-element-net-native.md) element.</span></span>  
  
 [<span data-ttu-id="bb477-108">\<Assembly></span><span class="sxs-lookup"><span data-stu-id="bb477-108">\<Assembly></span></span>](assembly-element-net-native.md)  
 <span data-ttu-id="bb477-109">アセンブリ内のすべての型に実行時ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="bb477-109">Applies runtime policy to all the types in an assembly.</span></span> <span data-ttu-id="bb477-110">これは、[\<Application>](application-element-net-native.md) 要素と [\<Library>](library-element-net-native.md) 要素の子です。</span><span class="sxs-lookup"><span data-stu-id="bb477-110">This is a child of the [\<Application>](application-element-net-native.md) and [\<Library>](library-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="bb477-111">\<AttributeImplies></span><span class="sxs-lookup"><span data-stu-id="bb477-111">\<AttributeImplies></span></span>](attributeimplies-element-net-native.md)  
 <span data-ttu-id="bb477-112">それを含んでいる [\<Type>](type-element-net-native.md) ディレクティブが属性の場合、その属性が適用されるコード要素に実行時ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="bb477-112">If its containing [\<Type>](type-element-net-native.md) directive is an attribute, applies runtime policy to code elements to which that attribute is applied.</span></span>  
  
 [<span data-ttu-id="bb477-113">\<Directives></span><span class="sxs-lookup"><span data-stu-id="bb477-113">\<Directives></span></span>](directives-element-net-native.md)  
 <span data-ttu-id="bb477-114">.NET ネイティブのすべてのランタイムディレクティブファイルのルート要素。</span><span class="sxs-lookup"><span data-stu-id="bb477-114">The root element in every runtime directives file for .NET Native.</span></span> <span data-ttu-id="bb477-115">その子要素は、[\<Application>](application-element-net-native.md) と [\<Library>](library-element-net-native.md) です。</span><span class="sxs-lookup"><span data-stu-id="bb477-115">Its child elements are [\<Application>](application-element-net-native.md) and [\<Library>](library-element-net-native.md).</span></span>  
  
 [<span data-ttu-id="bb477-116">\<Event></span><span class="sxs-lookup"><span data-stu-id="bb477-116">\<Event></span></span>](event-element-net-native.md)  
 <span data-ttu-id="bb477-117">イベントに実行時ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="bb477-117">Applies runtime policy to an event.</span></span> <span data-ttu-id="bb477-118">これは、[\<Type>](type-element-net-native.md) 要素と [\<TypeInstantiation>](typeinstantiation-element-net-native.md) 要素の子です。</span><span class="sxs-lookup"><span data-stu-id="bb477-118">This is a child of the [\<Type>](type-element-net-native.md) and [\<TypeInstantiation>](typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="bb477-119">\<Field></span><span class="sxs-lookup"><span data-stu-id="bb477-119">\<Field></span></span>](field-element-net-native.md)  
 <span data-ttu-id="bb477-120">フィールドに実行時ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="bb477-120">Applies runtime policy to a field.</span></span> <span data-ttu-id="bb477-121">これは、[\<Type>](type-element-net-native.md) 要素と [\<TypeInstantiation>](typeinstantiation-element-net-native.md) 要素の子です。</span><span class="sxs-lookup"><span data-stu-id="bb477-121">This is a child of the [\<Type>](type-element-net-native.md) and [\<TypeInstantiation>](typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="bb477-122">\<GenericParameter></span><span class="sxs-lookup"><span data-stu-id="bb477-122">\<GenericParameter></span></span>](genericparameter-element-net-native.md)  
 <span data-ttu-id="bb477-123">ジェネリック型またはメソッドのパラメーター型に実行時ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="bb477-123">Applies runtime policy to the parameter type of a generic type or method.</span></span>  
  
 [<span data-ttu-id="bb477-124">\<ImpliesType></span><span class="sxs-lookup"><span data-stu-id="bb477-124">\<ImpliesType></span></span>](impliestype-element-net-native.md)  
 <span data-ttu-id="bb477-125">型に実行時ポリシーを適用します (それを含んでいる型またはメソッドにそのポリシーが適用されている場合)。</span><span class="sxs-lookup"><span data-stu-id="bb477-125">Applies runtime policy to a type, if that policy has been applied to the containing type or method.</span></span>  
  
 [<span data-ttu-id="bb477-126">\<Library></span><span class="sxs-lookup"><span data-stu-id="bb477-126">\<Library></span></span>](library-element-net-native.md)  
 <span data-ttu-id="bb477-127">アセンブリ内のすべての型に実行時ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="bb477-127">Applies runtime policy to all the types in an assembly.</span></span> <span data-ttu-id="bb477-128">これは、[\<Application>](application-element-net-native.md) 要素と [\<Library>](library-element-net-native.md) 要素の子です。</span><span class="sxs-lookup"><span data-stu-id="bb477-128">This is a child of the [\<Application>](application-element-net-native.md) and [\<Library>](library-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="bb477-129">\<Method></span><span class="sxs-lookup"><span data-stu-id="bb477-129">\<Method></span></span>](method-element-net-native.md)  
 <span data-ttu-id="bb477-130">メソッドに実行時ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="bb477-130">Applies runtime policy to a method.</span></span> <span data-ttu-id="bb477-131">これは、[\<Type>](type-element-net-native.md) 要素と [\<TypeInstantiation>](typeinstantiation-element-net-native.md) 要素の子です。</span><span class="sxs-lookup"><span data-stu-id="bb477-131">This is a child of the [\<Type>](type-element-net-native.md) and [\<TypeInstantiation>](typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="bb477-132">\<MethodInstantiation></span><span class="sxs-lookup"><span data-stu-id="bb477-132">\<MethodInstantiation></span></span>](methodinstantiation-element-net-native.md)  
 <span data-ttu-id="bb477-133">構築されたジェネリック メソッドに実行時ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="bb477-133">Applies runtime policy to a constructed generic method.</span></span> <span data-ttu-id="bb477-134">これは、[\<Type>](type-element-net-native.md) 要素と [\<TypeInstantiation>](typeinstantiation-element-net-native.md) 要素の子です。</span><span class="sxs-lookup"><span data-stu-id="bb477-134">This is a child of the [\<Type>](type-element-net-native.md) and [\<TypeInstantiation>](typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="bb477-135">\<Namespace></span><span class="sxs-lookup"><span data-stu-id="bb477-135">\<Namespace></span></span>](namespace-element-net-native.md)  
 <span data-ttu-id="bb477-136">名前空間内のすべての型に実行時ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="bb477-136">Applies runtime policy to all the types in a namespace.</span></span>  
  
 [<span data-ttu-id="bb477-137">\<Parameter></span><span class="sxs-lookup"><span data-stu-id="bb477-137">\<Parameter></span></span>](parameter-element-net-native.md)  
 <span data-ttu-id="bb477-138">メソッドに渡された引数の型に実行時ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="bb477-138">Applies runtime policy to the type of the argument passed to a method.</span></span>  
  
 [<span data-ttu-id="bb477-139">\<Property></span><span class="sxs-lookup"><span data-stu-id="bb477-139">\<Property></span></span>](property-element-net-native.md)  
 <span data-ttu-id="bb477-140">プロパティに実行時ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="bb477-140">Applies runtime policy to a property.</span></span> <span data-ttu-id="bb477-141">これは、[\<Type>](type-element-net-native.md) 要素と [\<TypeInstantiation>](typeinstantiation-element-net-native.md) 要素の子です。</span><span class="sxs-lookup"><span data-stu-id="bb477-141">This is a child of the [\<Type>](type-element-net-native.md) and [\<TypeInstantiation>](typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="bb477-142">\<Subtypes></span><span class="sxs-lookup"><span data-stu-id="bb477-142">\<Subtypes></span></span>](subtypes-element-net-native.md)  
 <span data-ttu-id="bb477-143">それを含む型から継承されたすべてのクラスに実行時ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="bb477-143">Applies runtime policy to all classes inherited from the containing type.</span></span>  
  
 [<span data-ttu-id="bb477-144">\<Type></span><span class="sxs-lookup"><span data-stu-id="bb477-144">\<Type></span></span>](type-element-net-native.md)  
 <span data-ttu-id="bb477-145">型に実行時ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="bb477-145">Applies runtime policy to a type.</span></span>  
  
 [<span data-ttu-id="bb477-146">\<TypeInstantiation></span><span class="sxs-lookup"><span data-stu-id="bb477-146">\<TypeInstantiation></span></span>](typeinstantiation-element-net-native.md)  
 <span data-ttu-id="bb477-147">構築されたジェネリック型に実行時ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="bb477-147">Applies runtime policy to a constructed generic type.</span></span>  
  
 [<span data-ttu-id="bb477-148">\<TypeParameter></span><span class="sxs-lookup"><span data-stu-id="bb477-148">\<TypeParameter></span></span>](typeparameter-element-net-native.md)  
 <span data-ttu-id="bb477-149">メソッドに渡された <xref:System.Type> 引数によって表される型に実行時ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="bb477-149">Applies runtime policy to the type represented by a <xref:System.Type> argument passed to a method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb477-150">関連項目</span><span class="sxs-lookup"><span data-stu-id="bb477-150">See also</span></span>

- [<span data-ttu-id="bb477-151">rd.xml 構成ファイル リファレンス</span><span class="sxs-lookup"><span data-stu-id="bb477-151">rd.xml Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
