---
title: '方法: 構造体 (Visual Basic) を宣言します。'
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], structures
- structure statements [Visual Basic]
- statements [Visual Basic], structure
- structures [Visual Basic], declaring
ms.assetid: d5e98381-eb81-47d4-af83-48cc534a2572
ms.openlocfilehash: a52daddaa8701ccca9bd9b5b4a48535a6ffa19ed
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59343559"
---
# <a name="how-to-declare-a-structure-visual-basic"></a><span data-ttu-id="a95b8-102">方法: 構造体 (Visual Basic) を宣言します。</span><span class="sxs-lookup"><span data-stu-id="a95b8-102">How to: Declare a Structure (Visual Basic)</span></span>
<span data-ttu-id="a95b8-103">構造体の宣言を開始する、 [Structure ステートメント](../../../../visual-basic/language-reference/statements/structure-statement.md)、それを終了して、`End Structure`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="a95b8-103">You begin a structure declaration with the [Structure Statement](../../../../visual-basic/language-reference/statements/structure-statement.md), and you end it with the `End Structure` statement.</span></span> <span data-ttu-id="a95b8-104">これら 2 つのステートメントの間で、少なくとも 1 つを宣言する必要があります*要素*します。</span><span class="sxs-lookup"><span data-stu-id="a95b8-104">Between these two statements you must declare at least one *element*.</span></span> <span data-ttu-id="a95b8-105">任意のデータ型の要素ができますが、非共有変数または非共有の非カスタム イベントのいずれかに少なくとも 1 つである必要があります。</span><span class="sxs-lookup"><span data-stu-id="a95b8-105">The elements can be of any data type, but at least one must be either a nonshared variable or a nonshared, noncustom event.</span></span>  
  
 <span data-ttu-id="a95b8-106">構造体の宣言で構造体の要素を初期化することはできません。</span><span class="sxs-lookup"><span data-stu-id="a95b8-106">You cannot initialize any of the structure elements in the structure declaration.</span></span> <span data-ttu-id="a95b8-107">構造型の変数を宣言するときに、要素に、変数を通じてアクセスすることにより値を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="a95b8-107">When you declare a variable to be of a structure type, you assign values to the elements by accessing them through the variable.</span></span>  
  
 <span data-ttu-id="a95b8-108">構造体とクラス間の違いの詳細については、次を参照してください。[構造体とクラス](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)します。</span><span class="sxs-lookup"><span data-stu-id="a95b8-108">For a discussion of the differences between structures and classes, see [Structures and Classes](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md).</span></span>  
  
 <span data-ttu-id="a95b8-109">デモンストレーションを目的として、従業員の名前、電話の拡張機能と給与を追跡する必要がある状況を検討してください。</span><span class="sxs-lookup"><span data-stu-id="a95b8-109">For demonstration purposes, consider a situation where you want to keep track of an employee's name, telephone extension, and salary.</span></span> <span data-ttu-id="a95b8-110">構造体を使用すると、1 つの変数でこれを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="a95b8-110">A structure allows you to do this in a single variable.</span></span>  
  
### <a name="to-declare-a-structure"></a><span data-ttu-id="a95b8-111">構造体を宣言するには</span><span class="sxs-lookup"><span data-stu-id="a95b8-111">To declare a structure</span></span>  
  
1. <span data-ttu-id="a95b8-112">最初と最後のステートメントの構造を作成します。</span><span class="sxs-lookup"><span data-stu-id="a95b8-112">Create the beginning and ending statements for the structure.</span></span>  
  
     <span data-ttu-id="a95b8-113">使用して、構造体のアクセス レベルを指定することができます、[パブリック](../../../../visual-basic/language-reference/modifiers/public.md)、 [Protected](../../../../visual-basic/language-reference/modifiers/protected.md)、[フレンド](../../../../visual-basic/language-reference/modifiers/friend.md)、または[プライベート](../../../../visual-basic/language-reference/modifiers/private.md)キーワード、またはことことができます既定で`Public`します。</span><span class="sxs-lookup"><span data-stu-id="a95b8-113">You can specify the access level of a structure using the [Public](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), or [Private](../../../../visual-basic/language-reference/modifiers/private.md) keyword, or you can let it default to `Public`.</span></span>  
  
    ```  
    Private Structure employee  
    End Structure  
    ```  
  
2. <span data-ttu-id="a95b8-114">構造体の本文には、要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="a95b8-114">Add elements to the body of the structure.</span></span>  
  
     <span data-ttu-id="a95b8-115">構造体には、少なくとも 1 つの要素が必要です。</span><span class="sxs-lookup"><span data-stu-id="a95b8-115">A structure must have at least one element.</span></span> <span data-ttu-id="a95b8-116">すべての要素を宣言し、アクセス レベルを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a95b8-116">You must declare every element and specify an access level for it.</span></span> <span data-ttu-id="a95b8-117">使用する場合、 [Dim ステートメント](../../../../visual-basic/language-reference/statements/dim-statement.md)、キーワードを指定せずに既定でアクセシビリティ`Public`します。</span><span class="sxs-lookup"><span data-stu-id="a95b8-117">If you use the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) without any keywords, the accessibility defaults to `Public`.</span></span>  
  
    ```  
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
  
     <span data-ttu-id="a95b8-118">`salary`フィールドが前の例で`Private`、つまりは外側のクラスからでも、構造体の外部アクセスできません。</span><span class="sxs-lookup"><span data-stu-id="a95b8-118">The `salary` field in the preceding example is `Private`, which means it is inaccessible outside the structure, even from the containing class.</span></span> <span data-ttu-id="a95b8-119">ただし、`giveRaise`プロシージャが`Public`ので、構造体の外側から呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="a95b8-119">However, the `giveRaise` procedure is `Public`, so it can be called from outside the structure.</span></span> <span data-ttu-id="a95b8-120">同様に、増やすことができます、`salaryReviewTime`構造の外からのイベント。</span><span class="sxs-lookup"><span data-stu-id="a95b8-120">Similarly, you can raise the `salaryReviewTime` event from outside the structure.</span></span>  
  
     <span data-ttu-id="a95b8-121">変数に加えて`Sub`プロシージャ、およびイベント、定数を定義することもできます。`Function`プロシージャ、および構造のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="a95b8-121">In addition to variables, `Sub` procedures, and events, you can also define constants, `Function` procedures, and properties in a structure.</span></span> <span data-ttu-id="a95b8-122">として最大で 1 つのプロパティを指定することができます、*プロパティの既定*、少なくとも 1 つの引数を受け取る。</span><span class="sxs-lookup"><span data-stu-id="a95b8-122">You can designate at most one property as the *default property*, provided it takes at least one argument.</span></span> <span data-ttu-id="a95b8-123">イベントを処理することができます、 [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) `Sub`プロシージャ。</span><span class="sxs-lookup"><span data-stu-id="a95b8-123">You can handle an event with a [Shared](../../../../visual-basic/language-reference/modifiers/shared.md)`Sub` procedure.</span></span> <span data-ttu-id="a95b8-124">詳細については、「[方法 :宣言し、Visual Basic では、既定のプロパティを呼び出す](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md)します。</span><span class="sxs-lookup"><span data-stu-id="a95b8-124">For more information, see [How to: Declare and Call a Default Property in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a95b8-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="a95b8-125">See also</span></span>

- [<span data-ttu-id="a95b8-126">データの種類</span><span class="sxs-lookup"><span data-stu-id="a95b8-126">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [<span data-ttu-id="a95b8-127">基本データ型</span><span class="sxs-lookup"><span data-stu-id="a95b8-127">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [<span data-ttu-id="a95b8-128">複合データ型</span><span class="sxs-lookup"><span data-stu-id="a95b8-128">Composite Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [<span data-ttu-id="a95b8-129">値型と参照型</span><span class="sxs-lookup"><span data-stu-id="a95b8-129">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [<span data-ttu-id="a95b8-130">構造体</span><span class="sxs-lookup"><span data-stu-id="a95b8-130">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="a95b8-131">トラブルシューティング (データ型)</span><span class="sxs-lookup"><span data-stu-id="a95b8-131">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="a95b8-132">構造体変数</span><span class="sxs-lookup"><span data-stu-id="a95b8-132">Structure Variables</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structure-variables.md)
- [<span data-ttu-id="a95b8-133">構造体とその他のプログラミング要素</span><span class="sxs-lookup"><span data-stu-id="a95b8-133">Structures and Other Programming Elements</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)
- [<span data-ttu-id="a95b8-134">構造体とクラス</span><span class="sxs-lookup"><span data-stu-id="a95b8-134">Structures and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)
- [<span data-ttu-id="a95b8-135">ユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="a95b8-135">User-Defined Data Type</span></span>](../../../../visual-basic/language-reference/data-types/user-defined-data-type.md)
