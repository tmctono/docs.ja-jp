---
title: Visual Studio 2017 を使用して C# .NET Standard ライブラリを構築する
description: Visual Studio 2017 を使用して C# で記述された .NET Standard クラス ライブラリを作成する方法について説明します。
author: BillWagner
ms.author: wiwagn
ms.date: 08/07/2017
ms.custom: vs-dotnet, seodec18
ms.openlocfilehash: 440ef2ed398b22262923422efd7f1259e3ee9b74
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65633691"
---
# <a name="build-a-net-standard-library-with-c-and-the-net-core-sdk-in-visual-studio-2017"></a><span data-ttu-id="b7291-103">Visual Studio 2017 の C# と .NET Core を使用して .NET Standard ライブラリを構築する</span><span class="sxs-lookup"><span data-stu-id="b7291-103">Build a .NET Standard library with C# and the .NET Core SDK in Visual Studio 2017</span></span>

<span data-ttu-id="b7291-104">"*クラス ライブラリ*" は、アプリケーションから呼び出される型とメソッドを定義します。</span><span class="sxs-lookup"><span data-stu-id="b7291-104">A *class library* defines types and methods that are called by an application.</span></span> <span data-ttu-id="b7291-105">.NET Standard 2.0 をターゲットとするクラス ライブラリでは、お使いのライブラリを、そのバージョンの .NET Standard をサポートする任意の .NET 実装によって呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="b7291-105">A class library that targets the .NET Standard 2.0 allows your library to be called by any .NET implementation that supports that version of the .NET Standard.</span></span> <span data-ttu-id="b7291-106">クラス ライブラリを完了させたら、サードパーティ製のコンポーネントとして配布するかどうか、あるいは 1 つまたは複数のアプリケーションにバンドルされたコンポーネントとして含めるかどうかを決定できます。</span><span class="sxs-lookup"><span data-stu-id="b7291-106">When you finish your class library, you can decide whether you want to distribute it as a third-party component or whether you want to include it as a bundled component with one or more applications.</span></span>

> [!NOTE]
> <span data-ttu-id="b7291-107">.NET Standard のバージョンとサポート対象のプラットフォームの一覧は、[「.NET Standard」](../../standard/net-standard.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b7291-107">For a list of the .NET Standard versions and the platforms they support, see [.NET Standard](../../standard/net-standard.md).</span></span>

<span data-ttu-id="b7291-108">このトピックでは、1 つの文字列処理メソッドを含む簡単なユーティリティ ライブラリを作成します。</span><span class="sxs-lookup"><span data-stu-id="b7291-108">In this topic, you'll create a simple utility library that contains a single string-handling method.</span></span> <span data-ttu-id="b7291-109">それを[拡張メソッド](../../csharp/programming-guide/classes-and-structs/extension-methods.md)として実装し、<xref:System.String> クラスのメンバーと同じように呼び出すことができるようにします。</span><span class="sxs-lookup"><span data-stu-id="b7291-109">You'll implement it as an [extension method](../../csharp/programming-guide/classes-and-structs/extension-methods.md) so that you can call it as if it were a member of the <xref:System.String> class.</span></span>

## <a name="creating-a-class-library-solution"></a><span data-ttu-id="b7291-110">クラス ライブラリのソリューションを作成する</span><span class="sxs-lookup"><span data-stu-id="b7291-110">Creating a class library solution</span></span>

<span data-ttu-id="b7291-111">最初に、クラス ライブラリ プロジェクトとその関連プロジェクトのソリューションを作成します。</span><span class="sxs-lookup"><span data-stu-id="b7291-111">Start by creating a solution for your class library project and its related projects.</span></span> <span data-ttu-id="b7291-112">1 つの Visual Studio のソリューションは、1 つまたは複数のプロジェクトのコンテナーとして機能します。</span><span class="sxs-lookup"><span data-stu-id="b7291-112">A Visual Studio Solution just serves as a container for one or more projects.</span></span> <span data-ttu-id="b7291-113">このソリューションは次のように作成します。</span><span class="sxs-lookup"><span data-stu-id="b7291-113">To create the solution:</span></span>

1. <span data-ttu-id="b7291-114">Visual Studio のメニュー バーで、**[ファイル]** > **[新規作成]** > **[プロジェクト]** の順に選びます。</span><span class="sxs-lookup"><span data-stu-id="b7291-114">On the Visual Studio menu bar, choose **File** > **New** > **Project**.</span></span>

1. <span data-ttu-id="b7291-115">**[新しいプロジェクト]** ダイアログの **[その他のプロジェクトの種類]** ノードを展開し、**[Visual Studio ソリューション]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="b7291-115">In the **New Project** dialog, expand the **Other Project Types** node, and select **Visual Studio Solutions**.</span></span> <span data-ttu-id="b7291-116">ソリューションの名前を "ClassLibraryProjects" にして、**[OK]** ボタンを選びます。</span><span class="sxs-lookup"><span data-stu-id="b7291-116">Name the solution "ClassLibraryProjects" and select the **OK** button.</span></span>

   ![新しい空のソリューションが強調表示されている [新しいプロジェクト] ダイアログ](./media/library-with-visual-studio/new-project-dialog.png)

## <a name="creating-the-class-library-project"></a><span data-ttu-id="b7291-118">クラス ライブラリ プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="b7291-118">Creating the class library project</span></span>

<span data-ttu-id="b7291-119">クラス ライブラリ プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="b7291-119">Create your class library project:</span></span>

1. <span data-ttu-id="b7291-120">**ソリューション エクスプローラー**で **ClassLibraryProjects** ソリューション ファイルを右クリックし、コンテキスト メニューから **[追加]** > **[新しいプロジェクト]** の順に選びます。</span><span class="sxs-lookup"><span data-stu-id="b7291-120">In **Solution Explorer**, right-click on the **ClassLibraryProjects** solution file and from the context menu, select **Add** > **New Project**.</span></span>

1. <span data-ttu-id="b7291-121">**[新しいプロジェクトの追加]** ダイアログで、**[Visual C#]** ノードを展開し、**[.NET Standard]** ノードを選択し、**[クラス ライブラリ (.NET Standard)]** プロジェクト テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="b7291-121">In the **Add New Project** dialog, expand the **Visual C#** node, then select the **.NET Standard** node followed by the **Class Library (.NET Standard)** project template.</span></span> <span data-ttu-id="b7291-122">**[名前]** テキスト ボックスに、プロジェクト名として「StringLibrary」と入力します。</span><span class="sxs-lookup"><span data-stu-id="b7291-122">In the **Name** text box, enter "StringLibrary" as the name of the project.</span></span> <span data-ttu-id="b7291-123">**[OK]** を選んでクラス ライブラリ プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="b7291-123">Select **OK** to create the class library project.</span></span>

   ![新しいライブラリ プロジェクトの追加ダイアログ](./media/library-with-visual-studio/add-new-library-project.png)

   <span data-ttu-id="b7291-125">Visual Studio 開発環境でコード ウィンドウが開きます。</span><span class="sxs-lookup"><span data-stu-id="b7291-125">The code window then opens in the Visual Studio development environment.</span></span>

   ![既定のクラス ライブラリ テンプレート コードが表示された Visual Studio アプリケーション ウィンドウ](./media/library-with-visual-studio/string-library-project.png)

1. <span data-ttu-id="b7291-127">ライブラリが正しいバージョンの .NET Standard をターゲットにしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b7291-127">Check to make sure that our library targets the correct version of the .NET Standard.</span></span> <span data-ttu-id="b7291-128">**ソリューション エクスプローラー** ウィンドウで、ライブラリ プロジェクトを右クリックし、**[プロパティ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b7291-128">Right-click on the library project in the **Solution Explorer** windows, then select **Properties**.</span></span> <span data-ttu-id="b7291-129">**[ターゲット フレームワーク]** テキスト ボックスに、.NET Standard 2.0 がターゲットになっていることが示されています。</span><span class="sxs-lookup"><span data-stu-id="b7291-129">The **Target Framework** text box shows that we're targeting .NET Standard 2.0.</span></span>

   ![クラス ライブラリのプロジェクト プロパティ](./media/library-with-visual-studio/library-project-properties.png)

1. <span data-ttu-id="b7291-131">コード ウィンドウ内のコードを次のコードに置き換えて、ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="b7291-131">Replace the code in the code window with the following code and save the file:</span></span>

   [!CODE-csharp[ClassLib#1](../../../samples/snippets/csharp/getting_started/with_visual_studio_2017/classlib.cs)]

   <span data-ttu-id="b7291-132">クラス ライブラリ `UtilityLibraries.StringLibrary` には `StartsWithUpper` という名前のメソッドが含まれており、これによって、現在の文字列のインスタンスが大文字で始まるかどうかを示す <xref:System.Boolean> 値が返されます。</span><span class="sxs-lookup"><span data-stu-id="b7291-132">The class library, `UtilityLibraries.StringLibrary`, contains a method named `StartsWithUpper`, which returns a <xref:System.Boolean> value that indicates whether the current string instance begins with an uppercase character.</span></span> <span data-ttu-id="b7291-133">Unicode 規格では、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="b7291-133">The Unicode standard distinguishes uppercase characters from lowercase characters.</span></span> <span data-ttu-id="b7291-134"><xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> メソッドは文字が大文字の場合に `true` を返します。</span><span class="sxs-lookup"><span data-stu-id="b7291-134">The <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> method returns `true` if a character is uppercase.</span></span>

1. <span data-ttu-id="b7291-135">メニュー バーで **[ビルド]** > **[ソリューションのビルド]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="b7291-135">On the menu bar, select **Build** > **Build Solution**.</span></span> <span data-ttu-id="b7291-136">プロジェクトはエラーなしでコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="b7291-136">The project should compile without error.</span></span>

   ![ビルドが成功したことを示す出力ペイン](./media/library-with-visual-studio/output-pane-successful-build.png)

## <a name="next-step"></a><span data-ttu-id="b7291-138">次のステップ</span><span class="sxs-lookup"><span data-stu-id="b7291-138">Next step</span></span>

<span data-ttu-id="b7291-139">ライブラリを正常に作成できました。</span><span class="sxs-lookup"><span data-stu-id="b7291-139">You've successfully built the library.</span></span> <span data-ttu-id="b7291-140">そのメソッドの呼び出しをまだ行っていないので、期待どおりに動作するかわかりません。</span><span class="sxs-lookup"><span data-stu-id="b7291-140">Because you haven't called any of its methods, you don't know whether it works as expected.</span></span> <span data-ttu-id="b7291-141">ライブラリ開発の次のステップでは、[単体テスト プロジェクト](testing-library-with-visual-studio.md)を使ってライブラリをテストします。</span><span class="sxs-lookup"><span data-stu-id="b7291-141">The next step in developing your library is to test it by using a [Unit Test Project](testing-library-with-visual-studio.md).</span></span>
