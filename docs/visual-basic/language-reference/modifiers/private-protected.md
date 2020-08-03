---
title: Private Protected
ms.date: 05/10/2018
f1_keywords:
- vb.PrivateProtected
helpviewer_keywords:
- Private Protected keyword [Visual Basic]
- Private Protected keyword [Visual Basic], syntax
ms.openlocfilehash: 8ad1509da71bc80b33700d363ddd4569a0965dff
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303466"
---
# <a name="private-protected-visual-basic"></a><span data-ttu-id="f89fa-102">Private Protected (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f89fa-102">Private Protected (Visual Basic)</span></span>

<span data-ttu-id="f89fa-103">キーワード組み合わせ `Private Protected` はメンバー アクセス修飾子です。</span><span class="sxs-lookup"><span data-stu-id="f89fa-103">The `Private Protected` keyword combination is a member access modifier.</span></span> <span data-ttu-id="f89fa-104">`Private Protected` メンバーは、その親クラスのすべてのメンバーと、親クラスから派生した型でアクセスできますが、それらがその親アセンブリにも存在する場合に限られます。</span><span class="sxs-lookup"><span data-stu-id="f89fa-104">A `Private Protected` member is accessible by all members in its containing class, as well as by types derived from the containing class, but only if they are found in its containing assembly.</span></span>

<span data-ttu-id="f89fa-105">`Private Protected` は、クラスのメンバーに対してのみ指定できます。構造体は継承できないため、構造体のメンバーに `Private Protected` を適用することはできません。</span><span class="sxs-lookup"><span data-stu-id="f89fa-105">You can specify `Private Protected` only on members of classes; you cannot apply `Private Protected` to members of a structure because structures cannot be inherited.</span></span>

<span data-ttu-id="f89fa-106">`Private Protected` アクセス修飾子は Visual Basic 15.5 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="f89fa-106">The `Private Protected` access modifier is supported by Visual Basic 15.5 and later.</span></span> <span data-ttu-id="f89fa-107">これを使用するには、次の要素を Visual Basic プロジェクト (\*.vbproj) ファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="f89fa-107">To use it, you can add the following element to your Visual Basic project (\*.vbproj) file.</span></span> <span data-ttu-id="f89fa-108">システムに Visual Basic 15.5 以降がインストールされている限り、Visual Basic コンパイラの最新バージョンでサポートされているすべての言語機能を利用できます。</span><span class="sxs-lookup"><span data-stu-id="f89fa-108">As long as Visual Basic 15.5 or later is installed on your system, it lets you take advantage of all the language features supported by the latest version of the Visual Basic compiler:</span></span>

```xml
<PropertyGroup>
   <LangVersion>latest</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="f89fa-109">詳細については、[Visual Basic 言語バージョンの設定](../configure-language-version.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f89fa-109">For more information see [setting the Visual Basic language version](../configure-language-version.md).</span></span>

> [!NOTE]
> <span data-ttu-id="f89fa-110">Visual Studio で、`private protected` に対して F1 ヘルプを選択すると、[private](private.md) または [protected](protected.md) のヘルプが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f89fa-110">In Visual Studio, selecting F1 help on `private protected` provides help for either [private](private.md) or [protected](protected.md).</span></span> <span data-ttu-id="f89fa-111">IDE では、複合語ではなくカーソルの下にある 1 つのトークンが選択されます。</span><span class="sxs-lookup"><span data-stu-id="f89fa-111">The IDE picks the single token under the cursor rather than the compound word.</span></span>

## <a name="rules"></a><span data-ttu-id="f89fa-112">ルール</span><span class="sxs-lookup"><span data-stu-id="f89fa-112">Rules</span></span>

- <span data-ttu-id="f89fa-113">**宣言コンテキスト。**</span><span class="sxs-lookup"><span data-stu-id="f89fa-113">**Declaration Context.**</span></span> <span data-ttu-id="f89fa-114">`Private Protected` は、クラス レベルでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="f89fa-114">You can use `Private Protected` only at the class level.</span></span> <span data-ttu-id="f89fa-115">つまり、`Protected` 要素の宣言コンテキストはクラスにする必要があり、ソース ファイル、名前空間、インターフェイス、モジュール、構造体、またはプロシージャにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="f89fa-115">This means the declaration context for a `Protected` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span></span>

## <a name="behavior"></a><span data-ttu-id="f89fa-116">動作</span><span class="sxs-lookup"><span data-stu-id="f89fa-116">Behavior</span></span>

- <span data-ttu-id="f89fa-117">**アクセス レベル。**</span><span class="sxs-lookup"><span data-stu-id="f89fa-117">**Access Level.**</span></span> <span data-ttu-id="f89fa-118">クラス内のすべてのコードで、その要素にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="f89fa-118">All code in a class can access its elements.</span></span> <span data-ttu-id="f89fa-119">基底クラスから派生し、同じアセンブリに含まれるすべてのクラスのコードで、基底クラスのすべての `Private Protected` 要素にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="f89fa-119">Code in any class that derives from a base class and is contained in the same assembly can access all the `Private Protected` elements of the base class.</span></span> <span data-ttu-id="f89fa-120">ただし、基底クラスから派生し、別のアセンブリに含まれるクラスのコードでは、基底クラスの `Private Protected` 要素にアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="f89fa-120">However, code in any class that derives from a base class and is contained in a different assembly can't access the base class `Private Protected` elements.</span></span>

- <span data-ttu-id="f89fa-121">**アクセス修飾子。**</span><span class="sxs-lookup"><span data-stu-id="f89fa-121">**Access Modifiers.**</span></span> <span data-ttu-id="f89fa-122">アクセス レベルを指定するキーワードは、*アクセス修飾子*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="f89fa-122">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="f89fa-123">アクセス修飾子の比較については、「[Visual Basic でのアクセス レベル](../../programming-guide/language-features/declared-elements/access-levels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f89fa-123">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span></span>

<span data-ttu-id="f89fa-124">`Private Protected` 修飾子は、次のコンテキストで使用できます。</span><span class="sxs-lookup"><span data-stu-id="f89fa-124">The `Private Protected` modifier can be used in these contexts:</span></span>

- <span data-ttu-id="f89fa-125">入れ子になったクラスの [Class ステートメント](../statements/class-statement.md)</span><span class="sxs-lookup"><span data-stu-id="f89fa-125">[Class Statement](../statements/class-statement.md) of a nested class</span></span>

- [<span data-ttu-id="f89fa-126">Const ステートメント</span><span class="sxs-lookup"><span data-stu-id="f89fa-126">Const Statement</span></span>](../statements/const-statement.md)

- [<span data-ttu-id="f89fa-127">Declare ステートメント</span><span class="sxs-lookup"><span data-stu-id="f89fa-127">Declare Statement</span></span>](../statements/declare-statement.md)

- <span data-ttu-id="f89fa-128">クラスに入れ子にされたデリゲートの [Delegate ステートメント](../statements/delegate-statement.md)</span><span class="sxs-lookup"><span data-stu-id="f89fa-128">[Delegate Statement](../statements/delegate-statement.md) of a delegate nested in a class</span></span>

- [<span data-ttu-id="f89fa-129">Dim ステートメント</span><span class="sxs-lookup"><span data-stu-id="f89fa-129">Dim Statement</span></span>](../statements/dim-statement.md)

- <span data-ttu-id="f89fa-130">クラスに入れ子にされた列挙型の [Enum ステートメント](../statements/enum-statement.md)</span><span class="sxs-lookup"><span data-stu-id="f89fa-130">[Enum Statement](../statements/enum-statement.md) of an enumeration nested in a class</span></span>

- [<span data-ttu-id="f89fa-131">Event ステートメント</span><span class="sxs-lookup"><span data-stu-id="f89fa-131">Event Statement</span></span>](../statements/event-statement.md)

- [<span data-ttu-id="f89fa-132">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="f89fa-132">Function Statement</span></span>](../statements/function-statement.md)

- <span data-ttu-id="f89fa-133">クラスに入れ子にされたインターフェイスの [Interface ステートメント](../statements/interface-statement.md)</span><span class="sxs-lookup"><span data-stu-id="f89fa-133">[Interface Statement](../statements/interface-statement.md) of an interface nested in a class</span></span>

- [<span data-ttu-id="f89fa-134">Property ステートメント</span><span class="sxs-lookup"><span data-stu-id="f89fa-134">Property Statement</span></span>](../statements/property-statement.md)

- <span data-ttu-id="f89fa-135">クラスに入れ子にされた構造体の[Structure ステートメント](../statements/structure-statement.md)</span><span class="sxs-lookup"><span data-stu-id="f89fa-135">[Structure Statement](../statements/structure-statement.md) of a structure nested in a class</span></span>

- [<span data-ttu-id="f89fa-136">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="f89fa-136">Sub Statement</span></span>](../statements/sub-statement.md)

## <a name="see-also"></a><span data-ttu-id="f89fa-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="f89fa-137">See also</span></span>

- [<span data-ttu-id="f89fa-138">Public</span><span class="sxs-lookup"><span data-stu-id="f89fa-138">Public</span></span>](public.md)
- [<span data-ttu-id="f89fa-139">Protected</span><span class="sxs-lookup"><span data-stu-id="f89fa-139">Protected</span></span>](protected.md)
- [<span data-ttu-id="f89fa-140">Friend</span><span class="sxs-lookup"><span data-stu-id="f89fa-140">Friend</span></span>](friend.md)
- [<span data-ttu-id="f89fa-141">Private</span><span class="sxs-lookup"><span data-stu-id="f89fa-141">Private</span></span>](private.md)
- [<span data-ttu-id="f89fa-142">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="f89fa-142">Protected Friend</span></span>](./protected-friend.md)
- [<span data-ttu-id="f89fa-143">Visual Basic でのアクセス レベル</span><span class="sxs-lookup"><span data-stu-id="f89fa-143">Access levels in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="f89fa-144">手順</span><span class="sxs-lookup"><span data-stu-id="f89fa-144">Procedures</span></span>](../../programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="f89fa-145">構造体</span><span class="sxs-lookup"><span data-stu-id="f89fa-145">Structures</span></span>](../../programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="f89fa-146">クラスとオブジェクト</span><span class="sxs-lookup"><span data-stu-id="f89fa-146">Objects and Classes</span></span>](../../programming-guide/language-features/objects-and-classes/index.md)
