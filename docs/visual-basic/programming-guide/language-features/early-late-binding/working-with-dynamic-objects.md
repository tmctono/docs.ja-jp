---
title: 動的オブジェクトの使用
ms.date: 07/20/2015
helpviewer_keywords:
- dynamic objects [Visual Basic]
ms.assetid: bdee2a00-07ff-46f9-86dd-fdac9b99cc97
ms.openlocfilehash: 20d007fb48e1db352bab6d8e25d2e60e02554732
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345175"
---
# <a name="working-with-dynamic-objects-visual-basic"></a><span data-ttu-id="1686b-102">動的オブジェクトの使用 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1686b-102">Working with Dynamic Objects (Visual Basic)</span></span>
<span data-ttu-id="1686b-103">動的オブジェクトを使用すると、`Object` 型以外の別の方法で、実行時にオブジェクトへの遅延バインドを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="1686b-103">Dynamic objects provide another way, other than the `Object` type, to late bind to an object at run time.</span></span> <span data-ttu-id="1686b-104">動的オブジェクトは、<xref:System.Dynamic> 名前空間で定義されている動的インターフェイスを使用して、実行時にプロパティやメソッドなどのメンバーを公開します。</span><span class="sxs-lookup"><span data-stu-id="1686b-104">A dynamic object exposes members such as properties and methods at run time by using dynamic interfaces that are defined in the <xref:System.Dynamic> namespace.</span></span> <span data-ttu-id="1686b-105"><xref:System.Dynamic> 名前空間のクラスを使用すると、静的な型または形式に一致しないデータ構造体を操作するオブジェクトを作成できます。</span><span class="sxs-lookup"><span data-stu-id="1686b-105">You can use the classes in the <xref:System.Dynamic> namespace to create objects that work with data structures that do not match a static type or format.</span></span> <span data-ttu-id="1686b-106">IronPython や IronRuby などの動的言語で定義されている動的オブジェクトを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="1686b-106">You can also use the dynamic objects that are defined in dynamic languages such as IronPython and IronRuby.</span></span> <span data-ttu-id="1686b-107">動的オブジェクトを作成したり、動的言語で定義された動的オブジェクトを使用したりする方法を示す例については、「[チュートリアル: 動的オブジェクトの作成と使用](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)」、「<xref:System.Dynamic.DynamicObject>」、または「<xref:System.Dynamic.ExpandoObject>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1686b-107">For examples that show how to create dynamic objects or use a dynamic object defined in a dynamic language, see [Walkthrough: Creating and Using Dynamic Objects](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md), <xref:System.Dynamic.DynamicObject>, or <xref:System.Dynamic.ExpandoObject>.</span></span>  
  
 <span data-ttu-id="1686b-108">Visual Basic は、<xref:System.Dynamic.IDynamicMetaObjectProvider> インターフェイスを使用して、動的言語ランタイムおよび動的言語 (IronPython や IronRuby など) からオブジェクトにバインドします。</span><span class="sxs-lookup"><span data-stu-id="1686b-108">Visual Basic binds to objects from the dynamic language runtime and dynamic languages such as IronPython and IronRuby by using the <xref:System.Dynamic.IDynamicMetaObjectProvider> interface.</span></span> <span data-ttu-id="1686b-109">`IDynamicMetaObjectProvider` インターフェイスを実装するクラスの例として、<xref:System.Dynamic.DynamicObject> クラスと <xref:System.Dynamic.ExpandoObject> クラスがあります。</span><span class="sxs-lookup"><span data-stu-id="1686b-109">Examples of classes that implement the `IDynamicMetaObjectProvider` interface are the <xref:System.Dynamic.DynamicObject> and <xref:System.Dynamic.ExpandoObject> classes.</span></span>  
  
 <span data-ttu-id="1686b-110">`IDynamicMetaObjectProvider` インターフェイスを実装するオブジェクトに対して遅延バインディング呼び出しが行われた場合、Visual Basic はそのインターフェイスを使用して動的オブジェクトにバインドされます。</span><span class="sxs-lookup"><span data-stu-id="1686b-110">If a late-bound call is made to an object that implements the `IDynamicMetaObjectProvider` interface, Visual Basic binds to the dynamic object by using that interface.</span></span> <span data-ttu-id="1686b-111">`IDynamicMetaObjectProvider` インターフェイスを実装していないオブジェクトに対して遅延バインディング呼び出しが行われた場合、または `IDynamicMetaObjectProvider` インターフェイスへの呼び出しが失敗した場合、Visual Basic Visual Basic ランタイムの遅延バインディング機能を使用してオブジェクトにバインドされます。</span><span class="sxs-lookup"><span data-stu-id="1686b-111">If a late-bound call is made to an object that does not implement the `IDynamicMetaObjectProvider` interface, or if the call to the `IDynamicMetaObjectProvider` interface fails, Visual Basic binds to the object by using the late-binding capabilities of the Visual Basic runtime.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1686b-112">参照</span><span class="sxs-lookup"><span data-stu-id="1686b-112">See also</span></span>

- <xref:System.Dynamic.DynamicObject>
- <xref:System.Dynamic.ExpandoObject>
- [<span data-ttu-id="1686b-113">チュートリアル: 動的オブジェクトの作成と使用</span><span class="sxs-lookup"><span data-stu-id="1686b-113">Walkthrough: Creating and Using Dynamic Objects</span></span>](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)
- [<span data-ttu-id="1686b-114">事前バインディングと遅延バインディング</span><span class="sxs-lookup"><span data-stu-id="1686b-114">Early and Late Binding</span></span>](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
