---
title: '方法: 定数 (Visual Basic) の宣言します。'
ms.date: 07/20/2015
f1_keywords:
- vb.constant
helpviewer_keywords:
- Integer data type [Visual Basic], declaring constants
- Single data type [Visual Basic], declaring constants
- Const statement [Visual Basic], declaring constants
- procedures [Visual Basic], declaration
- data types [Visual Basic], constants
- Long data type [Visual Basic], declaring constants
- Visual Basic code, declaring variables and constants
- Double data type [Visual Basic], declaring constants
- Boolean data type [Visual Basic], declaring constants
- modules, declaring constants
- Byte data type [Visual Basic], declaring constants
- constants [Visual Basic], declaring
- Date data type [Visual Basic], declaring constants
- String data type [Visual Basic], declaring constants
- declaring constants [Visual Basic], const keyword
- Currency data type [Visual Basic], declaring constants and variants
- module-level constants and variables
- Object data type [Visual Basic], declaring constants
ms.assetid: f901b4fa-481f-4621-822e-427060577ad1
ms.openlocfilehash: b84afe4e354d4029bc61ba67bc93bd36a3430de4
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64610599"
---
# <a name="how-to-declare-a-constant-visual-basic"></a><span data-ttu-id="8f85b-102">方法: 定数 (Visual Basic) の宣言します。</span><span class="sxs-lookup"><span data-stu-id="8f85b-102">How to: Declare A Constant (Visual Basic)</span></span>
<span data-ttu-id="8f85b-103">使用する、`Const`定数を宣言し、その値を設定するステートメント。</span><span class="sxs-lookup"><span data-stu-id="8f85b-103">You use the `Const` statement to declare a constant and set its value.</span></span> <span data-ttu-id="8f85b-104">定数を宣言すると、値に意味のある名前を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="8f85b-104">By declaring a constant, you assign a meaningful name to a value.</span></span> <span data-ttu-id="8f85b-105">定数が宣言されると、変更または新しい値を代入することはできません。</span><span class="sxs-lookup"><span data-stu-id="8f85b-105">Once a constant is declared, it cannot be modified or assigned a new value.</span></span>  
  
 <span data-ttu-id="8f85b-106">または、モジュール、クラスまたは構造体の宣言セクションに、プロシージャ内で定数を宣言するとします。</span><span class="sxs-lookup"><span data-stu-id="8f85b-106">You declare a constant within a procedure or in the declarations section of a module, class, or structure.</span></span> <span data-ttu-id="8f85b-107">クラスまたは構造のレベルの定数は、`Private`既定では、としても宣言されている可能性がありますが、 `Public`、 `Friend`、 `Protected`、または`Protected Friend`コードへのアクセスのレベルの適切な場合。</span><span class="sxs-lookup"><span data-stu-id="8f85b-107">Class or structure-level constants are `Private` by default, but may also be declared as `Public`, `Friend`, `Protected`, or `Protected Friend` for the appropriate level of code access.</span></span>  
  
 <span data-ttu-id="8f85b-108">定数は、(、規則は、同じ変数名を作成するためのものと)、有効なシンボリック名と式で構成される数値または文字列定数、演算子、(関数呼び出しはありません) が必要です。</span><span class="sxs-lookup"><span data-stu-id="8f85b-108">The constant must have a valid symbolic name (the rules are the same as those for creating variable names) and an expression composed of numeric or string constants and operators (but no function calls).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-declare-a-constant"></a><span data-ttu-id="8f85b-109">定数を宣言するには</span><span class="sxs-lookup"><span data-stu-id="8f85b-109">To declare a constant</span></span>  
  
- <span data-ttu-id="8f85b-110">アクセス指定子を含む宣言を記述、`Const`キーワード、および次の例のように、式。</span><span class="sxs-lookup"><span data-stu-id="8f85b-110">Write a declaration that includes an access specifier, the `Const` keyword, and an expression, as in the following examples:</span></span>  
  
     [!code-vb[VbEnumsTask#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#8)]  
  
     <span data-ttu-id="8f85b-111">ときに[Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md)は`Off`と[Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)は`On`、データ型を指定することで、定数を明示的に宣言する必要があります (`Boolean`、 `Byte`、 `Char`、 `DateTime`、 `Decimal`、 `Double`、 `Integer`、 `Long`、 `Short`、 `Single`、または`String`)。</span><span class="sxs-lookup"><span data-stu-id="8f85b-111">When [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) is `Off` and [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) is `On`, you must declare a constant explicitly by specifying a data type (`Boolean`, `Byte`, `Char`, `DateTime`, `Decimal`, `Double`, `Integer`, `Long`, `Short`, `Single`, or `String`).</span></span>  
  
     <span data-ttu-id="8f85b-112">ときに`Option Infer`は`On`または`Option Strict`は`Off`、定数を宣言するにはデータ型を指定せず、`As`句。</span><span class="sxs-lookup"><span data-stu-id="8f85b-112">When `Option Infer` is `On` or `Option Strict` is `Off`, you can declare a constant without specifying a data type with an `As` clause.</span></span> <span data-ttu-id="8f85b-113">コンパイラは、定数式の型からの種類を決定します。</span><span class="sxs-lookup"><span data-stu-id="8f85b-113">The compiler determines the type of the constant from the type of the expression.</span></span> <span data-ttu-id="8f85b-114">詳細については、次を参照してください。[定数とリテラルのデータ型](constant-and-literal-data-types.md)します。</span><span class="sxs-lookup"><span data-stu-id="8f85b-114">For more information, see [Constant and Literal Data Types](constant-and-literal-data-types.md).</span></span>  
  
### <a name="to-declare-a-constant-that-has-an-explicitly-stated-data-type"></a><span data-ttu-id="8f85b-115">明示的な型を持つ定数を宣言するのには</span><span class="sxs-lookup"><span data-stu-id="8f85b-115">To declare a constant that has an explicitly stated data type</span></span>  
  
- <span data-ttu-id="8f85b-116">含む宣言を記述、`As`次の例のように、キーワードと、明示的なデータを入力します。</span><span class="sxs-lookup"><span data-stu-id="8f85b-116">Write a declaration that includes the `As` keyword and an explicit data type, as in the following examples:</span></span>  
  
     [!code-vb[VbEnumsTask#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#9)]  
  
     <span data-ttu-id="8f85b-117">コードは 1 行につき 1 つの定数のみを宣言する場合より読みやすい 1 つの行に複数の定数を宣言できます。</span><span class="sxs-lookup"><span data-stu-id="8f85b-117">You can declare multiple constants on a single line, although your code is more readable if you declare only a single constant per line.</span></span> <span data-ttu-id="8f85b-118">1 行に複数の定数を宣言する場合、すべて必要があります、同じアクセス レベル (`Public`、 `Private`、 `Friend`、 `Protected`、または`Protected Friend`)。</span><span class="sxs-lookup"><span data-stu-id="8f85b-118">If you declare multiple constants on a single line, they must all have the same access level (`Public`, `Private`, `Friend`, `Protected`, or `Protected Friend`).</span></span>  
  
### <a name="to-declare-multiple-constants-on-a-single-line"></a><span data-ttu-id="8f85b-119">1 行に複数の定数を宣言するには</span><span class="sxs-lookup"><span data-stu-id="8f85b-119">To declare multiple constants on a single line</span></span>  
  
- <span data-ttu-id="8f85b-120">宣言をコンマと次の例のように、スペースで区切ります。</span><span class="sxs-lookup"><span data-stu-id="8f85b-120">Separate the declarations with a comma and a space, as in the following example:</span></span>  
  
    ```  
    Public Const Four As Integer = 4, Five As Integer = 5, Six As Integer = 44  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="8f85b-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="8f85b-121">See also</span></span>

- [<span data-ttu-id="8f85b-122">Const ステートメント</span><span class="sxs-lookup"><span data-stu-id="8f85b-122">Const Statement</span></span>](../../../../visual-basic/language-reference/statements/const-statement.md)
- [<span data-ttu-id="8f85b-123">定数とリテラルのデータ型</span><span class="sxs-lookup"><span data-stu-id="8f85b-123">Constant and Literal Data Types</span></span>](constant-and-literal-data-types.md)
- [<span data-ttu-id="8f85b-124">定数の概要</span><span class="sxs-lookup"><span data-stu-id="8f85b-124">Constants Overview</span></span>](constants-overview.md)
- [<span data-ttu-id="8f85b-125">方法: 定数を宣言します。</span><span class="sxs-lookup"><span data-stu-id="8f85b-125">How to: Declare A Constant</span></span>](how-to-declare-a-constant.md)
- [<span data-ttu-id="8f85b-126">ユーザー定義定数</span><span class="sxs-lookup"><span data-stu-id="8f85b-126">User-Defined Constants</span></span>](user-defined-constants.md)
- [<span data-ttu-id="8f85b-127">定数とリテラルのデータ型</span><span class="sxs-lookup"><span data-stu-id="8f85b-127">Constant and Literal Data Types</span></span>](constant-and-literal-data-types.md)
- [<span data-ttu-id="8f85b-128">方法: 関連する定数値をまとめてグループ</span><span class="sxs-lookup"><span data-stu-id="8f85b-128">How to: Group Related Constant Values Together</span></span>](how-to-group-related-constant-values-together.md)
- [<span data-ttu-id="8f85b-129">列挙型の概要</span><span class="sxs-lookup"><span data-stu-id="8f85b-129">Enumerations Overview</span></span>](enumerations-overview.md)
- [<span data-ttu-id="8f85b-130">方法: 列挙体を宣言します。</span><span class="sxs-lookup"><span data-stu-id="8f85b-130">How to: Declare Enumerations</span></span>](how-to-declare-enumerations.md)
- [<span data-ttu-id="8f85b-131">方法: 列挙体のメンバーを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f85b-131">How to: Refer to an Enumeration Member</span></span>](how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="8f85b-132">列挙型と名前の修飾</span><span class="sxs-lookup"><span data-stu-id="8f85b-132">Enumerations and Name Qualification</span></span>](enumerations-and-name-qualification.md)
- [<span data-ttu-id="8f85b-133">方法: 列挙体を反復処理します。</span><span class="sxs-lookup"><span data-stu-id="8f85b-133">How to: Iterate Through An Enumeration</span></span>](how-to-iterate-through-an-enumeration.md)
- [<span data-ttu-id="8f85b-134">方法: 列挙値に関連付けられている文字列を確認します。</span><span class="sxs-lookup"><span data-stu-id="8f85b-134">How to: Determine the String Associated with an Enumeration Value</span></span>](how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [<span data-ttu-id="8f85b-135">列挙型を使用する状況</span><span class="sxs-lookup"><span data-stu-id="8f85b-135">When to Use an Enumeration</span></span>](when-to-use-an-enumeration.md)

- [<span data-ttu-id="8f85b-136">列挙型の概要</span><span class="sxs-lookup"><span data-stu-id="8f85b-136">Enumerations Overview</span></span>](enumerations-overview.md)
- [<span data-ttu-id="8f85b-137">定数の概要</span><span class="sxs-lookup"><span data-stu-id="8f85b-137">Constants Overview</span></span>](constants-overview.md)
- [<span data-ttu-id="8f85b-138">方法: 列挙体を宣言します。</span><span class="sxs-lookup"><span data-stu-id="8f85b-138">How to: Declare an Enumeration</span></span>](how-to-declare-enumerations.md)
- [<span data-ttu-id="8f85b-139">列挙型と名前の修飾</span><span class="sxs-lookup"><span data-stu-id="8f85b-139">Enumerations and Name Qualification</span></span>](enumerations-and-name-qualification.md)
- [<span data-ttu-id="8f85b-140">Option Strict ステートメント</span><span class="sxs-lookup"><span data-stu-id="8f85b-140">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="8f85b-141">定数と列挙体</span><span class="sxs-lookup"><span data-stu-id="8f85b-141">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)
