---
title: '方法: Visual C# の機能を使用して Office 相互運用オブジェクトにアクセスする - C# プログラミング ガイド'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- optional parameters [C#], Office programming
- named and optional arguments [C#], Office programming
- dynamic [C#], Office programming
- optional arguments [C#], Office programming
- named arguments [C#], Office programming
- Office programming [C#]
ms.assetid: 041b25c2-3512-4e0f-a4ea-ceb2999e4d5e
ms.openlocfilehash: 19fff39969933baa2510458400cabf9646e0c48d
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2019
ms.locfileid: "69589126"
---
# <a name="how-to-access-office-interop-objects-by-using-visual-c-features-c-programming-guide"></a><span data-ttu-id="0ab94-102">方法: Visual C# の機能を使用して Office 相互運用オブジェクトにアクセスする (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="0ab94-102">How to: Access Office Interop Objects by Using Visual C# Features (C# Programming Guide)</span></span>

<span data-ttu-id="0ab94-103">Visual C# には、Office API オブジェクトへのアクセスを容易にする機能があります。</span><span class="sxs-lookup"><span data-stu-id="0ab94-103">Visual C# has features that simplify access to Office API objects.</span></span> <span data-ttu-id="0ab94-104">新機能は、名前付き引数と省略可能な引数、`dynamic` と呼ばれる新しい型、値パラメーターの場合と同様に COM メソッドの参照パラメーターに引数を渡す機能などです。</span><span class="sxs-lookup"><span data-stu-id="0ab94-104">The new features include named and optional arguments, a new type called `dynamic`, and the ability to pass arguments to reference parameters in COM methods as if they were value parameters.</span></span>

<span data-ttu-id="0ab94-105">このトピックでは、新機能を使用して、Microsoft Office Excel ワークシートを作成および表示するコードを記述します。</span><span class="sxs-lookup"><span data-stu-id="0ab94-105">In this topic you will use the new features to write code that creates and displays a Microsoft Office Excel worksheet.</span></span> <span data-ttu-id="0ab94-106">その後、Excel ワークシートにリンクされているアイコンを含む Office Word 文書を追加するコードを記述します。</span><span class="sxs-lookup"><span data-stu-id="0ab94-106">You will then write code to add an Office Word document that contains an icon that is linked to the Excel worksheet.</span></span>

<span data-ttu-id="0ab94-107">このチュートリアルを実行するには、Microsoft Office Excel 2007 と Microsoft Office Word 2007 またはそれ以降のバージョンがコンピューターにインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="0ab94-107">To complete this walkthrough, you must have Microsoft Office Excel 2007 and Microsoft Office Word 2007, or later versions, installed on your computer.</span></span>

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-create-a-new-console-application"></a><span data-ttu-id="0ab94-108">新しいコンソール アプリケーションを作成するには</span><span class="sxs-lookup"><span data-stu-id="0ab94-108">To create a new console application</span></span>

1. <span data-ttu-id="0ab94-109">Visual Studio を起動します。</span><span class="sxs-lookup"><span data-stu-id="0ab94-109">Start Visual Studio.</span></span>

2. <span data-ttu-id="0ab94-110">**[ファイル]** メニューの **[新規作成]** をポイントし、 **[プロジェクト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0ab94-110">On the **File** menu, point to **New**, and then click **Project**.</span></span> <span data-ttu-id="0ab94-111">**[新しいプロジェクト]** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0ab94-111">The **New Project** dialog box appears.</span></span>

3. <span data-ttu-id="0ab94-112">**[インストールされたテンプレート]** ペインで、 **[Visual C#]** を展開し、 **[Windows]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0ab94-112">In the **Installed Templates** pane, expand **Visual C#**, and then click **Windows**.</span></span>

4. <span data-ttu-id="0ab94-113">**[新しいプロジェクト]** ダイアログ ボックスの上部で、 **.NET Framework 4** (またはそれ以降のバージョン) がターゲット フレームワークとして選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0ab94-113">Look at the top of the **New Project** dialog box to make sure that **.NET Framework 4** (or later version) is selected as a target framework.</span></span>

5. <span data-ttu-id="0ab94-114">**[テンプレート]** ペインの **[コンソール アプリケーション]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0ab94-114">In the **Templates** pane, click **Console Application**.</span></span>

6. <span data-ttu-id="0ab94-115">**[名前]** フィールドに、プロジェクトの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="0ab94-115">Type a name for your project in the **Name** field.</span></span>

7. <span data-ttu-id="0ab94-116">Click **OK**.</span><span class="sxs-lookup"><span data-stu-id="0ab94-116">Click **OK**.</span></span>

     <span data-ttu-id="0ab94-117">**ソリューション エクスプローラー**に新しいプロジェクトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0ab94-117">The new project appears in **Solution Explorer**.</span></span>

## <a name="to-add-references"></a><span data-ttu-id="0ab94-118">参照を追加するには</span><span class="sxs-lookup"><span data-stu-id="0ab94-118">To add references</span></span>

1. <span data-ttu-id="0ab94-119">**ソリューション エクスプローラー**で、プロジェクトの名前を右クリックし、 **[参照の追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0ab94-119">In **Solution Explorer**, right-click your project's name and then click **Add Reference**.</span></span> <span data-ttu-id="0ab94-120">**[参照の追加]** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0ab94-120">The **Add Reference** dialog box appears.</span></span>

2. <span data-ttu-id="0ab94-121">**[アセンブリ]** ページの **[コンポーネント名]** 一覧で **[Microsoft.Office.Interop.Word]** を選択し、Ctrl キーを押しながら **[Microsoft.Office.Interop.Excel]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0ab94-121">On the **Assemblies**  page, select **Microsoft.Office.Interop.Word** in the **Component Name** list, and then hold down the CTRL key and select **Microsoft.Office.Interop.Excel**.</span></span>  <span data-ttu-id="0ab94-122">アセンブリが表示されない場合は、それをインストールして表示させることが必要になる場合があります (「[方法: Office のプライマリ相互運用機能アセンブリをインストールする](/visualstudio/vsto/how-to-install-office-primary-interop-assemblies)」を参照)</span><span class="sxs-lookup"><span data-stu-id="0ab94-122">If you do not see the assemblies, you may need to ensure they are installed and displayed (see [How to: Install Office Primary Interop Assemblies](/visualstudio/vsto/how-to-install-office-primary-interop-assemblies))</span></span>

3. <span data-ttu-id="0ab94-123">Click **OK**.</span><span class="sxs-lookup"><span data-stu-id="0ab94-123">Click **OK**.</span></span>

## <a name="to-add-necessary-using-directives"></a><span data-ttu-id="0ab94-124">ディレクティブを使用して必要なものを追加するには</span><span class="sxs-lookup"><span data-stu-id="0ab94-124">To add necessary using directives</span></span>

1. <span data-ttu-id="0ab94-125">**ソリューション エクスプローラー**で、**Program.cs** ファイルを右クリックし、 **[コードの表示]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0ab94-125">In **Solution Explorer**, right-click the **Program.cs** file and then click **View Code**.</span></span>

2. <span data-ttu-id="0ab94-126">次の `using` ディレクティブをコード ファイルの先頭に追加します。</span><span class="sxs-lookup"><span data-stu-id="0ab94-126">Add the following `using` directives to the top of the code file.</span></span>

     [!code-csharp[csProgGuideOfficeHowTo#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#1)]

## <a name="to-create-a-list-of-bank-accounts"></a><span data-ttu-id="0ab94-127">銀行口座の一覧を作成するには</span><span class="sxs-lookup"><span data-stu-id="0ab94-127">To create a list of bank accounts</span></span>

1. <span data-ttu-id="0ab94-128">次のクラス定義を **Program.cs** の `Program` クラスの下に貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="0ab94-128">Paste the following class definition into **Program.cs**, under the `Program` class.</span></span>

     [!code-csharp[csProgGuideOfficeHowTo#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#2)]

2. <span data-ttu-id="0ab94-129">次のコードを `Main` メソッドに追加して、2 つの口座を含む `bankAccounts` 一覧を作成します。</span><span class="sxs-lookup"><span data-stu-id="0ab94-129">Add the following code to the `Main` method to create a `bankAccounts` list that contains two accounts.</span></span>

     [!code-csharp[csProgGuideOfficeHowTo#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#3)]

## <a name="to-declare-a-method-that-exports-account-information-to-excel"></a><span data-ttu-id="0ab94-130">口座情報を Excel にエクスポートするメソッドを宣言するには</span><span class="sxs-lookup"><span data-stu-id="0ab94-130">To declare a method that exports account information to Excel</span></span>

1. <span data-ttu-id="0ab94-131">次のメソッドを `Program` クラスに追加して、Excel ワークシートを設定します。</span><span class="sxs-lookup"><span data-stu-id="0ab94-131">Add the following method to the `Program` class to set up an Excel worksheet.</span></span>

     <span data-ttu-id="0ab94-132"><xref:Microsoft.Office.Interop.Excel.Workbooks.Add%2A> メソッドには、特定のテンプレートを指定する省略可能なパラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="0ab94-132">Method <xref:Microsoft.Office.Interop.Excel.Workbooks.Add%2A> has an optional parameter for specifying a particular template.</span></span> <span data-ttu-id="0ab94-133">C# 4 の新機能であるオプションのパラメーターでは、パラメーターの既定値を使用する場合は、そのパラメーターの引数を省略することができます。</span><span class="sxs-lookup"><span data-stu-id="0ab94-133">Optional parameters, new in C# 4, enable you to omit the argument for that parameter if you want to use the parameter's default value.</span></span> <span data-ttu-id="0ab94-134">次のコードで引数が渡されないため、`Add` は、既定のテンプレートを使用して、新しいブックを作成します。</span><span class="sxs-lookup"><span data-stu-id="0ab94-134">Because no argument is sent in the following code, `Add` uses the default template and creates a new workbook.</span></span> <span data-ttu-id="0ab94-135">以前のバージョンの C# では、同等のステートメントには、プレースホルダーの引数 `ExcelApp.Workbooks.Add(Type.Missing)` が必要です。</span><span class="sxs-lookup"><span data-stu-id="0ab94-135">The equivalent statement in earlier versions of C# requires a placeholder argument: `ExcelApp.Workbooks.Add(Type.Missing)`.</span></span>

     [!code-csharp[csProgGuideOfficeHowTo#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#4)]

2. <span data-ttu-id="0ab94-136">次のコードを `DisplayInExcel` の末尾に追加します。</span><span class="sxs-lookup"><span data-stu-id="0ab94-136">Add the following code at the end of `DisplayInExcel`.</span></span> <span data-ttu-id="0ab94-137">このコードでは、ワークシートの最初の行の最初の 2 つの列に値が挿入されます。</span><span class="sxs-lookup"><span data-stu-id="0ab94-137">The code inserts values into the first two columns of the first row of the worksheet.</span></span>

     [!code-csharp[csProgGuideOfficeHowTo#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#5)]

3. <span data-ttu-id="0ab94-138">次のコードを `DisplayInExcel` の末尾に追加します。</span><span class="sxs-lookup"><span data-stu-id="0ab94-138">Add the following code at the end of `DisplayInExcel`.</span></span> <span data-ttu-id="0ab94-139">`foreach` ループでは、ワークシートの連続した行の最初の 2 つの列に口座の一覧の情報が配置されます。</span><span class="sxs-lookup"><span data-stu-id="0ab94-139">The `foreach` loop puts the information from the list of accounts into the first two columns of successive rows of the worksheet.</span></span>

     [!code-csharp[csProgGuideOfficeHowTo#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#7)]

4. <span data-ttu-id="0ab94-140">次のコードを `DisplayInExcel` の末尾に追加して、コンテンツに合わせて列の幅を調整します。</span><span class="sxs-lookup"><span data-stu-id="0ab94-140">Add the following code at the end of `DisplayInExcel` to adjust the column widths to fit the content.</span></span>

     [!code-csharp[csProgGuideOfficeHowTo#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#13)]

     <span data-ttu-id="0ab94-141">C# の以前のバージョンでは、`ExcelApp.Columns[1]` が `Object` を返し、`AutoFit` が Excel <xref:Microsoft.Office.Interop.Excel.Range> メソッドであるため、これらの操作の明示的なキャストが必要です。</span><span class="sxs-lookup"><span data-stu-id="0ab94-141">Earlier versions of C# require explicit casting for these operations because `ExcelApp.Columns[1]` returns an `Object`, and `AutoFit` is an Excel <xref:Microsoft.Office.Interop.Excel.Range> method.</span></span> <span data-ttu-id="0ab94-142">次の行にキャストを示します。</span><span class="sxs-lookup"><span data-stu-id="0ab94-142">The following lines show the casting.</span></span>

     [!code-csharp[csProgGuideOfficeHowTo#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#14)]

     <span data-ttu-id="0ab94-143">C# 4 以降のバージョンでは、アセンブリが [/link](../../language-reference/compiler-options/link-compiler-option.md) コンパイラ オプションで参照される場合、または同等に、Excel の **[相互運用機能型の埋め込み]** プロパティが true に設定されている場合は、返される `Object` が `dynamic` に自動的に変換されます。</span><span class="sxs-lookup"><span data-stu-id="0ab94-143">C# 4, and later versions, converts the returned `Object` to `dynamic` automatically if the assembly is referenced by the [/link](../../language-reference/compiler-options/link-compiler-option.md) compiler option or, equivalently, if the Excel **Embed Interop Types** property is set to true.</span></span> <span data-ttu-id="0ab94-144">このプロパティの既定値は true です。</span><span class="sxs-lookup"><span data-stu-id="0ab94-144">True is the default value for this property.</span></span>

## <a name="to-run-the-project"></a><span data-ttu-id="0ab94-145">プロジェクトを実行するには</span><span class="sxs-lookup"><span data-stu-id="0ab94-145">To run the project</span></span>

1. <span data-ttu-id="0ab94-146">`Main` の末尾に次の行を追加します。</span><span class="sxs-lookup"><span data-stu-id="0ab94-146">Add the following line at the end of `Main`.</span></span>

     [!code-csharp[csProgGuideOfficeHowTo#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#8)]

2. <span data-ttu-id="0ab94-147">Ctrl キーを押しながら、F5 キーを押します。</span><span class="sxs-lookup"><span data-stu-id="0ab94-147">Press CTRL+F5.</span></span>

     <span data-ttu-id="0ab94-148">2 つの口座からのデータを含む Excel ワークシートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0ab94-148">An Excel worksheet appears that contains the data from the two accounts.</span></span>

## <a name="to-add-a-word-document"></a><span data-ttu-id="0ab94-149">Word 文書を追加するには</span><span class="sxs-lookup"><span data-stu-id="0ab94-149">To add a Word document</span></span>

1. <span data-ttu-id="0ab94-150">C# 4 およびそれ以降のバージョンで Office プログラミングを強化するその他の方法を説明するために、次のコードでは、Word アプリケーションを開き、Excel ワークシートにリンクするアイコンを作成します。</span><span class="sxs-lookup"><span data-stu-id="0ab94-150">To illustrate additional ways in which C# 4, and later versions, enhances Office programming, the following code opens a Word application and creates an icon that links to the Excel worksheet.</span></span>

     <span data-ttu-id="0ab94-151">この手順の後半で提供されている `CreateIconInWordDoc` メソッドを `Program` クラスに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="0ab94-151">Paste method `CreateIconInWordDoc`, provided later in this step, into the `Program` class.</span></span> <span data-ttu-id="0ab94-152"><xref:Microsoft.Office.Interop.Word.Documents.Add%2A> メソッドと <xref:Microsoft.Office.Interop.Word.Selection.PasteSpecial%2A> メソッドの呼び出しに伴う複雑さが、`CreateIconInWordDoc` の名前付き引数と省略可能な引数によって軽減されます。</span><span class="sxs-lookup"><span data-stu-id="0ab94-152">`CreateIconInWordDoc` uses named and optional arguments to reduce the complexity of the method calls to <xref:Microsoft.Office.Interop.Word.Documents.Add%2A> and <xref:Microsoft.Office.Interop.Word.Selection.PasteSpecial%2A>.</span></span> <span data-ttu-id="0ab94-153">これらの呼び出しによって、C# 4 で導入された、参照パラメーターを持つ COM メソッドの呼び出しを簡略化する 2 つの他の新しい機能が組み込まれます。</span><span class="sxs-lookup"><span data-stu-id="0ab94-153">These calls incorporate two other new features introduced in C# 4 that simplify calls to COM methods that have reference parameters.</span></span> <span data-ttu-id="0ab94-154">第一に、値パラメーターの場合と同様に参照パラメーターに引数を渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="0ab94-154">First, you can send arguments to the reference parameters as if they were value parameters.</span></span> <span data-ttu-id="0ab94-155">つまり、参照パラメーターごとに変数を作成することなく値を直接渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="0ab94-155">That is, you can send values directly, without creating a variable for each reference parameter.</span></span> <span data-ttu-id="0ab94-156">コンパイラは引数の値を保持する一時変数を生成し、呼び出しから戻るときに変数を破棄します。</span><span class="sxs-lookup"><span data-stu-id="0ab94-156">The compiler generates temporary variables to hold the argument values, and discards the variables when you return from the call.</span></span> <span data-ttu-id="0ab94-157">第二に、引数リスト内の `ref` キーワードを省略できます。</span><span class="sxs-lookup"><span data-stu-id="0ab94-157">Second, you can omit the `ref` keyword in the argument list.</span></span>

     <span data-ttu-id="0ab94-158">`Add` メソッドには 4 つの参照パラメーターがあり、これらはすべてオプションです。</span><span class="sxs-lookup"><span data-stu-id="0ab94-158">The `Add` method has four reference parameters, all of which are optional.</span></span> <span data-ttu-id="0ab94-159">C# 4.0 およびそれ以降のバージョンでは、既定値を使用する場合は、任意またはすべてのパラメーターの引数を省略できます。</span><span class="sxs-lookup"><span data-stu-id="0ab94-159">In C# 4.0 and later versions, you can omit arguments for any or all of the parameters if you want to use their default values.</span></span> <span data-ttu-id="0ab94-160">C# 3.0 およびそれ以前のバージョンでは、各パラメーターの引数を指定する必要があり、そのパラメーターが参照パラメーターであるため、引数は変数である必要があります。</span><span class="sxs-lookup"><span data-stu-id="0ab94-160">In C# 3.0 and earlier versions, an argument must be provided for each parameter, and the argument must be a variable because the parameters are reference parameters.</span></span>

     <span data-ttu-id="0ab94-161">`PasteSpecial` メソッドは、クリップボードの内容を挿入します。</span><span class="sxs-lookup"><span data-stu-id="0ab94-161">The `PasteSpecial` method inserts the contents of the Clipboard.</span></span> <span data-ttu-id="0ab94-162">このメソッドには 7 つの参照パラメーターがあり、これらはすべてオプションです。</span><span class="sxs-lookup"><span data-stu-id="0ab94-162">The method has seven reference parameters, all of which are optional.</span></span> <span data-ttu-id="0ab94-163">次のコードでは、クリップボードの内容のソースへのリンクを作成する `Link` とリンクをアイコンとして表示する `DisplayAsIcon` の 2 つの参照パラメーターの引数を指定します。</span><span class="sxs-lookup"><span data-stu-id="0ab94-163">The following code specifies arguments for two of them: `Link`, to create a link to the source of the Clipboard contents, and `DisplayAsIcon`, to display the link as an icon.</span></span> <span data-ttu-id="0ab94-164">C# 4.0 およびそれ以降のバージョンでは、これら 2 つに名前付き引数を使用して、その他を省略できます。</span><span class="sxs-lookup"><span data-stu-id="0ab94-164">In C# 4.0 and later versions, you can use named arguments for those two and omit the others.</span></span> <span data-ttu-id="0ab94-165">これらは参照パラメーターですが、`ref` キーワードを使用したり、引数として渡す変数を作成したりする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="0ab94-165">Although these are reference parameters, you do not have to use the `ref` keyword, or to create variables to send in as arguments.</span></span> <span data-ttu-id="0ab94-166">値は直接渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="0ab94-166">You can send the values directly.</span></span> <span data-ttu-id="0ab94-167">C# 3.0 およびそれ以前のバージョンでは、各参照パラメーターに変数引数を渡す必要があります。</span><span class="sxs-lookup"><span data-stu-id="0ab94-167">In C# 3.0 and earlier versions, you must supply a variable argument for each reference parameter.</span></span>

     [!code-csharp[csProgGuideOfficeHowTo#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#9)]

     <span data-ttu-id="0ab94-168">C# 3.0 およびそれ以前のバージョンの言語では、次のより複雑なコードが必要です。</span><span class="sxs-lookup"><span data-stu-id="0ab94-168">In C# 3.0 and earlier versions of the language, the following more complex code is required.</span></span>

     [!code-csharp[csProgGuideOfficeHowTo#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#10)]

2. <span data-ttu-id="0ab94-169">次のステートメントを `Main` の末尾に追加します。</span><span class="sxs-lookup"><span data-stu-id="0ab94-169">Add the following statement at the end of `Main`.</span></span>

     [!code-csharp[csProgGuideOfficeHowTo#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#11)]

3. <span data-ttu-id="0ab94-170">次のステートメントを `DisplayInExcel` の末尾に追加します。</span><span class="sxs-lookup"><span data-stu-id="0ab94-170">Add the following statement at the end of `DisplayInExcel`.</span></span> <span data-ttu-id="0ab94-171">`Copy` メソッドはクリップボードにワークシートを追加します。</span><span class="sxs-lookup"><span data-stu-id="0ab94-171">The `Copy` method adds the worksheet to the Clipboard.</span></span>

     [!code-csharp[csProgGuideOfficeHowTo#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#12)]

4. <span data-ttu-id="0ab94-172">Ctrl キーを押しながら、F5 キーを押します。</span><span class="sxs-lookup"><span data-stu-id="0ab94-172">Press CTRL+F5.</span></span>

     <span data-ttu-id="0ab94-173">アイコンを含む Word 文書が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0ab94-173">A Word document appears that contains an icon.</span></span> <span data-ttu-id="0ab94-174">ワークシートを前面に表示するアイコンをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="0ab94-174">Double-click the icon to bring the worksheet to the foreground.</span></span>

## <a name="to-set-the-embed-interop-types-property"></a><span data-ttu-id="0ab94-175">[相互運用機能型の埋め込み] プロパティを設定するには</span><span class="sxs-lookup"><span data-stu-id="0ab94-175">To set the Embed Interop Types property</span></span>

1. <span data-ttu-id="0ab94-176">実行時に、プライマリ相互運用機能アセンブリ (PIA) を必要としない COM 型を呼び出すときに、追加の拡張が可能です。</span><span class="sxs-lookup"><span data-stu-id="0ab94-176">Additional enhancements are possible when you call a COM type that does not require a primary interop assembly (PIA) at run time.</span></span> <span data-ttu-id="0ab94-177">PIA への依存関係を削除することによって、バージョンに依存しない、より簡単な展開が実現されます。</span><span class="sxs-lookup"><span data-stu-id="0ab94-177">Removing the dependency on PIAs results in version independence and easier deployment.</span></span> <span data-ttu-id="0ab94-178">PIA を使用しないプログラミングのメリットの詳細については、「[チュートリアル: マネージド アセンブリからの型の埋め込み](../concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-visual-studio.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0ab94-178">For more information about the advantages of programming without PIAs, see [Walkthrough: Embedding Types from Managed Assemblies](../concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-visual-studio.md).</span></span>

     <span data-ttu-id="0ab94-179">また、`dynamic` ではなく `Object` 型を使用して、COM メソッドに必要とされ、COM メソッドによって返される型を簡単に表現できるため、プログラミングがより簡単になります。</span><span class="sxs-lookup"><span data-stu-id="0ab94-179">In addition, programming is easier because the types that are required and returned by COM methods can be represented by using the type `dynamic` instead of `Object`.</span></span> <span data-ttu-id="0ab94-180">型が `dynamic` の変数は、明示的なキャストが不要になる実行時まで評価されません。</span><span class="sxs-lookup"><span data-stu-id="0ab94-180">Variables that have type `dynamic` are not evaluated until run time, which eliminates the need for explicit casting.</span></span> <span data-ttu-id="0ab94-181">詳細については、「[dynamic 型の使用](../types/using-type-dynamic.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0ab94-181">For more information, see [Using Type dynamic](../types/using-type-dynamic.md).</span></span>

     <span data-ttu-id="0ab94-182">C# 4 の既定の動作では、PIA を使用せずに型情報が埋め込まれます。</span><span class="sxs-lookup"><span data-stu-id="0ab94-182">In C# 4, embedding type information instead of using PIAs is default behavior.</span></span> <span data-ttu-id="0ab94-183">この既定のため、前の例のいくつかは、明示的なキャストが必要ないために簡素化されます。</span><span class="sxs-lookup"><span data-stu-id="0ab94-183">Because of that default, several of the previous examples are simplified because explicit casting is not required.</span></span> <span data-ttu-id="0ab94-184">たとえば、`worksheet` での `DisplayInExcel` の宣言は、`Excel._Worksheet workSheet = excelApp.ActiveSheet` ではなく `Excel._Worksheet workSheet = (Excel.Worksheet)excelApp.ActiveSheet` と記述されます。</span><span class="sxs-lookup"><span data-stu-id="0ab94-184">For example, the declaration of `worksheet` in `DisplayInExcel` is written as `Excel._Worksheet workSheet = excelApp.ActiveSheet` rather than `Excel._Worksheet workSheet = (Excel.Worksheet)excelApp.ActiveSheet`.</span></span> <span data-ttu-id="0ab94-185">同じメソッドの `AutoFit` への呼び出しでも、既定値を使用せずに明示的なキャストが必要になります。これは、`ExcelApp.Columns[1]` が `Object` を返し、`AutoFit` が Excel のメソッドであるためです。</span><span class="sxs-lookup"><span data-stu-id="0ab94-185">The calls to `AutoFit` in the same method also would require explicit casting without the default, because `ExcelApp.Columns[1]` returns an `Object`, and `AutoFit` is an Excel  method.</span></span> <span data-ttu-id="0ab94-186">次のコードはキャストを示しています。</span><span class="sxs-lookup"><span data-stu-id="0ab94-186">The following code shows the casting.</span></span>

     [!code-csharp[csProgGuideOfficeHowTo#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#14)]

2. <span data-ttu-id="0ab94-187">既定値を変更し、型情報を埋め込むのではなく PIA を使用するには、**ソリューション エクスプ ローラー**で **[参照設定]** ノードを展開し、 **[Microsoft.Office.Interop.Excel]** または **[Microsoft.Office.Interop.Word]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0ab94-187">To change the default and use PIAs instead of embedding type information, expand the **References** node in **Solution Explorer** and then select **Microsoft.Office.Interop.Excel** or **Microsoft.Office.Interop.Word**.</span></span>

3. <span data-ttu-id="0ab94-188">**[プロパティ]** ウィンドウが表示されない場合は、**F4** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="0ab94-188">If you cannot see the **Properties** window, press **F4**.</span></span>

4. <span data-ttu-id="0ab94-189">プロパティの一覧で **[相互運用機能型の埋め込み]** を見つけて、値を **[False]** に変更します。</span><span class="sxs-lookup"><span data-stu-id="0ab94-189">Find **Embed Interop Types** in the list of properties, and change its value to **False**.</span></span> <span data-ttu-id="0ab94-190">同様に、コマンド プロンプトで [/link](../../language-reference/compiler-options/link-compiler-option.md) の代わりに [/reference](../../language-reference/compiler-options/reference-compiler-option.md) コンパイラ オプションを使用してコンパイルすることができます。</span><span class="sxs-lookup"><span data-stu-id="0ab94-190">Equivalently, you can compile by using the [/reference](../../language-reference/compiler-options/reference-compiler-option.md) compiler option instead of [/link](../../language-reference/compiler-options/link-compiler-option.md) at a command prompt.</span></span>

## <a name="to-add-additional-formatting-to-the-table"></a><span data-ttu-id="0ab94-191">テーブルに追加の書式設定を追加するには</span><span class="sxs-lookup"><span data-stu-id="0ab94-191">To add additional formatting to the table</span></span>

1. <span data-ttu-id="0ab94-192">`AutoFit` の `DisplayInExcel` への 2 つの呼び出しを次のステートメントに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="0ab94-192">Replace the two calls to `AutoFit` in `DisplayInExcel` with the following statement.</span></span>

     [!code-csharp[csProgGuideOfficeHowTo#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#15)]

     <span data-ttu-id="0ab94-193"><xref:Microsoft.Office.Interop.Excel.Range.AutoFormat%2A> メソッドには、7 つの値パラメーターがあり、これらはすべて省略可能です。</span><span class="sxs-lookup"><span data-stu-id="0ab94-193">The <xref:Microsoft.Office.Interop.Excel.Range.AutoFormat%2A> method has seven value parameters, all of which are optional.</span></span> <span data-ttu-id="0ab94-194">名前付き引数と省略可能な引数を使用すると、一部またはすべてのパラメーターに引数を指定することができます。引数を指定しないこともできます。</span><span class="sxs-lookup"><span data-stu-id="0ab94-194">Named and optional arguments enable you to provide arguments for none, some, or all of them.</span></span> <span data-ttu-id="0ab94-195">前のステートメントでは、1 つのパラメーター `Format` にのみ引数が指定されています。</span><span class="sxs-lookup"><span data-stu-id="0ab94-195">In the previous statement, an argument is supplied for only one of the parameters, `Format`.</span></span> <span data-ttu-id="0ab94-196">`Format` はパラメーター リストの最初のパラメーターであるため、パラメーター名を指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="0ab94-196">Because `Format` is the first parameter in the parameter list, you do not have to provide the parameter name.</span></span> <span data-ttu-id="0ab94-197">ただし、次のコードに示すように、パラメーター名が含まれている場合、ステートメントがわかりやすい場合があります。</span><span class="sxs-lookup"><span data-stu-id="0ab94-197">However, the statement might be easier to understand if the parameter name is included, as is shown in the following code.</span></span>

     [!code-csharp[csProgGuideOfficeHowTo#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#16)]

2. <span data-ttu-id="0ab94-198">Ctrl + F5 キーを押して結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="0ab94-198">Press CTRL+F5 to see the result.</span></span> <span data-ttu-id="0ab94-199">その他の形式は、<xref:Microsoft.Office.Interop.Excel.XlRangeAutoFormat> 列挙型のページに掲載されています。</span><span class="sxs-lookup"><span data-stu-id="0ab94-199">Other formats are listed in the <xref:Microsoft.Office.Interop.Excel.XlRangeAutoFormat> enumeration.</span></span>

3. <span data-ttu-id="0ab94-200">手順 1 のステートメントと、C# 3.0 およびそれ以前のバージョンで必要な引数が示されている次のコードを比較します。</span><span class="sxs-lookup"><span data-stu-id="0ab94-200">Compare the statement in step 1 with the following code, which shows the arguments that are required in C# 3.0 and earlier versions.</span></span>

     [!code-csharp[csProgGuideOfficeHowTo#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#17)]

## <a name="example"></a><span data-ttu-id="0ab94-201">例</span><span class="sxs-lookup"><span data-stu-id="0ab94-201">Example</span></span>

<span data-ttu-id="0ab94-202">コード例全体を次に示します。</span><span class="sxs-lookup"><span data-stu-id="0ab94-202">The following code shows the complete example.</span></span>

[!code-csharp[csProgGuideOfficeHowTo#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/walkthrough.cs#18)]

## <a name="see-also"></a><span data-ttu-id="0ab94-203">関連項目</span><span class="sxs-lookup"><span data-stu-id="0ab94-203">See also</span></span>

- <xref:System.Type.Missing?displayProperty=nameWithType>
- [<span data-ttu-id="0ab94-204">dynamic</span><span class="sxs-lookup"><span data-stu-id="0ab94-204">dynamic</span></span>](../../language-reference/keywords/dynamic.md)
- [<span data-ttu-id="0ab94-205">dynamic 型の使用</span><span class="sxs-lookup"><span data-stu-id="0ab94-205">Using Type dynamic</span></span>](../types/using-type-dynamic.md)
- [<span data-ttu-id="0ab94-206">名前付き引数と省略可能な引数</span><span class="sxs-lookup"><span data-stu-id="0ab94-206">Named and Optional Arguments</span></span>](../classes-and-structs/named-and-optional-arguments.md)
- [<span data-ttu-id="0ab94-207">方法: Office プログラミングで名前付き引数と省略可能な引数を使用する</span><span class="sxs-lookup"><span data-stu-id="0ab94-207">How to: Use Named and Optional Arguments in Office Programming</span></span>](../classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md)
