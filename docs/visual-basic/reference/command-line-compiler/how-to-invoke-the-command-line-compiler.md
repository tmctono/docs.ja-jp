---
title: '方法: コマンドラインコンパイラ (Visual Basic) を起動します。'
ms.date: 07/20/2015
helpviewer_keywords:
- command-line arguments
- vbc.exe
- Visual Basic compiler, starting
- command line [Visual Basic], arguments
ms.assetid: 0fd9a8f6-f34e-4c35-a49d-9b9bbd8da4a9
ms.openlocfilehash: a81d5b4f4eae76b0306e2d27475cb8527bda0ff2
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2019
ms.locfileid: "71054215"
---
# <a name="how-to-invoke-the-command-line-compiler-visual-basic"></a><span data-ttu-id="5f974-102">方法: コマンドラインコンパイラ (Visual Basic) を起動します。</span><span class="sxs-lookup"><span data-stu-id="5f974-102">How to: Invoke the Command-Line Compiler (Visual Basic)</span></span>

<span data-ttu-id="5f974-103">コマンドラインコンパイラを起動するには、実行可能ファイルの名前をコマンドラインに入力します (MS-DOS プロンプトとも呼ばれます)。</span><span class="sxs-lookup"><span data-stu-id="5f974-103">You can invoke the command-line compiler by typing the name of its executable file into the command line, also known as the MS-DOS prompt.</span></span> <span data-ttu-id="5f974-104">既定の Windows コマンドプロンプトからコンパイルする場合は、実行可能ファイルへの完全修飾パスを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f974-104">If you compile from the default Windows Command Prompt, you must type the fully qualified path to the executable file.</span></span> <span data-ttu-id="5f974-105">この既定の動作をオーバーライドするには、Visual Studio の開発者コマンドプロンプトを使用するか、または PATH 環境変数を変更します。</span><span class="sxs-lookup"><span data-stu-id="5f974-105">To override this default behavior, you can either use the Developer Command Prompt for Visual Studio, or modify the PATH environment variable.</span></span> <span data-ttu-id="5f974-106">どちらの方法でも、コンパイラ名を入力するだけで、任意のディレクトリからコンパイルできます。</span><span class="sxs-lookup"><span data-stu-id="5f974-106">Both allow you to compile from any directory by simply typing the compiler name.</span></span>

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-invoke-the-compiler-using-the-developer-command-prompt-for-visual-studio"></a><span data-ttu-id="5f974-107">Visual Studio の開発者コマンドプロンプトを使用してコンパイラを呼び出すには</span><span class="sxs-lookup"><span data-stu-id="5f974-107">To invoke the compiler using the Developer Command Prompt for Visual Studio</span></span>

1. <span data-ttu-id="5f974-108">Microsoft Visual Studio プログラムグループ内の Visual Studio Tools program フォルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="5f974-108">Open the Visual Studio Tools program folder within the Microsoft Visual Studio program group.</span></span>

2. <span data-ttu-id="5f974-109">Visual studio がインストールされている場合は、Visual Studio の開発者コマンドプロンプトを使用して、コンピューター上の任意のディレクトリからコンパイラにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="5f974-109">You can use the Developer Command Prompt for Visual Studio to access the compiler from any directory on your machine, if Visual Studio is installed.</span></span>

3. <span data-ttu-id="5f974-110">Visual Studio の開発者コマンドプロンプトを起動します。</span><span class="sxs-lookup"><span data-stu-id="5f974-110">Invoke the Developer Command Prompt for Visual Studio.</span></span>

4. <span data-ttu-id="5f974-111">コマンドラインで、「 `vbc.exe` *sourcefilename* 」と入力し、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="5f974-111">At the command line, type `vbc.exe` *sourceFileName* and then press ENTER.</span></span>

    <span data-ttu-id="5f974-112">たとえば、というディレクトリにソースコードを格納した場合`SourceFiles`は、コマンドプロンプトを開き、「」 `cd SourceFiles`と入力してそのディレクトリに変更します。</span><span class="sxs-lookup"><span data-stu-id="5f974-112">For example, if you stored your source code in a directory called `SourceFiles`, you would open the Command Prompt and type `cd SourceFiles` to change to that directory.</span></span> <span data-ttu-id="5f974-113">ディレクトリにという名前のソースファイル`Source.vb`が含まれている場合は`vbc.exe Source.vb`、「」と入力してコンパイルできます。</span><span class="sxs-lookup"><span data-stu-id="5f974-113">If the directory contained a source file named `Source.vb`, you could compile it by typing `vbc.exe Source.vb`.</span></span>

## <a name="to-set-the-path-environment-variable-to-the-compiler-for-the-windows-command-prompt"></a><span data-ttu-id="5f974-114">Windows のコマンドプロンプト用に PATH 環境変数をコンパイラに設定するには</span><span class="sxs-lookup"><span data-stu-id="5f974-114">To set the PATH environment variable to the compiler for the Windows Command Prompt</span></span>

1. <span data-ttu-id="5f974-115">Windows 検索機能を使用して、ローカルディスクで Vbc.exe を検索します。</span><span class="sxs-lookup"><span data-stu-id="5f974-115">Use the Windows Search feature to find Vbc.exe on your local disk.</span></span>

    <span data-ttu-id="5f974-116">コンパイラが配置されているディレクトリの正確な名前は、Windows ディレクトリの場所とインストールされている ".NET Framework" のバージョンによって異なります。</span><span class="sxs-lookup"><span data-stu-id="5f974-116">The exact name of the directory where the compiler is located depends on the location of the Windows directory and the version of the ".NET Framework" installed.</span></span> <span data-ttu-id="5f974-117">".NET Framework" の複数のバージョンがインストールされている場合は、使用するバージョン (通常は最新バージョン) を決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f974-117">If you have more than one version of the ".NET Framework" installed, you must determine which version to use (typically the latest version).</span></span>

2. <span data-ttu-id="5f974-118">**[スタート]** メニューの **[マイコンピューター]** を右クリックし、ショートカットメニューの **[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5f974-118">From your **Start** Menu, right-click **My Computer**, and then click **Properties** from the shortcut menu.</span></span>

3. <span data-ttu-id="5f974-119">**[詳細設定]** タブをクリックし、 **[環境変数]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5f974-119">Click the **Advanced** tab, and then click **Environment Variables**.</span></span>

4. <span data-ttu-id="5f974-120">**[システム]** 変数 ペインで、一覧から **[パス]** を選択し、 **[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5f974-120">In the **System** variables pane, select **Path** from the list and click **Edit**.</span></span>

5. <span data-ttu-id="5f974-121">システム変数の **[編集]** ダイアログボックスで、 **[変数の値]** フィールドの文字列の末尾にカーソルを移動し、セミコロン (;) を入力します。の後に、手順 1. で見つかった完全なディレクトリ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="5f974-121">In the **Edit System** Variable dialog box, move the insertion point to the end of the string in the **Variable Value** field and type a semicolon (;) followed by the full directory name found in Step 1.</span></span>

6. <span data-ttu-id="5f974-122">**[OK]** をクリックして編集内容を確認し、ダイアログボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="5f974-122">Click **OK** to confirm your edits and close the dialog boxes.</span></span>

     <span data-ttu-id="5f974-123">PATH 環境変数を変更した後、コンピューター上の任意のディレクトリから Windows コマンドプロンプトで Visual Basic コンパイラを実行できます。</span><span class="sxs-lookup"><span data-stu-id="5f974-123">After you change the PATH environment variable, you can run the Visual Basic compiler at the Windows Command Prompt from any directory on the computer.</span></span>

## <a name="to-invoke-the-compiler-using-the-windows-command-prompt"></a><span data-ttu-id="5f974-124">Windows のコマンドプロンプトを使用してコンパイラを呼び出すには</span><span class="sxs-lookup"><span data-stu-id="5f974-124">To invoke the compiler using the Windows Command Prompt</span></span>

1. <span data-ttu-id="5f974-125">**[スタート]** メニューの **[アクセサリ]** フォルダーをクリックし、 **Windows コマンドプロンプト**を開きます。</span><span class="sxs-lookup"><span data-stu-id="5f974-125">From the **Start** menu, click on the **Accessories** folder, and then open the **Windows Command Prompt**.</span></span>

2. <span data-ttu-id="5f974-126">コマンドラインで、「 `vbc.exe` *sourcefilename* 」と入力し、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="5f974-126">At the command line, type `vbc.exe`*sourceFileName* and then press ENTER.</span></span>

     <span data-ttu-id="5f974-127">たとえば、というディレクトリにソースコードを格納した場合`SourceFiles`は、コマンドプロンプトを開き、「」 `cd SourceFiles`と入力してそのディレクトリに変更します。</span><span class="sxs-lookup"><span data-stu-id="5f974-127">For example, if you stored your source code in a directory called `SourceFiles`, you would open the Command Prompt and type `cd SourceFiles` to change to that directory.</span></span> <span data-ttu-id="5f974-128">ディレクトリにという名前のソースファイル`Source.vb`が含まれている場合は`vbc.exe Source.vb`、「」と入力してコンパイルできます。</span><span class="sxs-lookup"><span data-stu-id="5f974-128">If the directory contained a source file named `Source.vb`, you could compile it by typing `vbc.exe Source.vb`.</span></span>

## <a name="see-also"></a><span data-ttu-id="5f974-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="5f974-129">See also</span></span>

- [<span data-ttu-id="5f974-130">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="5f974-130">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="5f974-131">条件付きコンパイル</span><span class="sxs-lookup"><span data-stu-id="5f974-131">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
