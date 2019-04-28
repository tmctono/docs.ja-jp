---
title: NotOverridable (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.NotOverridable
- NotOverridable
helpviewer_keywords:
- sealed methods [Visual Basic]
- NotOverridable keyword [Visual Basic]
- properties [Visual Basic], redefining
- elements [Visual Basic], sealed
- sealed [elements VB]
- procedures [Visual Basic], overriding
- procedures [Visual Basic], redefining
- overriding
- methods [Visual Basic], sealed
- properties [Visual Basic], overriding
ms.assetid: 66ec6984-f5f5-4857-b362-6a3907aaf9e0
ms.openlocfilehash: 41c08a48fdb7501081e887fb5cf9f99c334c72ac
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61920654"
---
# <a name="notoverridable-visual-basic"></a><span data-ttu-id="bbccb-102">NotOverridable (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bbccb-102">NotOverridable (Visual Basic)</span></span>
<span data-ttu-id="bbccb-103">プロパティまたはプロシージャを派生クラスでオーバーライドできないことを指定します。</span><span class="sxs-lookup"><span data-stu-id="bbccb-103">Specifies that a property or procedure cannot be overridden in a derived class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bbccb-104">Remarks</span><span class="sxs-lookup"><span data-stu-id="bbccb-104">Remarks</span></span>  
 <span data-ttu-id="bbccb-105">`NotOverridable`修飾子が、プロパティまたはメソッドを派生クラスでオーバーライドされるを防ぎます。</span><span class="sxs-lookup"><span data-stu-id="bbccb-105">The `NotOverridable` modifier prevents a property or method from being overridden in a derived class.</span></span>  <span data-ttu-id="bbccb-106">[Overridable](../../../visual-basic/language-reference/modifiers/overridable.md)修飾子は派生クラスでオーバーライドするクラスでプロパティまたはメソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="bbccb-106">The [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md) modifier allows a property or method in a class to be overridden in a derived class.</span></span> <span data-ttu-id="bbccb-107">詳細については、「[継承の基本](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bbccb-107">For more information, see [Inheritance Basics](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md).</span></span>  
  
 <span data-ttu-id="bbccb-108">場合、`Overridable`または`NotOverridable`修飾子が指定されていない、既定の設定は、プロパティまたはメソッドが基底クラスのプロパティまたはメソッドをオーバーライドするかどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="bbccb-108">If the `Overridable` or `NotOverridable` modifier is not specified, the default setting depends on whether the property or method overrides a base class property or method.</span></span> <span data-ttu-id="bbccb-109">プロパティまたはメソッドは、基底クラスのプロパティまたはメソッドをオーバーライドする場合、既定値は`Overridable`。 それ以外は`NotOverridable`します。</span><span class="sxs-lookup"><span data-stu-id="bbccb-109">If the property or method overrides a base class property or method, the default setting is `Overridable`; otherwise, it is `NotOverridable`.</span></span>  
  
 <span data-ttu-id="bbccb-110">要素をオーバーライドすることはできませんとも呼ばれます、*シール*要素。</span><span class="sxs-lookup"><span data-stu-id="bbccb-110">An element that cannot be overridden is sometimes called a *sealed* element.</span></span>  
  
 <span data-ttu-id="bbccb-111">`NotOverridable` は、プロパティまたはプロシージャの宣言ステートメントでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="bbccb-111">You can use `NotOverridable` only in a property or procedure declaration statement.</span></span> <span data-ttu-id="bbccb-112">指定できる`NotOverridable`プロパティまたはとの組み合わせでのみ、つまり、別のプロパティまたはプロシージャをオーバーライドするプロシージャでのみ`Overrides`します。</span><span class="sxs-lookup"><span data-stu-id="bbccb-112">You can specify `NotOverridable` only on a property or procedure that overrides another property or procedure, that is, only in combination with `Overrides`.</span></span>  
  
## <a name="combined-modifiers"></a><span data-ttu-id="bbccb-113">修飾子の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="bbccb-113">Combined Modifiers</span></span>  
 <span data-ttu-id="bbccb-114">指定することはできません`Overridable`または`NotOverridable`の`Private`メソッド。</span><span class="sxs-lookup"><span data-stu-id="bbccb-114">You cannot specify `Overridable` or `NotOverridable` for a `Private` method.</span></span>  
  
 <span data-ttu-id="bbccb-115">指定することはできません`NotOverridable`と共に`MustOverride`、 `Overridable`、または`Shared`同じ宣言内。</span><span class="sxs-lookup"><span data-stu-id="bbccb-115">You cannot specify `NotOverridable` together with `MustOverride`, `Overridable`, or `Shared` in the same declaration.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="bbccb-116">使用法</span><span class="sxs-lookup"><span data-stu-id="bbccb-116">Usage</span></span>  
 <span data-ttu-id="bbccb-117">`NotOverridable` 修飾子は、次のコンテキストで使用できます。</span><span class="sxs-lookup"><span data-stu-id="bbccb-117">The `NotOverridable` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="bbccb-118">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="bbccb-118">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="bbccb-119">Property ステートメント</span><span class="sxs-lookup"><span data-stu-id="bbccb-119">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="bbccb-120">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="bbccb-120">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="bbccb-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="bbccb-121">See also</span></span>

- [<span data-ttu-id="bbccb-122">修飾子</span><span class="sxs-lookup"><span data-stu-id="bbccb-122">Modifiers</span></span>](../../../visual-basic/language-reference/modifiers/index.md)
- [<span data-ttu-id="bbccb-123">継承の基本</span><span class="sxs-lookup"><span data-stu-id="bbccb-123">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [<span data-ttu-id="bbccb-124">MustOverride</span><span class="sxs-lookup"><span data-stu-id="bbccb-124">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)
- [<span data-ttu-id="bbccb-125">Overridable</span><span class="sxs-lookup"><span data-stu-id="bbccb-125">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)
- [<span data-ttu-id="bbccb-126">Overrides</span><span class="sxs-lookup"><span data-stu-id="bbccb-126">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)
- [<span data-ttu-id="bbccb-127">キーワード</span><span class="sxs-lookup"><span data-stu-id="bbccb-127">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="bbccb-128">Visual Basic におけるシャドウ</span><span class="sxs-lookup"><span data-stu-id="bbccb-128">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
