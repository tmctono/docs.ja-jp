---
title: '方法: コレクション初期化子によって使用されるコレクションを作成する'
ms.date: 07/20/2015
helpviewer_keywords:
- collection initializers [Visual Basic]
ms.assetid: c858db10-424d-47e0-92cd-e08087cc5ebc
ms.openlocfilehash: b332ffb44ebc20ce8431e586fc380b8c6a29967d
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "91086375"
---
# <a name="how-to-create-a-collection-used-by-a-collection-initializer-visual-basic"></a><span data-ttu-id="47b2e-102">方法: コレクション初期化子を使用してコレクションを作成する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="47b2e-102">How to: Create a Collection Used by a Collection Initializer (Visual Basic)</span></span>

<span data-ttu-id="47b2e-103">コレクション初期化子を使用してコレクションを作成すると、`Add` メソッドのパラメーターがコレクション初期化子の値の型と一致するコレクション型の `Add` メソッドが、Visual Basic コンパイラによって検索されます。</span><span class="sxs-lookup"><span data-stu-id="47b2e-103">When you use a collection initializer to create a collection, the Visual Basic compiler searches for an `Add` method of the collection type for which the parameters for the `Add` method match the types of the values in the collection initializer.</span></span> <span data-ttu-id="47b2e-104">この `Add` メソッドは、コレクションに、コレクション初期化子の値を設定するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="47b2e-104">This `Add` method is used to populate the collection with the values from the collection initializer.</span></span>  
  
## <a name="example"></a><span data-ttu-id="47b2e-105">例</span><span class="sxs-lookup"><span data-stu-id="47b2e-105">Example</span></span>  

 <span data-ttu-id="47b2e-106">次の例が示す `OrderCollection` コレクションにはパブリック `Add` メソッドが含まれています。このメソッドは、コレクション初期化子が `Order` 型のオブジェクトを追加するときに使用できます。</span><span class="sxs-lookup"><span data-stu-id="47b2e-106">The following example shows an `OrderCollection` collection that contains a public `Add` method that a collection initializer can use to add objects of type `Order`.</span></span> <span data-ttu-id="47b2e-107">`Add` メソッドを使用すると、短縮されたコレクション初期化子構文を使用できます。</span><span class="sxs-lookup"><span data-stu-id="47b2e-107">The `Add` method enables you to use the shortened collection initializer syntax.</span></span>  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2/VB/Module1.vb#4)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2/VB/Module1.vb#1)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2/VB/Module1.vb#2)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2/VB/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="47b2e-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="47b2e-108">See also</span></span>

- [<span data-ttu-id="47b2e-109">コレクション初期化子</span><span class="sxs-lookup"><span data-stu-id="47b2e-109">Collection Initializers</span></span>](index.md)
- [<span data-ttu-id="47b2e-110">方法: コレクション初期化子によって使用される Add 拡張メソッドを作成する</span><span class="sxs-lookup"><span data-stu-id="47b2e-110">How to: Create an Add Extension Method Used by a Collection Initializer</span></span>](how-to-create-an-add-extension-method-used-by-a-collection-initializer.md)
