---
title: Visual Studio での .NET Standard ライブラリの使用
description: Visual Studio 2019 を使用して別のクラス ライブラリのメンバーを呼び出す .NET Core アプリケーションを構築します。
ms.date: 12/20/2019
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: 4eb75f23359334ea483cba1498f1804c4b24c80c
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2020
ms.locfileid: "76920453"
---
# <a name="consume-a-net-standard-library-in-visual-studio"></a><span data-ttu-id="1c5cb-103">Visual Studio での .NET Standard ライブラリの使用</span><span class="sxs-lookup"><span data-stu-id="1c5cb-103">Consume a .NET Standard library in Visual Studio</span></span>

<span data-ttu-id="1c5cb-104">.NET Standard クラス ライブラリを作成してテストし、そのライブラリのリリース バージョンを構築したら、次のステップとして、それを呼び出し元が使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="1c5cb-104">Once you've created a .NET Standard class library, tested it, and built a release version of the library, the next step is to make it available to callers.</span></span> <span data-ttu-id="1c5cb-105">これは次の 2 つの方法で実行できます。</span><span class="sxs-lookup"><span data-stu-id="1c5cb-105">You can do this in two ways:</span></span>

- <span data-ttu-id="1c5cb-106">ライブラリが 1 つのソリューションで使われる場合 (たとえば、1 つの大規模なアプリケーションのコンポーネントである場合)、1 つのプロジェクトとしてソリューションに含めることができます。</span><span class="sxs-lookup"><span data-stu-id="1c5cb-106">If the library will be used by a single solution (for example, if it's a component in a single large application), you can include it as a project in your solution.</span></span>
- <span data-ttu-id="1c5cb-107">ライブラリが一般に公開される場合は、NuGet パッケージとして配布できます。</span><span class="sxs-lookup"><span data-stu-id="1c5cb-107">If the library will be publicly available, you can distribute it as a NuGet package.</span></span>

<span data-ttu-id="1c5cb-108">このチュートリアルでは、次の作業を行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1c5cb-108">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="1c5cb-109">.NET Standard ライブラリ プロジェクトを参照するコンソール アプリをソリューションに追加します。</span><span class="sxs-lookup"><span data-stu-id="1c5cb-109">Add a console app to your solution that references a .NET Standard library project.</span></span>
> - <span data-ttu-id="1c5cb-110">.NET Standard ライブラリ ロジェクトを含む NuGet パッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="1c5cb-110">Create a NuGet package that contains a .NET Standard library project.</span></span>

## <a name="add-a-console-app-to-your-solution"></a><span data-ttu-id="1c5cb-111">ソリューションにコンソール アプリを追加する</span><span class="sxs-lookup"><span data-stu-id="1c5cb-111">Add a console app to your solution</span></span>

<span data-ttu-id="1c5cb-112">「[Visual Studio での .NET Standard ライブラリのテスト](testing-library-with-visual-studio.md)」で、単体テストをクラス ライブラリと同じソリューションに含めたのと同様に、アプリケーションをそのソリューションの一部として含めることができます。</span><span class="sxs-lookup"><span data-stu-id="1c5cb-112">Just as you included unit tests in the same solution as your class library in [Test a .NET Standard library in Visual Studio](testing-library-with-visual-studio.md), you can include your application as part of that solution.</span></span> <span data-ttu-id="1c5cb-113">たとえば、文字列を入力するようにユーザーに要求して、最初の文字が大文字かどうかを報告するコンソール アプリケーションで、このクラス ライブラリを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="1c5cb-113">For example, you can use your class library in a console application that prompts the user to enter a string and reports whether its first character is uppercase:</span></span>

1. <span data-ttu-id="1c5cb-114">[Visual Studio での .NET Standard ライブラリの構築](library-with-visual-studio.md)に関する記事で作成した `ClassLibraryProjects` ソリューションを開きます。</span><span class="sxs-lookup"><span data-stu-id="1c5cb-114">Open the `ClassLibraryProjects` solution you created in the [Build a .NET Standard library in Visual Studio](library-with-visual-studio.md) article.</span></span>

1. <span data-ttu-id="1c5cb-115">"ShowCase" という名前の新しい .NET Core コンソール アプリケーションをソリューションに追加します。</span><span class="sxs-lookup"><span data-stu-id="1c5cb-115">Add a new .NET Core console application named "ShowCase" to the solution.</span></span>

   1. <span data-ttu-id="1c5cb-116">**ソリューション エクスプローラー**で、ソリューションを右クリックし、 **[追加]**  >  **[新しいプロジェクト]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="1c5cb-116">Right-click on the solution in **Solution Explorer** and select **Add** > **New project**.</span></span>

   1. <span data-ttu-id="1c5cb-117">**[新しいプロジェクトの追加]** ページで、検索ボックスに「**コンソール**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="1c5cb-117">On the **Add a new project** page, enter **console** in the search box.</span></span> <span data-ttu-id="1c5cb-118">言語の一覧から **[C#]** または **[Visual Basic]** を選択し、次に、プラットフォームの一覧から **[すべてのプラットフォーム]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1c5cb-118">Choose **C#** or **Visual Basic** from the Language list, and then choose **All platforms** from the Platform list.</span></span> <span data-ttu-id="1c5cb-119">**[コンソール アプリ (.NET Core)]** テンプレートを選択し、 **[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1c5cb-119">Choose the **Console App (.NET Core)** template, and then choose **Next**.</span></span>

   1. <span data-ttu-id="1c5cb-120">**[新しいプロジェクトの構成]** ページで、 **[プロジェクト名]** ボックスに「**ShowCase**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="1c5cb-120">On the **Configure your new project** page, enter **ShowCase** in the **Project name** box.</span></span> <span data-ttu-id="1c5cb-121">次に、 **[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1c5cb-121">Then, choose **Create**.</span></span>

1. <span data-ttu-id="1c5cb-122">**ソリューション エクスプローラー**で、**ShowCase** プロジェクトを右クリックして、コンテキスト メニューで **[スタートアップ プロジェクトに設定]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="1c5cb-122">In **Solution Explorer**, right-click the **ShowCase** project and select **Set as StartUp Project** in the context menu.</span></span>

   ![スタートアップ プロジェクトを設定する Visual Studio プロジェクトのコンテキスト メニュー](./media/consuming-library-with-visual-studio/set-startup-project-context-menu.png)

1. <span data-ttu-id="1c5cb-124">初期状態では、プロジェクトにはクラス ライブラリへのアクセス権がありません。</span><span class="sxs-lookup"><span data-stu-id="1c5cb-124">Initially, your project doesn't have access to your class library.</span></span> <span data-ttu-id="1c5cb-125">プロジェクトでクラス ライブラリのメソッドを呼び出すことができるようにするには、クラス ライブラリへの参照を作成します。</span><span class="sxs-lookup"><span data-stu-id="1c5cb-125">To allow it to call methods in your class library, you create a reference to the class library.</span></span> <span data-ttu-id="1c5cb-126">**ソリューション エクスプローラー**で、`ShowCase` プロジェクトの **[依存関係]** ノードを右クリックして、 **[参照の追加]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="1c5cb-126">In **Solution Explorer**, right-click the `ShowCase` project's **Dependencies** node and select **Add Reference**.</span></span>

   ![Visual Studio の [参照の追加] コンテキスト メニュー](./media/consuming-library-with-visual-studio/add-reference-context-menu.png)

1. <span data-ttu-id="1c5cb-128">**[参照マネージャー]** ダイアログ ボックスで、クラス ライブラリ プロジェクト **StringLibrary** を選び、 **[OK]** ボタンを選びます。</span><span class="sxs-lookup"><span data-stu-id="1c5cb-128">In the **Reference Manager** dialog, select **StringLibrary**, your class library project, and select the **OK** button.</span></span>

   ![StringLibrary が選択された [参照マネージャー] ダイアログ](./media/consuming-library-with-visual-studio/manage-project-references.png)

1. <span data-ttu-id="1c5cb-130">*Program.cs* または *Program.vb* ファイルのコード ウィンドウで、すべてのコードを次のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="1c5cb-130">In the code window for the *Program.cs* or *Program.vb* file, replace all of the code with the following code:</span></span>

   [!code-csharp[UsingClassLib#1](~/samples/snippets/csharp/getting_started/with_visual_studio_2017/showcase.cs)]
   [!code-vb[UsingClassLib#1](~/samples/snippets/core/tutorials/vb-library-with-visual-studio/showcase.vb)]

   <span data-ttu-id="1c5cb-131">このコードでは、`row` 変数を使って、コンソール ウィンドウに書き込まれるデータの行数のカウントを維持します。</span><span class="sxs-lookup"><span data-stu-id="1c5cb-131">The code uses the `row` variable to maintain a count of the number of rows of data written to the console window.</span></span> <span data-ttu-id="1c5cb-132">これが 25 以上になると、コードによってコンソール ウィンドウがクリアされ、ユーザーにメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1c5cb-132">Whenever it's greater than or equal to 25, the code clears the console window and displays a message to the user.</span></span>

   <span data-ttu-id="1c5cb-133">プログラムは、ユーザーに文字列の入力を要求し、</span><span class="sxs-lookup"><span data-stu-id="1c5cb-133">The program prompts the user to enter a string.</span></span> <span data-ttu-id="1c5cb-134">文字列が大文字で始まるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="1c5cb-134">It indicates whether the string starts with an uppercase character.</span></span> <span data-ttu-id="1c5cb-135">ユーザーが文字列を入力せずに Enter キーを押すと、アプリケーションが終了し、コンソール ウィンドウが閉じます。</span><span class="sxs-lookup"><span data-stu-id="1c5cb-135">If the user presses the Enter key without entering a string, the application ends, and the console window closes.</span></span>

1. <span data-ttu-id="1c5cb-136">必要に応じて、ツールバーを変更して、`ShowCase` プロジェクトの**デバッグ** リリースをコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="1c5cb-136">If necessary, change the toolbar to compile the **Debug** release of the `ShowCase` project.</span></span> <span data-ttu-id="1c5cb-137">**ShowCase** の緑色の矢印を選び、プログラムをコンパイルして実行します。</span><span class="sxs-lookup"><span data-stu-id="1c5cb-137">Compile and run the program by selecting the green arrow on the **ShowCase** button.</span></span>

   ![[デバッグ] ボタンを示している Visual Studio プロジェクトのツールバー](./media/consuming-library-with-visual-studio/visual-studio-project-toolbar.png)

<span data-ttu-id="1c5cb-139">「[Visual Studio を使用して C# または Visual Basic .NET Core の Hello World アプリケーションをデバッグする](debugging-with-visual-studio.md)」および「[Visual Studio での .NET Core Hello World アプリケーションの発行](publishing-with-visual-studio.md)」の手順に従って、このライブラリを使うアプリケーションをデバッグして発行できます。</span><span class="sxs-lookup"><span data-stu-id="1c5cb-139">You can debug and publish the application that uses this library by following the steps in [Debug your C# or Visual Basic .NET Core Hello World application using Visual Studio](debugging-with-visual-studio.md) and [Publish your .NET Core Hello World application with Visual Studio](publishing-with-visual-studio.md).</span></span>

## <a name="create-a-nuget-package"></a><span data-ttu-id="1c5cb-140">NuGet パッケージの作成</span><span class="sxs-lookup"><span data-stu-id="1c5cb-140">Create a NuGet package</span></span>

<span data-ttu-id="1c5cb-141">NuGet パッケージとして発行すると、クラス ライブラリが広く利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="1c5cb-141">You can make your class library widely available by publishing it as a NuGet package.</span></span> <span data-ttu-id="1c5cb-142">NuGet パッケージの作成は Visual Studio ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="1c5cb-142">Visual Studio doesn't support the creation of NuGet packages.</span></span> <span data-ttu-id="1c5cb-143">作成するには、.NET Core CLI コマンドを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c5cb-143">To create one, you need to use the .NET Core CLI commands:</span></span>

1. <span data-ttu-id="1c5cb-144">コンソール ウィンドウが開きます。</span><span class="sxs-lookup"><span data-stu-id="1c5cb-144">Open a console window.</span></span>

   <span data-ttu-id="1c5cb-145">たとえば、Windows タスク バーの検索ボックスに「**コマンド プロンプト**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="1c5cb-145">For example, enter **Command Prompt** in the search box on the Windows task bar.</span></span> <span data-ttu-id="1c5cb-146">**[コマンド プロンプト]** デスクトップ アプリを選択するか、検索結果で既に選択されている場合は、**Enter** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="1c5cb-146">Select the **Command Prompt** desktop app or press **Enter** if it's already selected in the search results.</span></span>

1. <span data-ttu-id="1c5cb-147">ライブラリのプロジェクト ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="1c5cb-147">Navigate to your library's project directory.</span></span> <span data-ttu-id="1c5cb-148">このディレクトリには、ソース コードおよびプロジェクト ファイル *StringLibrary.csproj* または *StringLibrary.vbproj* が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1c5cb-148">The directory contains your source code and a project file, *StringLibrary.csproj* or *StringLibrary.vbproj*.</span></span>

1. <span data-ttu-id="1c5cb-149">[dotnet pack](../tools/dotnet-pack.md) コマンドを実行して、 *.nupkg* 拡張子を持つパッケージを生成します。</span><span class="sxs-lookup"><span data-stu-id="1c5cb-149">Run the [dotnet pack](../tools/dotnet-pack.md) command to generate a package with a *.nupkg* extension:</span></span>

   ```dotnetcli
   dotnet pack --no-build
   ```

   > [!TIP]
   > <span data-ttu-id="1c5cb-150">*dotnet.exe* を含むディレクトリが PATH になくても、コンソール ウィンドウで「`where dotnet.exe`」と入力して、場所を検索できます。</span><span class="sxs-lookup"><span data-stu-id="1c5cb-150">If the directory that contains *dotnet.exe* is not in your PATH, you can find its location by entering `where dotnet.exe` in the console window.</span></span>

<span data-ttu-id="1c5cb-151">NuGet パッケージの作成に関する詳細については、「[.NET Core CLI を使用して NuGet パッケージを作成する方法](../deploying/creating-nuget-packages.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1c5cb-151">For more information on creating NuGet packages, see [How to create a NuGet package with the .NET Core CLI](../deploying/creating-nuget-packages.md).</span></span>
