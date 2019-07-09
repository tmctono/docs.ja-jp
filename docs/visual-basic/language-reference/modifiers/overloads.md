---
title: Overloads (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Overloads
- Overloads
helpviewer_keywords:
- Overloads keyword [Visual Basic]
- hiding by signature
- Shadows keyword [Visual Basic]
- signature, hiding by
ms.assetid: 0c6820b8-25b2-4664-bc59-5ca93c99c042
ms.openlocfilehash: 838207fe3ac5b8f57d030617546b9b7fa25dc939
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2019
ms.locfileid: "67663538"
---
# <a name="overloads-visual-basic"></a><span data-ttu-id="a475b-102">Overloads (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a475b-102">Overloads (Visual Basic)</span></span>

<span data-ttu-id="a475b-103">プロパティまたはプロシージャが、同じ名前の 1 つ以上の既存のプロパティまたはプロシージャを再度宣言することを示します。</span><span class="sxs-lookup"><span data-stu-id="a475b-103">Specifies that a property or procedure redeclares one or more existing properties or procedures with the same name.</span></span>

## <a name="remarks"></a><span data-ttu-id="a475b-104">Remarks</span><span class="sxs-lookup"><span data-stu-id="a475b-104">Remarks</span></span>

<span data-ttu-id="a475b-105">*オーバー ロード*は同じスコープ内で指定されたプロパティまたはプロシージャ名の 1 つ以上の定義を指定する方法です。</span><span class="sxs-lookup"><span data-stu-id="a475b-105">*Overloading* is the practice of supplying more than one definition for a given property or procedure name in the same scope.</span></span> <span data-ttu-id="a475b-106">プロパティまたは異なるシグネチャを持つプロシージャを再度宣言した場合とも呼ばれます*シグネチャによる隠ぺい*します。</span><span class="sxs-lookup"><span data-stu-id="a475b-106">Redeclaring a property or procedure with a different signature is sometimes called *hiding by signature*.</span></span>

## <a name="rules"></a><span data-ttu-id="a475b-107">ルール</span><span class="sxs-lookup"><span data-stu-id="a475b-107">Rules</span></span>

- <span data-ttu-id="a475b-108">**宣言コンテキスト。**</span><span class="sxs-lookup"><span data-stu-id="a475b-108">**Declaration Context.**</span></span> <span data-ttu-id="a475b-109">`Overloads` は、プロパティまたはプロシージャの宣言ステートメントでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="a475b-109">You can use `Overloads` only in a property or procedure declaration statement.</span></span>

- <span data-ttu-id="a475b-110">**結合された修飾子。**</span><span class="sxs-lookup"><span data-stu-id="a475b-110">**Combined Modifiers.**</span></span> <span data-ttu-id="a475b-111">指定することはできません`Overloads`と共に[Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)で同じプロシージャ宣言。</span><span class="sxs-lookup"><span data-stu-id="a475b-111">You cannot specify `Overloads` together with [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md) in the same procedure declaration.</span></span>

- <span data-ttu-id="a475b-112">**相違点が必要です。**</span><span class="sxs-lookup"><span data-stu-id="a475b-112">**Required Differences.**</span></span> <span data-ttu-id="a475b-113">*署名*この宣言内で異なる必要があるすべてのプロパティまたはプロシージャをオーバー ロードのシグネチャ。</span><span class="sxs-lookup"><span data-stu-id="a475b-113">The *signature* in this declaration must be different from the signature of every property or procedure that it overloads.</span></span> <span data-ttu-id="a475b-114">シグネチャは、プロパティまたはプロシージャの名前と以下の項目で構成されます。</span><span class="sxs-lookup"><span data-stu-id="a475b-114">The signature comprises the property or procedure name together with the following:</span></span>

  - <span data-ttu-id="a475b-115">パラメーターの数</span><span class="sxs-lookup"><span data-stu-id="a475b-115">the number of parameters</span></span>

  - <span data-ttu-id="a475b-116">パラメーターの順序</span><span class="sxs-lookup"><span data-stu-id="a475b-116">the order of the parameters</span></span>

  - <span data-ttu-id="a475b-117">パラメーターのデータ型</span><span class="sxs-lookup"><span data-stu-id="a475b-117">the data types of the parameters</span></span>

  - <span data-ttu-id="a475b-118">型パラメーターの数 (ジェネリック プロシージャの場合)</span><span class="sxs-lookup"><span data-stu-id="a475b-118">the number of type parameters (for a generic procedure)</span></span>

  - <span data-ttu-id="a475b-119">戻り値の型 (変換演算子プロシージャの場合のみ)</span><span class="sxs-lookup"><span data-stu-id="a475b-119">the return type (only for a conversion operator procedure)</span></span>

  <span data-ttu-id="a475b-120">すべてのオーバーロードを同じ名前にする必要はありますが、各オーバーロードは、前の項目の 1 つ以上において他のすべてのオーバーロードと異なっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a475b-120">All overloads must have the same name, but each must differ from all the others in one or more of the preceding respects.</span></span> <span data-ttu-id="a475b-121">これにより、コンパイラは、コードでプロパティまたはプロシージャが呼び出すときに使用するバージョンを区別できます。</span><span class="sxs-lookup"><span data-stu-id="a475b-121">This allows the compiler to distinguish which version to use when code calls the property or procedure.</span></span>

- <span data-ttu-id="a475b-122">**相違点が許可されていません。**</span><span class="sxs-lookup"><span data-stu-id="a475b-122">**Disallowed Differences.**</span></span> <span data-ttu-id="a475b-123">以下の項目はシグネチャに含まれないため、これらの項目の 1 つ以上を変更しても、プロパティまたはプロシージャのオーバーロードには有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="a475b-123">Changing one or more of the following is not valid for overloading a property or procedure, because they are not part of the signature:</span></span>

  - <span data-ttu-id="a475b-124">値を返すかどうか (プロシージャの場合)</span><span class="sxs-lookup"><span data-stu-id="a475b-124">whether or not it returns a value (for a procedure)</span></span>

  - <span data-ttu-id="a475b-125">戻り値のデータ型 (変換演算子を除く)</span><span class="sxs-lookup"><span data-stu-id="a475b-125">the data type of the return value (except for a conversion operator)</span></span>

  - <span data-ttu-id="a475b-126">パラメーターまたは型パラメーターの名前</span><span class="sxs-lookup"><span data-stu-id="a475b-126">the names of the parameters or type parameters</span></span>

  - <span data-ttu-id="a475b-127">型パラメーターに対する制約 (ジェネリック プロシージャの場合)</span><span class="sxs-lookup"><span data-stu-id="a475b-127">the constraints on the type parameters (for a generic procedure)</span></span>

  - <span data-ttu-id="a475b-128">パラメーター修飾子キーワード (`ByRef` や `Optional` など)</span><span class="sxs-lookup"><span data-stu-id="a475b-128">parameter modifier keywords (such as `ByRef` or `Optional`)</span></span>

  - <span data-ttu-id="a475b-129">プロパティまたはプロシージャ修飾子キーワード (`Public` や `Shared` など)</span><span class="sxs-lookup"><span data-stu-id="a475b-129">property or procedure modifier keywords (such as `Public` or `Shared`)</span></span>

- <span data-ttu-id="a475b-130">**オプションの修飾子。**</span><span class="sxs-lookup"><span data-stu-id="a475b-130">**Optional Modifier.**</span></span> <span data-ttu-id="a475b-131">同じクラス内でオーバーロードされるプロパティまたはプロシージャを複数定義する場合、`Overloads` 修飾子を使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="a475b-131">You do not have to use the `Overloads` modifier when you are defining multiple overloaded properties or procedures in the same class.</span></span> <span data-ttu-id="a475b-132">ただし、宣言の 1 つで `Overloads` を使用した場合は、すべての宣言で Overloads を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a475b-132">However, if you use `Overloads` in one of the declarations, you must use it in all of them.</span></span>

- <span data-ttu-id="a475b-133">**シャドウとオーバー ロードします。**</span><span class="sxs-lookup"><span data-stu-id="a475b-133">**Shadowing and Overloading.**</span></span> <span data-ttu-id="a475b-134">`Overloads` 既存のメンバーをシャドウしたり、基底クラスのオーバー ロードされたメンバーのセットも使用できます。</span><span class="sxs-lookup"><span data-stu-id="a475b-134">`Overloads` can also be used to shadow an existing member, or set of overloaded members, in a base class.</span></span> <span data-ttu-id="a475b-135">この方法で `Overloads` を使用する場合は、基底クラスのメンバーと同じ名前とパラメーター リストを使用してプロパティまたはメソッドを宣言し、`Shadows` キーワードは指定しません。</span><span class="sxs-lookup"><span data-stu-id="a475b-135">When you use `Overloads` in this way, you declare the property or method with the same name and the same parameter list as the base class member, and you do not supply the `Shadows` keyword.</span></span>

<span data-ttu-id="a475b-136">`Overrides` を使用する場合は、ライブラリ API と C# が連携しやすくなるように、コンパイラが暗黙的に `Overloads` を追加します。</span><span class="sxs-lookup"><span data-stu-id="a475b-136">If you use `Overrides`, the compiler implicitly adds `Overloads` so that your library APIs work with C# more easily.</span></span>

<span data-ttu-id="a475b-137">`Overloads` 修飾子は、次のコンテキストで使用できます。</span><span class="sxs-lookup"><span data-stu-id="a475b-137">The `Overloads` modifier can be used in these contexts:</span></span>

- [<span data-ttu-id="a475b-138">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="a475b-138">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)

- [<span data-ttu-id="a475b-139">Operator ステートメント</span><span class="sxs-lookup"><span data-stu-id="a475b-139">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)

- [<span data-ttu-id="a475b-140">Property ステートメント</span><span class="sxs-lookup"><span data-stu-id="a475b-140">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)

- [<span data-ttu-id="a475b-141">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="a475b-141">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)

## <a name="see-also"></a><span data-ttu-id="a475b-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="a475b-142">See also</span></span>

- [<span data-ttu-id="a475b-143">Shadows</span><span class="sxs-lookup"><span data-stu-id="a475b-143">Shadows</span></span>](../../../visual-basic/language-reference/modifiers/shadows.md)
- [<span data-ttu-id="a475b-144">プロシージャのオーバーロード</span><span class="sxs-lookup"><span data-stu-id="a475b-144">Procedure Overloading</span></span>](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)
- [<span data-ttu-id="a475b-145">Visual Basic におけるジェネリック型</span><span class="sxs-lookup"><span data-stu-id="a475b-145">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="a475b-146">演算子プロシージャ</span><span class="sxs-lookup"><span data-stu-id="a475b-146">Operator Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)
- [<span data-ttu-id="a475b-147">方法: 変換演算子を定義します。</span><span class="sxs-lookup"><span data-stu-id="a475b-147">How to: Define a Conversion Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
