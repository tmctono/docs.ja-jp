---
title: クラスの定義 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- execution [Visual Basic], ending
- objects [Visual Basic], initializing
- Initialize event [Visual Basic]
- files [Visual Basic], closing
- programs [Visual Basic], quitting
- code, exiting
- objects [Visual Basic], creating
- program termination
- classes [Visual Basic], walkthroughs
- class modules, walkthroughs
- Terminate event [Visual Basic]
- execution [Visual Basic], stopping
ms.assetid: 07018828-2d49-4cf5-a44b-19fb15d9efea
ms.openlocfilehash: 679f4fd55f142c2c4bb63a556feb95c074960b12
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69914730"
---
# <a name="walkthrough-defining-classes-visual-basic"></a><span data-ttu-id="c5930-102">チュートリアル: クラスの定義 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c5930-102">Walkthrough: Defining Classes (Visual Basic)</span></span>

<span data-ttu-id="c5930-103">このチュートリアルでは、クラスを定義する方法を示します。このクラスを使用してオブジェクトを作成できます。</span><span class="sxs-lookup"><span data-stu-id="c5930-103">This walkthrough demonstrates how to define classes, which you can then use to create objects.</span></span> <span data-ttu-id="c5930-104">また、新しいクラスにプロパティとメソッドを追加する方法と、オブジェクトを初期化する方法についても説明します。</span><span class="sxs-lookup"><span data-stu-id="c5930-104">It also shows you how to add properties and methods to the new class, and demonstrates how to initialize an object.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="to-define-a-class"></a><span data-ttu-id="c5930-105">クラスを定義するには</span><span class="sxs-lookup"><span data-stu-id="c5930-105">To define a class</span></span>
  
1. <span data-ttu-id="c5930-106">**[ファイル]** メニューの **[新しいプロジェクト]** をクリックして、プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="c5930-106">Create a project by clicking **New Project** on the **File** menu.</span></span> <span data-ttu-id="c5930-107">**[新しいプロジェクト]** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c5930-107">The **New Project** dialog box appears.</span></span>  
  
2. <span data-ttu-id="c5930-108">Visual Basic プロジェクトテンプレートの一覧から [Windows アプリケーション] を選択して、新しいプロジェクトを表示します。</span><span class="sxs-lookup"><span data-stu-id="c5930-108">Select Windows Application from the list of Visual Basic project templates to display the new project.</span></span>  
  
3. <span data-ttu-id="c5930-109">**[プロジェクト]** メニューの **[クラスの追加]** をクリックして、新しいクラスをプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="c5930-109">Add a new class to the project by clicking **Add Class** on the **Project** menu.</span></span> <span data-ttu-id="c5930-110">**[新しい項目の追加]** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c5930-110">The **Add New Item** dialog box appears.</span></span>  
  
4. <span data-ttu-id="c5930-111">**クラス**テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="c5930-111">Select the **Class** template.</span></span>  
  
5. <span data-ttu-id="c5930-112">新しい`UserNameInfo.vb`クラスにという名前を指定し、 **[追加]** をクリックして新しいクラスのコードを表示します。</span><span class="sxs-lookup"><span data-stu-id="c5930-112">Name the new class `UserNameInfo.vb`, and then click **Add** to display the code for the new class.</span></span>  
  
     [!code-vb[VbVbalrOOP#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#5)]
  
    > [!NOTE]
    > <span data-ttu-id="c5930-113">Visual Basic**コードエディター**を使用して、クラスをスタートアップフォームに追加するには、 `Class`キーワードに続けて新しいクラスの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="c5930-113">You can use the Visual Basic **Code Editor** to add a class to your startup form by typing the `Class` keyword followed by the name of the new class.</span></span> <span data-ttu-id="c5930-114">**コードエディター**には、対応`End Class`するステートメントが用意されています。</span><span class="sxs-lookup"><span data-stu-id="c5930-114">The **Code Editor** provides a corresponding `End Class` statement for you.</span></span>  
  
6. <span data-ttu-id="c5930-115">ステートメントと`Class` `End Class`ステートメントの間に次のコードを追加して、クラスのプライベートフィールドを定義します。</span><span class="sxs-lookup"><span data-stu-id="c5930-115">Define a private field for the class by adding the following code between the `Class` and `End Class` statements:</span></span>  
  
     [!code-vb[VbVbalrOOP#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#7)]
  
     <span data-ttu-id="c5930-116">フィールドをとし`Private`て宣言することは、クラス内でのみ使用できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="c5930-116">Declaring the field as `Private` means it can be used only within the class.</span></span> <span data-ttu-id="c5930-117">など`Public`のアクセス修飾子を使用して、クラスの外部からフィールドを使用できるようにすることができます。これにより、より多くのアクセス権が提供されます。</span><span class="sxs-lookup"><span data-stu-id="c5930-117">You can make fields available from outside a class by using access modifiers such as `Public` that provide more access.</span></span> <span data-ttu-id="c5930-118">詳細については、[ Visual Basic のアクセス レベル](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5930-118">For more information, see [Access levels in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
7. <span data-ttu-id="c5930-119">次のコードを追加して、クラスのプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="c5930-119">Define a property for the class by adding the following code:</span></span>  
  
     [!code-vb[VbVbalrOOP#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#8)]
  
8. <span data-ttu-id="c5930-120">次のコードを追加して、クラスのメソッドを定義します。</span><span class="sxs-lookup"><span data-stu-id="c5930-120">Define a method for the class by adding the following code:</span></span>  
  
     [!code-vb[VbVbalrOOP#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#9)]
  
9. <span data-ttu-id="c5930-121">という名前`Sub New`のプロシージャを追加して、新しいクラスのパラメーター化されたコンストラクターを定義します。</span><span class="sxs-lookup"><span data-stu-id="c5930-121">Define a parameterized constructor for the new class by adding a procedure named `Sub New`:</span></span>  
  
     [!code-vb[VbVbalrOOP#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#10)]
  
     <span data-ttu-id="c5930-122">コンストラクター `Sub New`は、このクラスに基づくオブジェクトが作成されるときに自動的に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="c5930-122">The `Sub New` constructor is called automatically when an object based on this class is created.</span></span> <span data-ttu-id="c5930-123">このコンストラクターは、ユーザー名を保持するフィールドの値を設定します。</span><span class="sxs-lookup"><span data-stu-id="c5930-123">This constructor sets the value of the field that holds the user name.</span></span>  
  
## <a name="to-create-a-button-to-test-the-class"></a><span data-ttu-id="c5930-124">クラスをテストするボタンを作成するには</span><span class="sxs-lookup"><span data-stu-id="c5930-124">To create a button to test the class</span></span>
  
1. <span data-ttu-id="c5930-125">**ソリューションエクスプローラー**で名前を右クリックし、 **[デザイナーの表示]** をクリックして、スタートアップフォームをデザインモードに変更します。</span><span class="sxs-lookup"><span data-stu-id="c5930-125">Change the startup form to design mode by right-clicking its name in **Solution Explorer** and then clicking **View Designer**.</span></span> <span data-ttu-id="c5930-126">既定では、Windows アプリケーションプロジェクトのスタートアップフォームには、Form1.vb という名前が付けられています。</span><span class="sxs-lookup"><span data-stu-id="c5930-126">By default, the startup form for Windows Application projects is named Form1.vb.</span></span> <span data-ttu-id="c5930-127">メインフォームが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c5930-127">The main form will then appear.</span></span>  
  
2. <span data-ttu-id="c5930-128">メインフォームにボタンを追加し、それをダブルクリックして`Button1_Click`イベントハンドラーのコードを表示します。</span><span class="sxs-lookup"><span data-stu-id="c5930-128">Add a button to the main form and double-click it to display the code for the `Button1_Click` event handler.</span></span> <span data-ttu-id="c5930-129">次のコードを追加して、テストプロシージャを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="c5930-129">Add the following code to call the test procedure:</span></span>  
  
     [!code-vb[VbVbalrOOP#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#12)]
  
## <a name="to-run-your-application"></a><span data-ttu-id="c5930-130">アプリケーションを実行するには</span><span class="sxs-lookup"><span data-stu-id="c5930-130">To run your application</span></span>
  
1. <span data-ttu-id="c5930-131">F5 キーを押してアプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="c5930-131">Run your application by pressing F5.</span></span> <span data-ttu-id="c5930-132">フォーム上のボタンをクリックして、テストプロシージャを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="c5930-132">Click the button on the form to call the test procedure.</span></span> <span data-ttu-id="c5930-133">このメソッドは、オブジェクトのメソッドを`UserName` `Capitalize`呼び出したため、元のが "真人, 村中" であることを示すメッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="c5930-133">It displays a message stating that the original `UserName` is "MOORE, BOBBY", because the procedure called the `Capitalize` method of the object.</span></span>  
  
2. <span data-ttu-id="c5930-134">**[OK]** をクリックしてメッセージ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="c5930-134">Click **OK** to dismiss the message box.</span></span> <span data-ttu-id="c5930-135">この`Button1 Click`プロシージャは`UserName`プロパティの値を変更し、の`UserName`新しい値が "?" であることを示すメッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="c5930-135">The `Button1 Click` procedure changes the value of the `UserName` property and displays a message stating that the new value of `UserName` is "Worden, Joe".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5930-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="c5930-136">See also</span></span>

- [<span data-ttu-id="c5930-137">オブジェクト指向プログラミング (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c5930-137">Object-Oriented Programming (Visual Basic)</span></span>](../../concepts/object-oriented-programming.md)
- [<span data-ttu-id="c5930-138">クラスとオブジェクト</span><span class="sxs-lookup"><span data-stu-id="c5930-138">Objects and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
