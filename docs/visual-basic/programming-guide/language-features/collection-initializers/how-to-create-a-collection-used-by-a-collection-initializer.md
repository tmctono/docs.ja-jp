---
title: '方法: コレクション初期化子を使用してコレクションを作成する'
ms.date: 07/20/2015
helpviewer_keywords:
- collection initializers [Visual Basic]
ms.assetid: c858db10-424d-47e0-92cd-e08087cc5ebc
ms.openlocfilehash: 5eaf9e828455bf2accda86ab52a1ce645f10b9ee
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349061"
---
# <a name="how-to-create-a-collection-used-by-a-collection-initializer-visual-basic"></a><span data-ttu-id="e2328-102">方法: コレクション初期化子を使用してコレクションを作成する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e2328-102">How to: Create a Collection Used by a Collection Initializer (Visual Basic)</span></span>
<span data-ttu-id="e2328-103">コレクション初期化子を使用してコレクションを作成すると、Visual Basic コンパイラは、`Add` メソッドのパラメーターがコレクション初期化子の値の型と一致するコレクション型の `Add` メソッドを検索します。</span><span class="sxs-lookup"><span data-stu-id="e2328-103">When you use a collection initializer to create a collection, the Visual Basic compiler searches for an `Add` method of the collection type for which the parameters for the `Add` method match the types of the values in the collection initializer.</span></span> <span data-ttu-id="e2328-104">この `Add` メソッドを使用して、コレクション初期化子の値をコレクションに設定します。</span><span class="sxs-lookup"><span data-stu-id="e2328-104">This `Add` method is used to populate the collection with the values from the collection initializer.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e2328-105">例</span><span class="sxs-lookup"><span data-stu-id="e2328-105">Example</span></span>  
 <span data-ttu-id="e2328-106">次の例は、コレクション初期化子が `Order`型のオブジェクトを追加するために使用できるパブリック `Add` メソッドを含む `OrderCollection` コレクションを示しています。</span><span class="sxs-lookup"><span data-stu-id="e2328-106">The following example shows an `OrderCollection` collection that contains a public `Add` method that a collection initializer can use to add objects of type `Order`.</span></span> <span data-ttu-id="e2328-107">`Add` メソッドを使用すると、簡略化されたコレクション初期化子の構文を使用できます。</span><span class="sxs-lookup"><span data-stu-id="e2328-107">The `Add` method enables you to use the shortened collection initializer syntax.</span></span>  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2/VB/Module1.vb#4)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2/VB/Module1.vb#1)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2/VB/Module1.vb#2)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2/VB/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="e2328-108">参照</span><span class="sxs-lookup"><span data-stu-id="e2328-108">See also</span></span>

- [<span data-ttu-id="e2328-109">コレクション初期化子</span><span class="sxs-lookup"><span data-stu-id="e2328-109">Collection Initializers</span></span>](../../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)
- [<span data-ttu-id="e2328-110">方法: コレクション初期化子で使用される拡張メソッドを作成または追加する</span><span class="sxs-lookup"><span data-stu-id="e2328-110">How to: Create an Add Extension Method Used by a Collection Initializer</span></span>](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-an-add-extension-method-used-by-a-collection-initializer.md)
