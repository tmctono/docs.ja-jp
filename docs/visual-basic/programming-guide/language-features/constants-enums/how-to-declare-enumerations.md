---
title: '方法: (Visual Basic) 列挙型を宣言します。'
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], enumerations
- enumerations [Visual Basic], declaring
- declaring enumerations [Visual Basic]
ms.assetid: db4ca1c3-f429-4c81-ae81-29e0157b29fd
ms.openlocfilehash: f168d6d9cd6970353e75fa35a7e52cc7156fda72
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61907648"
---
# <a name="how-to-declare-enumerations-visual-basic"></a><span data-ttu-id="54dba-102">方法: (Visual Basic) 列挙型を宣言します。</span><span class="sxs-lookup"><span data-stu-id="54dba-102">How to: Declare Enumerations (Visual Basic)</span></span>
<span data-ttu-id="54dba-103">持つ列挙体を作成する、`Enum`クラスまたはモジュールの宣言セクション内のステートメント。</span><span class="sxs-lookup"><span data-stu-id="54dba-103">You create an enumeration with the `Enum` statement in the declarations section of a class or module.</span></span> <span data-ttu-id="54dba-104">メソッド内で列挙型を宣言することはできません。</span><span class="sxs-lookup"><span data-stu-id="54dba-104">You cannot declare an enumeration within a method.</span></span> <span data-ttu-id="54dba-105">適切なアクセス レベルを指定するには、使用`Private`、 `Protected`、 `Friend`、または`Public`します。</span><span class="sxs-lookup"><span data-stu-id="54dba-105">To specify the appropriate level of access, use `Private`, `Protected`, `Friend`, or `Public`.</span></span>  
  
 <span data-ttu-id="54dba-106">`Enum`型の名前、基になる型とに一連のフィールドでは、それぞれの定数を表します。</span><span class="sxs-lookup"><span data-stu-id="54dba-106">An `Enum` type has a name, an underlying type, and a set of fields, each representing a constant.</span></span> <span data-ttu-id="54dba-107">名前は、有効な Visual Basic .NET 修飾子にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="54dba-107">The name must be a valid Visual Basic .NET qualifier.</span></span> <span data-ttu-id="54dba-108">基になる型が整数型のいずれかを指定する必要があります:`Byte`、 `Short`、`Long`または`Integer`します。</span><span class="sxs-lookup"><span data-stu-id="54dba-108">The underlying type must be one of the integer types—`Byte`, `Short`, `Long` or `Integer`.</span></span> <span data-ttu-id="54dba-109">`Integer` が既定値です。</span><span class="sxs-lookup"><span data-stu-id="54dba-109">`Integer` is the default.</span></span> <span data-ttu-id="54dba-110">列挙型では、常に厳密に型指定し、整数の数値型で置き換えることはできません。</span><span class="sxs-lookup"><span data-stu-id="54dba-110">Enumerations are always strongly typed and are not interchangeable with integer number types.</span></span>  
  
 <span data-ttu-id="54dba-111">列挙体は、浮動小数点値を持つことはできません。</span><span class="sxs-lookup"><span data-stu-id="54dba-111">Enumerations cannot have floating-point values.</span></span> <span data-ttu-id="54dba-112">列挙には、浮動小数点値が割り当てられている場合`Option Strict On`、コンパイラ エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="54dba-112">If an enumeration is assigned a floating-point value with `Option Strict On`, a compiler error results.</span></span> <span data-ttu-id="54dba-113">場合`Option Strict`は`Off`に、値が自動的に変換、`Enum`型。</span><span class="sxs-lookup"><span data-stu-id="54dba-113">If `Option Strict` is `Off`, the value is automatically converted to the `Enum` type.</span></span>  
  
 <span data-ttu-id="54dba-114">使用する方法と、名について、`Imports`ステートメント、不要な名前の修飾を参照してください[列挙型と名前修飾](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)します。</span><span class="sxs-lookup"><span data-stu-id="54dba-114">For information on names, and how to use the `Imports` statement to make name qualification unnecessary, see [Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).</span></span>  
  
### <a name="to-declare-an-enumeration"></a><span data-ttu-id="54dba-115">列挙型を宣言するには</span><span class="sxs-lookup"><span data-stu-id="54dba-115">To declare an enumeration</span></span>  
  
1. <span data-ttu-id="54dba-116">コードのアクセス レベルを含む宣言を記述、`Enum`キーワード、および有効な名前を次の例のようにそれぞれの宣言を異なる`Enum`します。</span><span class="sxs-lookup"><span data-stu-id="54dba-116">Write a declaration that includes a code access level, the `Enum` keyword, and a valid name, as in the following examples, each of which declares a different `Enum`.</span></span>  
  
     [!code-vb[VbEnumsTask#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#3)]  
  
2. <span data-ttu-id="54dba-117">列挙体の定数を定義します。</span><span class="sxs-lookup"><span data-stu-id="54dba-117">Define the constants in the enumeration.</span></span> <span data-ttu-id="54dba-118">既定では、最初の定数、列挙型でに初期化`0`、され、それに続く定数よりも前の定数のいずれかの値に初期化します。</span><span class="sxs-lookup"><span data-stu-id="54dba-118">By default, the first constant in an enumeration is initialized to `0`, and subsequent constants are initialized to a value of one more than the previous constant.</span></span> <span data-ttu-id="54dba-119">たとえば、次の列挙`Days`、という名前の定数が含まれています`Sunday`値を持つ`0`、という名前の定数`Monday`値を持つ`1`、という名前の定数`Tuesday`の値を持つ`2`など。</span><span class="sxs-lookup"><span data-stu-id="54dba-119">For example, the following enumeration, `Days`, contains a constant named `Sunday` with the value `0`, a constant named `Monday` with the value `1`, a constant named `Tuesday` with the value of `2`, and so on.</span></span>  
  
     [!code-vb[VbEnumsTask#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#4)]  
  
3. <span data-ttu-id="54dba-120">代入ステートメントを使用して、列挙型の定数に値を明示的に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="54dba-120">You can explicitly assign values to constants in an enumeration by using an assignment statement.</span></span> <span data-ttu-id="54dba-121">負の数値を含む、任意の整数値を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="54dba-121">You can assign any integer value, including negative numbers.</span></span> <span data-ttu-id="54dba-122">たとえば、エラー条件を表す 0 より小さい値を持つ定数たい場合があります。</span><span class="sxs-lookup"><span data-stu-id="54dba-122">For example, you may want constants with values less than zero to represent error conditions.</span></span> <span data-ttu-id="54dba-123">次の列挙型定数`Invalid`値を明示的に割り当てられて`–1`と定数`Sunday`値が割り当てられている`0`します。</span><span class="sxs-lookup"><span data-stu-id="54dba-123">In the following enumeration, the constant `Invalid` is explicitly assigned the value `–1`, and the constant `Sunday` is assigned the value `0`.</span></span> <span data-ttu-id="54dba-124">最初の定数、列挙型である`Saturday`値にも初期化`0`します。</span><span class="sxs-lookup"><span data-stu-id="54dba-124">Because it is the first constant in the enumeration, `Saturday` is also initialized to the value `0`.</span></span> <span data-ttu-id="54dba-125">値`Monday`は`1`(いずれかの値よりも詳細`Sunday`); の値`Tuesday`は`2`など。</span><span class="sxs-lookup"><span data-stu-id="54dba-125">The value of `Monday` is `1` (one more than the value of `Sunday`); the value of `Tuesday` is `2`, and so on.</span></span>  
  
     [!code-vb[VbEnumsTask#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#5)]  
  
### <a name="to-declare-an-enumeration-as-an-explicit-type"></a><span data-ttu-id="54dba-126">明示的な型として列挙型を宣言するには</span><span class="sxs-lookup"><span data-stu-id="54dba-126">To declare an enumeration as an explicit type</span></span>  
  
-   <span data-ttu-id="54dba-127">使用して、列挙型の種類を指定、`As`句では、次の例に示すようにします。</span><span class="sxs-lookup"><span data-stu-id="54dba-127">Specify the type of the enum by using the `As` clause, as shown in the following example.</span></span>  
  
     [!code-vb[VbEnumsTask#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="54dba-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="54dba-128">See also</span></span>

- [<span data-ttu-id="54dba-129">列挙型と名前の修飾</span><span class="sxs-lookup"><span data-stu-id="54dba-129">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [<span data-ttu-id="54dba-130">方法: 列挙体のメンバーを参照してください。</span><span class="sxs-lookup"><span data-stu-id="54dba-130">How to: Refer to an Enumeration Member</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="54dba-131">方法: Visual Basic で列挙型を反復処理します。</span><span class="sxs-lookup"><span data-stu-id="54dba-131">How to: Iterate Through An Enumeration in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)
- [<span data-ttu-id="54dba-132">方法: 列挙値に関連付けられている文字列を確認します。</span><span class="sxs-lookup"><span data-stu-id="54dba-132">How to: Determine the String Associated with an Enumeration Value</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [<span data-ttu-id="54dba-133">列挙型を使用する状況</span><span class="sxs-lookup"><span data-stu-id="54dba-133">When to Use an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
- [<span data-ttu-id="54dba-134">定数の概要</span><span class="sxs-lookup"><span data-stu-id="54dba-134">Constants Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)
- [<span data-ttu-id="54dba-135">定数とリテラルのデータ型</span><span class="sxs-lookup"><span data-stu-id="54dba-135">Constant and Literal Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)
- [<span data-ttu-id="54dba-136">定数と列挙体</span><span class="sxs-lookup"><span data-stu-id="54dba-136">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)
