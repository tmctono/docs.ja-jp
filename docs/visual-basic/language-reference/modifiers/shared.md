---
title: Shared
ms.date: 07/20/2015
f1_keywords:
- vb.Shared
helpviewer_keywords:
- Shared keyword [Visual Basic]
- members [Visual Basic], shared
- shared members
- nonshared
- shared [elements VB]
- elements [Visual Basic], shared
ms.assetid: 2bf7cf2c-b0dd-485e-8749-b5d674dab4cd
ms.openlocfilehash: 000cc13bc6e80914e9a21b6ee60e91127809ee08
ms.sourcegitcommit: 5280b2aef60a1ed99002dba44e4b9e7f6c830604
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/03/2020
ms.locfileid: "84307086"
---
# <a name="shared-visual-basic"></a><span data-ttu-id="f3b40-102">Shared (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f3b40-102">Shared (Visual Basic)</span></span>

<span data-ttu-id="f3b40-103">1 つ以上の宣言されたプログラミング要素が、クラスまたは構造体の特定のインスタンスではなく、クラスまたは構造体全体に関連付けられることを指定します。</span><span class="sxs-lookup"><span data-stu-id="f3b40-103">Specifies that one or more declared programming elements are associated with a class or structure at large, and not with a specific instance of the class or structure.</span></span>

## <a name="when-to-use-shared"></a><span data-ttu-id="f3b40-104">Shared を使用する場面</span><span class="sxs-lookup"><span data-stu-id="f3b40-104">When to Use Shared</span></span>

<span data-ttu-id="f3b40-105">クラスまたは構造体のメンバーを共有すると、各インスタンスが独自のコピーを維持する*非共有*とは異なり、すべてのインスタンスでそれを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="f3b40-105">Sharing a member of a class or structure makes it available to every instance, rather than *non-shared*, where each instance keeps its own copy.</span></span> <span data-ttu-id="f3b40-106">これは、変数の値をアプリケーション全体に適用する場合などに便利です。</span><span class="sxs-lookup"><span data-stu-id="f3b40-106">This is useful, for example, if the value of a variable applies to the entire application.</span></span> <span data-ttu-id="f3b40-107">この変数を `Shared` として宣言すると、すべてのインスタンスが同じストレージの場所にアクセスするため、1 つのインスタンスで変数の値が変更されると、すべてのインスタンスが更新された値にアクセスするようになります。</span><span class="sxs-lookup"><span data-stu-id="f3b40-107">If you declare that variable to be `Shared`, then all instances access the same storage location, and if one instance changes the variable's value, all instances access the updated value.</span></span>

<span data-ttu-id="f3b40-108">共有によってメンバーのアクセス レベルが変更されることはありません。</span><span class="sxs-lookup"><span data-stu-id="f3b40-108">Sharing does not alter the access level of a member.</span></span> <span data-ttu-id="f3b40-109">たとえば、クラス メンバーには、共有とプライベート (クラス内からのみアクセス可能)、または非共有とパブリックを指定できます。</span><span class="sxs-lookup"><span data-stu-id="f3b40-109">For example, a class member can be shared and private (accessible only from within the class), or non-shared and public.</span></span> <span data-ttu-id="f3b40-110">詳しくは、「[Visual Basic でのアクセス レベル](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3b40-110">For more information, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>

## <a name="rules"></a><span data-ttu-id="f3b40-111">ルール</span><span class="sxs-lookup"><span data-stu-id="f3b40-111">Rules</span></span>

- <span data-ttu-id="f3b40-112">**宣言コンテキスト。**</span><span class="sxs-lookup"><span data-stu-id="f3b40-112">**Declaration Context.**</span></span> <span data-ttu-id="f3b40-113">`Shared` は、モジュール レベルでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="f3b40-113">You can use `Shared` only at module level.</span></span> <span data-ttu-id="f3b40-114">つまり、`Shared` 要素の宣言コンテキストは、クラスまたは構造体にする必要があり、ソース ファイル、名前空間、プロシージャにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="f3b40-114">This means the declaration context for a `Shared` element must be a class or structure, and cannot be a source file, namespace, or procedure.</span></span>

- <span data-ttu-id="f3b40-115">**結合された修飾子。**</span><span class="sxs-lookup"><span data-stu-id="f3b40-115">**Combined Modifiers.**</span></span> <span data-ttu-id="f3b40-116">`Shared` は、同じ宣言内で、[Overrides](../../../visual-basic/language-reference/modifiers/overrides.md)、[Overridable](../../../visual-basic/language-reference/modifiers/overridable.md)、[NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)、[MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)、または [Static](../../../visual-basic/language-reference/modifiers/static.md) と一緒に指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="f3b40-116">You cannot specify `Shared` together with [Overrides](../../../visual-basic/language-reference/modifiers/overrides.md), [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md), [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md), [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md), or [Static](../../../visual-basic/language-reference/modifiers/static.md) in the same declaration.</span></span>

- <span data-ttu-id="f3b40-117">**アクセス。**</span><span class="sxs-lookup"><span data-stu-id="f3b40-117">**Accessing.**</span></span> <span data-ttu-id="f3b40-118">共有要素にアクセスするには、そのクラスまたは構造体の特定のインスタンスの変数名ではなく、そのクラスまたは構造体の名前で修飾します。</span><span class="sxs-lookup"><span data-stu-id="f3b40-118">You access a shared element by qualifying it with its class or structure name, not with the variable name of a specific instance of its class or structure.</span></span> <span data-ttu-id="f3b40-119">その共有メンバーにアクセスするために、クラスまたは構造体のインスタンスを作成する必要もありません。</span><span class="sxs-lookup"><span data-stu-id="f3b40-119">You do not even have to create an instance of a class or structure to access its shared members.</span></span>

     <span data-ttu-id="f3b40-120">次の例では、<xref:System.Double> 構造体によって公開された <xref:System.Double.IsNaN%2A> 共有プロシージャを呼び出しています。</span><span class="sxs-lookup"><span data-stu-id="f3b40-120">The following example calls the shared procedure <xref:System.Double.IsNaN%2A> exposed by the <xref:System.Double> structure.</span></span>

     ```vb
     If Double.IsNaN(result) Then Console.WriteLine("Result is mathematically undefined.")
     ```

- <span data-ttu-id="f3b40-121">**暗黙的共有。**</span><span class="sxs-lookup"><span data-stu-id="f3b40-121">**Implicit Sharing.**</span></span> <span data-ttu-id="f3b40-122">[Const ステートメント](../../../visual-basic/language-reference/statements/const-statement.md)では `Shared` 修飾子を使用できませんが、定数は暗黙的に共有されます。</span><span class="sxs-lookup"><span data-stu-id="f3b40-122">You cannot use the `Shared` modifier in a [Const Statement](../../../visual-basic/language-reference/statements/const-statement.md), but constants are implicitly shared.</span></span> <span data-ttu-id="f3b40-123">同様に、モジュールまたはインターフェイスのメンバーを `Shared` として宣言できませんが、それらは暗黙的に共有されます。</span><span class="sxs-lookup"><span data-stu-id="f3b40-123">Similarly, you cannot declare a member of a module or an interface to be `Shared`, but they are implicitly shared.</span></span>

## <a name="behavior"></a><span data-ttu-id="f3b40-124">動作</span><span class="sxs-lookup"><span data-stu-id="f3b40-124">Behavior</span></span>

- <span data-ttu-id="f3b40-125">**ストレージ。**</span><span class="sxs-lookup"><span data-stu-id="f3b40-125">**Storage.**</span></span> <span data-ttu-id="f3b40-126">共有変数またはイベントは、そのクラスまたは構造体の、作成するインスタンスの数に関係なく、メモリに 1 回だけ格納されます。</span><span class="sxs-lookup"><span data-stu-id="f3b40-126">A shared variable or event is stored in memory only once, no matter how many or few instances you create of its class or structure.</span></span> <span data-ttu-id="f3b40-127">同様に、共有プロシージャまたはプロパティは、ローカル変数のセットを 1 つだけ保持します。</span><span class="sxs-lookup"><span data-stu-id="f3b40-127">Similarly, a shared procedure or property holds only one set of local variables.</span></span>

- <span data-ttu-id="f3b40-128">**インスタンス変数によるアクセス。**</span><span class="sxs-lookup"><span data-stu-id="f3b40-128">**Accessing through an Instance Variable.**</span></span> <span data-ttu-id="f3b40-129">共有要素にアクセスするには、そのクラスまたは構造体の特定のインスタンスを格納する変数の名前でそれを修飾します。</span><span class="sxs-lookup"><span data-stu-id="f3b40-129">It is possible to access a shared element by qualifying it with the name of a variable that contains a specific instance of its class or structure.</span></span> <span data-ttu-id="f3b40-130">これは通常、想定どおりに動作しますが、コンパイラでは警告メッセージが生成され、変数ではなくクラスまたは構造体の名前によってアクセスが行われます。</span><span class="sxs-lookup"><span data-stu-id="f3b40-130">Although this usually works as expected, the compiler generates a warning message and makes the access through the class or structure name instead of the variable.</span></span>

- <span data-ttu-id="f3b40-131">**インスタンス式によるアクセス。**</span><span class="sxs-lookup"><span data-stu-id="f3b40-131">**Accessing through an Instance Expression.**</span></span> <span data-ttu-id="f3b40-132">クラスまたは構造体のインスタンスを返す式によって共有要素にアクセスする場合、コンパイラでは、式を評価するのではなく、クラスまたは構造体の名前によってアクセスが行われます。</span><span class="sxs-lookup"><span data-stu-id="f3b40-132">If you access a shared element through an expression that returns an instance of its class or structure, the compiler makes the access through the class or structure name instead of evaluating the expression.</span></span> <span data-ttu-id="f3b40-133">これにより、式でインスタンスを返すことに加えて、他のアクションを実行することを意図した場合に、予期しない結果が発生します。</span><span class="sxs-lookup"><span data-stu-id="f3b40-133">This produces unexpected results if you intended the expression to perform other actions as well as returning the instance.</span></span> <span data-ttu-id="f3b40-134">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f3b40-134">The following example illustrates this.</span></span>
  
    ```vb
    Sub Main()
        ' The following line is the preferred way to access Total.
        ShareTotal.Total = 10

        ' The following line generates a compiler warning message and
        ' accesses total through class ShareTotal instead of through
        ' the variable instanceVar. This works as expected and adds
        ' 100 to Total.
        Dim instanceVar As New ShareTotal
        instanceVar.Total += 100

        ' The following line generates a compiler warning message and
        ' accesses total through class ShareTotal instead of calling
        ' ReturnClass(). This adds 1000 to total but does not work as
        ' expected, because the WriteLine in ReturnClass() does not run.
        Console.WriteLine("Value of total is " & CStr(ShareTotal.Total))
        ReturnClass().Total += 1000
    End Sub

    Public Function ReturnClass() As ShareTotal
        Console.WriteLine("Function ReturnClass() called")
        Return New ShareTotal
    End Function

    Public Class ShareTotal
        Public Shared Property Total As Integer
    End Class
    ```

     <span data-ttu-id="f3b40-135">前の例では、コードがインスタンス経由で共有プロパティ `Total` にアクセスするどちらのときも、コンパイラによって警告メッセージが生成されます。</span><span class="sxs-lookup"><span data-stu-id="f3b40-135">In the preceding example, the compiler generates a warning message both times the code accesses the shared property `Total` through an instance.</span></span> <span data-ttu-id="f3b40-136">いずれの場合も、クラス `ShareTotal` 経由で直接アクセスが行われ、インスタンスが使用されません。</span><span class="sxs-lookup"><span data-stu-id="f3b40-136">In each case it makes the access directly through the class `ShareTotal` and does not make use of any instance.</span></span> <span data-ttu-id="f3b40-137">プロシージャ `ReturnClass` への意図した呼び出しの場合、これは `ReturnClass` への呼び出しも生成されないことを意味するため、"Function ReturnClass() called" を表示する追加のアクションが実行されません。</span><span class="sxs-lookup"><span data-stu-id="f3b40-137">In the case of the intended call to the procedure `ReturnClass`, this means it does not even generate a call to `ReturnClass`, so the additional action of displaying "Function ReturnClass() called" is not performed.</span></span>

<span data-ttu-id="f3b40-138">`Shared` 修飾子は、次のコンテキストで使用できます。</span><span class="sxs-lookup"><span data-stu-id="f3b40-138">The `Shared` modifier can be used in these contexts:</span></span>

- [<span data-ttu-id="f3b40-139">Dim ステートメント</span><span class="sxs-lookup"><span data-stu-id="f3b40-139">Dim Statement</span></span>](../statements/dim-statement.md)
- [<span data-ttu-id="f3b40-140">Event ステートメント</span><span class="sxs-lookup"><span data-stu-id="f3b40-140">Event Statement</span></span>](../statements/event-statement.md)
- [<span data-ttu-id="f3b40-141">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="f3b40-141">Function Statement</span></span>](../statements/function-statement.md)
- [<span data-ttu-id="f3b40-142">Operator ステートメント</span><span class="sxs-lookup"><span data-stu-id="f3b40-142">Operator Statement</span></span>](../statements/operator-statement.md)
- [<span data-ttu-id="f3b40-143">Property ステートメント</span><span class="sxs-lookup"><span data-stu-id="f3b40-143">Property Statement</span></span>](../statements/property-statement.md)
- [<span data-ttu-id="f3b40-144">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="f3b40-144">Sub Statement</span></span>](../statements/sub-statement.md)
  
## <a name="see-also"></a><span data-ttu-id="f3b40-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="f3b40-145">See also</span></span>

- [<span data-ttu-id="f3b40-146">Shadows</span><span class="sxs-lookup"><span data-stu-id="f3b40-146">Shadows</span></span>](shadows.md)
- [<span data-ttu-id="f3b40-147">Static</span><span class="sxs-lookup"><span data-stu-id="f3b40-147">Static</span></span>](static.md)
- [<span data-ttu-id="f3b40-148">Visual Basic における有効期間</span><span class="sxs-lookup"><span data-stu-id="f3b40-148">Lifetime in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/lifetime.md)
- [<span data-ttu-id="f3b40-149">手順</span><span class="sxs-lookup"><span data-stu-id="f3b40-149">Procedures</span></span>](../../programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="f3b40-150">構造体</span><span class="sxs-lookup"><span data-stu-id="f3b40-150">Structures</span></span>](../../programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="f3b40-151">クラスとオブジェクト</span><span class="sxs-lookup"><span data-stu-id="f3b40-151">Objects and Classes</span></span>](../../programming-guide/language-features/objects-and-classes/index.md)
