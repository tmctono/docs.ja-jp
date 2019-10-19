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
ms.openlocfilehash: ba09bdbc35779afba3dd24f6352cb99a49f931c8
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583050"
---
# <a name="readonly-visual-basic"></a><span data-ttu-id="25082-102">ReadOnly (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="25082-102">ReadOnly (Visual Basic)</span></span>
<span data-ttu-id="25082-103">変数またはプロパティを読み取ることができても書き込まれないことを指定します。</span><span class="sxs-lookup"><span data-stu-id="25082-103">Specifies that a variable or property can be read but not written.</span></span>

## <a name="remarks"></a><span data-ttu-id="25082-104">Remarks</span><span class="sxs-lookup"><span data-stu-id="25082-104">Remarks</span></span>

## <a name="rules"></a><span data-ttu-id="25082-105">ルール</span><span class="sxs-lookup"><span data-stu-id="25082-105">Rules</span></span>

- <span data-ttu-id="25082-106">**宣言コンテキスト。**</span><span class="sxs-lookup"><span data-stu-id="25082-106">**Declaration Context.**</span></span> <span data-ttu-id="25082-107">`ReadOnly` は、モジュール レベルでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="25082-107">You can use `ReadOnly` only at module level.</span></span> <span data-ttu-id="25082-108">つまり、`ReadOnly` 要素の宣言コンテキストはクラス、構造体、またはモジュールである必要があり、ソースファイル、名前空間、またはプロシージャにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="25082-108">This means the declaration context for a `ReadOnly` element must be a class, structure, or module, and cannot be a source file, namespace, or procedure.</span></span>

- <span data-ttu-id="25082-109">**結合された修飾子。**</span><span class="sxs-lookup"><span data-stu-id="25082-109">**Combined Modifiers.**</span></span> <span data-ttu-id="25082-110">同じ宣言内の `Static` と共に `ReadOnly` を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="25082-110">You cannot specify `ReadOnly` together with `Static` in the same declaration.</span></span>

- <span data-ttu-id="25082-111">**値の割り当て。**</span><span class="sxs-lookup"><span data-stu-id="25082-111">**Assigning a Value.**</span></span> <span data-ttu-id="25082-112">@No__t_0 プロパティを使用するコードでは、値を設定できません。</span><span class="sxs-lookup"><span data-stu-id="25082-112">Code consuming a `ReadOnly` property cannot set its value.</span></span> <span data-ttu-id="25082-113">ただし、基になるストレージにアクセスできるコードは、いつでも値を割り当てたり、変更したりできます。</span><span class="sxs-lookup"><span data-stu-id="25082-113">But code that has access to the underlying storage can assign or change the value at any time.</span></span>

     <span data-ttu-id="25082-114">@No__t_0 変数に値を割り当てることができるのは、その宣言、またはそれが定義されているクラスまたは構造体のコンストラクター内でのみです。</span><span class="sxs-lookup"><span data-stu-id="25082-114">You can assign a value to a `ReadOnly` variable only in its declaration or in the constructor of a class or structure in which it is defined.</span></span>

## <a name="when-to-use-a-readonly-variable"></a><span data-ttu-id="25082-115">ReadOnly 変数を使用する場合</span><span class="sxs-lookup"><span data-stu-id="25082-115">When to Use a ReadOnly Variable</span></span>

<span data-ttu-id="25082-116">[Const ステートメント](../../../visual-basic/language-reference/statements/const-statement.md)を使用して定数値を宣言し、割り当てることができない場合があります。</span><span class="sxs-lookup"><span data-stu-id="25082-116">There are situations in which you cannot use a [Const Statement](../../../visual-basic/language-reference/statements/const-statement.md) to declare and assign a constant value.</span></span> <span data-ttu-id="25082-117">たとえば、`Const` ステートメントでは、割り当てたいデータ型が受け入れられない場合や、コンパイル時に定数式を使用して値を計算できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="25082-117">For example, the `Const` statement might not accept the data type you want to assign, or you might not be able to compute the value at compile time with a constant expression.</span></span> <span data-ttu-id="25082-118">コンパイル時に値がわからない場合もあります。</span><span class="sxs-lookup"><span data-stu-id="25082-118">You might not even know the value at compile time.</span></span> <span data-ttu-id="25082-119">このような場合は、`ReadOnly` 変数を使用して定数値を保持できます。</span><span class="sxs-lookup"><span data-stu-id="25082-119">In these cases, you can use a `ReadOnly` variable to hold a constant value.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="25082-120">変数のデータ型が配列やクラスインスタンスなどの参照型である場合、変数自体が `ReadOnly` 場合でも、そのメンバーを変更できます。</span><span class="sxs-lookup"><span data-stu-id="25082-120">If the data type of the variable is a reference type, such as an array or a class instance, its members can be changed even if the variable itself is `ReadOnly`.</span></span> <span data-ttu-id="25082-121">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="25082-121">The following example illustrates this.</span></span>

```vb
ReadOnly characterArray() As Char = {"x"c, "y"c, "z"c}
Sub ChangeArrayElement()
    characterArray(1) = "M"c
End Sub
```

<span data-ttu-id="25082-122">初期化されると、`characterArray()` が指す配列は、"x"、"y"、および "z" を保持します。</span><span class="sxs-lookup"><span data-stu-id="25082-122">When initialized, the array pointed to by `characterArray()` holds "x", "y", and "z".</span></span> <span data-ttu-id="25082-123">変数 `characterArray` が `ReadOnly` ので、初期化後に値を変更することはできません。つまり、新しい配列を割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="25082-123">Because the variable `characterArray` is `ReadOnly`, you cannot change its value once it is initialized; that is, you cannot assign a new array to it.</span></span> <span data-ttu-id="25082-124">ただし、1つまたは複数の配列メンバーの値を変更できます。</span><span class="sxs-lookup"><span data-stu-id="25082-124">However, you can change the values of one or more of the array members.</span></span> <span data-ttu-id="25082-125">プロシージャ `ChangeArrayElement` の呼び出しの後、`characterArray()` が指す配列は、"x"、"M"、および "z" を保持します。</span><span class="sxs-lookup"><span data-stu-id="25082-125">Following a call to the procedure `ChangeArrayElement`, the array pointed to by `characterArray()` holds "x", "M", and "z".</span></span>

<span data-ttu-id="25082-126">これは、プロシージャパラメーターを[ByVal](byval.md)に宣言するのと似ています。これにより、プロシージャが呼び出し元の引数自体を変更するのではなく、メンバーを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="25082-126">Note that this is similar to declaring a procedure parameter to be [ByVal](byval.md), which prevents the procedure from changing the calling argument itself but allows it to change its members.</span></span>

## <a name="example"></a><span data-ttu-id="25082-127">例</span><span class="sxs-lookup"><span data-stu-id="25082-127">Example</span></span>

<span data-ttu-id="25082-128">次の例では、従業員が雇用された日付の `ReadOnly` プロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="25082-128">The following example defines a `ReadOnly` property for the date on which an employee was hired.</span></span> <span data-ttu-id="25082-129">クラスは `Private` 変数として内部的にプロパティ値を格納します。クラス内のコードだけがその値を変更できます。</span><span class="sxs-lookup"><span data-stu-id="25082-129">The class stores the property value internally as a `Private` variable, and only code inside the class can change that value.</span></span> <span data-ttu-id="25082-130">ただし、プロパティは `Public`、クラスにアクセスできるすべてのコードでプロパティを読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="25082-130">However, the property is `Public`, and any code that can access the class can read the property.</span></span>

[!code-vb[VbVbalrKeywords#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#4)]

<span data-ttu-id="25082-131">`ReadOnly` 修飾子は、次のコンテキストで使用できます。</span><span class="sxs-lookup"><span data-stu-id="25082-131">The `ReadOnly` modifier can be used in these contexts:</span></span>

- [<span data-ttu-id="25082-132">Dim ステートメント</span><span class="sxs-lookup"><span data-stu-id="25082-132">Dim Statement</span></span>](../statements/dim-statement.md)
- [<span data-ttu-id="25082-133">Property ステートメント</span><span class="sxs-lookup"><span data-stu-id="25082-133">Property Statement</span></span>](../statements/property-statement.md)

## <a name="see-also"></a><span data-ttu-id="25082-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="25082-134">See also</span></span>

- [<span data-ttu-id="25082-135">WriteOnly</span><span class="sxs-lookup"><span data-stu-id="25082-135">WriteOnly</span></span>](writeonly.md)
- [<span data-ttu-id="25082-136">キーワード</span><span class="sxs-lookup"><span data-stu-id="25082-136">Keywords</span></span>](../keywords/index.md)
