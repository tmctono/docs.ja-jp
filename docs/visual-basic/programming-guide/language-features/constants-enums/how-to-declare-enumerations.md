---
title: '方法: 列挙型を宣言する'
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], enumerations
- enumerations [Visual Basic], declaring
- declaring enumerations [Visual Basic]
ms.assetid: db4ca1c3-f429-4c81-ae81-29e0157b29fd
ms.openlocfilehash: 042aea045313bcaf3832274acf1000f87a084b72
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74354043"
---
# <a name="how-to-declare-enumerations-visual-basic"></a><span data-ttu-id="ad77c-102">方法: 列挙型を宣言する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ad77c-102">How to: Declare Enumerations (Visual Basic)</span></span>
<span data-ttu-id="ad77c-103">列挙体を作成するには、クラスまたはモジュールの宣言セクションにある `Enum` ステートメントを使用します。</span><span class="sxs-lookup"><span data-stu-id="ad77c-103">You create an enumeration with the `Enum` statement in the declarations section of a class or module.</span></span> <span data-ttu-id="ad77c-104">メソッド内で列挙を宣言することはできません。</span><span class="sxs-lookup"><span data-stu-id="ad77c-104">You cannot declare an enumeration within a method.</span></span> <span data-ttu-id="ad77c-105">適切なアクセスレベルを指定するには、`Private`、`Protected`、`Friend`、または `Public`を使用します。</span><span class="sxs-lookup"><span data-stu-id="ad77c-105">To specify the appropriate level of access, use `Private`, `Protected`, `Friend`, or `Public`.</span></span>  
  
 <span data-ttu-id="ad77c-106">`Enum` 型には、名前、基になる型、および一連のフィールドがあり、それぞれが定数を表します。</span><span class="sxs-lookup"><span data-stu-id="ad77c-106">An `Enum` type has a name, an underlying type, and a set of fields, each representing a constant.</span></span> <span data-ttu-id="ad77c-107">名前は、有効な Visual Basic .NET 修飾子である必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad77c-107">The name must be a valid Visual Basic .NET qualifier.</span></span> <span data-ttu-id="ad77c-108">基になる型は、整数型 (`Byte`、`Short`、`Long`、または `Integer`のいずれかである必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad77c-108">The underlying type must be one of the integer types—`Byte`, `Short`, `Long` or `Integer`.</span></span> <span data-ttu-id="ad77c-109">既定値は `Integer` です。</span><span class="sxs-lookup"><span data-stu-id="ad77c-109">`Integer` is the default.</span></span> <span data-ttu-id="ad77c-110">列挙は常に厳密に型指定され、整数の数値型とは交換できません。</span><span class="sxs-lookup"><span data-stu-id="ad77c-110">Enumerations are always strongly typed and are not interchangeable with integer number types.</span></span>  
  
 <span data-ttu-id="ad77c-111">列挙体に浮動小数点値を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="ad77c-111">Enumerations cannot have floating-point values.</span></span> <span data-ttu-id="ad77c-112">列挙に `Option Strict On`を持つ浮動小数点値が割り当てられている場合、コンパイラエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="ad77c-112">If an enumeration is assigned a floating-point value with `Option Strict On`, a compiler error results.</span></span> <span data-ttu-id="ad77c-113">`Option Strict` が `Off`場合、値は `Enum` の型に自動的に変換されます。</span><span class="sxs-lookup"><span data-stu-id="ad77c-113">If `Option Strict` is `Off`, the value is automatically converted to the `Enum` type.</span></span>  
  
 <span data-ttu-id="ad77c-114">名前について、および `Imports` ステートメントを使用して名前の修飾を不要にする方法については、「[列挙型と名前の修飾](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ad77c-114">For information on names, and how to use the `Imports` statement to make name qualification unnecessary, see [Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).</span></span>  
  
### <a name="to-declare-an-enumeration"></a><span data-ttu-id="ad77c-115">列挙体を宣言するには</span><span class="sxs-lookup"><span data-stu-id="ad77c-115">To declare an enumeration</span></span>  
  
1. <span data-ttu-id="ad77c-116">次の例に示すように、コードアクセスレベル、`Enum` キーワード、有効な名前を含む宣言を記述します。それぞれが異なる `Enum`を宣言します。</span><span class="sxs-lookup"><span data-stu-id="ad77c-116">Write a declaration that includes a code access level, the `Enum` keyword, and a valid name, as in the following examples, each of which declares a different `Enum`.</span></span>  
  
     [!code-vb[VbEnumsTask#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#3)]  
  
2. <span data-ttu-id="ad77c-117">列挙体の定数を定義します。</span><span class="sxs-lookup"><span data-stu-id="ad77c-117">Define the constants in the enumeration.</span></span> <span data-ttu-id="ad77c-118">既定では、列挙体の最初の定数は `0`に初期化され、後続の定数は前の定数より1つ大きい値に初期化されます。</span><span class="sxs-lookup"><span data-stu-id="ad77c-118">By default, the first constant in an enumeration is initialized to `0`, and subsequent constants are initialized to a value of one more than the previous constant.</span></span> <span data-ttu-id="ad77c-119">たとえば、次の列挙型の `Days`には、値 `0`を持つ `Sunday` という定数と、値 `1`を持つ `Monday` という名前の定数が含まれています。また、`Tuesday` という名前の定数を `2`の値と共に使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="ad77c-119">For example, the following enumeration, `Days`, contains a constant named `Sunday` with the value `0`, a constant named `Monday` with the value `1`, a constant named `Tuesday` with the value of `2`, and so on.</span></span>  
  
     [!code-vb[VbEnumsTask#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#4)]  
  
3. <span data-ttu-id="ad77c-120">代入ステートメントを使用して、列挙体の定数に値を明示的に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="ad77c-120">You can explicitly assign values to constants in an enumeration by using an assignment statement.</span></span> <span data-ttu-id="ad77c-121">負の数値を含む任意の整数値を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="ad77c-121">You can assign any integer value, including negative numbers.</span></span> <span data-ttu-id="ad77c-122">たとえば、0未満の値を持つ定数を使用して、エラー条件を表すことができます。</span><span class="sxs-lookup"><span data-stu-id="ad77c-122">For example, you may want constants with values less than zero to represent error conditions.</span></span> <span data-ttu-id="ad77c-123">次の列挙体では、定数 `Invalid` に `–1`値が明示的に割り当てられており、定数 `Sunday` に `0`値が割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="ad77c-123">In the following enumeration, the constant `Invalid` is explicitly assigned the value `–1`, and the constant `Sunday` is assigned the value `0`.</span></span> <span data-ttu-id="ad77c-124">列挙体の最初の定数であるため、`Saturday` も `0`値に初期化されます。</span><span class="sxs-lookup"><span data-stu-id="ad77c-124">Because it is the first constant in the enumeration, `Saturday` is also initialized to the value `0`.</span></span> <span data-ttu-id="ad77c-125">`Monday` の値が `1` (`Sunday`の値を超えています)。`Tuesday` の値は `2`のようになります。</span><span class="sxs-lookup"><span data-stu-id="ad77c-125">The value of `Monday` is `1` (one more than the value of `Sunday`); the value of `Tuesday` is `2`, and so on.</span></span>  
  
     [!code-vb[VbEnumsTask#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#5)]  
  
### <a name="to-declare-an-enumeration-as-an-explicit-type"></a><span data-ttu-id="ad77c-126">列挙型を明示的な型として宣言するには</span><span class="sxs-lookup"><span data-stu-id="ad77c-126">To declare an enumeration as an explicit type</span></span>  
  
- <span data-ttu-id="ad77c-127">次の例に示すように、`As` 句を使用して列挙型の型を指定します。</span><span class="sxs-lookup"><span data-stu-id="ad77c-127">Specify the type of the enum by using the `As` clause, as shown in the following example.</span></span>  
  
     [!code-vb[VbEnumsTask#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="ad77c-128">参照</span><span class="sxs-lookup"><span data-stu-id="ad77c-128">See also</span></span>

- [<span data-ttu-id="ad77c-129">列挙型と名前の修飾</span><span class="sxs-lookup"><span data-stu-id="ad77c-129">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [<span data-ttu-id="ad77c-130">方法 : 列挙型のメンバーを参照する</span><span class="sxs-lookup"><span data-stu-id="ad77c-130">How to: Refer to an Enumeration Member</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="ad77c-131">方法: Visual Basic 内の列挙体を反復処理する</span><span class="sxs-lookup"><span data-stu-id="ad77c-131">How to: Iterate Through An Enumeration in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)
- [<span data-ttu-id="ad77c-132">方法 : 列挙値に関連付けられている文字列を確認する</span><span class="sxs-lookup"><span data-stu-id="ad77c-132">How to: Determine the String Associated with an Enumeration Value</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [<span data-ttu-id="ad77c-133">列挙型を使用する状況</span><span class="sxs-lookup"><span data-stu-id="ad77c-133">When to Use an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
- [<span data-ttu-id="ad77c-134">定数の概要</span><span class="sxs-lookup"><span data-stu-id="ad77c-134">Constants Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)
- [<span data-ttu-id="ad77c-135">定数とリテラルのデータ型</span><span class="sxs-lookup"><span data-stu-id="ad77c-135">Constant and Literal Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)
- [<span data-ttu-id="ad77c-136">定数と列挙体</span><span class="sxs-lookup"><span data-stu-id="ad77c-136">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)
