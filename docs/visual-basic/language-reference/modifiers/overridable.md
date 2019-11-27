---
title: Overridable
ms.date: 07/20/2015
f1_keywords:
- Overridable
- vb.Overridable
helpviewer_keywords:
- elements [Visual Basic], concrete
- properties [Visual Basic], redefining
- overriding, Overridable keyword
- elements [Visual Basic], virtual
- virtual [elements VB]
- procedures [Visual Basic], overriding
- concrete [elements VB]
- procedures [Visual Basic], redefining
- Overridable keyword [Visual Basic]
- properties [Visual Basic], overriding
ms.assetid: 612581e7-8a4c-4a5d-beff-3402fffa6f35
ms.openlocfilehash: 9c639665fd92a56de6fb6e5147cda873ef457b45
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351398"
---
# <a name="overridable-visual-basic"></a><span data-ttu-id="e25a0-102">Overridable (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e25a0-102">Overridable (Visual Basic)</span></span>
<span data-ttu-id="e25a0-103">派生クラス内の同じ名前のプロパティまたはプロシージャによって、プロパティまたはプロシージャをオーバーライドできることを指定します。</span><span class="sxs-lookup"><span data-stu-id="e25a0-103">Specifies that a property or procedure can be overridden by an identically named property or procedure in a derived class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e25a0-104">コメント</span><span class="sxs-lookup"><span data-stu-id="e25a0-104">Remarks</span></span>  
 <span data-ttu-id="e25a0-105">`Overridable` 修飾子を使用すると、クラスのプロパティまたはメソッドを派生クラスでオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="e25a0-105">The `Overridable` modifier allows a property or method in a class to be overridden in a derived class.</span></span> <span data-ttu-id="e25a0-106">[NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)修飾子は、プロパティまたはメソッドが派生クラスでオーバーライドされないようにします。</span><span class="sxs-lookup"><span data-stu-id="e25a0-106">The [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md) modifier prevents a property or method from being overridden in a derived class.</span></span>  <span data-ttu-id="e25a0-107">詳細については、「[継承の基本](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e25a0-107">For more information, see [Inheritance Basics](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md).</span></span>  
  
 <span data-ttu-id="e25a0-108">`Overridable` または `NotOverridable` 修飾子が指定されていない場合、既定の設定は、プロパティまたはメソッドが基底クラスのプロパティまたはメソッドをオーバーライドするかどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="e25a0-108">If the `Overridable` or `NotOverridable` modifier is not specified, the default setting depends on whether the property or method overrides a base class property or method.</span></span> <span data-ttu-id="e25a0-109">プロパティまたはメソッドが基底クラスのプロパティまたはメソッドをオーバーライドする場合、既定の設定は `Overridable`になります。それ以外の場合は、`NotOverridable`ます。</span><span class="sxs-lookup"><span data-stu-id="e25a0-109">If the property or method overrides a base class property or method, the default setting is `Overridable`; otherwise, it is `NotOverridable`.</span></span>  
  
 <span data-ttu-id="e25a0-110">Shadow または override を使用して継承された要素を再定義できますが、この2つの方法には大きな違いがあります。</span><span class="sxs-lookup"><span data-stu-id="e25a0-110">You can shadow or override to redefine an inherited element, but there are significant differences between the two approaches.</span></span> <span data-ttu-id="e25a0-111">詳細については、「 [Visual Basic でのシャドウ](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e25a0-111">For more information, see [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span></span>  
  
 <span data-ttu-id="e25a0-112">オーバーライドできる要素は、*仮想*要素と呼ばれることもあります。</span><span class="sxs-lookup"><span data-stu-id="e25a0-112">An element that can be overridden is sometimes referred to as a *virtual* element.</span></span> <span data-ttu-id="e25a0-113">オーバーライドできるが、にする必要がない場合は、*具象*要素とも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="e25a0-113">If it can be overridden, but does not have to be, it is sometimes also called a *concrete* element.</span></span>  
  
 <span data-ttu-id="e25a0-114">`Overridable` は、プロパティまたはプロシージャの宣言ステートメントでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="e25a0-114">You can use `Overridable` only in a property or procedure declaration statement.</span></span>  
  
## <a name="combined-modifiers"></a><span data-ttu-id="e25a0-115">結合された修飾子</span><span class="sxs-lookup"><span data-stu-id="e25a0-115">Combined Modifiers</span></span>  
 <span data-ttu-id="e25a0-116">`Private` メソッドに `Overridable` または `NotOverridable` を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="e25a0-116">You cannot specify `Overridable` or `NotOverridable` for a `Private` method.</span></span>  
  
 <span data-ttu-id="e25a0-117">同じ宣言内で `MustOverride`、`NotOverridable`、または `Shared` と共に `Overridable` を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="e25a0-117">You cannot specify `Overridable` together with `MustOverride`, `NotOverridable`, or `Shared` in the same declaration.</span></span>  
  
 <span data-ttu-id="e25a0-118">オーバーライドする要素は暗黙的にオーバーライド可能であるため、`Overridable` と `Overrides` を結合することはできません。</span><span class="sxs-lookup"><span data-stu-id="e25a0-118">Because an overriding element is implicitly overridable, you cannot combine `Overridable` with `Overrides`.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="e25a0-119">使用法</span><span class="sxs-lookup"><span data-stu-id="e25a0-119">Usage</span></span>  
 <span data-ttu-id="e25a0-120">`Overridable` 修飾子は、次のコンテキストで使用できます。</span><span class="sxs-lookup"><span data-stu-id="e25a0-120">The `Overridable` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="e25a0-121">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="e25a0-121">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="e25a0-122">Property ステートメント</span><span class="sxs-lookup"><span data-stu-id="e25a0-122">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="e25a0-123">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="e25a0-123">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="e25a0-124">参照</span><span class="sxs-lookup"><span data-stu-id="e25a0-124">See also</span></span>

- [<span data-ttu-id="e25a0-125">修飾子</span><span class="sxs-lookup"><span data-stu-id="e25a0-125">Modifiers</span></span>](../../../visual-basic/language-reference/modifiers/index.md)
- [<span data-ttu-id="e25a0-126">継承の基本</span><span class="sxs-lookup"><span data-stu-id="e25a0-126">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [<span data-ttu-id="e25a0-127">MyBase</span><span class="sxs-lookup"><span data-stu-id="e25a0-127">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)
- [<span data-ttu-id="e25a0-128">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="e25a0-128">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)
- [<span data-ttu-id="e25a0-129">Overrides</span><span class="sxs-lookup"><span data-stu-id="e25a0-129">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)
- [<span data-ttu-id="e25a0-130">キーワード</span><span class="sxs-lookup"><span data-stu-id="e25a0-130">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="e25a0-131">Visual Basic でのシャドウ処理</span><span class="sxs-lookup"><span data-stu-id="e25a0-131">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
