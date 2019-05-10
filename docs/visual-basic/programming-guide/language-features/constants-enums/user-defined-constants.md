---
title: ユーザー定義定数 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- constants [Visual Basic], circular references
- Const statement [Visual Basic], user-defined constants
- user-defined constants [Visual Basic]
- scope [Visual Basic], constants
- constants [Visual Basic], user-defined
- circular references between constants [Visual Basic]
ms.assetid: a1206d5c-c45e-4ac2-970a-4a0be6a05fdd
ms.openlocfilehash: 5d4fe5d1b9048f4a8ae22a84e14456318ca38f0f
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64645862"
---
# <a name="user-defined-constants-visual-basic"></a><span data-ttu-id="1fcd5-102">ユーザー定義定数 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1fcd5-102">User-Defined Constants (Visual Basic)</span></span>
<span data-ttu-id="1fcd5-103">定数とは、数値または変更されない文字列の代わりに使用されるわかりやすい名前です。</span><span class="sxs-lookup"><span data-stu-id="1fcd5-103">A constant is a meaningful name that takes the place of a number or string that does not change.</span></span> <span data-ttu-id="1fcd5-104">定数に格納された値は、その名が示すとおり、アプリケーションの実行中に変わることはありません。</span><span class="sxs-lookup"><span data-stu-id="1fcd5-104">Constants store values that, as the name implies, remain constant throughout the execution of an application.</span></span> <span data-ttu-id="1fcd5-105">コントロールまたは使用するコンポーネントで定義されている定数を使用することができますか、独自に作成することができます。</span><span class="sxs-lookup"><span data-stu-id="1fcd5-105">You can use constants that are defined by the controls or components you work with, or you can create your own.</span></span> <span data-ttu-id="1fcd5-106">自分で作成した定数は*ユーザー定義*します。</span><span class="sxs-lookup"><span data-stu-id="1fcd5-106">Constants you create yourself are described as *user-defined*.</span></span>  
  
 <span data-ttu-id="1fcd5-107">定数を宣言する、`Const`ステートメントでは、変数名を作成するための場合と同じガイドラインを使用します。</span><span class="sxs-lookup"><span data-stu-id="1fcd5-107">You declare a constant with the `Const` statement, using the same guidelines you would for creating a variable name.</span></span> <span data-ttu-id="1fcd5-108">場合`Option Strict`は`On`、定数の型を明示的に宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1fcd5-108">If `Option Strict` is `On`, you must explicitly declare the constant type.</span></span>  
  
## <a name="const-statement-usage"></a><span data-ttu-id="1fcd5-109">Const ステートメントの使用状況</span><span class="sxs-lookup"><span data-stu-id="1fcd5-109">Const Statement Usage</span></span>  
 <span data-ttu-id="1fcd5-110">A`Const`ステートメント、数学的表現したり、数量の日付/時刻。</span><span class="sxs-lookup"><span data-stu-id="1fcd5-110">A `Const` statement can represent a mathematical or date/time quantity:</span></span>  
  
 [!code-vb[VbEnumsTask#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#10)]  
  
 <span data-ttu-id="1fcd5-111">これも定義できます`String`定数。</span><span class="sxs-lookup"><span data-stu-id="1fcd5-111">It also can define `String` constants:</span></span>  
  
 [!code-vb[VbEnumsTask#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#13)]  
  
 <span data-ttu-id="1fcd5-112">等号の右側にある式 ( `=` )、数値またはリテラル文字列は、多くの場合は、(ただし、その式には、関数への呼び出しを含めることはできません)、数値または文字列に評価される式を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="1fcd5-112">The expression on the right side of the equal sign ( `=` ) is often a number or literal string, but it also can be an expression that results in a number or string (although that expression cannot contain calls to functions).</span></span> <span data-ttu-id="1fcd5-113">以前に定義された定数の観点から定数を定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="1fcd5-113">You can even define constants in terms of previously defined constants:</span></span>  
  
 [!code-vb[VbEnumsTask#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#15)]  
  
## <a name="scope-of-user-defined-constants"></a><span data-ttu-id="1fcd5-114">ユーザー定義関数のスコープ</span><span class="sxs-lookup"><span data-stu-id="1fcd5-114">Scope of User-Defined Constants</span></span>  
 <span data-ttu-id="1fcd5-115">A`Const`ステートメントのスコープは、同じ場所で宣言された変数の場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="1fcd5-115">A `Const` statement's scope is the same as that of a variable declared in the same location.</span></span> <span data-ttu-id="1fcd5-116">スコープは、次の方法のいずれかで指定できます。</span><span class="sxs-lookup"><span data-stu-id="1fcd5-116">You can specify scope in any of the following ways:</span></span>  
  
- <span data-ttu-id="1fcd5-117">プロシージャ内でのみ存在する定数を作成するには、そのプロシージャ内で宣言します。</span><span class="sxs-lookup"><span data-stu-id="1fcd5-117">To create a constant that exists only within a procedure, declare it within that procedure.</span></span>  
  
- <span data-ttu-id="1fcd5-118">使用できるは、そのモジュール外のコードではなく、クラス内のすべてのプロシージャに定数を作成するには、クラスの宣言セクションに宣言します。</span><span class="sxs-lookup"><span data-stu-id="1fcd5-118">To create a constant available to all procedures within a class, but not to any code outside that module, declare it in the declarations section of the class.</span></span>  
  
- <span data-ttu-id="1fcd5-119">アセンブリの外部のクライアントではなく、アセンブリでは、すべてのメンバーに使用できる定数を作成するには、宣言を使用して、`Friend`クラスの宣言セクション内のキーワード。</span><span class="sxs-lookup"><span data-stu-id="1fcd5-119">To create a constant that is available to all members of an assembly, but not to outside clients of the assembly, declare it using the `Friend` keyword in the declarations section of the class.</span></span>  
  
- <span data-ttu-id="1fcd5-120">アプリケーション全体で使用できる定数を作成するには、宣言を使用して、`Public`セクション クラスの宣言でキーワード。</span><span class="sxs-lookup"><span data-stu-id="1fcd5-120">To create a constant available throughout the application, declare it using the `Public` keyword in the declarations section the class.</span></span>  
  
 <span data-ttu-id="1fcd5-121">詳細については、「[方法 :定数を宣言](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md)します。</span><span class="sxs-lookup"><span data-stu-id="1fcd5-121">For more information, see [How to: Declare A Constant](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md).</span></span>  
  
### <a name="avoiding-circular-references"></a><span data-ttu-id="1fcd5-122">循環参照の回避</span><span class="sxs-lookup"><span data-stu-id="1fcd5-122">Avoiding Circular References</span></span>  
 <span data-ttu-id="1fcd5-123">他の定数では、定数を定義することができます、ために、誤ってを作成することは、*サイクル*、または 2 つ以上の定数との間の循環参照。</span><span class="sxs-lookup"><span data-stu-id="1fcd5-123">Because constants can be defined in terms of other constants, it is possible to inadvertently create a *cycle*, or circular reference, between two or more constants.</span></span> <span data-ttu-id="1fcd5-124">サイクルは、2 つ以上パブリック定数がある場合、次の例のように、他の観点から各が定義されているときに発生します。</span><span class="sxs-lookup"><span data-stu-id="1fcd5-124">A cycle occurs when you have two or more public constants, each of which is defined in terms of the other, as in the following example:</span></span>  
  
 [!code-vb[VbEnumsTask#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#16)]  
[!code-vb[VbEnumsTask#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#17)]  
  
 <span data-ttu-id="1fcd5-125">循環参照が発生した場合、Visual Basic には、コンパイラ エラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="1fcd5-125">If a cycle occurs, Visual Basic generates a compiler error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fcd5-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="1fcd5-126">See also</span></span>

- [<span data-ttu-id="1fcd5-127">Const ステートメント</span><span class="sxs-lookup"><span data-stu-id="1fcd5-127">Const Statement</span></span>](../../../../visual-basic/language-reference/statements/const-statement.md)
- [<span data-ttu-id="1fcd5-128">定数とリテラルのデータ型</span><span class="sxs-lookup"><span data-stu-id="1fcd5-128">Constant and Literal Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)
- [<span data-ttu-id="1fcd5-129">定数と列挙体</span><span class="sxs-lookup"><span data-stu-id="1fcd5-129">Constants and Enumerations</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/index.md)
- [<span data-ttu-id="1fcd5-130">定数と列挙体</span><span class="sxs-lookup"><span data-stu-id="1fcd5-130">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)
- [<span data-ttu-id="1fcd5-131">列挙型の概要</span><span class="sxs-lookup"><span data-stu-id="1fcd5-131">Enumerations Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)
- [<span data-ttu-id="1fcd5-132">定数の概要</span><span class="sxs-lookup"><span data-stu-id="1fcd5-132">Constants Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)
- [<span data-ttu-id="1fcd5-133">方法: 列挙体を宣言します。</span><span class="sxs-lookup"><span data-stu-id="1fcd5-133">How to: Declare an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [<span data-ttu-id="1fcd5-134">列挙型と名前の修飾</span><span class="sxs-lookup"><span data-stu-id="1fcd5-134">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [<span data-ttu-id="1fcd5-135">Option Strict ステートメント</span><span class="sxs-lookup"><span data-stu-id="1fcd5-135">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
