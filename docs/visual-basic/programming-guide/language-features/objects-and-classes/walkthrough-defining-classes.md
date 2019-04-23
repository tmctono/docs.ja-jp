---
title: クラスを定義する (Visual Basic)
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
ms.openlocfilehash: 3129824f6e4047420c422503cc366a1c8d28b7e7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59326217"
---
# <a name="walkthrough-defining-classes-visual-basic"></a><span data-ttu-id="97459-102">チュートリアル: クラスを定義する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="97459-102">Walkthrough: Defining Classes (Visual Basic)</span></span>

<span data-ttu-id="97459-103">このチュートリアルでは、オブジェクトを作成し使用するクラスを定義する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="97459-103">This walkthrough demonstrates how to define classes, which you can then use to create objects.</span></span> <span data-ttu-id="97459-104">また、プロパティとメソッドを新しいクラスに追加する方法を示しますされ、オブジェクトを初期化する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="97459-104">It also shows you how to add properties and methods to the new class, and demonstrates how to initialize an object.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="to-define-a-class"></a><span data-ttu-id="97459-105">クラスを定義するには</span><span class="sxs-lookup"><span data-stu-id="97459-105">To define a class</span></span>
  
1. <span data-ttu-id="97459-106">クリックしてプロジェクトを作成**新しいプロジェクト**上、**ファイル**メニュー。</span><span class="sxs-lookup"><span data-stu-id="97459-106">Create a project by clicking **New Project** on the **File** menu.</span></span> <span data-ttu-id="97459-107">**[新しいプロジェクト]** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="97459-107">The **New Project** dialog box appears.</span></span>  
  
2. <span data-ttu-id="97459-108">Windows アプリケーションを新しいプロジェクトを表示する Visual Basic プロジェクト テンプレートの一覧から選択します。</span><span class="sxs-lookup"><span data-stu-id="97459-108">Select Windows Application from the list of Visual Basic project templates to display the new project.</span></span>  
  
3. <span data-ttu-id="97459-109">クリックして、プロジェクトに新しいクラスを追加**クラスの追加**上、**プロジェクト**メニュー。</span><span class="sxs-lookup"><span data-stu-id="97459-109">Add a new class to the project by clicking **Add Class** on the **Project** menu.</span></span> <span data-ttu-id="97459-110">**[新しい項目の追加]** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="97459-110">The **Add New Item** dialog box appears.</span></span>  
  
4. <span data-ttu-id="97459-111">選択、**クラス**テンプレート。</span><span class="sxs-lookup"><span data-stu-id="97459-111">Select the **Class** template.</span></span>  
  
5. <span data-ttu-id="97459-112">新しいクラスの名前`UserNameInfo.vb`、 をクリックし、**追加**新しいクラスのコードを表示します。</span><span class="sxs-lookup"><span data-stu-id="97459-112">Name the new class `UserNameInfo.vb`, and then click **Add** to display the code for the new class.</span></span>  
  
     [!code-vb[VbVbalrOOP#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#5)]
  
    > [!NOTE]
    >  <span data-ttu-id="97459-113">Visual Basic を使用する**コード エディター** 」と入力して、スタートアップ フォームにクラスを追加する、`Class`キーワードの後に、新しいクラスの名前。</span><span class="sxs-lookup"><span data-stu-id="97459-113">You can use the Visual Basic **Code Editor** to add a class to your startup form by typing the `Class` keyword followed by the name of the new class.</span></span> <span data-ttu-id="97459-114">**コード エディター** 、対応する提供`End Class`するステートメント。</span><span class="sxs-lookup"><span data-stu-id="97459-114">The **Code Editor** provides a corresponding `End Class` statement for you.</span></span>  
  
6. <span data-ttu-id="97459-115">間に次のコードを追加することで、クラスのプライベート フィールドを定義、`Class`と`End Class`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="97459-115">Define a private field for the class by adding the following code between the `Class` and `End Class` statements:</span></span>  
  
     [!code-vb[VbVbalrOOP#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#7)]
  
     <span data-ttu-id="97459-116">フィールドとして宣言する`Private`クラス内でのみ使用できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="97459-116">Declaring the field as `Private` means it can be used only within the class.</span></span> <span data-ttu-id="97459-117">利用できるフィールドからクラスの外部でなどのアクセス修飾子を使用して`Public`のアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="97459-117">You can make fields available from outside a class by using access modifiers such as `Public` that provide more access.</span></span> <span data-ttu-id="97459-118">詳細については、[ Visual Basic のアクセス レベル](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="97459-118">For more information, see [Access levels in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
7. <span data-ttu-id="97459-119">次のコードを追加することで、クラスのプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="97459-119">Define a property for the class by adding the following code:</span></span>  
  
     [!code-vb[VbVbalrOOP#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#8)]
  
8. <span data-ttu-id="97459-120">次のコードを追加することで、クラスのメソッドを定義します。</span><span class="sxs-lookup"><span data-stu-id="97459-120">Define a method for the class by adding the following code:</span></span>  
  
     [!code-vb[VbVbalrOOP#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#9)]
  
9. <span data-ttu-id="97459-121">という名前のプロシージャを追加することで、新しいクラスのパラメーター化されたコンス トラクターを定義`Sub New`:</span><span class="sxs-lookup"><span data-stu-id="97459-121">Define a parameterized constructor for the new class by adding a procedure named `Sub New`:</span></span>  
  
     [!code-vb[VbVbalrOOP#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#10)]
  
     <span data-ttu-id="97459-122">`Sub New`コンス トラクターはこのクラスに基づくオブジェクトが作成されたときに自動的に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="97459-122">The `Sub New` constructor is called automatically when an object based on this class is created.</span></span> <span data-ttu-id="97459-123">このコンス トラクターは、ユーザー名を保持するフィールドの値を設定します。</span><span class="sxs-lookup"><span data-stu-id="97459-123">This constructor sets the value of the field that holds the user name.</span></span>  
  
## <a name="to-create-a-button-to-test-the-class"></a><span data-ttu-id="97459-124">クラスをテストするためのボタンを作成するには</span><span class="sxs-lookup"><span data-stu-id="97459-124">To create a button to test the class</span></span>
  
1. <span data-ttu-id="97459-125">その名前を右クリックしてスタートアップ フォームをデザイン モードに変更**ソリューション エクスプ ローラー**  をクリックし、**ビュー デザイナー**します。</span><span class="sxs-lookup"><span data-stu-id="97459-125">Change the startup form to design mode by right-clicking its name in **Solution Explorer** and then clicking **View Designer**.</span></span> <span data-ttu-id="97459-126">既定では、Windows アプリケーション プロジェクトのスタートアップ フォームは、Form1.vb をという名前です。</span><span class="sxs-lookup"><span data-stu-id="97459-126">By default, the startup form for Windows Application projects is named Form1.vb.</span></span> <span data-ttu-id="97459-127">メイン フォームが表示されます。</span><span class="sxs-lookup"><span data-stu-id="97459-127">The main form will then appear.</span></span>  
  
2. <span data-ttu-id="97459-128">メイン フォームにボタンを追加し、ダブルクリックのコードを表示して、`Button1_Click`イベント ハンドラー。</span><span class="sxs-lookup"><span data-stu-id="97459-128">Add a button to the main form and double-click it to display the code for the `Button1_Click` event handler.</span></span> <span data-ttu-id="97459-129">テストのプロシージャを呼び出すには、次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="97459-129">Add the following code to call the test procedure:</span></span>  
  
     [!code-vb[VbVbalrOOP#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#12)]
  
## <a name="to-run-your-application"></a><span data-ttu-id="97459-130">アプリケーションを実行するには</span><span class="sxs-lookup"><span data-stu-id="97459-130">To run your application</span></span>
  
1. <span data-ttu-id="97459-131">F5 キーを押してアプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="97459-131">Run your application by pressing F5.</span></span> <span data-ttu-id="97459-132">テストのプロシージャを呼び出すフォーム上のボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="97459-132">Click the button on the form to call the test procedure.</span></span> <span data-ttu-id="97459-133">元のことを示すメッセージを表示`UserName`"MOORE、BOBBY"は、プロシージャが呼び出されるため、`Capitalize`オブジェクトのメソッド。</span><span class="sxs-lookup"><span data-stu-id="97459-133">It displays a message stating that the original `UserName` is "MOORE, BOBBY", because the procedure called the `Capitalize` method of the object.</span></span>  
  
2. <span data-ttu-id="97459-134">**[OK]** をクリックしてメッセージ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="97459-134">Click **OK** to dismiss the message box.</span></span> <span data-ttu-id="97459-135">`Button1 Click`の値を変更する手順、`UserName`プロパティの新しい値のことを示すメッセージを表示および`UserName`"Worden、Joe"は。</span><span class="sxs-lookup"><span data-stu-id="97459-135">The `Button1 Click` procedure changes the value of the `UserName` property and displays a message stating that the new value of `UserName` is "Worden, Joe".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97459-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="97459-136">See also</span></span>

- [<span data-ttu-id="97459-137">オブジェクト指向プログラミング (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="97459-137">Object-Oriented Programming (Visual Basic)</span></span>](../../concepts/object-oriented-programming.md)
- [<span data-ttu-id="97459-138">クラスとオブジェクト</span><span class="sxs-lookup"><span data-stu-id="97459-138">Objects and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
