---
title: 汎用性のあるクラス ライブラリを使用したプラットフォーム間の開発
description: .NET でポータブルクラスライブラリのプロジェクトタイプを使用して、Microsoft プラットフォーム向けのクロスプラットフォームアプリやライブラリをすばやく簡単にビルドできます。
ms.date: 09/17/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- Portable Class Library [.NET Framework]
- targeting multiple platforms
- multiple platforms, targeting
ms.assetid: c31e1663-c164-4e65-b66d-d3aa8750a154
ms.openlocfilehash: be1a49f7da7ce98f9e5e3ff8d927ce5230bfa8d8
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/15/2020
ms.locfileid: "84769146"
---
# <a name="cross-platform-development-with-the-portable-class-library"></a><span data-ttu-id="50434-103">ポータブルクラスライブラリを使用したクロスプラットフォーム開発</span><span class="sxs-lookup"><span data-stu-id="50434-103">Cross-platform development with the Portable Class Library</span></span>

<span data-ttu-id="50434-104">Visual Studio のポータブルクラスライブラリのプロジェクトの種類を使用すると、Microsoft プラットフォーム向けのクロスプラットフォームアプリやライブラリをすばやく簡単にビルドできます。</span><span class="sxs-lookup"><span data-stu-id="50434-104">The Portable Class Library project type in Visual Studio helps you build cross-platform apps and libraries for Microsoft platforms quickly and easily.</span></span>

[!INCLUDE[standard](../../../includes/pcl-to-standard.md)]

<span data-ttu-id="50434-105">ポータブル クラス ライブラリにより、コードの開発とテストにかかる時間とコストを削減できます。</span><span class="sxs-lookup"><span data-stu-id="50434-105">Portable class libraries can help you reduce the time and costs of developing and testing code.</span></span> <span data-ttu-id="50434-106">このプロジェクトの種類を使用して、ポータブル .NET Framework アセンブリを作成してビルドし、.NET Framework、iOS、Mac などの複数のプラットフォームを対象とするアプリからそれらのアセンブリを参照します。</span><span class="sxs-lookup"><span data-stu-id="50434-106">Use this project type to write and build portable .NET Framework assemblies, and then reference those assemblies from apps that target multiple platforms such as the .NET Framework, iOS, or Mac.</span></span>

<span data-ttu-id="50434-107">Visual Studio でポータブル クラス ライブラリ プロジェクトを作成し、プロジェクトの開発を開始した後でも、ターゲット プラットフォームを変更できます。</span><span class="sxs-lookup"><span data-stu-id="50434-107">Even after you create a Portable Class Library project in Visual Studio and start developing it, you can change the target platforms.</span></span> <span data-ttu-id="50434-108">Visual Studio では、新しいアセンブリを使用してライブラリをコンパイルします。これにより、コードで行う必要がある変更を特定できます。</span><span class="sxs-lookup"><span data-stu-id="50434-108">Visual Studio compiles your library with the new assemblies, which helps you identify the changes you need to make in your code.</span></span>

## <a name="create-a-portable-class-library-project"></a><span data-ttu-id="50434-109">ポータブルクラスライブラリプロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="50434-109">Create a Portable Class Library project</span></span>

<span data-ttu-id="50434-110">ポータブルクラスライブラリを作成するには、Visual Studio に用意されているテンプレートを使用します。</span><span class="sxs-lookup"><span data-stu-id="50434-110">To create a Portable Class Library, use the template provided in Visual Studio.</span></span> <span data-ttu-id="50434-111">新しいプロジェクトを作成し ([**ファイル**  >  ] [**新しい**プロジェクト])、[**新しいプロジェクト**] ダイアログボックスで、プログラミング言語 (Visual C# または Visual Basic) を選択します。</span><span class="sxs-lookup"><span data-stu-id="50434-111">Create a new project (**File** > **New Project**), and in the **New Project** dialog box, select your programming language (Visual C# or Visual Basic).</span></span> <span data-ttu-id="50434-112">次に、[**クラスライブラリ (レガシポータブル)** ] テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="50434-112">Then, select the **Class Library (Legacy Portable)** template.</span></span> <span data-ttu-id="50434-113">プロジェクトの名前を入力し、[ **OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="50434-113">Enter a name for your project and choose **OK**.</span></span>

<span data-ttu-id="50434-114">[**ポータブルクラスライブラリの追加**] ダイアログボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="50434-114">The **Add Portable Class Library** dialog box appears.</span></span> <span data-ttu-id="50434-115">2つ以上のターゲットを選択し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="50434-115">Choose two or more targets, and then choose **OK**.</span></span>

![Visual Studio でポータブルクラスライブラリターゲットを追加する](media/add-portable-class-library.png)

## <a name="change-targets"></a><span data-ttu-id="50434-117">ターゲットの変更</span><span class="sxs-lookup"><span data-stu-id="50434-117">Change targets</span></span>

<span data-ttu-id="50434-118">ポータブルクラスライブラリプロジェクトを作成するとき、または開発を開始した後で、ターゲットプラットフォームを変更できます。</span><span class="sxs-lookup"><span data-stu-id="50434-118">You can change the target platforms of a portable class library project when you create it or after you've started development.</span></span> <span data-ttu-id="50434-119">プロジェクトの作成後にターゲットを変更する場合は、**ソリューションエクスプローラー**で、ポータブルクラスライブラリプロジェクト (ソリューションではない) のショートカットメニューを開き、[**プロパティ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="50434-119">If you want to change the targets after you've created your project, in **Solution Explorer**, open the shortcut menu for your Portable Class Library project (not the solution), and then choose **Properties**.</span></span> <span data-ttu-id="50434-120">プロジェクトのプロパティページの [**ライブラリ**] タブに、プロジェクトが現在対象としているプラットフォームが表示されます。</span><span class="sxs-lookup"><span data-stu-id="50434-120">On the project properties page, the **Library** tab shows the platforms that your project currently targets.</span></span>

![Visual Studio のポータブルクラスライブラリのプロジェクトプロパティ](media/pcl-project-properties.png)

<span data-ttu-id="50434-122">ターゲットを追加または削除するには、[**変更**] ボタンをクリックし、適切なチェックボックスをオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="50434-122">To add or remove targets, choose the **Change** button, and then select and clear the appropriate check boxes.</span></span>

<span data-ttu-id="50434-123">ターゲットを変更すると、変更後のターゲットに合わせて、プロジェクトの開発に使用できる API が変更されます。</span><span class="sxs-lookup"><span data-stu-id="50434-123">When you change the targets, the APIs that are available to you for developing your project will change to match your selection.</span></span> <span data-ttu-id="50434-124">Visual Studio は、ターゲットを変更したことで発生する可能性があるエラーと警告を報告します。</span><span class="sxs-lookup"><span data-stu-id="50434-124">Visual Studio reports the errors and warnings that may occur as a result of the targets changing.</span></span>

<span data-ttu-id="50434-125">Visual Studio で変更を加える前にアセンブリの移植性を評価する場合は、 [.Net 移植性アナライザー](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer)を使用できます。</span><span class="sxs-lookup"><span data-stu-id="50434-125">If you want to evaluate the portability of your assemblies before you make changes in Visual Studio, you can use the [.NET Portability Analyzer](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer).</span></span>

## <a name="supported-types-and-members"></a><span data-ttu-id="50434-126">サポートされている型とメンバー</span><span class="sxs-lookup"><span data-stu-id="50434-126">Supported types and members</span></span>

<span data-ttu-id="50434-127">ポータブル クラス ライブラリのプロジェクトで使用できる型とメンバーは、互換性に関するいくつかの要因による制約を受けます。</span><span class="sxs-lookup"><span data-stu-id="50434-127">The types and members that are available in Portable Class Library projects are constrained by several compatibility factors:</span></span>

- <span data-ttu-id="50434-128">選択したターゲット間で共有される必要があります。</span><span class="sxs-lookup"><span data-stu-id="50434-128">They must be shared across the targets you selected.</span></span>

- <span data-ttu-id="50434-129">それらのターゲット間で同様に動作する必要があります。</span><span class="sxs-lookup"><span data-stu-id="50434-129">The must behave similarly across those targets.</span></span>

- <span data-ttu-id="50434-130">廃止候補であってはなりません。</span><span class="sxs-lookup"><span data-stu-id="50434-130">They must not be candidates for deprecation.</span></span>

- <span data-ttu-id="50434-131">特にサポートしているメンバーがポータブルでない場合は、ポータブルな環境に意味がある必要があります。</span><span class="sxs-lookup"><span data-stu-id="50434-131">They must make sense in a portable environment, especially when supporting members are not portable.</span></span>

<span data-ttu-id="50434-132">メンバーがポータブル クラス ライブラリでサポートされており、選択したターゲットのメンバーである場合、IntelliSense でプロジェクトにこのメンバーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="50434-132">If a member is supported in the Portable Class Library and for your selected targets, it will appear in your project in IntelliSense.</span></span> <span data-ttu-id="50434-133">ただし、API がポータブル クラス ライブラリでサポートされている可能性があります。API を使用できるかどうかは、選択したターゲットによって異なります。</span><span class="sxs-lookup"><span data-stu-id="50434-133">However, remember that an API may be supported in the Portable Class Library, but whether you can use the API depends on the targets you select.</span></span>

## <a name="api-differences-in-the-portable-class-library"></a><span data-ttu-id="50434-134">ポータブル クラス ライブラリでの API の相違点</span><span class="sxs-lookup"><span data-stu-id="50434-134">API differences in the Portable Class Library</span></span>

<span data-ttu-id="50434-135">サポートされるすべてのプラットフォームでポータブル クラス ライブラリ アセンブリの互換性を確保するために、ポータブル クラス ライブラリでは一部のメンバーが若干変更されています。</span><span class="sxs-lookup"><span data-stu-id="50434-135">To make Portable Class Library assemblies compatible across all supported platforms, some members have been slightly changed in the Portable Class Library.</span></span>

## <a name="use-the-portable-class-library"></a><span data-ttu-id="50434-136">ポータブルクラスライブラリを使用する</span><span class="sxs-lookup"><span data-stu-id="50434-136">Use the Portable Class Library</span></span>

<span data-ttu-id="50434-137">ポータブル クラス ライブラリ プロジェクトをビルドしたら、他のプロジェクトからそのプロジェクトを参照します。</span><span class="sxs-lookup"><span data-stu-id="50434-137">After you build your Portable Class Library project, you just reference it from other projects.</span></span> <span data-ttu-id="50434-138">プロジェクトを参照することも、アクセスする必要のあるクラスを含む特定のアセンブリを参照することもできます。</span><span class="sxs-lookup"><span data-stu-id="50434-138">You can reference either the project or specific assemblies that contain the classes you want to access.</span></span>

<span data-ttu-id="50434-139">ポータブル クラス ライブラリ アセンブリを参照するアプリを実行するには、ターゲット プラットフォームの必要なバージョン (またはそれ以上のバージョン) がコンピューターにインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="50434-139">To run an app that references a Portable Class Library assembly, the required version (or later) of the targeted platforms must be installed on your computer.</span></span> <span data-ttu-id="50434-140">Visual Studio には必要なすべてのフレームワークが含まれるため、さらに変更を加えることなく、アプリケーションの開発に使用したコンピューターでアプリケーションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="50434-140">Visual Studio contains all the required frameworks, so you can run the app without further modification on the computer that you used to develop the app.</span></span>

### <a name="deploy-a-universal-windows-app"></a><span data-ttu-id="50434-141">ユニバーサル Windows アプリを展開する</span><span class="sxs-lookup"><span data-stu-id="50434-141">Deploy a Universal Windows app</span></span>

<span data-ttu-id="50434-142">ポータブルクラスライブラリアセンブリを参照するユニバーサル Windows アプリを作成する場合、アプリを展開するために必要なものはすべてアプリパッケージに含まれており、それ以上の手順は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="50434-142">When you create a Universal Windows app that references a Portable Class Library assembly, everything you need to deploy the app is included in the app package, and no further steps are required.</span></span>

### <a name="deploy-a-net-framework-app"></a><span data-ttu-id="50434-143">.NET Framework アプリをデプロイする</span><span class="sxs-lookup"><span data-stu-id="50434-143">Deploy a .NET Framework app</span></span>

<span data-ttu-id="50434-144">ポータブル クラス ライブラリ アセンブリを参照する .NET Framework アプリを配置するときは、.NET Framework の正しいバージョンに対する依存関係を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="50434-144">When you deploy a .NET Framework app that references a Portable Class Library assembly, you must specify a dependency on the correct version of the .NET Framework.</span></span> <span data-ttu-id="50434-145">この依存関係を指定することで、必要なバージョンがアプリケーションと共に確実にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="50434-145">By specifying this dependency, you ensure that the required version is installed with your app.</span></span>

- <span data-ttu-id="50434-146">ClickOnce 配置を使用して依存関係を作成するには:**ソリューションエクスプローラー**で、発行するプロジェクトのプロジェクトノードを選択します。</span><span class="sxs-lookup"><span data-stu-id="50434-146">To create a dependency with ClickOnce deployment: In **Solution Explorer**, choose the project node for the project you want to publish.</span></span> <span data-ttu-id="50434-147">(これは、ポータブルクラスライブラリプロジェクトを参照するプロジェクトです)。メニューバーで [**プロジェクト**のプロパティ] を選択し、  >  **Properties**[**発行**] タブを選択します。[**発行**] ページで、[**前提条件**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="50434-147">(This is the project that references the Portable Class Library project.) On the menu bar, choose **Project** > **Properties**, and then choose the **Publish** tab. On the **Publish** page, choose **Prerequisites**.</span></span> <span data-ttu-id="50434-148">必須コンポーネントとして、必要な .NET Framework のバージョンを選択します。</span><span class="sxs-lookup"><span data-stu-id="50434-148">Select the required .NET Framework version as a prerequisite.</span></span>

- <span data-ttu-id="50434-149">セットアッププロジェクトとの依存関係を作成するには、**ソリューションエクスプローラー**で、セットアッププロジェクトを選択します。</span><span class="sxs-lookup"><span data-stu-id="50434-149">To create a dependency with a setup project: In **Solution Explorer**, choose the setup project.</span></span> <span data-ttu-id="50434-150">メニューバーで、[**プロジェクト**  >  **プロパティ**] [  >  **前提条件**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="50434-150">On the menu bar, choose **Project** > **Properties** > **Prerequisites**.</span></span> <span data-ttu-id="50434-151">必須コンポーネントとして、必要な .NET Framework のバージョンを選択します。</span><span class="sxs-lookup"><span data-stu-id="50434-151">Select the required .NET Framework version as a prerequisite.</span></span>

<span data-ttu-id="50434-152">.NET Framework アプリのデプロイの詳細については、「[開発者向け配置ガイド](../../framework/deployment/deployment-guide-for-developers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="50434-152">For more information about deploying .NET Framework apps, see [Deployment Guide for Developers](../../framework/deployment/deployment-guide-for-developers.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="50434-153">関連項目</span><span class="sxs-lookup"><span data-stu-id="50434-153">See also</span></span>

- [<span data-ttu-id="50434-154">MVVM を利用した汎用性のあるクラス ライブラリの使用</span><span class="sxs-lookup"><span data-stu-id="50434-154">Using Portable Class Library with MVVM</span></span>](using-portable-class-library-with-model-view-view-model.md)
- [<span data-ttu-id="50434-155">複数のプラットフォームを対象とするライブラリのアプリリソース</span><span class="sxs-lookup"><span data-stu-id="50434-155">App Resources for Libraries That Target Multiple Platforms</span></span>](app-resources-for-libraries-that-target-multiple-platforms.md)
- [<span data-ttu-id="50434-156">.NET Portability Analyzer</span><span class="sxs-lookup"><span data-stu-id="50434-156">.NET Portability Analyzer</span></span>](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer)
- [<span data-ttu-id="50434-157">Windows ストア アプリおよび Windows ランタイムのための .NET Framework サポート</span><span class="sxs-lookup"><span data-stu-id="50434-157">.NET Framework Support for Windows Store Apps and Windows Runtime</span></span>](support-for-windows-store-apps-and-windows-runtime.md)
- [<span data-ttu-id="50434-158">デプロイ</span><span class="sxs-lookup"><span data-stu-id="50434-158">Deployment</span></span>](../../framework/deployment/net-framework-applications.md)
