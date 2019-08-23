---
title: インターフェイスの作成と実装 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- interfaces [Visual Basic], walkthroughs
- interfaces [Visual Basic], testing
- interface implementation [Visual Basic], walkthrough
- interfaces [Visual Basic], creating
ms.assetid: ded82af2-9f52-4232-98ef-fe458180f112
ms.openlocfilehash: 62e301e9eb366d14b58088d3e2cda3b567d17f5b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69923319"
---
# <a name="walkthrough-creating-and-implementing-interfaces-visual-basic"></a><span data-ttu-id="edcf2-102">チュートリアル: インターフェイスの作成と実装 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="edcf2-102">Walkthrough: Creating and Implementing Interfaces (Visual Basic)</span></span>

<span data-ttu-id="edcf2-103">インターフェイスには、プロパティ、メソッド、およびイベントの特性が記述されていますが、実装の詳細は構造体またはクラスにはありません。</span><span class="sxs-lookup"><span data-stu-id="edcf2-103">Interfaces describe the characteristics of properties, methods, and events, but leave the implementation details up to structures or classes.</span></span>  
  
 <span data-ttu-id="edcf2-104">このチュートリアルでは、インターフェイスを宣言して実装する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="edcf2-104">This walkthrough demonstrates how to declare and implement an interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="edcf2-105">このチュートリアルでは、ユーザーインターフェイスの作成方法については説明しません。</span><span class="sxs-lookup"><span data-stu-id="edcf2-105">This walkthrough doesn't provide information about how to create a user interface.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="to-define-an-interface"></a><span data-ttu-id="edcf2-106">インターフェイスを定義するには</span><span class="sxs-lookup"><span data-stu-id="edcf2-106">To define an interface</span></span>
  
1. <span data-ttu-id="edcf2-107">新しい Visual Basic Windows アプリケーション プロジェクトを開きます。</span><span class="sxs-lookup"><span data-stu-id="edcf2-107">Open a new Visual Basic Windows Application project.</span></span>  
  
2. <span data-ttu-id="edcf2-108">**[プロジェクト]** メニューの **[モジュールの追加]** をクリックして、新しいモジュールをプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="edcf2-108">Add a new module to the project by clicking **Add Module** on the **Project** menu.</span></span>  
  
3. <span data-ttu-id="edcf2-109">新しいモジュール`Module1.vb`の名前を指定し、 **[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="edcf2-109">Name the new module `Module1.vb` and click **Add**.</span></span> <span data-ttu-id="edcf2-110">新しいモジュールのコードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="edcf2-110">The code for the new module is displayed.</span></span>  
  
4. <span data-ttu-id="edcf2-111">ステートメントとステートメントの`TestInterface` `Module1` `Interface TestInterface` `End Module`間に「」と入力し、enter キーを押して、内にという名前のインターフェイスを定義します。 `Module`</span><span class="sxs-lookup"><span data-stu-id="edcf2-111">Define an interface named `TestInterface` within `Module1` by typing `Interface TestInterface` between the `Module` and `End Module` statements, and then pressing ENTER.</span></span> <span data-ttu-id="edcf2-112">**コードエディター**によって`Interface`キーワードがインデントさ`End Interface`れ、コードブロックを形成するステートメントが追加されます。</span><span class="sxs-lookup"><span data-stu-id="edcf2-112">The **Code Editor** indents the `Interface` keyword and adds an `End Interface` statement to form a code block.</span></span>  
  
5. <span data-ttu-id="edcf2-113">`End Interface`ステートメントとステートメントの`Interface`間に次のコードを配置して、インターフェイスのプロパティ、メソッド、およびイベントを定義します。</span><span class="sxs-lookup"><span data-stu-id="edcf2-113">Define a property, method, and event for the interface by placing the following code between the `Interface` and `End Interface` statements:</span></span>  
  
     [!code-vb[VbVbalrOOP#98](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#98)]
  
## <a name="implementation"></a><span data-ttu-id="edcf2-114">実装</span><span class="sxs-lookup"><span data-stu-id="edcf2-114">Implementation</span></span>

 <span data-ttu-id="edcf2-115">インターフェイスメンバーの宣言に使用される構文は、クラスメンバーの宣言に使用される構文とは異なることがあります。</span><span class="sxs-lookup"><span data-stu-id="edcf2-115">You may notice that the syntax used to declare interface members is different from the syntax used to declare class members.</span></span> <span data-ttu-id="edcf2-116">この違いは、インターフェイスに実装コードを含めることができないという事実を反映しています。</span><span class="sxs-lookup"><span data-stu-id="edcf2-116">This difference reflects the fact that interfaces cannot contain implementation code.</span></span>  
  
### <a name="to-implement-the-interface"></a><span data-ttu-id="edcf2-117">インターフェイスを実装するには</span><span class="sxs-lookup"><span data-stu-id="edcf2-117">To implement the interface</span></span>
  
1. <span data-ttu-id="edcf2-118">という`ImplementationClass`名前のクラスを追加します。 `Module1`そのために`End Interface`は、ステートメントの`End Module`後、ステートメントの前に、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="edcf2-118">Add a class named `ImplementationClass` by adding the following statement to `Module1`, after the `End Interface` statement but before the `End Module` statement, and then pressing ENTER:</span></span>  
  
     [!code-vb[VbVbalrOOP#99](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#99)]
  
     <span data-ttu-id="edcf2-119">統合開発環境内で作業している場合、enter キーを押すと`End Class` 、**コードエディター**によって一致するステートメントが提供されます。</span><span class="sxs-lookup"><span data-stu-id="edcf2-119">If you are working within the integrated development environment, the **Code Editor** supplies a matching `End Class` statement when you press ENTER.</span></span>  
  
2. <span data-ttu-id="edcf2-120">次`Implements`のステートメントをに`ImplementationClass`追加します。このステートメントは、クラスが実装するインターフェイスに名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="edcf2-120">Add the following `Implements` statement to `ImplementationClass`, which names the interface the class implements:</span></span>  
  
     [!code-vb[VbVbalrOOP#100](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#100)]
  
     <span data-ttu-id="edcf2-121">クラスまたは構造体の先頭にある他の項目とは別に`Implements`リストされている場合、ステートメントは、クラスまたは構造体がインターフェイスを実装していることを示します。</span><span class="sxs-lookup"><span data-stu-id="edcf2-121">When listed separately from other items at the top of a class or structure, the `Implements` statement indicates that the class or structure implements an interface.</span></span>  
  
     <span data-ttu-id="edcf2-122">統合開発環境内で作業している場合、enter キーを押すと、で`TestInterface`必要なクラスメンバーが**コードエディター**に実装されます。次の手順は省略できます。</span><span class="sxs-lookup"><span data-stu-id="edcf2-122">If you are working within the integrated development environment, the **Code Editor** implements the class members required by `TestInterface` when you press ENTER, and you can skip the next step.</span></span>  
  
3. <span data-ttu-id="edcf2-123">統合開発環境で作業していない場合は、インターフェイス`MyInterface`のすべてのメンバーを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="edcf2-123">If you are not working within the integrated development environment, you must implement all the members of the interface `MyInterface`.</span></span> <span data-ttu-id="edcf2-124">`ImplementationClass` `Event1`、 、および`Prop1`を実装するには、に次のコードを追加します。 `Method1`</span><span class="sxs-lookup"><span data-stu-id="edcf2-124">Add the following code to `ImplementationClass` to implement `Event1`, `Method1`, and `Prop1`:</span></span>  
  
     [!code-vb[VbVbalrOOP#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#101)]
  
     <span data-ttu-id="edcf2-125">ステートメント`Implements`は、実装されているインターフェイスとインターフェイスメンバーの名前を記述します。</span><span class="sxs-lookup"><span data-stu-id="edcf2-125">The `Implements` statement names the interface and interface member being implemented.</span></span>  
  
4. <span data-ttu-id="edcf2-126">プロパティ値を格納`Prop1`したクラスにプライベートフィールドを追加して、の定義を完了します。</span><span class="sxs-lookup"><span data-stu-id="edcf2-126">Complete the definition of `Prop1` by adding a private field to the class that stored the property value:</span></span>  
  
     [!code-vb[VbVbalrOOP#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#102)]
  
     <span data-ttu-id="edcf2-127">プロパティ get アクセサー `pval`からの値を返します。</span><span class="sxs-lookup"><span data-stu-id="edcf2-127">Return the value of the `pval` from the property get accessor.</span></span>  
  
     [!code-vb[VbVbalrOOP#103](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#103)]
  
     <span data-ttu-id="edcf2-128">プロパティセットアクセサーで`pval`の値を設定します。</span><span class="sxs-lookup"><span data-stu-id="edcf2-128">Set the value of `pval` in the property set accessor.</span></span>  
  
     [!code-vb[VbVbalrOOP#104](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#104)]
  
5. <span data-ttu-id="edcf2-129">次のコードを`Method1`追加して、の定義を完了します。</span><span class="sxs-lookup"><span data-stu-id="edcf2-129">Complete the definition of `Method1` by adding the following code.</span></span>  
  
     [!code-vb[VbVbalrOOP#105](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#105)]
  
### <a name="to-test-the-implementation-of-the-interface"></a><span data-ttu-id="edcf2-130">インターフェイスの実装をテストするには</span><span class="sxs-lookup"><span data-stu-id="edcf2-130">To test the implementation of the interface</span></span>
  
1. <span data-ttu-id="edcf2-131">**ソリューションエクスプローラー**でプロジェクトのスタートアップフォームを右クリックし、 **[コードの表示]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="edcf2-131">Right-click the startup form for your project in the **Solution Explorer**, and click **View Code**.</span></span> <span data-ttu-id="edcf2-132">エディターに、スタートアップフォームのクラスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="edcf2-132">The editor displays the class for your startup form.</span></span> <span data-ttu-id="edcf2-133">既定では、スタートアップフォームが呼び出さ`Form1`れます。</span><span class="sxs-lookup"><span data-stu-id="edcf2-133">By default, the startup form is called `Form1`.</span></span>  
  
2. <span data-ttu-id="edcf2-134">クラスに次`testInstance`のフィールドを追加します。 `Form1`</span><span class="sxs-lookup"><span data-stu-id="edcf2-134">Add the following `testInstance` field to the `Form1` class:</span></span>  
  
     [!code-vb[VbVbalrOOP#120](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#120)]
  
     <span data-ttu-id="edcf2-135">とし`testInstance` `WithEvents`て宣言する`Form1`ことで、クラスはそのイベントを処理できます。</span><span class="sxs-lookup"><span data-stu-id="edcf2-135">By declaring `testInstance` as `WithEvents`, the `Form1` class can handle its events.</span></span>  
  
3. <span data-ttu-id="edcf2-136">次のイベントハンドラーを`Form1`クラスに追加して、によって`testInstance`発生したイベントを処理します。</span><span class="sxs-lookup"><span data-stu-id="edcf2-136">Add the following event handler to the `Form1` class to handle events raised by `testInstance`:</span></span>  
  
     [!code-vb[VbVbalrOOP#106](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#106)]
  
4. <span data-ttu-id="edcf2-137">クラスにという`Test`名前のサブルーチンを追加して、実装クラスをテストします。 `Form1`</span><span class="sxs-lookup"><span data-stu-id="edcf2-137">Add a subroutine named `Test` to the `Form1` class to test the implementation class:</span></span>  
  
     [!code-vb[VbVbalrOOP#107](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#107)]
  
     <span data-ttu-id="edcf2-138">この`Test`プロシージャは、を実装`MyInterface`するクラスのインスタンスを作成し、そのインスタンス`testInstance`をフィールドに割り当て、プロパティを設定し、インターフェイスを介してメソッドを実行します。</span><span class="sxs-lookup"><span data-stu-id="edcf2-138">The `Test` procedure creates an instance of the class that implements `MyInterface`, assigns that instance to the `testInstance` field, sets a property, and runs a method through the interface.</span></span>  
  
5. <span data-ttu-id="edcf2-139">スタートアップフォームの`Form1 Load`プロシージャから`Test`プロシージャを呼び出すコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="edcf2-139">Add code to call the `Test` procedure from the `Form1 Load` procedure of your startup form:</span></span>  
  
     [!code-vb[VbVbalrOOP#108](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#108)]
  
6. <span data-ttu-id="edcf2-140">F5 キー `Test`を押してプロシージャを実行します。</span><span class="sxs-lookup"><span data-stu-id="edcf2-140">Run the `Test` procedure by pressing F5.</span></span> <span data-ttu-id="edcf2-141">"Prop1 が9に設定されました" というメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="edcf2-141">The message "Prop1 was set to 9" is displayed.</span></span> <span data-ttu-id="edcf2-142">[OK] をクリックすると、"Method1 の X パラメーターは 5" というメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="edcf2-142">After you click OK, the message "The X parameter for Method1 is 5" is displayed.</span></span> <span data-ttu-id="edcf2-143">[OK] をクリックすると、"イベントをキャッチしたイベントハンドラー" というメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="edcf2-143">Click OK, and the message "The event handler caught the event" is displayed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edcf2-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="edcf2-144">See also</span></span>

- [<span data-ttu-id="edcf2-145">Implements ステートメント</span><span class="sxs-lookup"><span data-stu-id="edcf2-145">Implements Statement</span></span>](../../../../visual-basic/language-reference/statements/implements-statement.md)
- [<span data-ttu-id="edcf2-146">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="edcf2-146">Interfaces</span></span>](../../../../visual-basic/programming-guide/language-features/interfaces/index.md)
- [<span data-ttu-id="edcf2-147">Interface ステートメント</span><span class="sxs-lookup"><span data-stu-id="edcf2-147">Interface Statement</span></span>](../../../../visual-basic/language-reference/statements/interface-statement.md)
- [<span data-ttu-id="edcf2-148">Event ステートメント</span><span class="sxs-lookup"><span data-stu-id="edcf2-148">Event Statement</span></span>](../../../../visual-basic/language-reference/statements/event-statement.md)
