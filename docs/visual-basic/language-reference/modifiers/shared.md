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
ms.openlocfilehash: 98fa25d2283408dfb80e82fbc620a1b284e5c530
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349124"
---
# <a name="shared-visual-basic"></a><span data-ttu-id="a571a-102">Shared (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a571a-102">Shared (Visual Basic)</span></span>
<span data-ttu-id="a571a-103">1つ以上の宣言されたプログラミング要素が、クラスまたは構造体の特定のインスタンスではなく、大規模なクラスまたは構造体に関連付けられていることを指定します。</span><span class="sxs-lookup"><span data-stu-id="a571a-103">Specifies that one or more declared programming elements are associated with a class or structure at large, and not with a specific instance of the class or structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a571a-104">コメント</span><span class="sxs-lookup"><span data-stu-id="a571a-104">Remarks</span></span>  
  
## <a name="when-to-use-shared"></a><span data-ttu-id="a571a-105">共有を使用する場合</span><span class="sxs-lookup"><span data-stu-id="a571a-105">When to Use Shared</span></span>  
 <span data-ttu-id="a571a-106">クラスまたは構造体のメンバーを共有すると、共有ではなく、すべてのインスタンスで使用できるようになります。この*場合、各*インスタンスは独自のコピーを保持します。</span><span class="sxs-lookup"><span data-stu-id="a571a-106">Sharing a member of a class or structure makes it available to every instance, rather than *nonshared*, where each instance keeps its own copy.</span></span> <span data-ttu-id="a571a-107">これは、変数の値がアプリケーション全体に適用される場合などに便利です。</span><span class="sxs-lookup"><span data-stu-id="a571a-107">This is useful, for example, if the value of a variable applies to the entire application.</span></span> <span data-ttu-id="a571a-108">この変数を `Shared`するように宣言すると、すべてのインスタンスが同じストレージの場所にアクセスし、1つのインスタンスが変数の値を変更すると、すべてのインスタンスが更新された値にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="a571a-108">If you declare that variable to be `Shared`, then all instances access the same storage location, and if one instance changes the variable's value, all instances access the updated value.</span></span>  
  
 <span data-ttu-id="a571a-109">共有によってメンバーのアクセスレベルが変更されることはありません。</span><span class="sxs-lookup"><span data-stu-id="a571a-109">Sharing does not alter the access level of a member.</span></span> <span data-ttu-id="a571a-110">たとえば、クラスメンバーは、共有およびプライベート (クラス内からのみアクセス可能)、または非共有およびパブリックにすることができます。</span><span class="sxs-lookup"><span data-stu-id="a571a-110">For example, a class member can be shared and private (accessible only from within the class), or nonshared and public.</span></span> <span data-ttu-id="a571a-111">詳細については、「 [Visual Basic のアクセスレベル](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a571a-111">For more information, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="a571a-112">ルール</span><span class="sxs-lookup"><span data-stu-id="a571a-112">Rules</span></span>  
  
- <span data-ttu-id="a571a-113">**宣言コンテキスト。**</span><span class="sxs-lookup"><span data-stu-id="a571a-113">**Declaration Context.**</span></span> <span data-ttu-id="a571a-114">`Shared` は、モジュール レベルでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="a571a-114">You can use `Shared` only at module level.</span></span> <span data-ttu-id="a571a-115">つまり、`Shared` 要素の宣言コンテキストは、クラスまたは構造体である必要があり、ソースファイル、名前空間、またはプロシージャにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="a571a-115">This means the declaration context for a `Shared` element must be a class or structure, and cannot be a source file, namespace, or procedure.</span></span>  
  
- <span data-ttu-id="a571a-116">**結合された修飾子。**</span><span class="sxs-lookup"><span data-stu-id="a571a-116">**Combined Modifiers.**</span></span> <span data-ttu-id="a571a-117">同じ宣言で、[オーバーライド](../../../visual-basic/language-reference/modifiers/overrides.md)、 [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md)、 [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)、 [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)、または[Static](../../../visual-basic/language-reference/modifiers/static.md)と共に `Shared` を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="a571a-117">You cannot specify `Shared` together with [Overrides](../../../visual-basic/language-reference/modifiers/overrides.md), [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md), [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md), [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md), or [Static](../../../visual-basic/language-reference/modifiers/static.md) in the same declaration.</span></span>  
  
- <span data-ttu-id="a571a-118">**しよう.**</span><span class="sxs-lookup"><span data-stu-id="a571a-118">**Accessing.**</span></span> <span data-ttu-id="a571a-119">共有要素には、そのクラスまたは構造体の特定のインスタンスの変数名ではなく、そのクラスまたは構造体の名前を修飾することによってアクセスします。</span><span class="sxs-lookup"><span data-stu-id="a571a-119">You access a shared element by qualifying it with its class or structure name, not with the variable name of a specific instance of its class or structure.</span></span> <span data-ttu-id="a571a-120">クラスまたは構造体のインスタンスを作成しなくても、その共有メンバーにアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="a571a-120">You do not even have to create an instance of a class or structure to access its shared members.</span></span>  
  
     <span data-ttu-id="a571a-121">次の例では、<xref:System.Double> 構造によって公開される <xref:System.Double.IsNaN%2A> 共有プロシージャを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="a571a-121">The following example calls the shared procedure <xref:System.Double.IsNaN%2A> exposed by the <xref:System.Double> structure.</span></span>  
  
     `If Double.IsNaN(result) Then MsgBox("Result is mathematically undefined.")`  
  
- <span data-ttu-id="a571a-122">**暗黙の共有。**</span><span class="sxs-lookup"><span data-stu-id="a571a-122">**Implicit Sharing.**</span></span> <span data-ttu-id="a571a-123">[Const ステートメント](../../../visual-basic/language-reference/statements/const-statement.md)では `Shared` 修飾子を使用できませんが、定数は暗黙的に共有されます。</span><span class="sxs-lookup"><span data-stu-id="a571a-123">You cannot use the `Shared` modifier in a [Const Statement](../../../visual-basic/language-reference/statements/const-statement.md), but constants are implicitly shared.</span></span> <span data-ttu-id="a571a-124">同様に、モジュールまたはインターフェイスのメンバーを `Shared`するように宣言することはできませんが、暗黙的に共有されます。</span><span class="sxs-lookup"><span data-stu-id="a571a-124">Similarly, you cannot declare a member of a module or an interface to be `Shared`, but they are implicitly shared.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="a571a-125">動作</span><span class="sxs-lookup"><span data-stu-id="a571a-125">Behavior</span></span>  
  
- <span data-ttu-id="a571a-126">**・.**</span><span class="sxs-lookup"><span data-stu-id="a571a-126">**Storage.**</span></span> <span data-ttu-id="a571a-127">共有変数またはイベントは、クラスまたは構造体を作成するインスタンスの数または数に関係なく、メモリに1回だけ格納されます。</span><span class="sxs-lookup"><span data-stu-id="a571a-127">A shared variable or event is stored in memory only once, no matter how many or few instances you create of its class or structure.</span></span> <span data-ttu-id="a571a-128">同様に、共有プロシージャまたはプロパティは、ローカル変数のセットを1つだけ保持します。</span><span class="sxs-lookup"><span data-stu-id="a571a-128">Similarly, a shared procedure or property holds only one set of local variables.</span></span>  
  
- <span data-ttu-id="a571a-129">**インスタンス変数を使用したへのアクセス。**</span><span class="sxs-lookup"><span data-stu-id="a571a-129">**Accessing through an Instance Variable.**</span></span> <span data-ttu-id="a571a-130">共有要素にアクセスするには、そのクラスまたは構造体の特定のインスタンスを含む変数の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="a571a-130">It is possible to access a shared element by qualifying it with the name of a variable that contains a specific instance of its class or structure.</span></span> <span data-ttu-id="a571a-131">これは通常、想定どおりに動作しますが、コンパイラは警告メッセージを生成し、変数ではなくクラスまたは構造体の名前を使用してアクセスを行います。</span><span class="sxs-lookup"><span data-stu-id="a571a-131">Although this usually works as expected, the compiler generates a warning message and makes the access through the class or structure name instead of the variable.</span></span>  
  
- <span data-ttu-id="a571a-132">**インスタンス式を使用したへのアクセス。**</span><span class="sxs-lookup"><span data-stu-id="a571a-132">**Accessing through an Instance Expression.**</span></span> <span data-ttu-id="a571a-133">クラスまたは構造体のインスタンスを返す式を使用して共有要素にアクセスする場合、コンパイラは、式を評価するのではなく、クラスまたは構造体の名前を使用してアクセスを行います。</span><span class="sxs-lookup"><span data-stu-id="a571a-133">If you access a shared element through an expression that returns an instance of its class or structure, the compiler makes the access through the class or structure name instead of evaluating the expression.</span></span> <span data-ttu-id="a571a-134">これにより、他のアクションを実行するための式を作成する場合や、インスタンスを返す場合に、予期しない結果が発生します。</span><span class="sxs-lookup"><span data-stu-id="a571a-134">This produces unexpected results if you intended the expression to perform other actions as well as returning the instance.</span></span> <span data-ttu-id="a571a-135">これを次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="a571a-135">The following example illustrates this.</span></span>  
  
    ```vb
    Sub main()  
        shareTotal.total = 10  
        ' The preceding line is the preferred way to access total.  
        Dim instanceVar As New shareTotal  
        instanceVar.total += 100  
        ' The preceding line generates a compiler warning message and  
        ' accesses total through class shareTotal instead of through  
        ' the variable instanceVar. This works as expected and adds  
        ' 100 to total.  
        returnClass().total += 1000  
        ' The preceding line generates a compiler warning message and  
        ' accesses total through class shareTotal instead of calling  
        ' returnClass(). This adds 1000 to total but does not work as  
        ' expected, because the MsgBox in returnClass() does not run.  
        MsgBox("Value of total is " & CStr(shareTotal.total))  
    End Sub  
    Public Function returnClass() As shareTotal  
        MsgBox("Function returnClass() called")  
        Return New shareTotal  
    End Function  
    Public Class shareTotal  
        Public Shared total As Integer  
    End Class  
    ```  
  
     <span data-ttu-id="a571a-136">前の例では、コードがインスタンスを介して `total` 共有変数にアクセスするときに、コンパイラによって警告メッセージが生成されます。</span><span class="sxs-lookup"><span data-stu-id="a571a-136">In the preceding example, the compiler generates a warning message both times the code accesses the shared variable `total` through an instance.</span></span> <span data-ttu-id="a571a-137">各ケースでは、クラス `shareTotal` を通じて直接アクセスを行い、インスタンスを使用しません。</span><span class="sxs-lookup"><span data-stu-id="a571a-137">In each case it makes the access directly through the class `shareTotal` and does not make use of any instance.</span></span> <span data-ttu-id="a571a-138">このプロシージャ `returnClass`の呼び出しの場合、これは `returnClass`の呼び出しを生成しないことを意味するため、"関数 returnClass ()" を表示する追加のアクションは実行されません。</span><span class="sxs-lookup"><span data-stu-id="a571a-138">In the case of the intended call to the procedure `returnClass`, this means it does not even generate a call to `returnClass`, so the additional action of displaying "Function returnClass() called" is not performed.</span></span>  
  
 <span data-ttu-id="a571a-139">`Shared` 修飾子は、次のコンテキストで使用できます。</span><span class="sxs-lookup"><span data-stu-id="a571a-139">The `Shared` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="a571a-140">Dim ステートメント</span><span class="sxs-lookup"><span data-stu-id="a571a-140">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="a571a-141">Event ステートメント</span><span class="sxs-lookup"><span data-stu-id="a571a-141">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="a571a-142">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="a571a-142">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="a571a-143">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="a571a-143">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [<span data-ttu-id="a571a-144">Property ステートメント</span><span class="sxs-lookup"><span data-stu-id="a571a-144">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="a571a-145">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="a571a-145">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="a571a-146">参照</span><span class="sxs-lookup"><span data-stu-id="a571a-146">See also</span></span>

- [<span data-ttu-id="a571a-147">Shadows</span><span class="sxs-lookup"><span data-stu-id="a571a-147">Shadows</span></span>](../../../visual-basic/language-reference/modifiers/shadows.md)
- [<span data-ttu-id="a571a-148">Static</span><span class="sxs-lookup"><span data-stu-id="a571a-148">Static</span></span>](../../../visual-basic/language-reference/modifiers/static.md)
- [<span data-ttu-id="a571a-149">Visual Basic の有効期間</span><span class="sxs-lookup"><span data-stu-id="a571a-149">Lifetime in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)
- [<span data-ttu-id="a571a-150">手順</span><span class="sxs-lookup"><span data-stu-id="a571a-150">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="a571a-151">構造体</span><span class="sxs-lookup"><span data-stu-id="a571a-151">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="a571a-152">クラスとオブジェクト</span><span class="sxs-lookup"><span data-stu-id="a571a-152">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
