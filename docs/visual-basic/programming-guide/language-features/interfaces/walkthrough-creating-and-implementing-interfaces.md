---
title: インターフェイスの作成と実装
ms.date: 07/20/2015
helpviewer_keywords:
- interfaces [Visual Basic], walkthroughs
- interfaces [Visual Basic], testing
- interface implementation [Visual Basic], walkthrough
- interfaces [Visual Basic], creating
ms.assetid: ded82af2-9f52-4232-98ef-fe458180f112
ms.openlocfilehash: 47176d2e7a512d8e8c27a90ac04d2a2a2af274b5
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345040"
---
# <a name="walkthrough-creating-and-implementing-interfaces-visual-basic"></a><span data-ttu-id="9613c-102">チュートリアル: インターフェイスの作成と実装 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9613c-102">Walkthrough: Creating and Implementing Interfaces (Visual Basic)</span></span>

<span data-ttu-id="9613c-103">インターフェイスには、プロパティ、メソッド、およびイベントの特性が記述されていますが、実装の詳細は構造体またはクラスにはありません。</span><span class="sxs-lookup"><span data-stu-id="9613c-103">Interfaces describe the characteristics of properties, methods, and events, but leave the implementation details up to structures or classes.</span></span>  
  
 <span data-ttu-id="9613c-104">このチュートリアルでは、インターフェイスを宣言して実装する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9613c-104">This walkthrough demonstrates how to declare and implement an interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9613c-105">このチュートリアルでは、ユーザーインターフェイスの作成方法については説明しません。</span><span class="sxs-lookup"><span data-stu-id="9613c-105">This walkthrough doesn't provide information about how to create a user interface.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="to-define-an-interface"></a><span data-ttu-id="9613c-106">インターフェイスを定義するには</span><span class="sxs-lookup"><span data-stu-id="9613c-106">To define an interface</span></span>
  
1. <span data-ttu-id="9613c-107">新しい Visual Basic Windows アプリケーション プロジェクトを開きます。</span><span class="sxs-lookup"><span data-stu-id="9613c-107">Open a new Visual Basic Windows Application project.</span></span>  
  
2. <span data-ttu-id="9613c-108">**[プロジェクト]** メニューの **[モジュールの追加]** をクリックして、新しいモジュールをプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="9613c-108">Add a new module to the project by clicking **Add Module** on the **Project** menu.</span></span>  
  
3. <span data-ttu-id="9613c-109">新しいモジュールに `Module1.vb` 名前を指定し、 **[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9613c-109">Name the new module `Module1.vb` and click **Add**.</span></span> <span data-ttu-id="9613c-110">新しいモジュールのコードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9613c-110">The code for the new module is displayed.</span></span>  
  
4. <span data-ttu-id="9613c-111">`Module` と `End Module` のステートメントの間に `Interface TestInterface` を入力し、ENTER キーを押して、`Module1` 内の `TestInterface` という名前のインターフェイスを定義します。</span><span class="sxs-lookup"><span data-stu-id="9613c-111">Define an interface named `TestInterface` within `Module1` by typing `Interface TestInterface` between the `Module` and `End Module` statements, and then pressing ENTER.</span></span> <span data-ttu-id="9613c-112">**コードエディター**によって `Interface` キーワードがインデントされ、コードブロックを形成するための `End Interface` ステートメントが追加されます。</span><span class="sxs-lookup"><span data-stu-id="9613c-112">The **Code Editor** indents the `Interface` keyword and adds an `End Interface` statement to form a code block.</span></span>  
  
5. <span data-ttu-id="9613c-113">`Interface` と `End Interface` ステートメントの間に次のコードを配置して、インターフェイスのプロパティ、メソッド、およびイベントを定義します。</span><span class="sxs-lookup"><span data-stu-id="9613c-113">Define a property, method, and event for the interface by placing the following code between the `Interface` and `End Interface` statements:</span></span>  
  
     [!code-vb[VbVbalrOOP#98](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#98)]
  
## <a name="implementation"></a><span data-ttu-id="9613c-114">実装</span><span class="sxs-lookup"><span data-stu-id="9613c-114">Implementation</span></span>

 <span data-ttu-id="9613c-115">インターフェイスメンバーの宣言に使用される構文は、クラスメンバーの宣言に使用される構文とは異なることがあります。</span><span class="sxs-lookup"><span data-stu-id="9613c-115">You may notice that the syntax used to declare interface members is different from the syntax used to declare class members.</span></span> <span data-ttu-id="9613c-116">この違いは、インターフェイスに実装コードを含めることができないという事実を反映しています。</span><span class="sxs-lookup"><span data-stu-id="9613c-116">This difference reflects the fact that interfaces cannot contain implementation code.</span></span>  
  
### <a name="to-implement-the-interface"></a><span data-ttu-id="9613c-117">インターフェイスを実装するには</span><span class="sxs-lookup"><span data-stu-id="9613c-117">To implement the interface</span></span>
  
1. <span data-ttu-id="9613c-118">`Module1`に次のステートメントを追加して、`ImplementationClass` という名前のクラスを追加します。そのためには、`End Interface` ステートメントの後、`End Module` ステートメントの前に、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="9613c-118">Add a class named `ImplementationClass` by adding the following statement to `Module1`, after the `End Interface` statement but before the `End Module` statement, and then pressing ENTER:</span></span>  
  
     [!code-vb[VbVbalrOOP#99](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#99)]
  
     <span data-ttu-id="9613c-119">統合開発環境内で作業している場合は、ENTER キーを押すと、一致する `End Class` ステートメントが**コードエディター**に表示されます。</span><span class="sxs-lookup"><span data-stu-id="9613c-119">If you are working within the integrated development environment, the **Code Editor** supplies a matching `End Class` statement when you press ENTER.</span></span>  
  
2. <span data-ttu-id="9613c-120">次の `Implements` ステートメントを `ImplementationClass`に追加します。これは、クラスが実装するインターフェイスの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="9613c-120">Add the following `Implements` statement to `ImplementationClass`, which names the interface the class implements:</span></span>  
  
     [!code-vb[VbVbalrOOP#100](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#100)]
  
     <span data-ttu-id="9613c-121">クラスまたは構造体の先頭にある他の項目とは別にリストされている場合、`Implements` ステートメントは、クラスまたは構造体がインターフェイスを実装していることを示します。</span><span class="sxs-lookup"><span data-stu-id="9613c-121">When listed separately from other items at the top of a class or structure, the `Implements` statement indicates that the class or structure implements an interface.</span></span>  
  
     <span data-ttu-id="9613c-122">統合開発環境内で作業している場合、ENTER キーを押したときに `TestInterface` に必要なクラスメンバーが**コードエディター**に実装され、次の手順は省略できます。</span><span class="sxs-lookup"><span data-stu-id="9613c-122">If you are working within the integrated development environment, the **Code Editor** implements the class members required by `TestInterface` when you press ENTER, and you can skip the next step.</span></span>  
  
3. <span data-ttu-id="9613c-123">統合開発環境内で作業していない場合は、`MyInterface`インターフェイスのすべてのメンバーを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9613c-123">If you are not working within the integrated development environment, you must implement all the members of the interface `MyInterface`.</span></span> <span data-ttu-id="9613c-124">`ImplementationClass` に次のコードを追加して、`Event1`、`Method1`、および `Prop1`を実装します。</span><span class="sxs-lookup"><span data-stu-id="9613c-124">Add the following code to `ImplementationClass` to implement `Event1`, `Method1`, and `Prop1`:</span></span>  
  
     [!code-vb[VbVbalrOOP#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#101)]
  
     <span data-ttu-id="9613c-125">`Implements` ステートメントは、実装されているインターフェイスとインターフェイスメンバーの名前を記述します。</span><span class="sxs-lookup"><span data-stu-id="9613c-125">The `Implements` statement names the interface and interface member being implemented.</span></span>  
  
4. <span data-ttu-id="9613c-126">プロパティ値を格納したクラスにプライベートフィールドを追加して、`Prop1` の定義を完了します。</span><span class="sxs-lookup"><span data-stu-id="9613c-126">Complete the definition of `Prop1` by adding a private field to the class that stored the property value:</span></span>  
  
     [!code-vb[VbVbalrOOP#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#102)]
  
     <span data-ttu-id="9613c-127">プロパティ get アクセサーから `pval` の値を返します。</span><span class="sxs-lookup"><span data-stu-id="9613c-127">Return the value of the `pval` from the property get accessor.</span></span>  
  
     [!code-vb[VbVbalrOOP#103](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#103)]
  
     <span data-ttu-id="9613c-128">プロパティセットアクセサーの `pval` の値を設定します。</span><span class="sxs-lookup"><span data-stu-id="9613c-128">Set the value of `pval` in the property set accessor.</span></span>  
  
     [!code-vb[VbVbalrOOP#104](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#104)]
  
5. <span data-ttu-id="9613c-129">次のコードを追加して、`Method1` の定義を完了します。</span><span class="sxs-lookup"><span data-stu-id="9613c-129">Complete the definition of `Method1` by adding the following code.</span></span>  
  
     [!code-vb[VbVbalrOOP#105](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#105)]
  
### <a name="to-test-the-implementation-of-the-interface"></a><span data-ttu-id="9613c-130">インターフェイスの実装をテストするには</span><span class="sxs-lookup"><span data-stu-id="9613c-130">To test the implementation of the interface</span></span>
  
1. <span data-ttu-id="9613c-131">**ソリューションエクスプローラー**でプロジェクトのスタートアップフォームを右クリックし、 **[コードの表示]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9613c-131">Right-click the startup form for your project in the **Solution Explorer**, and click **View Code**.</span></span> <span data-ttu-id="9613c-132">エディターに、スタートアップフォームのクラスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9613c-132">The editor displays the class for your startup form.</span></span> <span data-ttu-id="9613c-133">既定では、スタートアップフォームは `Form1`と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="9613c-133">By default, the startup form is called `Form1`.</span></span>  
  
2. <span data-ttu-id="9613c-134">次の `testInstance` フィールドを `Form1` クラスに追加します。</span><span class="sxs-lookup"><span data-stu-id="9613c-134">Add the following `testInstance` field to the `Form1` class:</span></span>  
  
     [!code-vb[VbVbalrOOP#120](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#120)]
  
     <span data-ttu-id="9613c-135">`testInstance` を `WithEvents`として宣言することで、`Form1` クラスはそのイベントを処理できます。</span><span class="sxs-lookup"><span data-stu-id="9613c-135">By declaring `testInstance` as `WithEvents`, the `Form1` class can handle its events.</span></span>  
  
3. <span data-ttu-id="9613c-136">`testInstance`によって発生したイベントを処理するために、次のイベントハンドラーを `Form1` クラスに追加します。</span><span class="sxs-lookup"><span data-stu-id="9613c-136">Add the following event handler to the `Form1` class to handle events raised by `testInstance`:</span></span>  
  
     [!code-vb[VbVbalrOOP#106](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#106)]
  
4. <span data-ttu-id="9613c-137">`Test` という名前のサブルーチンを `Form1` クラスに追加して、実装クラスをテストします。</span><span class="sxs-lookup"><span data-stu-id="9613c-137">Add a subroutine named `Test` to the `Form1` class to test the implementation class:</span></span>  
  
     [!code-vb[VbVbalrOOP#107](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#107)]
  
     <span data-ttu-id="9613c-138">`Test` プロシージャは、`MyInterface`を実装するクラスのインスタンスを作成し、そのインスタンスを `testInstance` フィールドに割り当て、プロパティを設定して、インターフェイスを介してメソッドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9613c-138">The `Test` procedure creates an instance of the class that implements `MyInterface`, assigns that instance to the `testInstance` field, sets a property, and runs a method through the interface.</span></span>  
  
5. <span data-ttu-id="9613c-139">スタートアップフォームの `Form1 Load` プロシージャから `Test` プロシージャを呼び出すコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="9613c-139">Add code to call the `Test` procedure from the `Form1 Load` procedure of your startup form:</span></span>  
  
     [!code-vb[VbVbalrOOP#108](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#108)]
  
6. <span data-ttu-id="9613c-140">F5 キーを押して `Test` プロシージャを実行します。</span><span class="sxs-lookup"><span data-stu-id="9613c-140">Run the `Test` procedure by pressing F5.</span></span> <span data-ttu-id="9613c-141">"Prop1 が9に設定されました" というメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9613c-141">The message "Prop1 was set to 9" is displayed.</span></span> <span data-ttu-id="9613c-142">[OK] をクリックすると、"Method1 の X パラメーターは 5" というメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9613c-142">After you click OK, the message "The X parameter for Method1 is 5" is displayed.</span></span> <span data-ttu-id="9613c-143">[OK] をクリックすると、"イベントをキャッチしたイベントハンドラー" というメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9613c-143">Click OK, and the message "The event handler caught the event" is displayed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9613c-144">参照</span><span class="sxs-lookup"><span data-stu-id="9613c-144">See also</span></span>

- [<span data-ttu-id="9613c-145">Implements ステートメント</span><span class="sxs-lookup"><span data-stu-id="9613c-145">Implements Statement</span></span>](../../../../visual-basic/language-reference/statements/implements-statement.md)
- [<span data-ttu-id="9613c-146">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9613c-146">Interfaces</span></span>](../../../../visual-basic/programming-guide/language-features/interfaces/index.md)
- [<span data-ttu-id="9613c-147">Interface ステートメント</span><span class="sxs-lookup"><span data-stu-id="9613c-147">Interface Statement</span></span>](../../../../visual-basic/language-reference/statements/interface-statement.md)
- [<span data-ttu-id="9613c-148">Event ステートメント</span><span class="sxs-lookup"><span data-stu-id="9613c-148">Event Statement</span></span>](../../../../visual-basic/language-reference/statements/event-statement.md)
