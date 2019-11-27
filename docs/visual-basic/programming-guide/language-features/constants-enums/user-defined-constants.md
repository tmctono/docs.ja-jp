---
title: ユーザー定義定数
ms.date: 07/20/2015
helpviewer_keywords:
- constants [Visual Basic], circular references
- Const statement [Visual Basic], user-defined constants
- user-defined constants [Visual Basic]
- scope [Visual Basic], constants
- constants [Visual Basic], user-defined
- circular references between constants [Visual Basic]
ms.assetid: a1206d5c-c45e-4ac2-970a-4a0be6a05fdd
ms.openlocfilehash: 194a420b3749ca5c858a65c07b8c164287c1582a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74354007"
---
# <a name="user-defined-constants-visual-basic"></a><span data-ttu-id="6e016-102">ユーザー定義定数 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6e016-102">User-Defined Constants (Visual Basic)</span></span>
<span data-ttu-id="6e016-103">定数は、変更されない数値または文字列の代わりとなるわかりやすい名前です。</span><span class="sxs-lookup"><span data-stu-id="6e016-103">A constant is a meaningful name that takes the place of a number or string that does not change.</span></span> <span data-ttu-id="6e016-104">定数に格納された値は、その名が示すとおり、アプリケーションの実行中に変わることはありません。</span><span class="sxs-lookup"><span data-stu-id="6e016-104">Constants store values that, as the name implies, remain constant throughout the execution of an application.</span></span> <span data-ttu-id="6e016-105">操作するコントロールまたはコンポーネントによって定義された定数を使用することも、独自の定数を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="6e016-105">You can use constants that are defined by the controls or components you work with, or you can create your own.</span></span> <span data-ttu-id="6e016-106">自分で作成した定数は、*ユーザー定義*として記述されます。</span><span class="sxs-lookup"><span data-stu-id="6e016-106">Constants you create yourself are described as *user-defined*.</span></span>  
  
 <span data-ttu-id="6e016-107">変数名を作成する場合と同じガイドラインを使用して、`Const` ステートメントを使用して定数を宣言します。</span><span class="sxs-lookup"><span data-stu-id="6e016-107">You declare a constant with the `Const` statement, using the same guidelines you would for creating a variable name.</span></span> <span data-ttu-id="6e016-108">`Option Strict` が `On`場合は、定数型を明示的に宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e016-108">If `Option Strict` is `On`, you must explicitly declare the constant type.</span></span>  
  
## <a name="const-statement-usage"></a><span data-ttu-id="6e016-109">Const ステートメントの使用法</span><span class="sxs-lookup"><span data-stu-id="6e016-109">Const Statement Usage</span></span>  
 <span data-ttu-id="6e016-110">`Const` ステートメントは、数値または日付/時刻の数量を表すことができます。</span><span class="sxs-lookup"><span data-stu-id="6e016-110">A `Const` statement can represent a mathematical or date/time quantity:</span></span>  
  
 [!code-vb[VbEnumsTask#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#10)]  
  
 <span data-ttu-id="6e016-111">また、`String` 定数を定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="6e016-111">It also can define `String` constants:</span></span>  
  
 [!code-vb[VbEnumsTask#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#13)]  
  
 <span data-ttu-id="6e016-112">等号 (`=`) の右側にある式は、多くの場合、数値またはリテラル文字列ですが、数値または文字列を生成する式にすることもできます (ただし、その式に関数の呼び出しを含めることはできません)。</span><span class="sxs-lookup"><span data-stu-id="6e016-112">The expression on the right side of the equal sign ( `=` ) is often a number or literal string, but it also can be an expression that results in a number or string (although that expression cannot contain calls to functions).</span></span> <span data-ttu-id="6e016-113">以前に定義された定数の観点から定数を定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="6e016-113">You can even define constants in terms of previously defined constants:</span></span>  
  
 [!code-vb[VbEnumsTask#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#15)]  
  
## <a name="scope-of-user-defined-constants"></a><span data-ttu-id="6e016-114">ユーザー定義定数のスコープ</span><span class="sxs-lookup"><span data-stu-id="6e016-114">Scope of User-Defined Constants</span></span>  
 <span data-ttu-id="6e016-115">`Const` ステートメントのスコープは、同じ場所で宣言された変数と同じです。</span><span class="sxs-lookup"><span data-stu-id="6e016-115">A `Const` statement's scope is the same as that of a variable declared in the same location.</span></span> <span data-ttu-id="6e016-116">スコープは、次のいずれかの方法で指定できます。</span><span class="sxs-lookup"><span data-stu-id="6e016-116">You can specify scope in any of the following ways:</span></span>  
  
- <span data-ttu-id="6e016-117">プロシージャ内にのみ存在する定数を作成するには、そのプロシージャ内で宣言します。</span><span class="sxs-lookup"><span data-stu-id="6e016-117">To create a constant that exists only within a procedure, declare it within that procedure.</span></span>  
  
- <span data-ttu-id="6e016-118">クラス内のすべてのプロシージャで使用できる定数を作成し、そのモジュールの外部のコードには使用できないようにするには、クラスの宣言セクションで宣言します。</span><span class="sxs-lookup"><span data-stu-id="6e016-118">To create a constant available to all procedures within a class, but not to any code outside that module, declare it in the declarations section of the class.</span></span>  
  
- <span data-ttu-id="6e016-119">アセンブリのすべてのメンバーが使用できる定数を作成するには、アセンブリの外部のクライアントではなく、クラスの宣言セクションで `Friend` キーワードを使用して宣言します。</span><span class="sxs-lookup"><span data-stu-id="6e016-119">To create a constant that is available to all members of an assembly, but not to outside clients of the assembly, declare it using the `Friend` keyword in the declarations section of the class.</span></span>  
  
- <span data-ttu-id="6e016-120">アプリケーション全体で使用可能な定数を作成するには、クラスの宣言セクションで `Public` キーワードを使用して宣言します。</span><span class="sxs-lookup"><span data-stu-id="6e016-120">To create a constant available throughout the application, declare it using the `Public` keyword in the declarations section the class.</span></span>  
  
 <span data-ttu-id="6e016-121">詳細については、「[方法: 定数を宣言](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6e016-121">For more information, see [How to: Declare A Constant](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md).</span></span>  
  
### <a name="avoiding-circular-references"></a><span data-ttu-id="6e016-122">循環参照の回避</span><span class="sxs-lookup"><span data-stu-id="6e016-122">Avoiding Circular References</span></span>  
 <span data-ttu-id="6e016-123">定数は他の定数として定義できるので、誤って2つ以上の定数間に循環*参照を作成*することもできます。</span><span class="sxs-lookup"><span data-stu-id="6e016-123">Because constants can be defined in terms of other constants, it is possible to inadvertently create a *cycle*, or circular reference, between two or more constants.</span></span> <span data-ttu-id="6e016-124">循環は、次の例のように、2つ以上のパブリック定数がある場合に発生します。各定数は、もう一方の項で定義されています。</span><span class="sxs-lookup"><span data-stu-id="6e016-124">A cycle occurs when you have two or more public constants, each of which is defined in terms of the other, as in the following example:</span></span>  
  
 [!code-vb[VbEnumsTask#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#16)]  
[!code-vb[VbEnumsTask#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#17)]  
  
 <span data-ttu-id="6e016-125">循環が発生した場合、Visual Basic によってコンパイラエラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="6e016-125">If a cycle occurs, Visual Basic generates a compiler error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e016-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="6e016-126">See also</span></span>

- [<span data-ttu-id="6e016-127">Const ステートメント</span><span class="sxs-lookup"><span data-stu-id="6e016-127">Const Statement</span></span>](../../../../visual-basic/language-reference/statements/const-statement.md)
- [<span data-ttu-id="6e016-128">定数とリテラルのデータ型</span><span class="sxs-lookup"><span data-stu-id="6e016-128">Constant and Literal Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)
- [<span data-ttu-id="6e016-129">定数と列挙体</span><span class="sxs-lookup"><span data-stu-id="6e016-129">Constants and Enumerations</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/index.md)
- [<span data-ttu-id="6e016-130">定数と列挙体</span><span class="sxs-lookup"><span data-stu-id="6e016-130">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)
- [<span data-ttu-id="6e016-131">列挙型の概要</span><span class="sxs-lookup"><span data-stu-id="6e016-131">Enumerations Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)
- [<span data-ttu-id="6e016-132">定数の概要</span><span class="sxs-lookup"><span data-stu-id="6e016-132">Constants Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)
- [<span data-ttu-id="6e016-133">方法: 列挙型を宣言する</span><span class="sxs-lookup"><span data-stu-id="6e016-133">How to: Declare an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [<span data-ttu-id="6e016-134">列挙型と名前の修飾</span><span class="sxs-lookup"><span data-stu-id="6e016-134">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [<span data-ttu-id="6e016-135">Option Strict ステートメント</span><span class="sxs-lookup"><span data-stu-id="6e016-135">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
