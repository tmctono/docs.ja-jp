---
title: Default (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Default
helpviewer_keywords:
- defaults, properties
- properties [Visual Basic], default
- default properties, in Visual Basic
- Default keyword [Visual Basic]
- default properties
ms.assetid: 45fce9b9-d212-4b2d-ab86-6e359b8b57af
ms.openlocfilehash: f78ffe42a9d618d44da2a50c0de831396576430c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61800933"
---
# <a name="default-visual-basic"></a><span data-ttu-id="02c52-102">Default (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="02c52-102">Default (Visual Basic)</span></span>
<span data-ttu-id="02c52-103">クラス、構造体、またはインターフェイスの既定のプロパティとしてプロパティを識別します。</span><span class="sxs-lookup"><span data-stu-id="02c52-103">Identifies a property as the default property of its class, structure, or interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="02c52-104">Remarks</span><span class="sxs-lookup"><span data-stu-id="02c52-104">Remarks</span></span>  
 <span data-ttu-id="02c52-105">クラス、構造体、またはインターフェイスは多くて 1 つとしてのプロパティで指定できます、*プロパティの既定*、そのプロパティは、少なくとも 1 つのパラメーターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="02c52-105">A class, structure, or interface can designate at most one of its properties as the *default property*, provided that property takes at least one parameter.</span></span> <span data-ttu-id="02c52-106">コードでは、クラスまたは構造体への参照をメンバーを指定しなくても、Visual Basic は、既定のプロパティには、その参照を解決します。</span><span class="sxs-lookup"><span data-stu-id="02c52-106">If code makes a reference to a class or structure without specifying a member, Visual Basic resolves that reference to the default property.</span></span>  
  
 <span data-ttu-id="02c52-107">既定のプロパティは、ソース コードの文字のわずかな低下につながるが行えるように、コードが読みにくくします。</span><span class="sxs-lookup"><span data-stu-id="02c52-107">Default properties can result in a small reduction in source code-characters, but they can make your code more difficult to read.</span></span> <span data-ttu-id="02c52-108">クラスまたは構造体名への参照を行うときに、呼び出し元のコードがクラスまたは構造に習熟していない場合にすることはできません特定その参照が、クラスまたは構造体自体、または既定のプロパティにアクセスするかどうか。</span><span class="sxs-lookup"><span data-stu-id="02c52-108">If the calling code is not familiar with your class or structure, when it makes a reference to the class or structure name it cannot be certain whether that reference accesses the class or structure itself, or a default property.</span></span> <span data-ttu-id="02c52-109">これについては、コンパイラ エラーまたはランタイム ロジックの微妙なエラーにつながります。</span><span class="sxs-lookup"><span data-stu-id="02c52-109">This can lead to compiler errors or subtle run-time logic errors.</span></span>  
  
 <span data-ttu-id="02c52-110">常を使用して既定のプロパティのエラーの可能性を低くことができますやや、 [Option Strict ステートメント](../../../visual-basic/language-reference/statements/option-strict-statement.md)コンパイラ型チェックを設定する`On`します。</span><span class="sxs-lookup"><span data-stu-id="02c52-110">You can somewhat reduce the chance of default property errors by always using the [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md) to set compiler type checking to `On`.</span></span>  
  
 <span data-ttu-id="02c52-111">使用して、定義済みのクラスまたは構造体コードで判断する必要があります、既定のプロパティがあるかどうかであればしようとしている場合、名前は。</span><span class="sxs-lookup"><span data-stu-id="02c52-111">If you are planning to use a predefined class or structure in your code, you must determine whether it has a default property, and if so, what its name is.</span></span>  
  
 <span data-ttu-id="02c52-112">このような短所のためには、既定のプロパティを定義しないを検討してください。</span><span class="sxs-lookup"><span data-stu-id="02c52-112">Because of these disadvantages, you should consider not defining default properties.</span></span> <span data-ttu-id="02c52-113">コードを読みやすくは必要がありますも常に明示的に参照するすべてのプロパティを検討してくださいも既定のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="02c52-113">For code readability, you should also consider always referring to all properties explicitly, even default properties.</span></span>  
  
 <span data-ttu-id="02c52-114">`Default`修飾子は、このコンテキストで使用できます。</span><span class="sxs-lookup"><span data-stu-id="02c52-114">The `Default` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="02c52-115">Property ステートメント</span><span class="sxs-lookup"><span data-stu-id="02c52-115">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="02c52-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="02c52-116">See also</span></span>

- [<span data-ttu-id="02c52-117">方法: 宣言し、Visual Basic では、既定のプロパティを呼び出す</span><span class="sxs-lookup"><span data-stu-id="02c52-117">How to: Declare and Call a Default Property in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md)
- [<span data-ttu-id="02c52-118">キーワード</span><span class="sxs-lookup"><span data-stu-id="02c52-118">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
