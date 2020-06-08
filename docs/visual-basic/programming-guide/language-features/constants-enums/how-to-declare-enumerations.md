---
title: '方法: 列挙型を宣言する'
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], enumerations
- enumerations [Visual Basic], declaring
- declaring enumerations [Visual Basic]
ms.assetid: db4ca1c3-f429-4c81-ae81-29e0157b29fd
ms.openlocfilehash: c8f228c205c93adf7f2f555dc840a7daac61950b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414454"
---
# <a name="how-to-declare-enumerations-visual-basic"></a><span data-ttu-id="fb51a-102">方法: 列挙型を宣言する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fb51a-102">How to: Declare Enumerations (Visual Basic)</span></span>
<span data-ttu-id="fb51a-103">列挙型は、クラスまたはモジュールの宣言セクションで `Enum` ステートメントを使用して作成します。</span><span class="sxs-lookup"><span data-stu-id="fb51a-103">You create an enumeration with the `Enum` statement in the declarations section of a class or module.</span></span> <span data-ttu-id="fb51a-104">メソッド内で列挙型を宣言することはできません。</span><span class="sxs-lookup"><span data-stu-id="fb51a-104">You cannot declare an enumeration within a method.</span></span> <span data-ttu-id="fb51a-105">`Private`、`Protected`、`Friend`、`Public` のいずれかを使用して、適切なアクセス レベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="fb51a-105">To specify the appropriate level of access, use `Private`, `Protected`, `Friend`, or `Public`.</span></span>  
  
 <span data-ttu-id="fb51a-106">`Enum` 型には、名前、基になる型、フィールド一式を、それぞれ定数で指定します。</span><span class="sxs-lookup"><span data-stu-id="fb51a-106">An `Enum` type has a name, an underlying type, and a set of fields, each representing a constant.</span></span> <span data-ttu-id="fb51a-107">名前は、有効な Visual Basic .NET 修飾子である必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb51a-107">The name must be a valid Visual Basic .NET qualifier.</span></span> <span data-ttu-id="fb51a-108">基になる型は、いずれかの整数型 (`Byte`、`Short`、`Long` または `Integer`) である必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb51a-108">The underlying type must be one of the integer types—`Byte`, `Short`, `Long` or `Integer`.</span></span> <span data-ttu-id="fb51a-109">`Integer` が既定値です。</span><span class="sxs-lookup"><span data-stu-id="fb51a-109">`Integer` is the default.</span></span> <span data-ttu-id="fb51a-110">列挙型の型指定は常に厳密であり、整数型との互換性はありません。</span><span class="sxs-lookup"><span data-stu-id="fb51a-110">Enumerations are always strongly typed and are not interchangeable with integer number types.</span></span>  
  
 <span data-ttu-id="fb51a-111">列挙型に浮動小数点値を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="fb51a-111">Enumerations cannot have floating-point values.</span></span> <span data-ttu-id="fb51a-112">`Option Strict On` を指定して列挙型に浮動小数点値を割り当てた場合、コンパイラ エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="fb51a-112">If an enumeration is assigned a floating-point value with `Option Strict On`, a compiler error results.</span></span> <span data-ttu-id="fb51a-113">`Option Strict` に `Off` を指定した場合は、値は自動的に `Enum` 型に変換されます。</span><span class="sxs-lookup"><span data-stu-id="fb51a-113">If `Option Strict` is `Off`, the value is automatically converted to the `Enum` type.</span></span>  
  
 <span data-ttu-id="fb51a-114">名前、および `Imports` ステートメントにより名前の修飾を不要にする方法については、[列挙型と名前の修飾](enumerations-and-name-qualification.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb51a-114">For information on names, and how to use the `Imports` statement to make name qualification unnecessary, see [Enumerations and Name Qualification](enumerations-and-name-qualification.md).</span></span>  
  
### <a name="to-declare-an-enumeration"></a><span data-ttu-id="fb51a-115">列挙型を宣言するには</span><span class="sxs-lookup"><span data-stu-id="fb51a-115">To declare an enumeration</span></span>  
  
1. <span data-ttu-id="fb51a-116">次の例に示すように、コード アクセス レベル、`Enum` キーワード、有効な名前を含む宣言を記述し、それぞれで異なる `Enum` を宣言します。</span><span class="sxs-lookup"><span data-stu-id="fb51a-116">Write a declaration that includes a code access level, the `Enum` keyword, and a valid name, as in the following examples, each of which declares a different `Enum`.</span></span>  
  
     [!code-vb[VbEnumsTask#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#3)]  
  
2. <span data-ttu-id="fb51a-117">列挙型の定数を定義します。</span><span class="sxs-lookup"><span data-stu-id="fb51a-117">Define the constants in the enumeration.</span></span> <span data-ttu-id="fb51a-118">既定では、列挙型の最初の定数は `0` に初期化され、以降の定数は前の定数より 1 大きい値に初期化されます。</span><span class="sxs-lookup"><span data-stu-id="fb51a-118">By default, the first constant in an enumeration is initialized to `0`, and subsequent constants are initialized to a value of one more than the previous constant.</span></span> <span data-ttu-id="fb51a-119">たとえば、次の列挙型 `Days` では、`Sunday` という定数の値は `0`、`Monday` という定数の値は `1`、`Tuesday` という定数の値は `2` のようになります。</span><span class="sxs-lookup"><span data-stu-id="fb51a-119">For example, the following enumeration, `Days`, contains a constant named `Sunday` with the value `0`, a constant named `Monday` with the value `1`, a constant named `Tuesday` with the value of `2`, and so on.</span></span>  
  
     [!code-vb[VbEnumsTask#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#4)]  
  
3. <span data-ttu-id="fb51a-120">代入ステートメントを使用することで、列挙型の定数に値を明示的に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="fb51a-120">You can explicitly assign values to constants in an enumeration by using an assignment statement.</span></span> <span data-ttu-id="fb51a-121">負の数値を含む任意の整数値を割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="fb51a-121">You can assign any integer value, including negative numbers.</span></span> <span data-ttu-id="fb51a-122">たとえば、エラー状態を示す 0 未満の値を定数に設定できます。</span><span class="sxs-lookup"><span data-stu-id="fb51a-122">For example, you may want constants with values less than zero to represent error conditions.</span></span> <span data-ttu-id="fb51a-123">次の列挙型では、定数 `Invalid` に値 `–1` を、定数 `Sunday` に値 `0` を明示的に割り当てています。</span><span class="sxs-lookup"><span data-stu-id="fb51a-123">In the following enumeration, the constant `Invalid` is explicitly assigned the value `–1`, and the constant `Sunday` is assigned the value `0`.</span></span> <span data-ttu-id="fb51a-124">`Saturday` は列挙型の最初の定数であるため、これも値 `0` に初期化されます。</span><span class="sxs-lookup"><span data-stu-id="fb51a-124">Because it is the first constant in the enumeration, `Saturday` is also initialized to the value `0`.</span></span> <span data-ttu-id="fb51a-125">`Monday` の値は (`Sunday` の値より 1 大きい) `1`、`Tuesday` の値は `2` のようになります。</span><span class="sxs-lookup"><span data-stu-id="fb51a-125">The value of `Monday` is `1` (one more than the value of `Sunday`); the value of `Tuesday` is `2`, and so on.</span></span>  
  
     [!code-vb[VbEnumsTask#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#5)]  
  
### <a name="to-declare-an-enumeration-as-an-explicit-type"></a><span data-ttu-id="fb51a-126">明示的な型として列挙型を宣言するには</span><span class="sxs-lookup"><span data-stu-id="fb51a-126">To declare an enumeration as an explicit type</span></span>  
  
- <span data-ttu-id="fb51a-127">列挙型の型は、次の例に示すように `As` 句を使用して指定します。</span><span class="sxs-lookup"><span data-stu-id="fb51a-127">Specify the type of the enum by using the `As` clause, as shown in the following example.</span></span>  
  
     [!code-vb[VbEnumsTask#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="fb51a-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="fb51a-128">See also</span></span>

- [<span data-ttu-id="fb51a-129">列挙型と名前の修飾</span><span class="sxs-lookup"><span data-stu-id="fb51a-129">Enumerations and Name Qualification</span></span>](enumerations-and-name-qualification.md)
- [<span data-ttu-id="fb51a-130">方法: 列挙型のメンバーを参照する</span><span class="sxs-lookup"><span data-stu-id="fb51a-130">How to: Refer to an Enumeration Member</span></span>](how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="fb51a-131">方法: Visual Basic で列挙型を反復処理する</span><span class="sxs-lookup"><span data-stu-id="fb51a-131">How to: Iterate Through An Enumeration in Visual Basic</span></span>](how-to-iterate-through-an-enumeration.md)
- [<span data-ttu-id="fb51a-132">方法: 列挙値に関連付けられている文字列を確認する</span><span class="sxs-lookup"><span data-stu-id="fb51a-132">How to: Determine the String Associated with an Enumeration Value</span></span>](how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [<span data-ttu-id="fb51a-133">列挙型を使用する状況</span><span class="sxs-lookup"><span data-stu-id="fb51a-133">When to Use an Enumeration</span></span>](when-to-use-an-enumeration.md)
- [<span data-ttu-id="fb51a-134">定数の概要</span><span class="sxs-lookup"><span data-stu-id="fb51a-134">Constants Overview</span></span>](constants-overview.md)
- [<span data-ttu-id="fb51a-135">定数とリテラルのデータ型</span><span class="sxs-lookup"><span data-stu-id="fb51a-135">Constant and Literal Data Types</span></span>](constant-and-literal-data-types.md)
- [<span data-ttu-id="fb51a-136">定数と列挙体</span><span class="sxs-lookup"><span data-stu-id="fb51a-136">Constants and Enumerations</span></span>](../../../language-reference/constants-and-enumerations.md)
