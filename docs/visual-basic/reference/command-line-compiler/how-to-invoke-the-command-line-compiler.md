---
title: '方法: コマンド ライン コンパイラ (Visual Basic) を呼び出す'
ms.date: 07/20/2015
helpviewer_keywords:
- command-line arguments
- vbc.exe
- Visual Basic compiler, starting
- command line [Visual Basic], arguments
ms.assetid: 0fd9a8f6-f34e-4c35-a49d-9b9bbd8da4a9
ms.openlocfilehash: 67cad0df3f10ff1fa1f6a58546fe150232fe1283
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62032072"
---
# <a name="how-to-invoke-the-command-line-compiler-visual-basic"></a><span data-ttu-id="9a864-102">方法: コマンド ライン コンパイラ (Visual Basic) を呼び出す</span><span class="sxs-lookup"><span data-stu-id="9a864-102">How to: Invoke the Command-Line Compiler (Visual Basic)</span></span>
<span data-ttu-id="9a864-103">コマンドライン プロンプトとも呼ばれますにその実行可能ファイルの名前を入力して、コマンド ライン コンパイラを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="9a864-103">You can invoke the command-line compiler by typing the name of its executable file into the command line, also known as the MS-DOS prompt.</span></span> <span data-ttu-id="9a864-104">既定の Windows コマンド プロンプトからコンパイルする場合は、実行可能ファイルへの完全修飾パスを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9a864-104">If you compile from the default Windows Command Prompt, you must type the fully qualified path to the executable file.</span></span> <span data-ttu-id="9a864-105">この既定の動作を上書きするには、for Visual Studio は、開発者コマンド プロンプトを使用するか、PATH 環境変数を変更します。</span><span class="sxs-lookup"><span data-stu-id="9a864-105">To override this default behavior, you can either use the Developer Command Prompt for Visual Studio, or modify the PATH environment variable.</span></span> <span data-ttu-id="9a864-106">コンパイラの名前を入力するだけで、任意のディレクトリからコンパイルをどちらもができます。</span><span class="sxs-lookup"><span data-stu-id="9a864-106">Both allow you to compile from any directory by simply typing the compiler name.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-invoke-the-compiler-using-the-developer-command-prompt-for-visual-studio"></a><span data-ttu-id="9a864-107">Visual Studio 用開発者コマンド プロンプトを使用してコンパイラを起動するには</span><span class="sxs-lookup"><span data-stu-id="9a864-107">To invoke the compiler using the Developer Command Prompt for Visual Studio</span></span>  
  
1. <span data-ttu-id="9a864-108">Microsoft Visual Studio のプログラム グループ内の Visual Studio Tools のプログラム フォルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="9a864-108">Open the Visual Studio Tools program folder within the Microsoft Visual Studio program group.</span></span>  
  
2. <span data-ttu-id="9a864-109">Visual Studio がインストールされている場合は、任意のディレクトリからコンピューターには、コンパイラにアクセスする Visual Studio 用開発者コマンド プロンプトを使用できます。</span><span class="sxs-lookup"><span data-stu-id="9a864-109">You can use the Developer Command Prompt for Visual Studio to access the compiler from any directory on your machine, if Visual Studio is installed.</span></span>  
  
3. <span data-ttu-id="9a864-110">Visual Studio 用開発者コマンド プロンプトを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="9a864-110">Invoke the Developer Command Prompt for Visual Studio.</span></span>  
  
4. <span data-ttu-id="9a864-111">コマンドラインで「 `vbc.exe` *sourceFileName*し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="9a864-111">At the command line, type `vbc.exe` *sourceFileName* and then press ENTER.</span></span>  
  
     <span data-ttu-id="9a864-112">という名前のディレクトリで、ソース コードが格納されている場合など、 `SourceFiles`、コマンド プロンプトと種類を開くと`cd SourceFiles`そのディレクトリに変更します。</span><span class="sxs-lookup"><span data-stu-id="9a864-112">For example, if you stored your source code in a directory called `SourceFiles`, you would open the Command Prompt and type `cd SourceFiles` to change to that directory.</span></span> <span data-ttu-id="9a864-113">ディレクトリには、という名前のソース ファイルが含まれている場合`Source.vb`、」と入力してコンパイルする`vbc.exe Source.vb`します。</span><span class="sxs-lookup"><span data-stu-id="9a864-113">If the directory contained a source file named `Source.vb`, you could compile it by typing `vbc.exe Source.vb`.</span></span>  
  
### <a name="to-set-the-path-environment-variable-to-the-compiler-for-the-windows-command-prompt"></a><span data-ttu-id="9a864-114">Windows コマンド プロンプトをコンパイラに PATH 環境変数を設定するには</span><span class="sxs-lookup"><span data-stu-id="9a864-114">To set the PATH environment variable to the compiler for the Windows Command Prompt</span></span>  
  
1. <span data-ttu-id="9a864-115">Windows Search の機能を使用して、ローカル ディスク上の Vbc.exe を検索します。</span><span class="sxs-lookup"><span data-stu-id="9a864-115">Use the Windows Search feature to find Vbc.exe on your local disk.</span></span>  
  
     <span data-ttu-id="9a864-116">コンパイラがあるディレクトリの正確な名前は、Windows ディレクトリの場所とインストール".NET Framework"のバージョンによって異なります。</span><span class="sxs-lookup"><span data-stu-id="9a864-116">The exact name of the directory where the compiler is located depends on the location of the Windows directory and the version of the ".NET Framework" installed.</span></span> <span data-ttu-id="9a864-117">".NET Framework"インストールされているは、複数のバージョンがあれば、(通常は最新のバージョン) を使用するバージョンを決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9a864-117">If you have more than one version of the ".NET Framework" installed, you must determine which version to use (typically the latest version).</span></span>  
  
2. <span data-ttu-id="9a864-118">**開始** メニューを右クリックして**マイ コンピューター**、順にクリックします**プロパティ**ショートカット メニューから。</span><span class="sxs-lookup"><span data-stu-id="9a864-118">From your **Start** Menu, right-click **My Computer**, and then click **Properties** from the shortcut menu.</span></span>  
  
3. <span data-ttu-id="9a864-119">をクリックして、**詳細** タブをクリックして**環境変数**します。</span><span class="sxs-lookup"><span data-stu-id="9a864-119">Click the **Advanced** tab, and then click **Environment Variables**.</span></span>  
  
4. <span data-ttu-id="9a864-120">**システム**変数ウィンドウで、**パス** をクリックし、リストから**編集**します。</span><span class="sxs-lookup"><span data-stu-id="9a864-120">In the **System** variables pane, select **Path** from the list and click **Edit**.</span></span>  
  
5. <span data-ttu-id="9a864-121">**編集システム**変数 ダイアログ ボックスで文字列の末尾にカーソルを移動、**変数値**フィールドし、セミコロン (;) を入力後に手順 1. で見つかった完全なディレクトリ名。</span><span class="sxs-lookup"><span data-stu-id="9a864-121">In the **Edit System** Variable dialog box, move the insertion point to the end of the string in the **Variable Value** field and type a semicolon (;) followed by the full directory name found in Step 1.</span></span>  
  
6. <span data-ttu-id="9a864-122">クリックして**OK**を編集内容を確認し、ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="9a864-122">Click **OK** to confirm your edits and close the dialog boxes.</span></span>  
  
     <span data-ttu-id="9a864-123">PATH 環境変数を変更した後行うことができます、Visual Basic コンパイラ、Windows コマンド プロンプトで任意のディレクトリからコンピューターにします。</span><span class="sxs-lookup"><span data-stu-id="9a864-123">After you change the PATH environment variable, you can run the Visual Basic compiler at the Windows Command Prompt from any directory on the computer.</span></span>  
  
### <a name="to-invoke-the-compiler-using-the-windows-command-prompt"></a><span data-ttu-id="9a864-124">Windows コマンド プロンプトを使用してコンパイラを起動するには</span><span class="sxs-lookup"><span data-stu-id="9a864-124">To invoke the compiler using the Windows Command Prompt</span></span>  
  
1. <span data-ttu-id="9a864-125">**開始** メニューをクリックして、**アクセサリ**フォルダー、および順に開いて、 **Windows コマンド プロンプト**。</span><span class="sxs-lookup"><span data-stu-id="9a864-125">From the **Start** menu, click on the **Accessories** folder, and then open the **Windows Command Prompt**.</span></span>  
  
2. <span data-ttu-id="9a864-126">コマンドラインで「 `vbc.exe` *sourceFileName*し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="9a864-126">At the command line, type `vbc.exe`*sourceFileName* and then press ENTER.</span></span>  
  
     <span data-ttu-id="9a864-127">という名前のディレクトリで、ソース コードが格納されている場合など、 `SourceFiles`、コマンド プロンプトと種類を開くと`cd SourceFiles`そのディレクトリに変更します。</span><span class="sxs-lookup"><span data-stu-id="9a864-127">For example, if you stored your source code in a directory called `SourceFiles`, you would open the Command Prompt and type `cd SourceFiles` to change to that directory.</span></span> <span data-ttu-id="9a864-128">ディレクトリには、という名前のソース ファイルが含まれている場合`Source.vb`、」と入力してコンパイルする`vbc.exe Source.vb`します。</span><span class="sxs-lookup"><span data-stu-id="9a864-128">If the directory contained a source file named `Source.vb`, you could compile it by typing `vbc.exe Source.vb`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a864-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="9a864-129">See also</span></span>

- [<span data-ttu-id="9a864-130">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="9a864-130">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="9a864-131">条件付きコンパイル</span><span class="sxs-lookup"><span data-stu-id="9a864-131">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
