---
title: Private Protected (Visual Basic)
ms.date: 05/10/2018
helpviewer_keywords:
- Private Protected keyword [Visual Basic]
- Private Protected keyword [Visual Basic], syntax
ms.openlocfilehash: fea43558ac0fe8181f2786b69f2621346d446b2e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61920498"
---
# <a name="private-protected-visual-basic"></a><span data-ttu-id="22feb-102">Private Protected (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="22feb-102">Private Protected (Visual Basic)</span></span>

<span data-ttu-id="22feb-103">キーワード組み合わせ `Private Protected` はメンバー アクセス修飾子です。</span><span class="sxs-lookup"><span data-stu-id="22feb-103">The `Private Protected` keyword combination is a member access modifier.</span></span> <span data-ttu-id="22feb-104">A`Private Protected`メンバーがアクセスできるは、外側のクラスから派生した型と、含まれるクラスのすべてのメンバーによっては、含んでいるアセンブリが見つかった場合にのみです。</span><span class="sxs-lookup"><span data-stu-id="22feb-104">A `Private Protected` member is accessible by all members in its containing class, as well as by types derived from the containing class, but only if they are found in its containing assembly.</span></span>

<span data-ttu-id="22feb-105">指定できます`Private Protected`クラスのメンバーにのみ適用することはできません`Private Protected`構造体のメンバーに構造体は継承できないためです。</span><span class="sxs-lookup"><span data-stu-id="22feb-105">You can specify `Private Protected` only on members of classes; you cannot apply `Private Protected` to members of a structure because structures cannot be inherited.</span></span>

<span data-ttu-id="22feb-106">`Private Protected`アクセス修飾子は Visual Basic 15.5 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="22feb-106">The `Private Protected` access modifier is supported by Visual Basic 15.5 and later.</span></span> <span data-ttu-id="22feb-107">これを使用する Visual Basic プロジェクトに次の要素を追加することができます (\*.vbproj) ファイル。</span><span class="sxs-lookup"><span data-stu-id="22feb-107">To use it, you can add the following element to your Visual Basic project (\*.vbproj) file.</span></span> <span data-ttu-id="22feb-108">Visual Basic 15.5 いる限り、またはそれ以降は、システムにインストールされているが、最新バージョンの Visual Basic コンパイラでサポートされているすべての言語機能を活用することができます。</span><span class="sxs-lookup"><span data-stu-id="22feb-108">As long as Visual Basic 15.5 or later is installed on your system, it lets you take advantage of all the language features supported by the latest version of the Visual Basic compiler:</span></span>

```xml
<PropertyGroup>
   <LangVersion>latest</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="22feb-109">詳細については、次を参照してください。 [Visual Basic の言語バージョンを設定](../../language-reference/configure-language-version.md)します。</span><span class="sxs-lookup"><span data-stu-id="22feb-109">For more information see [setting the Visual Basic language version](../../language-reference/configure-language-version.md).</span></span>

> [!NOTE]
> <span data-ttu-id="22feb-110">Visual Studio での F1 ヘルプを選択する`private protected`のいずれかのヘルプを提供します。[プライベート](private.md)または[保護](protected.md)します。</span><span class="sxs-lookup"><span data-stu-id="22feb-110">In Visual Studio, selecting F1 help on `private protected` provides help for either [private](private.md) or [protected](protected.md).</span></span> <span data-ttu-id="22feb-111">IDE では、複合語ではなく、カーソルの下の 1 つのトークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="22feb-111">The IDE picks the single token under the cursor rather than the compound word.</span></span>

## <a name="rules"></a><span data-ttu-id="22feb-112">ルール</span><span class="sxs-lookup"><span data-stu-id="22feb-112">Rules</span></span>

- <span data-ttu-id="22feb-113">**宣言コンテキスト。**</span><span class="sxs-lookup"><span data-stu-id="22feb-113">**Declaration Context.**</span></span> <span data-ttu-id="22feb-114">使用することができます`Private Protected`クラス レベルでのみです。</span><span class="sxs-lookup"><span data-stu-id="22feb-114">You can use `Private Protected` only at the class level.</span></span> <span data-ttu-id="22feb-115">これは、意味の宣言のコンテキストを`Protected`要素は、クラスでなければなりませんし、ソース ファイル、名前空間、インターフェイス、モジュール、構造体、またはプロシージャにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="22feb-115">This means the declaration context for a `Protected` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span></span>

## <a name="behavior"></a><span data-ttu-id="22feb-116">動作</span><span class="sxs-lookup"><span data-stu-id="22feb-116">Behavior</span></span>

- <span data-ttu-id="22feb-117">**アクセス レベルです。**</span><span class="sxs-lookup"><span data-stu-id="22feb-117">**Access Level.**</span></span> <span data-ttu-id="22feb-118">クラスのすべてのコードは、その要素にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="22feb-118">All code in a class can access its elements.</span></span> <span data-ttu-id="22feb-119">基本クラスから派生し、同じアセンブリに含まれているすべてのクラスでコードがすべてにアクセスできる、`Private Protected`基底クラスの要素。</span><span class="sxs-lookup"><span data-stu-id="22feb-119">Code in any class that derives from a base class and is contained in the same assembly can access all the `Private Protected` elements of the base class.</span></span> <span data-ttu-id="22feb-120">基本クラスを基底クラスから派生し、別のアセンブリに含まれているすべてのクラスでのコードでアクセスできませんただし、`Private Protected`要素。</span><span class="sxs-lookup"><span data-stu-id="22feb-120">However, code in any class that derives from a base class and is contained in a different assembly can't access the base class `Private Protected` elements.</span></span>

- <span data-ttu-id="22feb-121">**アクセス修飾子。**</span><span class="sxs-lookup"><span data-stu-id="22feb-121">**Access Modifiers.**</span></span> <span data-ttu-id="22feb-122">アクセス レベルを指定するキーワードが呼び出される*アクセス修飾子*します。</span><span class="sxs-lookup"><span data-stu-id="22feb-122">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="22feb-123">アクセス修飾子の比較は、次を参照してください。[アクセス レベルを Visual Basic で](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)します。</span><span class="sxs-lookup"><span data-stu-id="22feb-123">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>

<span data-ttu-id="22feb-124">`Private Protected` 修飾子は、次のコンテキストで使用できます。</span><span class="sxs-lookup"><span data-stu-id="22feb-124">The `Private Protected` modifier can be used in these contexts:</span></span>

- <span data-ttu-id="22feb-125">[Class ステートメント](../../../visual-basic/language-reference/statements/class-statement.md)の入れ子になったクラス</span><span class="sxs-lookup"><span data-stu-id="22feb-125">[Class Statement](../../../visual-basic/language-reference/statements/class-statement.md) of a nested class</span></span>

- [<span data-ttu-id="22feb-126">Const ステートメント</span><span class="sxs-lookup"><span data-stu-id="22feb-126">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)

- [<span data-ttu-id="22feb-127">Declare ステートメント</span><span class="sxs-lookup"><span data-stu-id="22feb-127">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)

- <span data-ttu-id="22feb-128">[Delegate ステートメント](../../../visual-basic/language-reference/statements/delegate-statement.md)デリゲートのクラスで入れ子になった</span><span class="sxs-lookup"><span data-stu-id="22feb-128">[Delegate Statement](../../../visual-basic/language-reference/statements/delegate-statement.md) of a delegate nested in a class</span></span>

- [<span data-ttu-id="22feb-129">Dim ステートメント</span><span class="sxs-lookup"><span data-stu-id="22feb-129">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)

- <span data-ttu-id="22feb-130">[Enum ステートメント](../../../visual-basic/language-reference/statements/enum-statement.md)列挙型のクラスで入れ子になった</span><span class="sxs-lookup"><span data-stu-id="22feb-130">[Enum Statement](../../../visual-basic/language-reference/statements/enum-statement.md) of an enumeration nested in a class</span></span>

- [<span data-ttu-id="22feb-131">Event ステートメント</span><span class="sxs-lookup"><span data-stu-id="22feb-131">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)

- [<span data-ttu-id="22feb-132">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="22feb-132">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)

- <span data-ttu-id="22feb-133">[Interface ステートメント](../../../visual-basic/language-reference/statements/interface-statement.md)インターフェイスのクラスで入れ子になった</span><span class="sxs-lookup"><span data-stu-id="22feb-133">[Interface Statement](../../../visual-basic/language-reference/statements/interface-statement.md) of an interface nested in a class</span></span>

- [<span data-ttu-id="22feb-134">Property ステートメント</span><span class="sxs-lookup"><span data-stu-id="22feb-134">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)

- <span data-ttu-id="22feb-135">[ステートメントの構造体](../../../visual-basic/language-reference/statements/structure-statement.md)クラスで入れ子になった構造体</span><span class="sxs-lookup"><span data-stu-id="22feb-135">[Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md) of a structure nested in a class</span></span>

- [<span data-ttu-id="22feb-136">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="22feb-136">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)

## <a name="see-also"></a><span data-ttu-id="22feb-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="22feb-137">See also</span></span>

- [<span data-ttu-id="22feb-138">Public</span><span class="sxs-lookup"><span data-stu-id="22feb-138">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="22feb-139">Protected</span><span class="sxs-lookup"><span data-stu-id="22feb-139">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)
- [<span data-ttu-id="22feb-140">Friend</span><span class="sxs-lookup"><span data-stu-id="22feb-140">Friend</span></span>](friend.md)
- [<span data-ttu-id="22feb-141">Private</span><span class="sxs-lookup"><span data-stu-id="22feb-141">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
- [<span data-ttu-id="22feb-142">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="22feb-142">Protected Friend</span></span>](./protected-friend.md)
- [<span data-ttu-id="22feb-143">Visual Basic でのアクセス レベル</span><span class="sxs-lookup"><span data-stu-id="22feb-143">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="22feb-144">プロシージャ</span><span class="sxs-lookup"><span data-stu-id="22feb-144">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="22feb-145">構造体</span><span class="sxs-lookup"><span data-stu-id="22feb-145">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="22feb-146">クラスとオブジェクト</span><span class="sxs-lookup"><span data-stu-id="22feb-146">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
