---
title: 汎用性のあるクラス ライブラリを使用したプラットフォーム間の開発
ms.date: 09/17/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- Portable Class Library [.NET Framework]
- targeting multiple platforms
- multiple platforms, targeting
ms.assetid: c31e1663-c164-4e65-b66d-d3aa8750a154
ms.openlocfilehash: 7caddd7361b8f364762fb4357e35cb918ae99263
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2020
ms.locfileid: "81242804"
---
# <a name="cross-platform-development-with-the-portable-class-library"></a><span data-ttu-id="804ca-102">ポータブル クラス ライブラリを使用したクロスプラットフォーム開発</span><span class="sxs-lookup"><span data-stu-id="804ca-102">Cross-platform development with the Portable Class Library</span></span>

<span data-ttu-id="804ca-103">Visual Studio のポータブル クラス ライブラリ プロジェクトの種類を使用すると、Microsoft プラットフォーム向けのクロスプラットフォーム アプリやライブラリをすばやく簡単にビルドできます。</span><span class="sxs-lookup"><span data-stu-id="804ca-103">The Portable Class Library project type in Visual Studio helps you build cross-platform apps and libraries for Microsoft platforms quickly and easily.</span></span>

[!INCLUDE[standard](../../../includes/pcl-to-standard.md)]

<span data-ttu-id="804ca-104">ポータブル クラス ライブラリにより、コードの開発とテストにかかる時間とコストを削減できます。</span><span class="sxs-lookup"><span data-stu-id="804ca-104">Portable class libraries can help you reduce the time and costs of developing and testing code.</span></span> <span data-ttu-id="804ca-105">このプロジェクトの種類を使用して、ポータブル .NET Framework アセンブリを作成およびビルドし、.NET Framework、iOS、Mac などの複数のプラットフォームを対象とするアプリからこれらのアセンブリを参照します。</span><span class="sxs-lookup"><span data-stu-id="804ca-105">Use this project type to write and build portable .NET Framework assemblies, and then reference those assemblies from apps that target multiple platforms such as the .NET Framework, iOS, or Mac.</span></span>

<span data-ttu-id="804ca-106">Visual Studio でポータブル クラス ライブラリ プロジェクトを作成し、プロジェクトの開発を開始した後でも、ターゲット プラットフォームを変更できます。</span><span class="sxs-lookup"><span data-stu-id="804ca-106">Even after you create a Portable Class Library project in Visual Studio and start developing it, you can change the target platforms.</span></span> <span data-ttu-id="804ca-107">Visual Studio は、新しいアセンブリを使用してライブラリをコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="804ca-107">Visual Studio compiles your library with the new assemblies, which helps you identify the changes you need to make in your code.</span></span>

## <a name="create-a-portable-class-library-project"></a><span data-ttu-id="804ca-108">ポータブル クラス ライブラリ プロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="804ca-108">Create a Portable Class Library project</span></span>

<span data-ttu-id="804ca-109">ポータブル クラス ライブラリを作成するには、Visual Studio で提供されているテンプレートを使用します。</span><span class="sxs-lookup"><span data-stu-id="804ca-109">To create a Portable Class Library, use the template provided in Visual Studio.</span></span> <span data-ttu-id="804ca-110">新しいプロジェクト (**ファイル** > **の新しいプロジェクト**) を作成し、[**新しいプロジェクト**] ダイアログ ボックスで、プログラミング言語 (Visual C# または Visual Basic) を選択します。</span><span class="sxs-lookup"><span data-stu-id="804ca-110">Create a new project (**File** > **New Project**), and in the **New Project** dialog box, select your programming language (Visual C# or Visual Basic).</span></span> <span data-ttu-id="804ca-111">次に、**クラス ライブラリ (レガシ ポータブル)** テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="804ca-111">Then, select the **Class Library (Legacy Portable)** template.</span></span> <span data-ttu-id="804ca-112">プロジェクトの名前を入力し **、[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="804ca-112">Enter a name for your project and choose **OK**.</span></span>

<span data-ttu-id="804ca-113">[**ポータブル クラス ライブラリの追加**] ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="804ca-113">The **Add Portable Class Library** dialog box appears.</span></span> <span data-ttu-id="804ca-114">複数のターゲットを選択し **、[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="804ca-114">Choose two or more targets, and then choose **OK**.</span></span>

![Visual Studio でポータブル クラス ライブラリ ターゲットを追加する](media/add-portable-class-library.png)

## <a name="change-targets"></a><span data-ttu-id="804ca-116">ターゲットの変更</span><span class="sxs-lookup"><span data-stu-id="804ca-116">Change targets</span></span>

<span data-ttu-id="804ca-117">ポータブル クラス ライブラリ プロジェクトのターゲット プラットフォームは、作成時または開発開始後に変更できます。</span><span class="sxs-lookup"><span data-stu-id="804ca-117">You can change the target platforms of a portable class library project when you create it or after you've started development.</span></span> <span data-ttu-id="804ca-118">プロジェクトを作成した後にターゲットを変更する場合は、**ソリューション エクスプローラー**で、ポータブル クラス ライブラリ プロジェクトのショートカット メニュー (ソリューションではなく) を開き、[**プロパティ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="804ca-118">If you want to change the targets after you've created your project, in **Solution Explorer**, open the shortcut menu for your Portable Class Library project (not the solution), and then choose **Properties**.</span></span> <span data-ttu-id="804ca-119">プロジェクトのプロパティ ページの [**ライブラリ**] タブには、プロジェクトが現在対象としているプラットフォームが表示されます。</span><span class="sxs-lookup"><span data-stu-id="804ca-119">On the project properties page, the **Library** tab shows the platforms that your project currently targets.</span></span>

![Visual Studio のポータブル クラス ライブラリのプロジェクト プロパティ](media/pcl-project-properties.png)

<span data-ttu-id="804ca-121">ターゲットを追加または削除するには、[**変更**] ボタンを選択し、該当するチェック ボックスをオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="804ca-121">To add or remove targets, choose the **Change** button, and then select and clear the appropriate check boxes.</span></span>

<span data-ttu-id="804ca-122">ターゲットを変更すると、変更後のターゲットに合わせて、プロジェクトの開発に使用できる API が変更されます。</span><span class="sxs-lookup"><span data-stu-id="804ca-122">When you change the targets, the APIs that are available to you for developing your project will change to match your selection.</span></span> <span data-ttu-id="804ca-123">Visual Studio は、ターゲットを変更したことで発生する可能性があるエラーと警告を報告します。</span><span class="sxs-lookup"><span data-stu-id="804ca-123">Visual Studio reports the errors and warnings that may occur as a result of the targets changing.</span></span>

<span data-ttu-id="804ca-124">Visual Studio で変更を加える前にアセンブリの移植性を評価する場合は[、.NET 移植性アナライザ](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer)ー を使用できます。</span><span class="sxs-lookup"><span data-stu-id="804ca-124">If you want to evaluate the portability of your assemblies before you make changes in Visual Studio, you can use the [.NET Portability Analyzer](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer).</span></span>

## <a name="supported-types-and-members"></a><span data-ttu-id="804ca-125">サポートされている型とメンバー</span><span class="sxs-lookup"><span data-stu-id="804ca-125">Supported types and members</span></span>

<span data-ttu-id="804ca-126">ポータブル クラス ライブラリのプロジェクトで使用できる型とメンバーは、互換性に関するいくつかの要因による制約を受けます。</span><span class="sxs-lookup"><span data-stu-id="804ca-126">The types and members that are available in Portable Class Library projects are constrained by several compatibility factors:</span></span>

- <span data-ttu-id="804ca-127">選択したターゲット間で共有される必要があります。</span><span class="sxs-lookup"><span data-stu-id="804ca-127">They must be shared across the targets you selected.</span></span>

- <span data-ttu-id="804ca-128">それらのターゲット間で同様に動作する必要があります。</span><span class="sxs-lookup"><span data-stu-id="804ca-128">The must behave similarly across those targets.</span></span>

- <span data-ttu-id="804ca-129">廃止候補であってはなりません。</span><span class="sxs-lookup"><span data-stu-id="804ca-129">They must not be candidates for deprecation.</span></span>

- <span data-ttu-id="804ca-130">特にサポートしているメンバーがポータブルでない場合は、ポータブルな環境に意味がある必要があります。</span><span class="sxs-lookup"><span data-stu-id="804ca-130">They must make sense in a portable environment, especially when supporting members are not portable.</span></span>

<span data-ttu-id="804ca-131">メンバーがポータブル クラス ライブラリでサポートされており、選択したターゲットのメンバーである場合、IntelliSense でプロジェクトにこのメンバーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="804ca-131">If a member is supported in the Portable Class Library and for your selected targets, it will appear in your project in IntelliSense.</span></span> <span data-ttu-id="804ca-132">ただし、API がポータブル クラス ライブラリでサポートされている可能性があります。API を使用できるかどうかは、選択したターゲットによって異なります。</span><span class="sxs-lookup"><span data-stu-id="804ca-132">However, remember that an API may be supported in the Portable Class Library, but whether you can use the API depends on the targets you select.</span></span>

## <a name="api-differences-in-the-portable-class-library"></a><span data-ttu-id="804ca-133">ポータブル クラス ライブラリでの API の相違点</span><span class="sxs-lookup"><span data-stu-id="804ca-133">API differences in the Portable Class Library</span></span>

<span data-ttu-id="804ca-134">サポートされるすべてのプラットフォームでポータブル クラス ライブラリ アセンブリの互換性を確保するために、ポータブル クラス ライブラリでは一部のメンバーが若干変更されています。</span><span class="sxs-lookup"><span data-stu-id="804ca-134">To make Portable Class Library assemblies compatible across all supported platforms, some members have been slightly changed in the Portable Class Library.</span></span>

## <a name="use-the-portable-class-library"></a><span data-ttu-id="804ca-135">ポータブル クラス ライブラリを使用する</span><span class="sxs-lookup"><span data-stu-id="804ca-135">Use the Portable Class Library</span></span>

<span data-ttu-id="804ca-136">ポータブル クラス ライブラリ プロジェクトをビルドしたら、他のプロジェクトからそのプロジェクトを参照します。</span><span class="sxs-lookup"><span data-stu-id="804ca-136">After you build your Portable Class Library project, you just reference it from other projects.</span></span> <span data-ttu-id="804ca-137">プロジェクトを参照することも、アクセスする必要のあるクラスを含む特定のアセンブリを参照することもできます。</span><span class="sxs-lookup"><span data-stu-id="804ca-137">You can reference either the project or specific assemblies that contain the classes you want to access.</span></span>

<span data-ttu-id="804ca-138">ポータブル クラス ライブラリ アセンブリを参照するアプリを実行するには、ターゲット プラットフォームの必要なバージョン (またはそれ以上のバージョン) がコンピューターにインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="804ca-138">To run an app that references a Portable Class Library assembly, the required version (or later) of the targeted platforms must be installed on your computer.</span></span> <span data-ttu-id="804ca-139">Visual Studio には必要なすべてのフレームワークが含まれるため、さらに変更を加えることなく、アプリケーションの開発に使用したコンピューターでアプリケーションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="804ca-139">Visual Studio contains all the required frameworks, so you can run the app without further modification on the computer that you used to develop the app.</span></span>

### <a name="deploy-a-universal-windows-app"></a><span data-ttu-id="804ca-140">ユニバーサル Windows アプリを展開する</span><span class="sxs-lookup"><span data-stu-id="804ca-140">Deploy a Universal Windows app</span></span>

<span data-ttu-id="804ca-141">ポータブル クラス ライブラリ アセンブリを参照するユニバーサル Windows アプリを作成する場合、アプリパッケージにアプリを展開するために必要なものはすべてアプリ パッケージに含まれ、それ以上の手順は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="804ca-141">When you create a Universal Windows app that references a Portable Class Library assembly, everything you need to deploy the app is included in the app package, and no further steps are required.</span></span>

### <a name="deploy-a-net-framework-app"></a><span data-ttu-id="804ca-142">.NET Framework アプリを展開する</span><span class="sxs-lookup"><span data-stu-id="804ca-142">Deploy a .NET Framework app</span></span>

<span data-ttu-id="804ca-143">ポータブル クラス ライブラリ アセンブリを参照する .NET Framework アプリを配置するときは、.NET Framework の正しいバージョンに対する依存関係を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="804ca-143">When you deploy a .NET Framework app that references a Portable Class Library assembly, you must specify a dependency on the correct version of the .NET Framework.</span></span> <span data-ttu-id="804ca-144">この依存関係を指定することで、必要なバージョンがアプリケーションと共に確実にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="804ca-144">By specifying this dependency, you ensure that the required version is installed with your app.</span></span>

- <span data-ttu-id="804ca-145">ClickOnce 配置を使用して依存関係を作成するには、**ソリューション エクスプローラー**で、発行するプロジェクトのプロジェクト ノードを選択します。</span><span class="sxs-lookup"><span data-stu-id="804ca-145">To create a dependency with ClickOnce deployment: In **Solution Explorer**, choose the project node for the project you want to publish.</span></span> <span data-ttu-id="804ca-146">(これは、ポータブル クラス ライブラリ プロジェクトを参照するプロジェクトです)。メニュー バーで [**プロジェクト** > **のプロパティ]** をクリックし、[**発行**] タブを選択します。[**発行**] ページで、[**必須コンポーネント**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="804ca-146">(This is the project that references the Portable Class Library project.) On the menu bar, choose **Project** > **Properties**, and then choose the **Publish** tab. On the **Publish** page, choose **Prerequisites**.</span></span> <span data-ttu-id="804ca-147">必須コンポーネントとして、必要な .NET Framework のバージョンを選択します。</span><span class="sxs-lookup"><span data-stu-id="804ca-147">Select the required .NET Framework version as a prerequisite.</span></span>

- <span data-ttu-id="804ca-148">セットアップ プロジェクトとの依存関係を作成するには、**ソリューション エクスプローラー**でセットアップ プロジェクトを選択します。</span><span class="sxs-lookup"><span data-stu-id="804ca-148">To create a dependency with a setup project: In **Solution Explorer**, choose the setup project.</span></span> <span data-ttu-id="804ca-149">メニュー バーで、[**プロジェクト** > **のプロパティの** > **前提条件**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="804ca-149">On the menu bar, choose **Project** > **Properties** > **Prerequisites**.</span></span> <span data-ttu-id="804ca-150">必須コンポーネントとして、必要な .NET Framework のバージョンを選択します。</span><span class="sxs-lookup"><span data-stu-id="804ca-150">Select the required .NET Framework version as a prerequisite.</span></span>

<span data-ttu-id="804ca-151">NET Framework アプリの展開の詳細については、「[開発者向けの展開ガイド](../../../docs/framework/deployment/deployment-guide-for-developers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="804ca-151">For more information about deploying .NET Framework apps, see [Deployment Guide for Developers](../../../docs/framework/deployment/deployment-guide-for-developers.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="804ca-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="804ca-152">See also</span></span>

- [<span data-ttu-id="804ca-153">MVVM を利用した汎用性のあるクラス ライブラリの使用</span><span class="sxs-lookup"><span data-stu-id="804ca-153">Using Portable Class Library with MVVM</span></span>](using-portable-class-library-with-model-view-view-model.md)
- [<span data-ttu-id="804ca-154">複数のプラットフォームを対象とするライブラリのアプリ リソース</span><span class="sxs-lookup"><span data-stu-id="804ca-154">App Resources for Libraries That Target Multiple Platforms</span></span>](app-resources-for-libraries-that-target-multiple-platforms.md)
- [<span data-ttu-id="804ca-155">.NET Portability Analyzer</span><span class="sxs-lookup"><span data-stu-id="804ca-155">.NET Portability Analyzer</span></span>](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer)
- [<span data-ttu-id="804ca-156">Windows ストア アプリおよび Windows ランタイムのための .NET Framework サポート</span><span class="sxs-lookup"><span data-stu-id="804ca-156">.NET Framework Support for Windows Store Apps and Windows Runtime</span></span>](../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md)
- [<span data-ttu-id="804ca-157">デプロイ</span><span class="sxs-lookup"><span data-stu-id="804ca-157">Deployment</span></span>](../../../docs/framework/deployment/net-framework-applications.md)
