---
title: '方法: 作成、コレクション初期化子 (Visual Basic) によって使用される拡張メソッドを追加'
ms.date: 07/20/2015
helpviewer_keywords:
- collection initializers [Visual Basic]
ms.assetid: f64b52c7-8b11-4410-93a6-cb3aeebcc772
ms.openlocfilehash: a5af41e25b8f82aa173e2df28cc41b313c8d68dd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61907076"
---
# <a name="how-to-create-an-add-extension-method-used-by-a-collection-initializer-visual-basic"></a><span data-ttu-id="1bff0-102">方法: 作成、コレクション初期化子 (Visual Basic) によって使用される拡張メソッドを追加</span><span class="sxs-lookup"><span data-stu-id="1bff0-102">How to: Create an Add Extension Method Used by a Collection Initializer (Visual Basic)</span></span>
<span data-ttu-id="1bff0-103">コレクション初期化子を使用してコレクションを作成するときに、Visual Basic コンパイラ検索、`Add`対象のコレクション型のメソッドのパラメーター、`Add`メソッド コレクション初期化子の値の型に一致します。</span><span class="sxs-lookup"><span data-stu-id="1bff0-103">When you use a collection initializer to create a collection, the Visual Basic compiler searches for an `Add` method of the collection type for which the parameters for the `Add` method match the types of the values in the collection initializer.</span></span> <span data-ttu-id="1bff0-104">これは、`Add`メソッドを使用して、コレクション、コレクション初期化子の値に設定します。</span><span class="sxs-lookup"><span data-stu-id="1bff0-104">This `Add` method is used to populate the collection with the values from the collection initializer.</span></span>  
  
 <span data-ttu-id="1bff0-105">一致する場合`Add`メソッドが存在して、コレクションのコードを変更することはできません、という拡張メソッドを追加する`Add`コレクション初期化子に必要なパラメータを受け取る。</span><span class="sxs-lookup"><span data-stu-id="1bff0-105">If no matching `Add` method exists and you cannot modify the code for the collection, you can add an extension method called `Add` that takes the parameters that are required by the collection initializer.</span></span> <span data-ttu-id="1bff0-106">ジェネリック コレクションに対するコレクション初期化子を使用している場合に行う必要がありますこれは通常です。</span><span class="sxs-lookup"><span data-stu-id="1bff0-106">This is typically what you need to do when you use collection initializers for generic collections.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1bff0-107">例</span><span class="sxs-lookup"><span data-stu-id="1bff0-107">Example</span></span>  
 <span data-ttu-id="1bff0-108">次の例は、ジェネリック拡張メソッドを追加する方法を示します<xref:System.Collections.Generic.List%601>コレクション初期化子を使用して、型のオブジェクトを追加することになるよう入力`Employee`します。</span><span class="sxs-lookup"><span data-stu-id="1bff0-108">The following example shows how to add an extension method to the generic <xref:System.Collections.Generic.List%601> type so that a collection initializer can be used to add objects of type `Employee`.</span></span> <span data-ttu-id="1bff0-109">拡張メソッドでは、簡略化されたコレクションの初期化子構文を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="1bff0-109">The extension method enables you to use the shortened collection initializer syntax.</span></span>  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo1/VB/Module1.vb#1)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo1/VB/Module1.vb#2)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo1/VB/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="1bff0-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="1bff0-110">See also</span></span>

- [<span data-ttu-id="1bff0-111">コレクション初期化子</span><span class="sxs-lookup"><span data-stu-id="1bff0-111">Collection Initializers</span></span>](../../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)
- [<span data-ttu-id="1bff0-112">方法: コレクション初期化子を使用してコレクションを作成します。</span><span class="sxs-lookup"><span data-stu-id="1bff0-112">How to: Create a Collection Used by a Collection Initializer</span></span>](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-a-collection-used-by-a-collection-initializer.md)
