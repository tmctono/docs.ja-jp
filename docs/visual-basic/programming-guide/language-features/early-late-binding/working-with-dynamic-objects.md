---
title: 動的オブジェクトの使用 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- dynamic objects [Visual Basic]
ms.assetid: bdee2a00-07ff-46f9-86dd-fdac9b99cc97
ms.openlocfilehash: ea7d7aae1cd79a0243a9c721b5e3958fba82f84f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61973187"
---
# <a name="working-with-dynamic-objects-visual-basic"></a><span data-ttu-id="040cb-102">動的オブジェクトの使用 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="040cb-102">Working with Dynamic Objects (Visual Basic)</span></span>
<span data-ttu-id="040cb-103">動的オブジェクトが他にも別の方法を提供、`Object`実行時にオブジェクトに遅延バインディングの種類。</span><span class="sxs-lookup"><span data-stu-id="040cb-103">Dynamic objects provide another way, other than the `Object` type, to late bind to an object at run time.</span></span> <span data-ttu-id="040cb-104">動的オブジェクトで定義されている動的インターフェイスを使用して実行時のプロパティやメソッドなどのメンバーを公開します、<xref:System.Dynamic>名前空間。</span><span class="sxs-lookup"><span data-stu-id="040cb-104">A dynamic object exposes members such as properties and methods at run time by using dynamic interfaces that are defined in the <xref:System.Dynamic> namespace.</span></span> <span data-ttu-id="040cb-105">クラスを使用することができます、<xref:System.Dynamic>名前空間を静的な型または形式が一致しないデータ構造を操作するオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="040cb-105">You can use the classes in the <xref:System.Dynamic> namespace to create objects that work with data structures that do not match a static type or format.</span></span> <span data-ttu-id="040cb-106">IronPython や IronRuby などの動的言語で定義されている動的オブジェクトを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="040cb-106">You can also use the dynamic objects that are defined in dynamic languages such as IronPython and IronRuby.</span></span> <span data-ttu-id="040cb-107">動的オブジェクトを作成したり、動的言語で定義されている動的オブジェクトを使用する方法を示す例については、次を参照してください。[チュートリアル。動的オブジェクトの作成と](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)、 <xref:System.Dynamic.DynamicObject>、または<xref:System.Dynamic.ExpandoObject>します。</span><span class="sxs-lookup"><span data-stu-id="040cb-107">For examples that show how to create dynamic objects or use a dynamic object defined in a dynamic language, see [Walkthrough: Creating and Using Dynamic Objects](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md), <xref:System.Dynamic.DynamicObject>, or <xref:System.Dynamic.ExpandoObject>.</span></span>  
  
 <span data-ttu-id="040cb-108">Visual Basic のオブジェクトへのバインド、動的言語ランタイムと動的言語 IronPython や IronRuby などを使用して、<xref:System.Dynamic.IDynamicMetaObjectProvider>インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="040cb-108">Visual Basic binds to objects from the dynamic language runtime and dynamic languages such as IronPython and IronRuby by using the <xref:System.Dynamic.IDynamicMetaObjectProvider> interface.</span></span> <span data-ttu-id="040cb-109">実装するクラスの例については、`IDynamicMetaObjectProvider`インターフェイスは、<xref:System.Dynamic.DynamicObject>と<xref:System.Dynamic.ExpandoObject>クラス。</span><span class="sxs-lookup"><span data-stu-id="040cb-109">Examples of classes that implement the `IDynamicMetaObjectProvider` interface are the <xref:System.Dynamic.DynamicObject> and <xref:System.Dynamic.ExpandoObject> classes.</span></span>  
  
 <span data-ttu-id="040cb-110">実装するオブジェクトを遅延バインディング呼び出しが行われたかどうか、`IDynamicMetaObjectProvider`インターフェイス、そのインターフェイスを使用して、動的オブジェクトを Visual Basic をバインドします。</span><span class="sxs-lookup"><span data-stu-id="040cb-110">If a late-bound call is made to an object that implements the `IDynamicMetaObjectProvider` interface, Visual Basic binds to the dynamic object by using that interface.</span></span> <span data-ttu-id="040cb-111">実装しないオブジェクトを遅延バインディング呼び出しが行われた場合、`IDynamicMetaObjectProvider`インターフェイス、または場合への呼び出し、`IDynamicMetaObjectProvider`インターフェイスが失敗した場合、Visual Basic が Visual Basic ランタイムの遅延バインディング機能を使用して、オブジェクトにバインドします。</span><span class="sxs-lookup"><span data-stu-id="040cb-111">If a late-bound call is made to an object that does not implement the `IDynamicMetaObjectProvider` interface, or if the call to the `IDynamicMetaObjectProvider` interface fails, Visual Basic binds to the object by using the late-binding capabilities of the Visual Basic runtime.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="040cb-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="040cb-112">See also</span></span>

- <xref:System.Dynamic.DynamicObject>
- <xref:System.Dynamic.ExpandoObject>
- [<span data-ttu-id="040cb-113">チュートリアル: 動的オブジェクトの作成と使用</span><span class="sxs-lookup"><span data-stu-id="040cb-113">Walkthrough: Creating and Using Dynamic Objects</span></span>](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)
- [<span data-ttu-id="040cb-114">事前バインディングと遅延バインディング</span><span class="sxs-lookup"><span data-stu-id="040cb-114">Early and Late Binding</span></span>](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
