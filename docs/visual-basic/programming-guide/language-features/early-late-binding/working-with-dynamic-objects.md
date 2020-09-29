---
title: 動的オブジェクトの使用
ms.date: 07/20/2015
helpviewer_keywords:
- dynamic objects [Visual Basic]
ms.assetid: bdee2a00-07ff-46f9-86dd-fdac9b99cc97
ms.openlocfilehash: 45f8b5c327d40f93b59c2115c75b3b7d385f5a8d
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "91057924"
---
# <a name="working-with-dynamic-objects-visual-basic"></a><span data-ttu-id="77b9b-102">動的オブジェクトの使用 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="77b9b-102">Working with Dynamic Objects (Visual Basic)</span></span>

<span data-ttu-id="77b9b-103">動的オブジェクトを使用すると、`Object` 型とは別に、実行時にオブジェクトへの遅延バインディングを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="77b9b-103">Dynamic objects provide another way, other than the `Object` type, to late bind to an object at run time.</span></span> <span data-ttu-id="77b9b-104">動的オブジェクトは、<xref:System.Dynamic> 名前空間で定義されている動的インターフェイスを使用して、プロパティやメソッドなどのメンバーを実行時に公開します。</span><span class="sxs-lookup"><span data-stu-id="77b9b-104">A dynamic object exposes members such as properties and methods at run time by using dynamic interfaces that are defined in the <xref:System.Dynamic> namespace.</span></span> <span data-ttu-id="77b9b-105"><xref:System.Dynamic> 名前空間のクラスを使用することで、静的な型や書式に一致しないデータ構造を操作するオブジェクトオブジェクトを作成できます。</span><span class="sxs-lookup"><span data-stu-id="77b9b-105">You can use the classes in the <xref:System.Dynamic> namespace to create objects that work with data structures that do not match a static type or format.</span></span> <span data-ttu-id="77b9b-106">また、IronPython や IronRuby などの動的言語で定義された動的オブジェクトを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="77b9b-106">You can also use the dynamic objects that are defined in dynamic languages such as IronPython and IronRuby.</span></span> <span data-ttu-id="77b9b-107">動的言語の作成方法の例、および動的言語で定義された動的オブジェクトの使用例については、[動的オブジェクトの作成と使用のチュートリアル](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)、<xref:System.Dynamic.DynamicObject>、または <xref:System.Dynamic.ExpandoObject> に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="77b9b-107">For examples that show how to create dynamic objects or use a dynamic object defined in a dynamic language, see [Walkthrough: Creating and Using Dynamic Objects](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md), <xref:System.Dynamic.DynamicObject>, or <xref:System.Dynamic.ExpandoObject>.</span></span>  
  
 <span data-ttu-id="77b9b-108">Visual Basic では、動的言語ランタイムおよび動的言語 (IronPython や IronRuby など) からオブジェクトへのバインドは、<xref:System.Dynamic.IDynamicMetaObjectProvider> インターフェイスを使用して行われます。</span><span class="sxs-lookup"><span data-stu-id="77b9b-108">Visual Basic binds to objects from the dynamic language runtime and dynamic languages such as IronPython and IronRuby by using the <xref:System.Dynamic.IDynamicMetaObjectProvider> interface.</span></span> <span data-ttu-id="77b9b-109">`IDynamicMetaObjectProvider` インターフェイスを実装したクラスの例としては、<xref:System.Dynamic.DynamicObject> や <xref:System.Dynamic.ExpandoObject> があります。</span><span class="sxs-lookup"><span data-stu-id="77b9b-109">Examples of classes that implement the `IDynamicMetaObjectProvider` interface are the <xref:System.Dynamic.DynamicObject> and <xref:System.Dynamic.ExpandoObject> classes.</span></span>  
  
 <span data-ttu-id="77b9b-110">`IDynamicMetaObjectProvider` インターフェイスを実装したオブジェクトに対して遅延バインディングによる呼び出しが行われると、Visual Basic はそのインターフェイスを使用して動的オブジェクトにバインドします。</span><span class="sxs-lookup"><span data-stu-id="77b9b-110">If a late-bound call is made to an object that implements the `IDynamicMetaObjectProvider` interface, Visual Basic binds to the dynamic object by using that interface.</span></span> <span data-ttu-id="77b9b-111">`IDynamicMetaObjectProvider` インターフェイスを実装していないオブジェクトに対して遅延バインディングによる呼び出しが行われた場合、または `IDynamicMetaObjectProvider` インターフェイスに対する呼び出しが失敗した場合は、Visual Basic は Visual Basic ランタイムの遅延バインディング機能を使用してオブジェクトにバインドします。</span><span class="sxs-lookup"><span data-stu-id="77b9b-111">If a late-bound call is made to an object that does not implement the `IDynamicMetaObjectProvider` interface, or if the call to the `IDynamicMetaObjectProvider` interface fails, Visual Basic binds to the object by using the late-binding capabilities of the Visual Basic runtime.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77b9b-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="77b9b-112">See also</span></span>

- <xref:System.Dynamic.DynamicObject>
- <xref:System.Dynamic.ExpandoObject>
- [<span data-ttu-id="77b9b-113">チュートリアル: 動的オブジェクトの作成と使用</span><span class="sxs-lookup"><span data-stu-id="77b9b-113">Walkthrough: Creating and Using Dynamic Objects</span></span>](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)
- [<span data-ttu-id="77b9b-114">事前バインディングと遅延バインディング</span><span class="sxs-lookup"><span data-stu-id="77b9b-114">Early and Late Binding</span></span>](index.md)
