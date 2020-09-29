---
title: New
ms.date: 07/20/2015
f1_keywords:
- vb.MustOverride
- MustOverride
helpviewer_keywords:
- virtual elements [Visual Basic], pure
- elements [Visual Basic], pure virtual
- properties [Visual Basic], redefining
- procedures [Visual Basic], overriding
- overriding, MustOverride keyword
- procedures [Visual Basic], redefining
- pure virtual elements [Visual Basic]
- MustOverride keyword [Visual Basic]
- properties [Visual Basic], overriding
ms.assetid: 6e9d9ad6-bb64-433f-b32b-3ef84293bf96
ms.openlocfilehash: cf73f07b6e13d524281129e3c5d8dceceb90764c
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867943"
---
# <a name="mustoverride-visual-basic"></a><span data-ttu-id="b7f7a-102">MustOverride (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b7f7a-102">MustOverride (Visual Basic)</span></span>

<span data-ttu-id="b7f7a-103">プロパティやプロシージャがこのクラスで実装されておらず、派生クラスでオーバーライドされないと使用できないことを示します。</span><span class="sxs-lookup"><span data-stu-id="b7f7a-103">Specifies that a property or procedure is not implemented in this class and must be overridden in a derived class before it can be used.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b7f7a-104">Remarks</span><span class="sxs-lookup"><span data-stu-id="b7f7a-104">Remarks</span></span>  

 <span data-ttu-id="b7f7a-105">`MustOverride` は、プロパティまたはプロシージャの宣言ステートメントでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="b7f7a-105">You can use `MustOverride` only in a property or procedure declaration statement.</span></span> <span data-ttu-id="b7f7a-106">`MustOverride` を指定するプロパティまたはプロシージャはクラスのメンバーである必要があり、クラスは [MustInherit](mustinherit.md) としてマークする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b7f7a-106">The property or procedure that specifies `MustOverride` must be a member of a class, and the class must be marked [MustInherit](mustinherit.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="b7f7a-107">ルール</span><span class="sxs-lookup"><span data-stu-id="b7f7a-107">Rules</span></span>  
  
- <span data-ttu-id="b7f7a-108">**不完全な宣言。**</span><span class="sxs-lookup"><span data-stu-id="b7f7a-108">**Incomplete Declaration.**</span></span> <span data-ttu-id="b7f7a-109">`MustOverride` を指定する場合、`End Function`、`End Property`、または `End Sub` ステートメントでも、プロパティまたはプロシージャに追加のコード行を指定しません。</span><span class="sxs-lookup"><span data-stu-id="b7f7a-109">When you specify `MustOverride`, you do not supply any additional lines of code for the property or procedure, not even the `End Function`, `End Property`, or `End Sub` statement.</span></span>  
  
- <span data-ttu-id="b7f7a-110">**結合された修飾子。**</span><span class="sxs-lookup"><span data-stu-id="b7f7a-110">**Combined Modifiers.**</span></span> <span data-ttu-id="b7f7a-111">同じ宣言内で `MustOverride` を `NotOverridable`、`Overridable`、または `Shared` と共に指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="b7f7a-111">You cannot specify `MustOverride` together with `NotOverridable`, `Overridable`, or `Shared` in the same declaration.</span></span>  
  
- <span data-ttu-id="b7f7a-112">**シャドウとオーバーライド。**</span><span class="sxs-lookup"><span data-stu-id="b7f7a-112">**Shadowing and Overriding.**</span></span> <span data-ttu-id="b7f7a-113">シャドウとオーバーライドは、どちらも継承された要素を再定義しますが、その方法は大きく異なります。</span><span class="sxs-lookup"><span data-stu-id="b7f7a-113">Both shadowing and overriding redefine an inherited element, but there are significant differences between the two approaches.</span></span> <span data-ttu-id="b7f7a-114">詳細については、「[Visual Basic におけるシャドウ](../../programming-guide/language-features/declared-elements/shadowing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b7f7a-114">For more information, see [Shadowing in Visual Basic](../../programming-guide/language-features/declared-elements/shadowing.md).</span></span>  
  
- <span data-ttu-id="b7f7a-115">**代替用語。**</span><span class="sxs-lookup"><span data-stu-id="b7f7a-115">**Alternate Terms.**</span></span> <span data-ttu-id="b7f7a-116">オーバーライド以外で使用できない要素は、*純粋仮想*要素と呼ばれることもあります。</span><span class="sxs-lookup"><span data-stu-id="b7f7a-116">An element that cannot be used except in an override is sometimes called a *pure virtual* element.</span></span>  
  
 <span data-ttu-id="b7f7a-117">`MustOverride` 修飾子は、次のコンテキストで使用できます。</span><span class="sxs-lookup"><span data-stu-id="b7f7a-117">The `MustOverride` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="b7f7a-118">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="b7f7a-118">Function Statement</span></span>](../statements/function-statement.md)  
  
 [<span data-ttu-id="b7f7a-119">Property ステートメント</span><span class="sxs-lookup"><span data-stu-id="b7f7a-119">Property Statement</span></span>](../statements/property-statement.md)  
  
 [<span data-ttu-id="b7f7a-120">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="b7f7a-120">Sub Statement</span></span>](../statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="b7f7a-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="b7f7a-121">See also</span></span>

- [<span data-ttu-id="b7f7a-122">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="b7f7a-122">NotOverridable</span></span>](notoverridable.md)
- [<span data-ttu-id="b7f7a-123">Overridable</span><span class="sxs-lookup"><span data-stu-id="b7f7a-123">Overridable</span></span>](overridable.md)
- [<span data-ttu-id="b7f7a-124">Overrides</span><span class="sxs-lookup"><span data-stu-id="b7f7a-124">Overrides</span></span>](overrides.md)
- [<span data-ttu-id="b7f7a-125">MustInherit</span><span class="sxs-lookup"><span data-stu-id="b7f7a-125">MustInherit</span></span>](mustinherit.md)
- [<span data-ttu-id="b7f7a-126">キーワード</span><span class="sxs-lookup"><span data-stu-id="b7f7a-126">Keywords</span></span>](../keywords/index.md)
- [<span data-ttu-id="b7f7a-127">Visual Basic におけるシャドウ</span><span class="sxs-lookup"><span data-stu-id="b7f7a-127">Shadowing in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/shadowing.md)
