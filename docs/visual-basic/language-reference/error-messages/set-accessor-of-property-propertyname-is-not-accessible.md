---
title: プロパティ '<propertyname>' の 'Set' アクセサーにアクセスできません。
ms.date: 07/20/2015
f1_keywords:
- vbc31102
- bc31102
helpviewer_keywords:
- BC31102
ms.assetid: 6f7b31b7-3656-4ae1-8851-90f5f4c6950a
ms.openlocfilehash: cf0158692c1154a8a903c893ba287e51c1e34ac8
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64593272"
---
# <a name="set-accessor-of-property-propertyname-is-not-accessible"></a><span data-ttu-id="e8140-102">プロパティ '\<propertyname>' の 'Set' アクセサーにアクセスできません</span><span class="sxs-lookup"><span data-stu-id="e8140-102">'Set' accessor of property '\<propertyname>' is not accessible</span></span>
<span data-ttu-id="e8140-103">ステートメントは、プロパティの `Set` プロシージャにアクセスできない場合、プロパティの値を格納しようとします。</span><span class="sxs-lookup"><span data-stu-id="e8140-103">A statement attempts to store the value of a property when it does not have access to the property's `Set` procedure.</span></span>  
  
 <span data-ttu-id="e8140-104">[Set ステートメント](../../../visual-basic/language-reference/statements/set-statement.md)がその [Property ステートメント](../../../visual-basic/language-reference/statements/property-statement.md)よりも制限の厳しいアクセス レベルでマークされている場合は、プロパティ値を設定しようとすると、次のような場合は失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e8140-104">If the [Set Statement](../../../visual-basic/language-reference/statements/set-statement.md) is marked with a more restrictive access level than its [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md), an attempt to set the property value could fail in the following cases:</span></span>  
  
- <span data-ttu-id="e8140-105">`Set` ステートメントが [Private](../../../visual-basic/language-reference/modifiers/private.md) とマークされていて、呼び出し元のコードが、プロパティが定義されているクラスまたは構造体の外側にある。</span><span class="sxs-lookup"><span data-stu-id="e8140-105">The `Set` statement is marked [Private](../../../visual-basic/language-reference/modifiers/private.md) and the calling code is outside the class or structure in which the property is defined.</span></span>  
  
- <span data-ttu-id="e8140-106">`Set` ステートメントが [Protected](../../../visual-basic/language-reference/modifiers/protected.md) とマークされていて、呼び出し元のコードが、プロパティが定義されているクラスまたは構造体内にも、派生クラス内にもない。</span><span class="sxs-lookup"><span data-stu-id="e8140-106">The `Set` statement is marked [Protected](../../../visual-basic/language-reference/modifiers/protected.md) and the calling code is not in the class or structure in which the property is defined, nor in a derived class.</span></span>  
  
- <span data-ttu-id="e8140-107">`Set` ステートメントが [Friend](../../../visual-basic/language-reference/modifiers/friend.md) とマークされていて、呼び出し元のコードが、プロパティが定義されているアセンブリと同じアセンブリ内にない。</span><span class="sxs-lookup"><span data-stu-id="e8140-107">The `Set` statement is marked [Friend](../../../visual-basic/language-reference/modifiers/friend.md) and the calling code is not in the same assembly in which the property is defined.</span></span>  
  
 <span data-ttu-id="e8140-108">**エラー ID:** BC31102</span><span class="sxs-lookup"><span data-stu-id="e8140-108">**Error ID:** BC31102</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e8140-109">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="e8140-109">To correct this error</span></span>  
  
- <span data-ttu-id="e8140-110">プロパティを定義するソース コードを制御できる場合は、プロパティ自体と同じアクセス レベルで `Set` プロシージャを宣言することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="e8140-110">If you have control of the source code defining the property, consider declaring the `Set` procedure with the same access level as the property itself.</span></span>  
  
- <span data-ttu-id="e8140-111">プロパティを定義するソース コードを制御できない場合、またはプロパティ自体よりも `Set` プロシージャのアクセス レベルを制限する必要がある場合は、プロパティ値を設定するステートメントを、プロパティによりアクセスしやすいコードの領域に移動してみてください。</span><span class="sxs-lookup"><span data-stu-id="e8140-111">If you do not have control of the source code defining the property, or you must restrict the `Set` procedure access level more than the property itself, try to move the statement that sets the property value to a region of code that has better access to the property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8140-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="e8140-112">See also</span></span>

- [<span data-ttu-id="e8140-113">Property プロシージャ</span><span class="sxs-lookup"><span data-stu-id="e8140-113">Property Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)
- [<span data-ttu-id="e8140-114">方法: 複数のアクセス レベルを持つプロパティを宣言する</span><span class="sxs-lookup"><span data-stu-id="e8140-114">How to: Declare a Property with Mixed Access Levels</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)
