---
title: MyBase
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
ms.openlocfilehash: dc6a153a604fd0e5cee9d7d46ebcd63294f33628
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351492"
---
# <a name="mustoverride-visual-basic"></a><span data-ttu-id="dad1d-102">MustOverride (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dad1d-102">MustOverride (Visual Basic)</span></span>
<span data-ttu-id="dad1d-103">プロパティまたはプロシージャがこのクラスで実装されておらず、派生クラスでオーバーライドされてから使用できるようにする必要があることを指定します。</span><span class="sxs-lookup"><span data-stu-id="dad1d-103">Specifies that a property or procedure is not implemented in this class and must be overridden in a derived class before it can be used.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dad1d-104">コメント</span><span class="sxs-lookup"><span data-stu-id="dad1d-104">Remarks</span></span>  
 <span data-ttu-id="dad1d-105">`MustOverride` は、プロパティまたはプロシージャの宣言ステートメントでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="dad1d-105">You can use `MustOverride` only in a property or procedure declaration statement.</span></span> <span data-ttu-id="dad1d-106">`MustOverride` を指定するプロパティまたはプロシージャは、クラスのメンバーである必要があります。また、クラスは[MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md)に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dad1d-106">The property or procedure that specifies `MustOverride` must be a member of a class, and the class must be marked [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="dad1d-107">ルール</span><span class="sxs-lookup"><span data-stu-id="dad1d-107">Rules</span></span>  
  
- <span data-ttu-id="dad1d-108">**不完全な宣言です。**</span><span class="sxs-lookup"><span data-stu-id="dad1d-108">**Incomplete Declaration.**</span></span> <span data-ttu-id="dad1d-109">`MustOverride`を指定すると、`End Function`、`End Property`、または `End Sub` ステートメントではなく、プロパティまたはプロシージャに追加のコード行を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="dad1d-109">When you specify `MustOverride`, you do not supply any additional lines of code for the property or procedure, not even the `End Function`, `End Property`, or `End Sub` statement.</span></span>  
  
- <span data-ttu-id="dad1d-110">**結合された修飾子。**</span><span class="sxs-lookup"><span data-stu-id="dad1d-110">**Combined Modifiers.**</span></span> <span data-ttu-id="dad1d-111">同じ宣言内で `NotOverridable`、`Overridable`、または `Shared` と共に `MustOverride` を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="dad1d-111">You cannot specify `MustOverride` together with `NotOverridable`, `Overridable`, or `Shared` in the same declaration.</span></span>  
  
- <span data-ttu-id="dad1d-112">**シャドウとオーバーライド。**</span><span class="sxs-lookup"><span data-stu-id="dad1d-112">**Shadowing and Overriding.**</span></span> <span data-ttu-id="dad1d-113">シャドウとオーバーライドは、どちらも継承された要素を再定義しますが、その方法は大きく異なります。</span><span class="sxs-lookup"><span data-stu-id="dad1d-113">Both shadowing and overriding redefine an inherited element, but there are significant differences between the two approaches.</span></span> <span data-ttu-id="dad1d-114">詳細については、「 [Visual Basic でのシャドウ](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dad1d-114">For more information, see [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span></span>  
  
- <span data-ttu-id="dad1d-115">**代替語句。**</span><span class="sxs-lookup"><span data-stu-id="dad1d-115">**Alternate Terms.**</span></span> <span data-ttu-id="dad1d-116">オーバーライドでは使用できない要素は、*純粋仮想*要素と呼ばれることもあります。</span><span class="sxs-lookup"><span data-stu-id="dad1d-116">An element that cannot be used except in an override is sometimes called a *pure virtual* element.</span></span>  
  
 <span data-ttu-id="dad1d-117">`MustOverride` 修飾子は、次のコンテキストで使用できます。</span><span class="sxs-lookup"><span data-stu-id="dad1d-117">The `MustOverride` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="dad1d-118">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="dad1d-118">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="dad1d-119">Property ステートメント</span><span class="sxs-lookup"><span data-stu-id="dad1d-119">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="dad1d-120">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="dad1d-120">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="dad1d-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="dad1d-121">See also</span></span>

- [<span data-ttu-id="dad1d-122">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="dad1d-122">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)
- [<span data-ttu-id="dad1d-123">Overridable</span><span class="sxs-lookup"><span data-stu-id="dad1d-123">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)
- [<span data-ttu-id="dad1d-124">Overrides</span><span class="sxs-lookup"><span data-stu-id="dad1d-124">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)
- [<span data-ttu-id="dad1d-125">MustInherit</span><span class="sxs-lookup"><span data-stu-id="dad1d-125">MustInherit</span></span>](../../../visual-basic/language-reference/modifiers/mustinherit.md)
- [<span data-ttu-id="dad1d-126">キーワード</span><span class="sxs-lookup"><span data-stu-id="dad1d-126">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="dad1d-127">Visual Basic でのシャドウ処理</span><span class="sxs-lookup"><span data-stu-id="dad1d-127">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
