---
title: ReadOnly (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ReadOnly
helpviewer_keywords:
- ReadOnly keyword [Visual Basic]
- variables [Visual Basic], read-only
- ReadOnly property
- properties [Visual Basic], read-only
- read-only variables
ms.assetid: e868185d-6142-4359-a2fd-a7965cadfce8
ms.openlocfilehash: 6e361cbe89f4c51f28199b008de817c2d48ef326
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62051859"
---
# <a name="readonly-visual-basic"></a><span data-ttu-id="14677-102">ReadOnly (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="14677-102">ReadOnly (Visual Basic)</span></span>
<span data-ttu-id="14677-103">ある変数またはプロパティを読み込めるが書き込まれませんを指定します。</span><span class="sxs-lookup"><span data-stu-id="14677-103">Specifies that a variable or property can be read but not written.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="14677-104">Remarks</span><span class="sxs-lookup"><span data-stu-id="14677-104">Remarks</span></span>  
  
## <a name="rules"></a><span data-ttu-id="14677-105">ルール</span><span class="sxs-lookup"><span data-stu-id="14677-105">Rules</span></span>  
  
- <span data-ttu-id="14677-106">**宣言コンテキスト。**</span><span class="sxs-lookup"><span data-stu-id="14677-106">**Declaration Context.**</span></span> <span data-ttu-id="14677-107">`ReadOnly` は、モジュール レベルでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="14677-107">You can use `ReadOnly` only at module level.</span></span> <span data-ttu-id="14677-108">これは、意味の宣言のコンテキストを`ReadOnly`要素は、クラス、構造体、またはモジュールにある必要があるあり、ソース ファイル、名前空間、またはプロシージャにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="14677-108">This means the declaration context for a `ReadOnly` element must be a class, structure, or module, and cannot be a source file, namespace, or procedure.</span></span>  
  
- <span data-ttu-id="14677-109">**結合された修飾子。**</span><span class="sxs-lookup"><span data-stu-id="14677-109">**Combined Modifiers.**</span></span> <span data-ttu-id="14677-110">指定することはできません`ReadOnly`と共に`Static`同じ宣言内。</span><span class="sxs-lookup"><span data-stu-id="14677-110">You cannot specify `ReadOnly` together with `Static` in the same declaration.</span></span>  
  
- <span data-ttu-id="14677-111">**値を代入します。**</span><span class="sxs-lookup"><span data-stu-id="14677-111">**Assigning a Value.**</span></span> <span data-ttu-id="14677-112">コードの使用、`ReadOnly`プロパティは、その値を設定できません。</span><span class="sxs-lookup"><span data-stu-id="14677-112">Code consuming a `ReadOnly` property cannot set its value.</span></span> <span data-ttu-id="14677-113">基になるストレージにアクセスするコードが割り当てるまたは値をいつでもでも変更します。</span><span class="sxs-lookup"><span data-stu-id="14677-113">But code that has access to the underlying storage can assign or change the value at any time.</span></span>  
  
     <span data-ttu-id="14677-114">値を割り当てることができます、`ReadOnly`変数の宣言でのみ、またはクラスまたは構造体が定義されているのコンス トラクター。</span><span class="sxs-lookup"><span data-stu-id="14677-114">You can assign a value to a `ReadOnly` variable only in its declaration or in the constructor of a class or structure in which it is defined.</span></span>  
  
## <a name="when-to-use-a-readonly-variable"></a><span data-ttu-id="14677-115">読み取り専用の変数を使用する場合</span><span class="sxs-lookup"><span data-stu-id="14677-115">When to Use a ReadOnly Variable</span></span>  
 <span data-ttu-id="14677-116">状況を使用することはできません、 [Const ステートメント](../../../visual-basic/language-reference/statements/const-statement.md)宣言して定数値を代入します。</span><span class="sxs-lookup"><span data-stu-id="14677-116">There are situations in which you cannot use a [Const Statement](../../../visual-basic/language-reference/statements/const-statement.md) to declare and assign a constant value.</span></span> <span data-ttu-id="14677-117">たとえば、`Const`ステートメントで割り当てるには、必要なデータ型を受け付けないことがありますまたはコンパイル時に定数式で値を計算することができません。</span><span class="sxs-lookup"><span data-stu-id="14677-117">For example, the `Const` statement might not accept the data type you want to assign, or you might not be able to compute the value at compile time with a constant expression.</span></span> <span data-ttu-id="14677-118">コンパイル時に値をも認識していない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="14677-118">You might not even know the value at compile time.</span></span> <span data-ttu-id="14677-119">このような場合は、使用することができます、`ReadOnly`定数値を保持する変数。</span><span class="sxs-lookup"><span data-stu-id="14677-119">In these cases, you can use a `ReadOnly` variable to hold a constant value.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="14677-120">場合でも、変数自体がそのメンバーを変更できます、変数のデータ型が配列やクラスのインスタンスなど、参照型の場合`ReadOnly`します。</span><span class="sxs-lookup"><span data-stu-id="14677-120">If the data type of the variable is a reference type, such as an array or a class instance, its members can be changed even if the variable itself is `ReadOnly`.</span></span> <span data-ttu-id="14677-121">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="14677-121">The following example illustrates this.</span></span>  
  
 `ReadOnly characterArray() As Char = {"x"c, "y"c, "z"c}`  
  
 `Sub changeArrayElement()`  
  
 `characterArray(1) = "M"c`  
  
 `End Sub`  
  
 <span data-ttu-id="14677-122">初期化されると、配列が指す`characterArray()`およびを保持"x"、"y"、"z"です。</span><span class="sxs-lookup"><span data-stu-id="14677-122">When initialized, the array pointed to by `characterArray()` holds "x", "y", and "z".</span></span> <span data-ttu-id="14677-123">変数`characterArray`は`ReadOnly`、初期化; であると、その値を変更することはできません、新しい配列を割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="14677-123">Because the variable `characterArray` is `ReadOnly`, you cannot change its value once it is initialized; that is, you cannot assign a new array to it.</span></span> <span data-ttu-id="14677-124">ただし、配列メンバーの 1 つ以上の値を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="14677-124">However, you can change the values of one or more of the array members.</span></span> <span data-ttu-id="14677-125">次のプロシージャの呼び出し`changeArrayElement`、によって示される配列`characterArray()`およびを保持"x"、"M"、"z"です。</span><span class="sxs-lookup"><span data-stu-id="14677-125">Following a call to the procedure `changeArrayElement`, the array pointed to by `characterArray()` holds "x", "M", and "z".</span></span>  
  
 <span data-ttu-id="14677-126">これは、プロシージャのパラメーターを宣言することのような[ByVal](../../../visual-basic/language-reference/modifiers/byval.md)、呼び出し元引数自体を変更できなくなります、プロシージャがそのメンバーを変更するようになります。</span><span class="sxs-lookup"><span data-stu-id="14677-126">Note that this is similar to declaring a procedure parameter to be [ByVal](../../../visual-basic/language-reference/modifiers/byval.md), which prevents the procedure from changing the calling argument itself but allows it to change its members.</span></span>  
  
## <a name="example"></a><span data-ttu-id="14677-127">例</span><span class="sxs-lookup"><span data-stu-id="14677-127">Example</span></span>  
 <span data-ttu-id="14677-128">次の例では、定義、`ReadOnly`従業員が雇用された日付のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="14677-128">The following example defines a `ReadOnly` property for the date on which an employee was hired.</span></span> <span data-ttu-id="14677-129">プロパティの値として内部的にクラス ストア、`Private`クラス内部の変数、そして唯一のコードは、その値を変更できます。</span><span class="sxs-lookup"><span data-stu-id="14677-129">The class stores the property value internally as a `Private` variable, and only code inside the class can change that value.</span></span> <span data-ttu-id="14677-130">ただし、このプロパティは`Public`、およびクラスにアクセスできる任意のコードは、プロパティを読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="14677-130">However, the property is `Public`, and any code that can access the class can read the property.</span></span>  
  
 [!code-vb[VbVbalrKeywords#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#4)]  
  
 <span data-ttu-id="14677-131">`ReadOnly` 修飾子は、次のコンテキストで使用できます。</span><span class="sxs-lookup"><span data-stu-id="14677-131">The `ReadOnly` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="14677-132">Dim ステートメント</span><span class="sxs-lookup"><span data-stu-id="14677-132">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="14677-133">Property ステートメント</span><span class="sxs-lookup"><span data-stu-id="14677-133">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="14677-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="14677-134">See also</span></span>

- [<span data-ttu-id="14677-135">WriteOnly</span><span class="sxs-lookup"><span data-stu-id="14677-135">WriteOnly</span></span>](../../../visual-basic/language-reference/modifiers/writeonly.md)
- [<span data-ttu-id="14677-136">キーワード</span><span class="sxs-lookup"><span data-stu-id="14677-136">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
