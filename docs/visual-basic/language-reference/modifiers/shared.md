---
title: Shared (Visual Basic)
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
ms.openlocfilehash: fd43ef7cb5c16995fff87a65fc0f0974d8f4a47d
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64647704"
---
# <a name="shared-visual-basic"></a><span data-ttu-id="a7fa9-102">Shared (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a7fa9-102">Shared (Visual Basic)</span></span>
<span data-ttu-id="a7fa9-103">1 つまたは複数の宣言されたプログラミング要素がクラスまたは構造体全体、クラスまたは構造体の特定のインスタンスではなくと関連付けられていることを指定します。</span><span class="sxs-lookup"><span data-stu-id="a7fa9-103">Specifies that one or more declared programming elements are associated with a class or structure at large, and not with a specific instance of the class or structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a7fa9-104">Remarks</span><span class="sxs-lookup"><span data-stu-id="a7fa9-104">Remarks</span></span>  
  
## <a name="when-to-use-shared"></a><span data-ttu-id="a7fa9-105">共有を使用する場合</span><span class="sxs-lookup"><span data-stu-id="a7fa9-105">When to Use Shared</span></span>  
 <span data-ttu-id="a7fa9-106">すべてのインスタンスを使用できるクラスまたは構造体のメンバーを共有するようになく*非共有*、各インスタンスが独自のコピーを保持します。</span><span class="sxs-lookup"><span data-stu-id="a7fa9-106">Sharing a member of a class or structure makes it available to every instance, rather than *nonshared*, where each instance keeps its own copy.</span></span> <span data-ttu-id="a7fa9-107">これは、変数の値は、アプリケーション全体に適用される場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="a7fa9-107">This is useful, for example, if the value of a variable applies to the entire application.</span></span> <span data-ttu-id="a7fa9-108">その変数を宣言する場合`Shared`すべてのインスタンスが、同じストレージの場所にアクセスし、更新された値にアクセスするすべてのインスタンス 1 つのインスタンスには、変数の値が変更された場合。</span><span class="sxs-lookup"><span data-stu-id="a7fa9-108">If you declare that variable to be `Shared`, then all instances access the same storage location, and if one instance changes the variable's value, all instances access the updated value.</span></span>  
  
 <span data-ttu-id="a7fa9-109">共有メンバーのアクセス レベルは変更されません。</span><span class="sxs-lookup"><span data-stu-id="a7fa9-109">Sharing does not alter the access level of a member.</span></span> <span data-ttu-id="a7fa9-110">たとえば、クラス メンバーを共有できるとプライベート (クラス内からのみアクセスできます)、または非共有と公開。</span><span class="sxs-lookup"><span data-stu-id="a7fa9-110">For example, a class member can be shared and private (accessible only from within the class), or nonshared and public.</span></span> <span data-ttu-id="a7fa9-111">詳細については、[ Visual Basic のアクセス レベル](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a7fa9-111">For more information, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="a7fa9-112">ルール</span><span class="sxs-lookup"><span data-stu-id="a7fa9-112">Rules</span></span>  
  
- <span data-ttu-id="a7fa9-113">**宣言コンテキスト。**</span><span class="sxs-lookup"><span data-stu-id="a7fa9-113">**Declaration Context.**</span></span> <span data-ttu-id="a7fa9-114">`Shared` は、モジュール レベルでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="a7fa9-114">You can use `Shared` only at module level.</span></span> <span data-ttu-id="a7fa9-115">これは、意味の宣言のコンテキストを`Shared`要素がクラスまたは構造体にある必要があるあり、ソース ファイル、名前空間、またはプロシージャにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="a7fa9-115">This means the declaration context for a `Shared` element must be a class or structure, and cannot be a source file, namespace, or procedure.</span></span>  
  
- <span data-ttu-id="a7fa9-116">**結合された修飾子。**</span><span class="sxs-lookup"><span data-stu-id="a7fa9-116">**Combined Modifiers.**</span></span> <span data-ttu-id="a7fa9-117">指定することはできません`Shared`と共に[オーバーライド](../../../visual-basic/language-reference/modifiers/overrides.md)、 [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md)、 [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)、 [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)、または[静的](../../../visual-basic/language-reference/modifiers/static.md)同じ宣言内。</span><span class="sxs-lookup"><span data-stu-id="a7fa9-117">You cannot specify `Shared` together with [Overrides](../../../visual-basic/language-reference/modifiers/overrides.md), [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md), [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md), [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md), or [Static](../../../visual-basic/language-reference/modifiers/static.md) in the same declaration.</span></span>  
  
- <span data-ttu-id="a7fa9-118">**アクセスします。**</span><span class="sxs-lookup"><span data-stu-id="a7fa9-118">**Accessing.**</span></span> <span data-ttu-id="a7fa9-119">共有要素にアクセスするには、そのクラスまたは構造体の名前を持つ、そのクラスまたは構造体の特定のインスタンスの変数名ではなくを修飾します。</span><span class="sxs-lookup"><span data-stu-id="a7fa9-119">You access a shared element by qualifying it with its class or structure name, not with the variable name of a specific instance of its class or structure.</span></span> <span data-ttu-id="a7fa9-120">でも、クラスまたはその共有メンバーにアクセスする構造体のインスタンスを作成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="a7fa9-120">You do not even have to create an instance of a class or structure to access its shared members.</span></span>  
  
     <span data-ttu-id="a7fa9-121">次の例では共有のプロシージャ<xref:System.Double.IsNaN%2A>によって公開されている、<xref:System.Double>構造体。</span><span class="sxs-lookup"><span data-stu-id="a7fa9-121">The following example calls the shared procedure <xref:System.Double.IsNaN%2A> exposed by the <xref:System.Double> structure.</span></span>  
  
     `If Double.IsNaN(result) Then MsgBox("Result is mathematically undefined.")`  
  
- <span data-ttu-id="a7fa9-122">**暗黙の型を共有します。**</span><span class="sxs-lookup"><span data-stu-id="a7fa9-122">**Implicit Sharing.**</span></span> <span data-ttu-id="a7fa9-123">使用することはできません、`Shared`修飾子、 [Const ステートメント](../../../visual-basic/language-reference/statements/const-statement.md)定数が暗黙的に共有しますが、できます。</span><span class="sxs-lookup"><span data-stu-id="a7fa9-123">You cannot use the `Shared` modifier in a [Const Statement](../../../visual-basic/language-reference/statements/const-statement.md), but constants are implicitly shared.</span></span> <span data-ttu-id="a7fa9-124">同様に、するには、モジュールまたはインターフェイスのメンバーを宣言することはできません`Shared`、暗黙的に共有しますが、できます。</span><span class="sxs-lookup"><span data-stu-id="a7fa9-124">Similarly, you cannot declare a member of a module or an interface to be `Shared`, but they are implicitly shared.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="a7fa9-125">動作</span><span class="sxs-lookup"><span data-stu-id="a7fa9-125">Behavior</span></span>  
  
- <span data-ttu-id="a7fa9-126">**記憶域。**</span><span class="sxs-lookup"><span data-stu-id="a7fa9-126">**Storage.**</span></span> <span data-ttu-id="a7fa9-127">共有変数またはイベントは、そのクラスまたは構造体の作成の数またはいくつかのインスタンスに関係なく、1 回だけメモリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="a7fa9-127">A shared variable or event is stored in memory only once, no matter how many or few instances you create of its class or structure.</span></span> <span data-ttu-id="a7fa9-128">同様に、共有プロシージャまたはプロパティは、ローカル変数の 1 つだけのセットを保持します。</span><span class="sxs-lookup"><span data-stu-id="a7fa9-128">Similarly, a shared procedure or property holds only one set of local variables.</span></span>  
  
- <span data-ttu-id="a7fa9-129">**インスタンス変数を通じてアクセスします。**</span><span class="sxs-lookup"><span data-stu-id="a7fa9-129">**Accessing through an Instance Variable.**</span></span> <span data-ttu-id="a7fa9-130">クラスまたは構造体の特定のインスタンスを格納する変数の名前で修飾して、共有要素にアクセスすることになります。</span><span class="sxs-lookup"><span data-stu-id="a7fa9-130">It is possible to access a shared element by qualifying it with the name of a variable that contains a specific instance of its class or structure.</span></span> <span data-ttu-id="a7fa9-131">通常、これは期待どおりに動作をコンパイラは警告メッセージを生成し、変数ではなく、クラスまたは構造体の名前を使ってアクセスします。</span><span class="sxs-lookup"><span data-stu-id="a7fa9-131">Although this usually works as expected, the compiler generates a warning message and makes the access through the class or structure name instead of the variable.</span></span>  
  
- <span data-ttu-id="a7fa9-132">**インスタンス式からアクセスします。**</span><span class="sxs-lookup"><span data-stu-id="a7fa9-132">**Accessing through an Instance Expression.**</span></span> <span data-ttu-id="a7fa9-133">共有要素をそのクラスまたは構造体のインスタンスを返す式を使用してアクセスする場合、コンパイラで式を評価するのではなく、クラスまたは構造体の名前でアクセスを行います。</span><span class="sxs-lookup"><span data-stu-id="a7fa9-133">If you access a shared element through an expression that returns an instance of its class or structure, the compiler makes the access through the class or structure name instead of evaluating the expression.</span></span> <span data-ttu-id="a7fa9-134">その他のアクション、インスタンスを返すことを実行する式を意図した場合、予期しない結果が生成されます。</span><span class="sxs-lookup"><span data-stu-id="a7fa9-134">This produces unexpected results if you intended the expression to perform other actions as well as returning the instance.</span></span> <span data-ttu-id="a7fa9-135">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="a7fa9-135">The following example illustrates this.</span></span>  
  
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
  
     <span data-ttu-id="a7fa9-136">前の例では、コンパイラ警告メッセージを生成、コード共有変数にアクセスする両方の回`total`インスタンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="a7fa9-136">In the preceding example, the compiler generates a warning message both times the code accesses the shared variable `total` through an instance.</span></span> <span data-ttu-id="a7fa9-137">クラスから直接アクセスは、各ケース`shareTotal`を行わないと、インスタンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="a7fa9-137">In each case it makes the access directly through the class `shareTotal` and does not make use of any instance.</span></span> <span data-ttu-id="a7fa9-138">プロシージャに目的の呼び出しの場合`returnClass`、つまりへの呼び出しも生成しません`returnClass`ので、"関数 returnClass() と呼ばれる"を表示する追加のアクションは実行されません。</span><span class="sxs-lookup"><span data-stu-id="a7fa9-138">In the case of the intended call to the procedure `returnClass`, this means it does not even generate a call to `returnClass`, so the additional action of displaying "Function returnClass() called" is not performed.</span></span>  
  
 <span data-ttu-id="a7fa9-139">`Shared` 修飾子は、次のコンテキストで使用できます。</span><span class="sxs-lookup"><span data-stu-id="a7fa9-139">The `Shared` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="a7fa9-140">Dim ステートメント</span><span class="sxs-lookup"><span data-stu-id="a7fa9-140">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="a7fa9-141">Event ステートメント</span><span class="sxs-lookup"><span data-stu-id="a7fa9-141">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="a7fa9-142">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="a7fa9-142">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="a7fa9-143">Operator ステートメント</span><span class="sxs-lookup"><span data-stu-id="a7fa9-143">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [<span data-ttu-id="a7fa9-144">Property ステートメント</span><span class="sxs-lookup"><span data-stu-id="a7fa9-144">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="a7fa9-145">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="a7fa9-145">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="a7fa9-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="a7fa9-146">See also</span></span>

- [<span data-ttu-id="a7fa9-147">Shadows</span><span class="sxs-lookup"><span data-stu-id="a7fa9-147">Shadows</span></span>](../../../visual-basic/language-reference/modifiers/shadows.md)
- [<span data-ttu-id="a7fa9-148">Static</span><span class="sxs-lookup"><span data-stu-id="a7fa9-148">Static</span></span>](../../../visual-basic/language-reference/modifiers/static.md)
- [<span data-ttu-id="a7fa9-149">Visual Basic での有効期間</span><span class="sxs-lookup"><span data-stu-id="a7fa9-149">Lifetime in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)
- [<span data-ttu-id="a7fa9-150">プロシージャ</span><span class="sxs-lookup"><span data-stu-id="a7fa9-150">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="a7fa9-151">構造体</span><span class="sxs-lookup"><span data-stu-id="a7fa9-151">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="a7fa9-152">クラスとオブジェクト</span><span class="sxs-lookup"><span data-stu-id="a7fa9-152">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
