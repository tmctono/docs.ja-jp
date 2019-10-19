---
title: '方法: 構造体を宣言する (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], structures
- structure statements [Visual Basic]
- statements [Visual Basic], structure
- structures [Visual Basic], declaring
ms.assetid: d5e98381-eb81-47d4-af83-48cc534a2572
ms.openlocfilehash: c3090b5b8e53e5a5a990ae11c91464797bde9803
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582300"
---
# <a name="how-to-declare-a-structure-visual-basic"></a><span data-ttu-id="e51a2-102">方法: 構造体を宣言する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e51a2-102">How to: Declare a Structure (Visual Basic)</span></span>
<span data-ttu-id="e51a2-103">Structure[ステートメント](../../../../visual-basic/language-reference/statements/structure-statement.md)を使用して構造体の宣言を開始し、`End Structure` ステートメントで終了します。</span><span class="sxs-lookup"><span data-stu-id="e51a2-103">You begin a structure declaration with the [Structure Statement](../../../../visual-basic/language-reference/statements/structure-statement.md), and you end it with the `End Structure` statement.</span></span> <span data-ttu-id="e51a2-104">これら2つのステートメントの間には、少なくとも1つの*要素*を宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e51a2-104">Between these two statements you must declare at least one *element*.</span></span> <span data-ttu-id="e51a2-105">要素は任意のデータ型にすることができますが、少なくとも1つは非共有変数または非共有のカスタムイベントのいずれかである必要があります。</span><span class="sxs-lookup"><span data-stu-id="e51a2-105">The elements can be of any data type, but at least one must be either a nonshared variable or a nonshared, noncustom event.</span></span>  
  
 <span data-ttu-id="e51a2-106">構造体の宣言で構造体の要素を初期化することはできません。</span><span class="sxs-lookup"><span data-stu-id="e51a2-106">You cannot initialize any of the structure elements in the structure declaration.</span></span> <span data-ttu-id="e51a2-107">変数を構造体型として宣言する場合は、変数を使用して値にアクセスすることによって、要素に値を代入します。</span><span class="sxs-lookup"><span data-stu-id="e51a2-107">When you declare a variable to be of a structure type, you assign values to the elements by accessing them through the variable.</span></span>  
  
 <span data-ttu-id="e51a2-108">構造体とクラスの違いについては、「[構造体とクラス](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e51a2-108">For a discussion of the differences between structures and classes, see [Structures and Classes](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md).</span></span>  
  
 <span data-ttu-id="e51a2-109">デモンストレーションを目的として、従業員の名前、電話の内線番号、給与を追跡する状況について考えてみましょう。</span><span class="sxs-lookup"><span data-stu-id="e51a2-109">For demonstration purposes, consider a situation where you want to keep track of an employee's name, telephone extension, and salary.</span></span> <span data-ttu-id="e51a2-110">構造体を使用すると、1つの変数でこれを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="e51a2-110">A structure allows you to do this in a single variable.</span></span>  
  
### <a name="to-declare-a-structure"></a><span data-ttu-id="e51a2-111">構造体を宣言するには</span><span class="sxs-lookup"><span data-stu-id="e51a2-111">To declare a structure</span></span>  
  
1. <span data-ttu-id="e51a2-112">構造体の開始および終了ステートメントを作成します。</span><span class="sxs-lookup"><span data-stu-id="e51a2-112">Create the beginning and ending statements for the structure.</span></span>  
  
     <span data-ttu-id="e51a2-113">[Public](../../../../visual-basic/language-reference/modifiers/public.md)、 [Protected](../../../../visual-basic/language-reference/modifiers/protected.md)、 [Friend](../../../../visual-basic/language-reference/modifiers/friend.md)、または[Private](../../../../visual-basic/language-reference/modifiers/private.md)キーワードを使用して構造体のアクセスレベルを指定できます。また、既定の `Public` に設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="e51a2-113">You can specify the access level of a structure using the [Public](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), or [Private](../../../../visual-basic/language-reference/modifiers/private.md) keyword, or you can let it default to `Public`.</span></span>  
  
    ```vb  
    Private Structure employee  
    End Structure  
    ```  
  
2. <span data-ttu-id="e51a2-114">構造体の本体に要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="e51a2-114">Add elements to the body of the structure.</span></span>  
  
     <span data-ttu-id="e51a2-115">構造体には、少なくとも1つの要素が必要です。</span><span class="sxs-lookup"><span data-stu-id="e51a2-115">A structure must have at least one element.</span></span> <span data-ttu-id="e51a2-116">すべての要素を宣言し、そのアクセスレベルを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e51a2-116">You must declare every element and specify an access level for it.</span></span> <span data-ttu-id="e51a2-117">キーワードを指定せずに[Dim ステートメント](../../../../visual-basic/language-reference/statements/dim-statement.md)を使用すると、ユーザー補助の既定値は `Public` になります。</span><span class="sxs-lookup"><span data-stu-id="e51a2-117">If you use the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) without any keywords, the accessibility defaults to `Public`.</span></span>  
  
    ```vb  
    Private Structure employee  
        Public givenName As String  
        Public familyName As String  
        Public phoneExtension As Long  
        Private salary As Decimal  
        Public Sub giveRaise(raise As Double)  
            salary *= raise  
        End Sub  
        Public Event salaryReviewTime()  
    End Structure  
    ```  
  
     <span data-ttu-id="e51a2-118">前の例の `salary` フィールドは `Private` です。これは、コンテナークラスからであっても、構造体の外部ではアクセスできないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="e51a2-118">The `salary` field in the preceding example is `Private`, which means it is inaccessible outside the structure, even from the containing class.</span></span> <span data-ttu-id="e51a2-119">ただし、`giveRaise` プロシージャは `Public` ため、構造の外部から呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="e51a2-119">However, the `giveRaise` procedure is `Public`, so it can be called from outside the structure.</span></span> <span data-ttu-id="e51a2-120">同様に、構造の外部から `salaryReviewTime` イベントを発生させることもできます。</span><span class="sxs-lookup"><span data-stu-id="e51a2-120">Similarly, you can raise the `salaryReviewTime` event from outside the structure.</span></span>  
  
     <span data-ttu-id="e51a2-121">変数、`Sub` プロシージャ、およびイベントに加えて、構造体の定数、`Function` プロシージャ、およびプロパティを定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="e51a2-121">In addition to variables, `Sub` procedures, and events, you can also define constants, `Function` procedures, and properties in a structure.</span></span> <span data-ttu-id="e51a2-122">少なくとも1つの引数を指定する場合は、*既定のプロパティ*として最大で1つのプロパティを指定できます。</span><span class="sxs-lookup"><span data-stu-id="e51a2-122">You can designate at most one property as the *default property*, provided it takes at least one argument.</span></span> <span data-ttu-id="e51a2-123">[共有](../../../../visual-basic/language-reference/modifiers/shared.md)`Sub` プロシージャを使用して、イベントを処理できます。</span><span class="sxs-lookup"><span data-stu-id="e51a2-123">You can handle an event with a [Shared](../../../../visual-basic/language-reference/modifiers/shared.md)`Sub` procedure.</span></span> <span data-ttu-id="e51a2-124">詳細については、「[方法: Visual Basic で既定のプロパティを宣言して呼び出す](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e51a2-124">For more information, see [How to: Declare and Call a Default Property in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e51a2-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="e51a2-125">See also</span></span>

- [<span data-ttu-id="e51a2-126">データの種類</span><span class="sxs-lookup"><span data-stu-id="e51a2-126">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [<span data-ttu-id="e51a2-127">基本データ型</span><span class="sxs-lookup"><span data-stu-id="e51a2-127">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [<span data-ttu-id="e51a2-128">複合データ型</span><span class="sxs-lookup"><span data-stu-id="e51a2-128">Composite Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [<span data-ttu-id="e51a2-129">値型と参照型</span><span class="sxs-lookup"><span data-stu-id="e51a2-129">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [<span data-ttu-id="e51a2-130">構造体</span><span class="sxs-lookup"><span data-stu-id="e51a2-130">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="e51a2-131">トラブルシューティング (データ型)</span><span class="sxs-lookup"><span data-stu-id="e51a2-131">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="e51a2-132">構造体変数</span><span class="sxs-lookup"><span data-stu-id="e51a2-132">Structure Variables</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structure-variables.md)
- [<span data-ttu-id="e51a2-133">構造体とその他のプログラミング要素</span><span class="sxs-lookup"><span data-stu-id="e51a2-133">Structures and Other Programming Elements</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)
- [<span data-ttu-id="e51a2-134">構造体とクラス</span><span class="sxs-lookup"><span data-stu-id="e51a2-134">Structures and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)
- [<span data-ttu-id="e51a2-135">ユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="e51a2-135">User-Defined Data Type</span></span>](../../../../visual-basic/language-reference/data-types/user-defined-data-type.md)
