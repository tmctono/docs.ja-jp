---
title: '方法: コレクション初期化子で使用される拡張メソッドを作成または追加する'
ms.date: 07/20/2015
helpviewer_keywords:
- collection initializers [Visual Basic]
ms.assetid: f64b52c7-8b11-4410-93a6-cb3aeebcc772
ms.openlocfilehash: 6d5f9d38b413b79f111a14ec3829c57a9797ce54
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346719"
---
# <a name="how-to-create-an-add-extension-method-used-by-a-collection-initializer-visual-basic"></a><span data-ttu-id="dfdeb-102">方法: コレクション初期化子で使用される拡張メソッドを作成または追加する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dfdeb-102">How to: Create an Add Extension Method Used by a Collection Initializer (Visual Basic)</span></span>
<span data-ttu-id="dfdeb-103">コレクション初期化子を使用してコレクションを作成すると、Visual Basic コンパイラは、`Add` メソッドのパラメーターがコレクション初期化子の値の型と一致するコレクション型の `Add` メソッドを検索します。</span><span class="sxs-lookup"><span data-stu-id="dfdeb-103">When you use a collection initializer to create a collection, the Visual Basic compiler searches for an `Add` method of the collection type for which the parameters for the `Add` method match the types of the values in the collection initializer.</span></span> <span data-ttu-id="dfdeb-104">この `Add` メソッドを使用して、コレクション初期化子の値をコレクションに設定します。</span><span class="sxs-lookup"><span data-stu-id="dfdeb-104">This `Add` method is used to populate the collection with the values from the collection initializer.</span></span>  
  
 <span data-ttu-id="dfdeb-105">一致する `Add` メソッドが存在せず、コレクションのコードを変更できない場合は、コレクション初期化子で必要なパラメーターを受け取る `Add` と呼ばれる拡張メソッドを追加できます。</span><span class="sxs-lookup"><span data-stu-id="dfdeb-105">If no matching `Add` method exists and you cannot modify the code for the collection, you can add an extension method called `Add` that takes the parameters that are required by the collection initializer.</span></span> <span data-ttu-id="dfdeb-106">これは通常、ジェネリックコレクションにコレクション初期化子を使用する場合に必要となります。</span><span class="sxs-lookup"><span data-stu-id="dfdeb-106">This is typically what you need to do when you use collection initializers for generic collections.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dfdeb-107">例</span><span class="sxs-lookup"><span data-stu-id="dfdeb-107">Example</span></span>  
 <span data-ttu-id="dfdeb-108">次の例では、コレクション初期化子を使用して `Employee`型のオブジェクトを追加できるように、ジェネリック <xref:System.Collections.Generic.List%601> 型に拡張メソッドを追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="dfdeb-108">The following example shows how to add an extension method to the generic <xref:System.Collections.Generic.List%601> type so that a collection initializer can be used to add objects of type `Employee`.</span></span> <span data-ttu-id="dfdeb-109">拡張メソッドを使用すると、簡略化されたコレクション初期化子の構文を使用できます。</span><span class="sxs-lookup"><span data-stu-id="dfdeb-109">The extension method enables you to use the shortened collection initializer syntax.</span></span>  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo1/VB/Module1.vb#1)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo1/VB/Module1.vb#2)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo1/VB/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="dfdeb-110">参照</span><span class="sxs-lookup"><span data-stu-id="dfdeb-110">See also</span></span>

- [<span data-ttu-id="dfdeb-111">コレクション初期化子</span><span class="sxs-lookup"><span data-stu-id="dfdeb-111">Collection Initializers</span></span>](../../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)
- [<span data-ttu-id="dfdeb-112">方法: コレクション初期化子を使用してコレクションを作成する</span><span class="sxs-lookup"><span data-stu-id="dfdeb-112">How to: Create a Collection Used by a Collection Initializer</span></span>](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-a-collection-used-by-a-collection-initializer.md)
