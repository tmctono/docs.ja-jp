---
title: Private Protected (Visual Basic)
ms.date: 05/10/2018
helpviewer_keywords:
- Private Protected keyword [Visual Basic]
- Private Protected keyword [Visual Basic], syntax
ms.openlocfilehash: 265141f77f4a61a61414a07214830feaa8a1ab05
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351340"
---
# <a name="private-protected-visual-basic"></a><span data-ttu-id="34bb7-102">Private Protected (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="34bb7-102">Private Protected (Visual Basic)</span></span>

<span data-ttu-id="34bb7-103">キーワード組み合わせ `Private Protected` はメンバー アクセス修飾子です。</span><span class="sxs-lookup"><span data-stu-id="34bb7-103">The `Private Protected` keyword combination is a member access modifier.</span></span> <span data-ttu-id="34bb7-104">`Private Protected` メンバーは、それを含んでいるクラスのすべてのメンバーと、それを含むクラスから派生した型によってアクセスできますが、それを含んでいるアセンブリ内に存在する場合に限ります。</span><span class="sxs-lookup"><span data-stu-id="34bb7-104">A `Private Protected` member is accessible by all members in its containing class, as well as by types derived from the containing class, but only if they are found in its containing assembly.</span></span>

<span data-ttu-id="34bb7-105">`Private Protected` は、クラスのメンバーに対してのみ指定できます。構造体のメンバーに `Private Protected` を適用することはできません。構造体を継承することはできません。</span><span class="sxs-lookup"><span data-stu-id="34bb7-105">You can specify `Private Protected` only on members of classes; you cannot apply `Private Protected` to members of a structure because structures cannot be inherited.</span></span>

<span data-ttu-id="34bb7-106">`Private Protected` アクセス修飾子は Visual Basic 15.5 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="34bb7-106">The `Private Protected` access modifier is supported by Visual Basic 15.5 and later.</span></span> <span data-ttu-id="34bb7-107">これを使用するには、次の要素を Visual Basic プロジェクト (\*.vbproj) ファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="34bb7-107">To use it, you can add the following element to your Visual Basic project (\*.vbproj) file.</span></span> <span data-ttu-id="34bb7-108">システムに Visual Basic 15.5 以降がインストールされている限り、最新バージョンの Visual Basic コンパイラでサポートされているすべての言語機能を利用できます。</span><span class="sxs-lookup"><span data-stu-id="34bb7-108">As long as Visual Basic 15.5 or later is installed on your system, it lets you take advantage of all the language features supported by the latest version of the Visual Basic compiler:</span></span>

```xml
<PropertyGroup>
   <LangVersion>latest</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="34bb7-109">詳細については、「[Visual Basic 言語バージョンの設定](../../language-reference/configure-language-version.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="34bb7-109">For more information see [setting the Visual Basic language version](../../language-reference/configure-language-version.md).</span></span>

> [!NOTE]
> <span data-ttu-id="34bb7-110">Visual Studio で、`private protected` で F1 ヘルプを選択すると、 [private](private.md)または[protected](protected.md)のヘルプが表示されます。</span><span class="sxs-lookup"><span data-stu-id="34bb7-110">In Visual Studio, selecting F1 help on `private protected` provides help for either [private](private.md) or [protected](protected.md).</span></span> <span data-ttu-id="34bb7-111">IDE は、複合単語ではなくカーソルの下にある1つのトークンを選択します。</span><span class="sxs-lookup"><span data-stu-id="34bb7-111">The IDE picks the single token under the cursor rather than the compound word.</span></span>

## <a name="rules"></a><span data-ttu-id="34bb7-112">ルール</span><span class="sxs-lookup"><span data-stu-id="34bb7-112">Rules</span></span>

- <span data-ttu-id="34bb7-113">**宣言コンテキスト。**</span><span class="sxs-lookup"><span data-stu-id="34bb7-113">**Declaration Context.**</span></span> <span data-ttu-id="34bb7-114">`Private Protected` はクラスレベルでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="34bb7-114">You can use `Private Protected` only at the class level.</span></span> <span data-ttu-id="34bb7-115">つまり、`Protected` 要素の宣言コンテキストはクラスである必要があり、ソースファイル、名前空間、インターフェイス、モジュール、構造体、またはプロシージャにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="34bb7-115">This means the declaration context for a `Protected` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span></span>

## <a name="behavior"></a><span data-ttu-id="34bb7-116">動作</span><span class="sxs-lookup"><span data-stu-id="34bb7-116">Behavior</span></span>

- <span data-ttu-id="34bb7-117">**アクセスレベル。**</span><span class="sxs-lookup"><span data-stu-id="34bb7-117">**Access Level.**</span></span> <span data-ttu-id="34bb7-118">クラス内のすべてのコードは、その要素にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="34bb7-118">All code in a class can access its elements.</span></span> <span data-ttu-id="34bb7-119">基底クラスから派生し、同じアセンブリに含まれるクラスのコードは、基底クラスのすべての `Private Protected` 要素にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="34bb7-119">Code in any class that derives from a base class and is contained in the same assembly can access all the `Private Protected` elements of the base class.</span></span> <span data-ttu-id="34bb7-120">ただし、基底クラスから派生し、別のアセンブリに含まれているクラスのコードは、基底クラスの `Private Protected` 要素にアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="34bb7-120">However, code in any class that derives from a base class and is contained in a different assembly can't access the base class `Private Protected` elements.</span></span>

- <span data-ttu-id="34bb7-121">**アクセス修飾子。**</span><span class="sxs-lookup"><span data-stu-id="34bb7-121">**Access Modifiers.**</span></span> <span data-ttu-id="34bb7-122">アクセスレベルを指定するキーワードは、*アクセス修飾子*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="34bb7-122">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="34bb7-123">アクセス修飾子の比較については、「 [Visual Basic のアクセスレベル](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="34bb7-123">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>

<span data-ttu-id="34bb7-124">`Private Protected` 修飾子は、次のコンテキストで使用できます。</span><span class="sxs-lookup"><span data-stu-id="34bb7-124">The `Private Protected` modifier can be used in these contexts:</span></span>

- <span data-ttu-id="34bb7-125">入れ子になったクラスの[Class ステートメント](../../../visual-basic/language-reference/statements/class-statement.md)</span><span class="sxs-lookup"><span data-stu-id="34bb7-125">[Class Statement](../../../visual-basic/language-reference/statements/class-statement.md) of a nested class</span></span>

- [<span data-ttu-id="34bb7-126">Const ステートメント</span><span class="sxs-lookup"><span data-stu-id="34bb7-126">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)

- [<span data-ttu-id="34bb7-127">Declare ステートメント</span><span class="sxs-lookup"><span data-stu-id="34bb7-127">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)

- <span data-ttu-id="34bb7-128">クラスで入れ子にされたデリゲートの[Delegate ステートメント](../../../visual-basic/language-reference/statements/delegate-statement.md)</span><span class="sxs-lookup"><span data-stu-id="34bb7-128">[Delegate Statement](../../../visual-basic/language-reference/statements/delegate-statement.md) of a delegate nested in a class</span></span>

- [<span data-ttu-id="34bb7-129">Dim ステートメント</span><span class="sxs-lookup"><span data-stu-id="34bb7-129">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)

- <span data-ttu-id="34bb7-130">クラスに入れ子になっている列挙型の[Enum ステートメント](../../../visual-basic/language-reference/statements/enum-statement.md)</span><span class="sxs-lookup"><span data-stu-id="34bb7-130">[Enum Statement](../../../visual-basic/language-reference/statements/enum-statement.md) of an enumeration nested in a class</span></span>

- [<span data-ttu-id="34bb7-131">Event ステートメント</span><span class="sxs-lookup"><span data-stu-id="34bb7-131">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)

- [<span data-ttu-id="34bb7-132">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="34bb7-132">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)

- <span data-ttu-id="34bb7-133">クラスで入れ子にされたインターフェイスの[Interface ステートメント](../../../visual-basic/language-reference/statements/interface-statement.md)</span><span class="sxs-lookup"><span data-stu-id="34bb7-133">[Interface Statement](../../../visual-basic/language-reference/statements/interface-statement.md) of an interface nested in a class</span></span>

- [<span data-ttu-id="34bb7-134">Property ステートメント</span><span class="sxs-lookup"><span data-stu-id="34bb7-134">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)

- <span data-ttu-id="34bb7-135">クラスで入れ子になった構造体の[Structure ステートメント](../../../visual-basic/language-reference/statements/structure-statement.md)</span><span class="sxs-lookup"><span data-stu-id="34bb7-135">[Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md) of a structure nested in a class</span></span>

- [<span data-ttu-id="34bb7-136">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="34bb7-136">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)

## <a name="see-also"></a><span data-ttu-id="34bb7-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="34bb7-137">See also</span></span>

- [<span data-ttu-id="34bb7-138">Public</span><span class="sxs-lookup"><span data-stu-id="34bb7-138">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="34bb7-139">Protected</span><span class="sxs-lookup"><span data-stu-id="34bb7-139">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)
- [<span data-ttu-id="34bb7-140">Friend</span><span class="sxs-lookup"><span data-stu-id="34bb7-140">Friend</span></span>](friend.md)
- [<span data-ttu-id="34bb7-141">Private</span><span class="sxs-lookup"><span data-stu-id="34bb7-141">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
- [<span data-ttu-id="34bb7-142">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="34bb7-142">Protected Friend</span></span>](./protected-friend.md)
- [<span data-ttu-id="34bb7-143">Visual Basic のアクセスレベル</span><span class="sxs-lookup"><span data-stu-id="34bb7-143">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="34bb7-144">Visual Basic におけるプロシージャ</span><span class="sxs-lookup"><span data-stu-id="34bb7-144">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="34bb7-145">構造体</span><span class="sxs-lookup"><span data-stu-id="34bb7-145">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="34bb7-146">クラスとオブジェクト</span><span class="sxs-lookup"><span data-stu-id="34bb7-146">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
