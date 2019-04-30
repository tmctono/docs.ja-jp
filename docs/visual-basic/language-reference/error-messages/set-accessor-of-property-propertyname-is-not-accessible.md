---
title: プロパティ '<propertyname>' の 'Set' アクセサーにアクセスできません。
ms.date: 07/20/2015
f1_keywords:
- vbc31102
- bc31102
helpviewer_keywords:
- BC31102
ms.assetid: 6f7b31b7-3656-4ae1-8851-90f5f4c6950a
ms.openlocfilehash: 3bc50d6762998ca5d8f445d84c8b698c9f46436f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62055148"
---
# <a name="set-accessor-of-property-propertyname-is-not-accessible"></a><span data-ttu-id="13e44-102">'Set' アクセサー プロパティの '\<propertyname >' にアクセスできません</span><span class="sxs-lookup"><span data-stu-id="13e44-102">'Set' accessor of property '\<propertyname>' is not accessible</span></span>
<span data-ttu-id="13e44-103">ステートメントが、プロパティへのアクセスがあるないときに、プロパティの値を格納しようとしています。`Set`プロシージャ。</span><span class="sxs-lookup"><span data-stu-id="13e44-103">A statement attempts to store the value of a property when it does not have access to the property's `Set` procedure.</span></span>  
  
 <span data-ttu-id="13e44-104">場合、 [Set ステートメント](../../../visual-basic/language-reference/statements/set-statement.md)レベルよりもより制限の厳しいアクセスでマークされたその[Property ステートメント](../../../visual-basic/language-reference/statements/property-statement.md)プロパティ値を設定しようとするが失敗する、次の場合。</span><span class="sxs-lookup"><span data-stu-id="13e44-104">If the [Set Statement](../../../visual-basic/language-reference/statements/set-statement.md) is marked with a more restrictive access level than its [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md), an attempt to set the property value could fail in the following cases:</span></span>  
  
- <span data-ttu-id="13e44-105">`Set`ステートメントがマークされている[プライベート](../../../visual-basic/language-reference/modifiers/private.md)呼び出し元のコードとそれには、クラスまたは構造体のプロパティが定義されているとします。</span><span class="sxs-lookup"><span data-stu-id="13e44-105">The `Set` statement is marked [Private](../../../visual-basic/language-reference/modifiers/private.md) and the calling code is outside the class or structure in which the property is defined.</span></span>  
  
- <span data-ttu-id="13e44-106">`Set`ステートメントがマークされている[Protected](../../../visual-basic/language-reference/modifiers/protected.md)呼び出し元のコードは、クラスまたはプロパティが定義されている構造体ではなく、派生クラスでも。</span><span class="sxs-lookup"><span data-stu-id="13e44-106">The `Set` statement is marked [Protected](../../../visual-basic/language-reference/modifiers/protected.md) and the calling code is not in the class or structure in which the property is defined, nor in a derived class.</span></span>  
  
- <span data-ttu-id="13e44-107">`Set`ステートメントがマークされている[フレンド](../../../visual-basic/language-reference/modifiers/friend.md)プロパティが定義されている同じアセンブリに呼び出し元のコードがないとします。</span><span class="sxs-lookup"><span data-stu-id="13e44-107">The `Set` statement is marked [Friend](../../../visual-basic/language-reference/modifiers/friend.md) and the calling code is not in the same assembly in which the property is defined.</span></span>  
  
 <span data-ttu-id="13e44-108">**エラー ID:** BC31102</span><span class="sxs-lookup"><span data-stu-id="13e44-108">**Error ID:** BC31102</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="13e44-109">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="13e44-109">To correct this error</span></span>  
  
- <span data-ttu-id="13e44-110">コントロールのプロパティを定義するソース コードを使っている場合を宣言することを検討してください、`Set`プロパティ自体と同じアクセス レベルを持つプロシージャ。</span><span class="sxs-lookup"><span data-stu-id="13e44-110">If you have control of the source code defining the property, consider declaring the `Set` procedure with the same access level as the property itself.</span></span>  
  
- <span data-ttu-id="13e44-111">場合は、プロパティを定義するソース コードがないか、または制限する必要があります、`Set`プロパティ自体にアクセスするより優れたコードの領域にプロパティ値を設定するステートメントに移動しようとする複数のプロシージャ アクセス レベル、プロパティ。</span><span class="sxs-lookup"><span data-stu-id="13e44-111">If you do not have control of the source code defining the property, or you must restrict the `Set` procedure access level more than the property itself, try to move the statement that sets the property value to a region of code that has better access to the property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13e44-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="13e44-112">See also</span></span>

- [<span data-ttu-id="13e44-113">Property プロシージャ</span><span class="sxs-lookup"><span data-stu-id="13e44-113">Property Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)
- [<span data-ttu-id="13e44-114">方法: 混合アクセス レベルを持つプロパティを宣言します。</span><span class="sxs-lookup"><span data-stu-id="13e44-114">How to: Declare a Property with Mixed Access Levels</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)
