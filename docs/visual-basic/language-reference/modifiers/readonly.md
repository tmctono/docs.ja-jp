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
ms.openlocfilehash: 01c441576cb4247933c053f2043296733f99fdeb
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965420"
---
# <a name="readonly-visual-basic"></a><span data-ttu-id="facd6-102">ReadOnly (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="facd6-102">ReadOnly (Visual Basic)</span></span>
<span data-ttu-id="facd6-103">変数またはプロパティを読み取ることができても書き込まれないことを指定します。</span><span class="sxs-lookup"><span data-stu-id="facd6-103">Specifies that a variable or property can be read but not written.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="facd6-104">Remarks</span><span class="sxs-lookup"><span data-stu-id="facd6-104">Remarks</span></span>  
  
## <a name="rules"></a><span data-ttu-id="facd6-105">ルール</span><span class="sxs-lookup"><span data-stu-id="facd6-105">Rules</span></span>  
  
- <span data-ttu-id="facd6-106">**宣言コンテキスト。**</span><span class="sxs-lookup"><span data-stu-id="facd6-106">**Declaration Context.**</span></span> <span data-ttu-id="facd6-107">`ReadOnly` は、モジュール レベルでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="facd6-107">You can use `ReadOnly` only at module level.</span></span> <span data-ttu-id="facd6-108">つまり、 `ReadOnly`要素の宣言コンテキストはクラス、構造体、またはモジュールである必要があり、ソースファイル、名前空間、またはプロシージャにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="facd6-108">This means the declaration context for a `ReadOnly` element must be a class, structure, or module, and cannot be a source file, namespace, or procedure.</span></span>  
  
- <span data-ttu-id="facd6-109">**結合された修飾子。**</span><span class="sxs-lookup"><span data-stu-id="facd6-109">**Combined Modifiers.**</span></span> <span data-ttu-id="facd6-110">を同じ宣言`ReadOnly`内で`Static`と共に指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="facd6-110">You cannot specify `ReadOnly` together with `Static` in the same declaration.</span></span>  
  
- <span data-ttu-id="facd6-111">**値の割り当て。**</span><span class="sxs-lookup"><span data-stu-id="facd6-111">**Assigning a Value.**</span></span> <span data-ttu-id="facd6-112">プロパティを使用`ReadOnly`するコードで値を設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="facd6-112">Code consuming a `ReadOnly` property cannot set its value.</span></span> <span data-ttu-id="facd6-113">ただし、基になるストレージにアクセスできるコードは、いつでも値を割り当てたり、変更したりできます。</span><span class="sxs-lookup"><span data-stu-id="facd6-113">But code that has access to the underlying storage can assign or change the value at any time.</span></span>  
  
     <span data-ttu-id="facd6-114">`ReadOnly`変数に値を割り当てることができるのは、その宣言または定義されているクラスまたは構造体のコンストラクター内の変数だけです。</span><span class="sxs-lookup"><span data-stu-id="facd6-114">You can assign a value to a `ReadOnly` variable only in its declaration or in the constructor of a class or structure in which it is defined.</span></span>  
  
## <a name="when-to-use-a-readonly-variable"></a><span data-ttu-id="facd6-115">ReadOnly 変数を使用する場合</span><span class="sxs-lookup"><span data-stu-id="facd6-115">When to Use a ReadOnly Variable</span></span>  
 <span data-ttu-id="facd6-116">[Const ステートメント](../../../visual-basic/language-reference/statements/const-statement.md)を使用して定数値を宣言し、割り当てることができない場合があります。</span><span class="sxs-lookup"><span data-stu-id="facd6-116">There are situations in which you cannot use a [Const Statement](../../../visual-basic/language-reference/statements/const-statement.md) to declare and assign a constant value.</span></span> <span data-ttu-id="facd6-117">たとえば、割り当てたい`Const`データ型がステートメントで受け入れられない場合や、コンパイル時に定数式を使用して値を計算できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="facd6-117">For example, the `Const` statement might not accept the data type you want to assign, or you might not be able to compute the value at compile time with a constant expression.</span></span> <span data-ttu-id="facd6-118">コンパイル時に値がわからない場合もあります。</span><span class="sxs-lookup"><span data-stu-id="facd6-118">You might not even know the value at compile time.</span></span> <span data-ttu-id="facd6-119">このような場合は、変数を`ReadOnly`使用して定数値を保持できます。</span><span class="sxs-lookup"><span data-stu-id="facd6-119">In these cases, you can use a `ReadOnly` variable to hold a constant value.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="facd6-120">変数のデータ型が配列やクラスインスタンスなどの参照型である場合、変数自体が`ReadOnly`の場合でも、そのメンバーを変更できます。</span><span class="sxs-lookup"><span data-stu-id="facd6-120">If the data type of the variable is a reference type, such as an array or a class instance, its members can be changed even if the variable itself is `ReadOnly`.</span></span> <span data-ttu-id="facd6-121">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="facd6-121">The following example illustrates this.</span></span>  
  
 `ReadOnly characterArray() As Char = {"x"c, "y"c, "z"c}`  
  
 `Sub changeArrayElement()`  
  
 `characterArray(1) = "M"c`  
  
 `End Sub`  
  
 <span data-ttu-id="facd6-122">初期化されると、が指す`characterArray()`配列は、"x"、"y"、および "z" を保持します。</span><span class="sxs-lookup"><span data-stu-id="facd6-122">When initialized, the array pointed to by `characterArray()` holds "x", "y", and "z".</span></span> <span data-ttu-id="facd6-123">変数`characterArray` は`ReadOnly`であるため、初期化後に値を変更することはできません。つまり、新しい配列を割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="facd6-123">Because the variable `characterArray` is `ReadOnly`, you cannot change its value once it is initialized; that is, you cannot assign a new array to it.</span></span> <span data-ttu-id="facd6-124">ただし、1つまたは複数の配列メンバーの値を変更できます。</span><span class="sxs-lookup"><span data-stu-id="facd6-124">However, you can change the values of one or more of the array members.</span></span> <span data-ttu-id="facd6-125">プロシージャ`changeArrayElement`の呼び出しの後、が指す`characterArray()`配列は、"x"、"M"、および "z" を保持します。</span><span class="sxs-lookup"><span data-stu-id="facd6-125">Following a call to the procedure `changeArrayElement`, the array pointed to by `characterArray()` holds "x", "M", and "z".</span></span>  
  
 <span data-ttu-id="facd6-126">これは、プロシージャパラメーターを[ByVal](../../../visual-basic/language-reference/modifiers/byval.md)に宣言するのと似ています。これにより、プロシージャが呼び出し元の引数自体を変更するのではなく、メンバーを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="facd6-126">Note that this is similar to declaring a procedure parameter to be [ByVal](../../../visual-basic/language-reference/modifiers/byval.md), which prevents the procedure from changing the calling argument itself but allows it to change its members.</span></span>  
  
## <a name="example"></a><span data-ttu-id="facd6-127">例</span><span class="sxs-lookup"><span data-stu-id="facd6-127">Example</span></span>  
 <span data-ttu-id="facd6-128">次の例では`ReadOnly` 、従業員が雇用された日付のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="facd6-128">The following example defines a `ReadOnly` property for the date on which an employee was hired.</span></span> <span data-ttu-id="facd6-129">クラスは、プロパティ値を`Private`変数として内部に格納します。クラス内のコードだけがその値を変更できます。</span><span class="sxs-lookup"><span data-stu-id="facd6-129">The class stores the property value internally as a `Private` variable, and only code inside the class can change that value.</span></span> <span data-ttu-id="facd6-130">ただし、プロパティは`Public`であり、クラスにアクセスできるすべてのコードでプロパティを読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="facd6-130">However, the property is `Public`, and any code that can access the class can read the property.</span></span>  
  
 [!code-vb[VbVbalrKeywords#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#4)]  
  
 <span data-ttu-id="facd6-131">`ReadOnly` 修飾子は、次のコンテキストで使用できます。</span><span class="sxs-lookup"><span data-stu-id="facd6-131">The `ReadOnly` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="facd6-132">Dim ステートメント</span><span class="sxs-lookup"><span data-stu-id="facd6-132">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="facd6-133">Property ステートメント</span><span class="sxs-lookup"><span data-stu-id="facd6-133">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="facd6-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="facd6-134">See also</span></span>

- [<span data-ttu-id="facd6-135">WriteOnly</span><span class="sxs-lookup"><span data-stu-id="facd6-135">WriteOnly</span></span>](../../../visual-basic/language-reference/modifiers/writeonly.md)
- [<span data-ttu-id="facd6-136">キーワード</span><span class="sxs-lookup"><span data-stu-id="facd6-136">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
