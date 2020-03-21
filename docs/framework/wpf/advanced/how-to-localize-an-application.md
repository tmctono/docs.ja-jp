---
title: '方法 : アプリケーションをローカライズする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- localization [WPF], applications
- LocBaml tool [WPF]
- applications [WPF], localizing
ms.assetid: 5001227e-9326-48a4-9dcd-ba1b89ee6653
ms.openlocfilehash: f2e7e5e8879e89806cfd457a1af80f51b91871cb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174213"
---
# <a name="how-to-localize-an-application"></a><span data-ttu-id="e4b48-102">方法 : アプリケーションをローカライズする</span><span class="sxs-lookup"><span data-stu-id="e4b48-102">How to: Localize an Application</span></span>
<span data-ttu-id="e4b48-103">このチュートリアルでは、LocBaml ツールを使用して、ローカライズされたアプリケーションを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e4b48-103">This tutorial explains how to create a localized application by using the LocBaml tool.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e4b48-104">LocBaml ツールは、実稼働可能なアプリケーションではありません。</span><span class="sxs-lookup"><span data-stu-id="e4b48-104">The LocBaml tool is not a production-ready application.</span></span> <span data-ttu-id="e4b48-105">それはローカリゼーション API の一部を使用するサンプルとして提供されており、ローカリゼーション ツールを記述する方法を例示します。</span><span class="sxs-lookup"><span data-stu-id="e4b48-105">It is presented as a sample that uses some of the localization APIs and illustrates how you might write a localization tool.</span></span>  
  
<a name="Introduction"></a>
## <a name="overview"></a><span data-ttu-id="e4b48-106">概要</span><span class="sxs-lookup"><span data-stu-id="e4b48-106">Overview</span></span>  
 <span data-ttu-id="e4b48-107">この説明では、アプリケーションのローカリゼーションの手順を段階を追って示します。</span><span class="sxs-lookup"><span data-stu-id="e4b48-107">This discussion gives you a step-by-step approach to localizing an application.</span></span> <span data-ttu-id="e4b48-108">最初に、翻訳されるテキストを抽出できるようにアプリケーションを準備します。</span><span class="sxs-lookup"><span data-stu-id="e4b48-108">First, you will prepare your application so that the text that will be translated can be extracted.</span></span> <span data-ttu-id="e4b48-109">テキストの翻訳後、翻訳されたテキストを元のアプリケーションの新しいコピーにマージします。</span><span class="sxs-lookup"><span data-stu-id="e4b48-109">After the text is translated, you will merge the translated text into a new copy of the original application.</span></span>  
  
<a name="Requirements"></a>
## <a name="requirements"></a><span data-ttu-id="e4b48-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="e4b48-110">Requirements</span></span>  
 <span data-ttu-id="e4b48-111">この説明の過程で、コマンド ラインから実行されるコンパイラである Microsoft ビルド エンジン (MSBuild) を使用します。</span><span class="sxs-lookup"><span data-stu-id="e4b48-111">Over the course of this discussion, you will use Microsoft build engine (MSBuild), which is a compiler that runs from the command line.</span></span>  
  
 <span data-ttu-id="e4b48-112">また、プロジェクト ファイルを使用するよう指示されます。</span><span class="sxs-lookup"><span data-stu-id="e4b48-112">Also, you will be instructed to use a project file.</span></span> <span data-ttu-id="e4b48-113">MSBuild ファイルとプロジェクト ファイルの使用方法については、「[ビルドと配置](../app-development/building-and-deploying-wpf-applications.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4b48-113">For instructions on how to use MSBuild and project files, see [Build and Deploy](../app-development/building-and-deploying-wpf-applications.md).</span></span>  
  
 <span data-ttu-id="e4b48-114">この説明のすべての例では、カルチャとして en-US (英語-米国) を使用します。</span><span class="sxs-lookup"><span data-stu-id="e4b48-114">All the examples in this discussion use en-US (English-US) as the culture.</span></span> <span data-ttu-id="e4b48-115">別の言語をインストールしなくても、この例の手順全体の作業を行えます。</span><span class="sxs-lookup"><span data-stu-id="e4b48-115">This enables you to work through the steps of the examples without installing a different language.</span></span>  
  
<a name="create_sample_app"></a>
## <a name="create-a-sample-application"></a><span data-ttu-id="e4b48-116">サンプルのアプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="e4b48-116">Create a Sample Application</span></span>  
 <span data-ttu-id="e4b48-117">このステップでは、ローカリゼーション用のアプリケーションを準備します。</span><span class="sxs-lookup"><span data-stu-id="e4b48-117">In this step, you will prepare your application for localization.</span></span> <span data-ttu-id="e4b48-118">[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] のサンプルでは、この説明のコード サンプルで使用される HelloApp のサンプルが提供されています。</span><span class="sxs-lookup"><span data-stu-id="e4b48-118">In the [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] samples, a HelloApp sample is supplied that will be used for the code examples in this discussion.</span></span> <span data-ttu-id="e4b48-119">このサンプルを使用する場合は[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)][、LocBaml ツールサンプル](https://github.com/microsoft/WPF-Samples/tree/master/Tools/LocBaml)からファイルをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="e4b48-119">If you would like to use this sample, download the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] files from the [LocBaml Tool Sample](https://github.com/microsoft/WPF-Samples/tree/master/Tools/LocBaml).</span></span>  
  
1. <span data-ttu-id="e4b48-120">ローカリゼーションを開始するポイントまで、アプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="e4b48-120">Develop your application to the point where you want to start localization.</span></span>  
  
2. <span data-ttu-id="e4b48-121">MSBuild がメイン アセンブリとサテライト アセンブリ (.resources.dll 拡張子を持つファイル) を生成してニュートラル言語リソースを含めるように、プロジェクト ファイルで開発言語を指定します。</span><span class="sxs-lookup"><span data-stu-id="e4b48-121">Specify the development language in the project file so that MSBuild generates a main assembly and a satellite assembly (a file with the .resources.dll extension) to contain the neutral language resources.</span></span> <span data-ttu-id="e4b48-122">HelloApp サンプルのプロジェクト ファイルは HelloApp.csproj です。</span><span class="sxs-lookup"><span data-stu-id="e4b48-122">The project file in the HelloApp sample is HelloApp.csproj.</span></span> <span data-ttu-id="e4b48-123">このファイルに、以下のように特定される開発言語があります。</span><span class="sxs-lookup"><span data-stu-id="e4b48-123">In that file, you will find the development language identified as follows:</span></span>  
  
     `<UICulture>en-US</UICulture>`  
  
3. <span data-ttu-id="e4b48-124">[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ファイルに UID を追加します。</span><span class="sxs-lookup"><span data-stu-id="e4b48-124">Add Uids to your [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] files.</span></span> <span data-ttu-id="e4b48-125">UID は、ファイルへの変更を追跡して、翻訳する必要がある項目を識別するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="e4b48-125">Uids are used to keep track of changes to files and to identify items that must be translated.</span></span> <span data-ttu-id="e4b48-126">ファイルに Uid を追加するには、プロジェクト ファイルで**updateuid**を実行します。</span><span class="sxs-lookup"><span data-stu-id="e4b48-126">To add Uids to your files, run **updateuid** on your project file:</span></span>  
  
     <span data-ttu-id="e4b48-127">**msbuild -t:アップデートイドハローアプリ.csproj**</span><span class="sxs-lookup"><span data-stu-id="e4b48-127">**msbuild -t:updateuid helloapp.csproj**</span></span>  
  
     <span data-ttu-id="e4b48-128">Uid が見つからないか重複していないかどうかを確認するには **、checkuid**を実行します。</span><span class="sxs-lookup"><span data-stu-id="e4b48-128">To verify that you have no missing or duplicate Uids, run **checkuid**:</span></span>  
  
     <span data-ttu-id="e4b48-129">**msbuild -t:チェックイド・ハローアプリ.csproj**</span><span class="sxs-lookup"><span data-stu-id="e4b48-129">**msbuild -t:checkuid helloapp.csproj**</span></span>  
  
     <span data-ttu-id="e4b48-130">**updateuid**を実行した後、ファイルに Uid が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4b48-130">After running **updateuid**, your files should contain Uids.</span></span> <span data-ttu-id="e4b48-131">たとえば、HelloApp の Pane1.xaml ファイルに、以下の内容があるはずです。</span><span class="sxs-lookup"><span data-stu-id="e4b48-131">For example, in the Pane1.xaml file of HelloApp, you should find the following:</span></span>  
  
     `<StackPanel x:Uid="StackPanel_1">`  
  
     `<TextBlock x:Uid="TextBlock_1">Hello World</TextBlock>`  
  
     `<TextBlock x:Uid="TextBlock_2">Goodbye World</TextBlock>`  
  
     `</StackPanel>`  
  
<a name="create_dll"></a>
## <a name="create-the-neutral-language-resources-satellite-assembly"></a><span data-ttu-id="e4b48-132">ニュートラル言語リソースのサテライト アセンブリを作成する</span><span class="sxs-lookup"><span data-stu-id="e4b48-132">Create the Neutral Language Resources Satellite Assembly</span></span>  
 <span data-ttu-id="e4b48-133">ニュートラル言語リソースのサテライト アセンブリを生成するようにアプリケーションを構成した後、アプリケーションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="e4b48-133">After the application is configured to generate a neutral language resources satellite assembly, you build the application.</span></span> <span data-ttu-id="e4b48-134">これにより、メイン アプリケーション アセンブリだけでなく、ローカリゼーションで LocBaml が必要とするニュートラル言語リソースのサテライト アセンブリが生成されます。</span><span class="sxs-lookup"><span data-stu-id="e4b48-134">This generates the main application assembly, as well as the neutral language resources satellite assembly that is required by LocBaml for localization.</span></span> <span data-ttu-id="e4b48-135">アプリケーションをビルドするには:</span><span class="sxs-lookup"><span data-stu-id="e4b48-135">To build the application:</span></span>  
  
1. <span data-ttu-id="e4b48-136">HelloApp をコンパイルしてダイナミック リンク ライブラリ (DLL) を作成します。</span><span class="sxs-lookup"><span data-stu-id="e4b48-136">Compile HelloApp to create a dynamic-link library (DLL):</span></span>  
  
     <span data-ttu-id="e4b48-137">**msbuild helloapp.csproj**</span><span class="sxs-lookup"><span data-stu-id="e4b48-137">**msbuild helloapp.csproj**</span></span>  
  
2. <span data-ttu-id="e4b48-138">新規作成されたメインのアプリケーション アセンブリ HelloApp.exe は、次のフォルダーに作成されます。</span><span class="sxs-lookup"><span data-stu-id="e4b48-138">The newly created main application assembly, HelloApp.exe, is created in the following folder:</span></span>  
  
     `C:\HelloApp\Bin\Debug\`  
  
3. <span data-ttu-id="e4b48-139">新規作成されたニュートラル言語リソースのサテライト アセンブリ HelloApp.resources.dll は次のフォルダーに作成されます。</span><span class="sxs-lookup"><span data-stu-id="e4b48-139">The newly created neutral language resources satellite assembly, HelloApp.resources.dll, is created in the following folder:</span></span>  
  
     `C:\HelloApp\Bin\Debug\en-US\`  
  
<a name="build_locbaml"></a>
## <a name="build-the-locbaml-tool"></a><span data-ttu-id="e4b48-140">LocBaml ツールをビルドする</span><span class="sxs-lookup"><span data-stu-id="e4b48-140">Build the LocBaml Tool</span></span>  
  
1. <span data-ttu-id="e4b48-141">LocBaml のビルドに必要なすべてのファイルは [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] サンプルに配置されています。</span><span class="sxs-lookup"><span data-stu-id="e4b48-141">All the files necessary to build LocBaml are located in the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] samples.</span></span> <span data-ttu-id="e4b48-142">[LocBaml ツールサンプル](https://github.com/microsoft/WPF-Samples/tree/master/Tools/LocBaml)から C# ファイルをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="e4b48-142">Download the C# files from the [LocBaml Tool Sample](https://github.com/microsoft/WPF-Samples/tree/master/Tools/LocBaml).</span></span>  
  
2. <span data-ttu-id="e4b48-143">ツールをビルドするには、コマンド ラインでプロジェクト ファイル (locbaml.csproj) を実行します。</span><span class="sxs-lookup"><span data-stu-id="e4b48-143">From the command line, run the project file (locbaml.csproj) to build the tool:</span></span>  
  
     <span data-ttu-id="e4b48-144">**msbuild locbaml.csproj**</span><span class="sxs-lookup"><span data-stu-id="e4b48-144">**msbuild locbaml.csproj**</span></span>  
  
3. <span data-ttu-id="e4b48-145">新しく作成された実行可能ファイル (locbaml.exe) を検索するには、bin \release ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="e4b48-145">Go to the Bin\Release directory to find the newly created executable file (locbaml.exe).</span></span> <span data-ttu-id="e4b48-146">例: C:\LocBaml\Bin\Release\locbaml.exe</span><span class="sxs-lookup"><span data-stu-id="e4b48-146">Example:C:\LocBaml\Bin\Release\locbaml.exe.</span></span>  
  
4. <span data-ttu-id="e4b48-147">LocBaml を実行するときに指定できるオプションは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e4b48-147">The options that you can specify when you run LocBaml are as follows:</span></span>  
  
    - <span data-ttu-id="e4b48-148">**解析**または **-p:** Baml、リソース、または DLL ファイルを解析して.csv ファイルまたは .txt ファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="e4b48-148">**parse** or **-p:** Parses Baml, resources, or DLL files to generate a .csv or .txt file.</span></span>  
  
    - <span data-ttu-id="e4b48-149">**生成**または **-g:** 翻訳されたファイルを使用して、ローカライズされたバイナリ ファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="e4b48-149">**generate** or **-g:** Generates a localized binary file by using a translated file.</span></span>  
  
    - <span data-ttu-id="e4b48-150">**out**または **-o** {*ファイルディレクトリ*] **:** 出力ファイル名。</span><span class="sxs-lookup"><span data-stu-id="e4b48-150">**out** or **-o** {*filedirectory*] **:** Output file name.</span></span>  
  
    - <span data-ttu-id="e4b48-151">**カルチャ**または **-cul** {*カルチャ*] **:** 出力アセンブリのロケール。</span><span class="sxs-lookup"><span data-stu-id="e4b48-151">**culture** or **-cul** {*culture*] **:** Locale of output assemblies.</span></span>  
  
    - <span data-ttu-id="e4b48-152">**翻訳**または **-trans** {*translation.csv*] **:** 翻訳されたファイルまたはローカライズされたファイル。</span><span class="sxs-lookup"><span data-stu-id="e4b48-152">**translation** or **-trans** {*translation.csv*] **:** Translated or localized file.</span></span>  
  
    - <span data-ttu-id="e4b48-153">**asmpath**または **-asmpath:** {*ファイルディレクトリ*] **:** コードにカスタム コントロールが[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]含まれている場合は、カスタム コントロール アセンブリに**asmpath**を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4b48-153">**asmpath** or **-asmpath:** {*filedirectory*] **:** If your [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] code contains custom controls, you must supply the **asmpath** to the custom control assembly.</span></span>  
  
    - <span data-ttu-id="e4b48-154">**nologo:** ロゴまたは著作権情報は表示されません。</span><span class="sxs-lookup"><span data-stu-id="e4b48-154">**nologo:** Displays no logo or copyright information.</span></span>  
  
    - <span data-ttu-id="e4b48-155">**verbose:** 詳細モードの情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e4b48-155">**verbose:** Displays verbose mode information.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="e4b48-156">ツールを実行するときにオプションの一覧が必要な場合は **、LocBaml.exe**と入力して Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="e4b48-156">If you need a list of the options when you are running the tool, type     **LocBaml.exe** and press ENTER.</span></span>  
  
<a name="parse_dll"></a>
## <a name="use-locbaml-to-parse-a-file"></a><span data-ttu-id="e4b48-157">LocBaml を使用してファイルを解析する</span><span class="sxs-lookup"><span data-stu-id="e4b48-157">Use LocBaml to Parse a File</span></span>  
 <span data-ttu-id="e4b48-158">LocBaml ツールが作成されたので、これを使用して HelloApp.resources.dll を解析し、ローカライズするテキスト コンテンツを抽出できる状態になりました。</span><span class="sxs-lookup"><span data-stu-id="e4b48-158">Now that you have created the LocBaml tool, you are ready to use it to parse HelloApp.resources.dll to extract the text content that will be localized.</span></span>  
  
1. <span data-ttu-id="e4b48-159">LocBaml.exe を、メインのアプリケーション アセンブリが作成された、アプリケーションの bin \debug フォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="e4b48-159">Copy LocBaml.exe to your application's bin\debug folder, where the main application assembly was created.</span></span>  
  
2. <span data-ttu-id="e4b48-160">サテライト アセンブリ ファイルを解析して、.csv ファイルとして出力を格納するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="e4b48-160">To parse the satellite assembly file and store the output as a .csv file, use the following command:</span></span>  
  
     <span data-ttu-id="e4b48-161">**LocBaml.exe /parse HelloApp.resources.dll /out:Hello.csv**</span><span class="sxs-lookup"><span data-stu-id="e4b48-161">**LocBaml.exe /parse HelloApp.resources.dll /out:Hello.csv**</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="e4b48-162">入力ファイル HelloApp.resources.dll が LocBaml.exe と同じディレクトリに存在しない場合は、いずれかのファイルを移動して両方のファイルが同じディレクトリにあるようにします。</span><span class="sxs-lookup"><span data-stu-id="e4b48-162">If the input file, HelloApp.resources.dll, is not in the same directory as LocBaml.exe move one of the files so that both files are in the same directory.</span></span>  
  
3. <span data-ttu-id="e4b48-163">LocBaml を実行してファイルを解析する際、出力はコンマ区切り (.csv ファイル) またはタブ区切り (.txt ファイル) された 7 つのフィールドで構成されます。</span><span class="sxs-lookup"><span data-stu-id="e4b48-163">When you run LocBaml to parse files, the output consists of seven fields delimited by commas (.csv files) or tabs (.txt files).</span></span> <span data-ttu-id="e4b48-164">HelloApp.resources.dll の解析済みの .csv ファイルを次に示します。</span><span class="sxs-lookup"><span data-stu-id="e4b48-164">The following shows the parsed .csv file for the HelloApp.resources.dll:</span></span>

   | |
   |-|
   |<span data-ttu-id="e4b48-165">HelloApp.g.en-US.resources:window1.baml,Stack1:System.Windows.Controls.StackPanel.$Content,Ignore,FALSE, FALSE,,#Text1;#Text2;</span><span class="sxs-lookup"><span data-stu-id="e4b48-165">HelloApp.g.en-US.resources:window1.baml,Stack1:System.Windows.Controls.StackPanel.$Content,Ignore,FALSE, FALSE,,#Text1;#Text2;</span></span>|
   |<span data-ttu-id="e4b48-166">HelloApp.g.en-US.resources:window1.baml,Text1:System.Windows.Controls.TextBlock.$Content,None,TRUE, TRUE,,Hello World</span><span class="sxs-lookup"><span data-stu-id="e4b48-166">HelloApp.g.en-US.resources:window1.baml,Text1:System.Windows.Controls.TextBlock.$Content,None,TRUE, TRUE,,Hello World</span></span>|
   |<span data-ttu-id="e4b48-167">HelloApp.g.en-US.resources:window1.baml,Text2:System.Windows.Controls.TextBlock.$Content,None,TRUE, TRUE,,Goodbye World</span><span class="sxs-lookup"><span data-stu-id="e4b48-167">HelloApp.g.en-US.resources:window1.baml,Text2:System.Windows.Controls.TextBlock.$Content,None,TRUE, TRUE,,Goodbye World</span></span>|

   <span data-ttu-id="e4b48-168">7 つのフィールドは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e4b48-168">The seven fields are:</span></span>  
  
   1. <span data-ttu-id="e4b48-169">**BAML 名**.</span><span class="sxs-lookup"><span data-stu-id="e4b48-169">**BAML Name**.</span></span> <span data-ttu-id="e4b48-170">ソース言語のサテライト アセンブリに関する BAML リソースの名前。</span><span class="sxs-lookup"><span data-stu-id="e4b48-170">The name of the BAML resource with respect to the source language satellite assembly.</span></span>  
  
   2. <span data-ttu-id="e4b48-171">**リソース キー**:</span><span class="sxs-lookup"><span data-stu-id="e4b48-171">**Resource Key**.</span></span> <span data-ttu-id="e4b48-172">ローカライズされたリソースの識別子。</span><span class="sxs-lookup"><span data-stu-id="e4b48-172">The localized resource identifier.</span></span>  
  
   3. <span data-ttu-id="e4b48-173">**カテゴリ**。</span><span class="sxs-lookup"><span data-stu-id="e4b48-173">**Category**.</span></span> <span data-ttu-id="e4b48-174">値の型です。</span><span class="sxs-lookup"><span data-stu-id="e4b48-174">The value type.</span></span> <span data-ttu-id="e4b48-175">[ローカリゼーション属性とコメントを](localization-attributes-and-comments.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4b48-175">See [Localization Attributes and Comments](localization-attributes-and-comments.md).</span></span>  
  
   4. <span data-ttu-id="e4b48-176">**読みやすさ**。</span><span class="sxs-lookup"><span data-stu-id="e4b48-176">**Readability**.</span></span> <span data-ttu-id="e4b48-177">ローカライザーによって値が読み取れるかどうか。</span><span class="sxs-lookup"><span data-stu-id="e4b48-177">Whether the value can be read by a localizer.</span></span> <span data-ttu-id="e4b48-178">[ローカリゼーション属性とコメントを](localization-attributes-and-comments.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4b48-178">See [Localization Attributes and Comments](localization-attributes-and-comments.md).</span></span>  
  
   5. <span data-ttu-id="e4b48-179">**変更可能性**。</span><span class="sxs-lookup"><span data-stu-id="e4b48-179">**Modifiability**.</span></span> <span data-ttu-id="e4b48-180">ローカライザーによって値が変更できるかどうか。</span><span class="sxs-lookup"><span data-stu-id="e4b48-180">Whether the value can be modified by a localizer.</span></span> <span data-ttu-id="e4b48-181">[ローカリゼーション属性とコメントを](localization-attributes-and-comments.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4b48-181">See [Localization Attributes and Comments](localization-attributes-and-comments.md).</span></span>  
  
   6. <span data-ttu-id="e4b48-182">**コメント**.</span><span class="sxs-lookup"><span data-stu-id="e4b48-182">**Comments**.</span></span> <span data-ttu-id="e4b48-183">値をローカライズする方法を決定するための値の追加の説明。</span><span class="sxs-lookup"><span data-stu-id="e4b48-183">Additional description of the value to help determine how a value is localized.</span></span> <span data-ttu-id="e4b48-184">[ローカリゼーション属性とコメントを](localization-attributes-and-comments.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4b48-184">See [Localization Attributes and Comments](localization-attributes-and-comments.md).</span></span>  
  
   7. <span data-ttu-id="e4b48-185">**値**。</span><span class="sxs-lookup"><span data-stu-id="e4b48-185">**Value**.</span></span> <span data-ttu-id="e4b48-186">目的のカルチャに翻訳するテキストの値。</span><span class="sxs-lookup"><span data-stu-id="e4b48-186">The text value to translate to the desired culture.</span></span>  
  
   <span data-ttu-id="e4b48-187">次の表は、.csv ファイルの区切り記号付きの値にこれらのフィールドをマップする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="e4b48-187">The following table shows how these fields map to the delimited values of the .csv file:</span></span>  
  
   |<span data-ttu-id="e4b48-188">BAML 名</span><span class="sxs-lookup"><span data-stu-id="e4b48-188">BAML name</span></span>|<span data-ttu-id="e4b48-189">リソース キー</span><span class="sxs-lookup"><span data-stu-id="e4b48-189">Resource key</span></span>|<span data-ttu-id="e4b48-190">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="e4b48-190">Category</span></span>|<span data-ttu-id="e4b48-191">読みやすさ</span><span class="sxs-lookup"><span data-stu-id="e4b48-191">Readability</span></span>|<span data-ttu-id="e4b48-192">変更可能性</span><span class="sxs-lookup"><span data-stu-id="e4b48-192">Modifiability</span></span>|<span data-ttu-id="e4b48-193">説明</span><span class="sxs-lookup"><span data-stu-id="e4b48-193">Comments</span></span>|<span data-ttu-id="e4b48-194">Value</span><span class="sxs-lookup"><span data-stu-id="e4b48-194">Value</span></span>|  
   |---------------|------------------|--------------|-----------------|-------------------|--------------|-----------|
   |<span data-ttu-id="e4b48-195">HelloApp.g.en-US.resources:window1.baml</span><span class="sxs-lookup"><span data-stu-id="e4b48-195">HelloApp.g.en-US.resources:window1.baml</span></span>|<span data-ttu-id="e4b48-196">Stack1:System.Windows.Controls.StackPanel.$Content</span><span class="sxs-lookup"><span data-stu-id="e4b48-196">Stack1:System.Windows.Controls.StackPanel.$Content</span></span>|<span data-ttu-id="e4b48-197">Ignore</span><span class="sxs-lookup"><span data-stu-id="e4b48-197">Ignore</span></span>|<span data-ttu-id="e4b48-198">FALSE</span><span class="sxs-lookup"><span data-stu-id="e4b48-198">FALSE</span></span>|<span data-ttu-id="e4b48-199">FALSE</span><span class="sxs-lookup"><span data-stu-id="e4b48-199">FALSE</span></span>||<span data-ttu-id="e4b48-200">#Text1;#Text2</span><span class="sxs-lookup"><span data-stu-id="e4b48-200">#Text1;#Text2</span></span>|
   |<span data-ttu-id="e4b48-201">HelloApp.g.en-US.resources:window1.baml</span><span class="sxs-lookup"><span data-stu-id="e4b48-201">HelloApp.g.en-US.resources:window1.baml</span></span>|<span data-ttu-id="e4b48-202">Stack1:System.Windows.Controls.StackPanel.$Content</span><span class="sxs-lookup"><span data-stu-id="e4b48-202">Text1:System.Windows.Controls.TextBlock.$Content</span></span>|<span data-ttu-id="e4b48-203">なし</span><span class="sxs-lookup"><span data-stu-id="e4b48-203">None</span></span>|<span data-ttu-id="e4b48-204">TRUE</span><span class="sxs-lookup"><span data-stu-id="e4b48-204">TRUE</span></span>|<span data-ttu-id="e4b48-205">TRUE</span><span class="sxs-lookup"><span data-stu-id="e4b48-205">TRUE</span></span>||<span data-ttu-id="e4b48-206">Hello World</span><span class="sxs-lookup"><span data-stu-id="e4b48-206">Hello World</span></span>|
   |<span data-ttu-id="e4b48-207">HelloApp.g.en-US.resources:window1.baml</span><span class="sxs-lookup"><span data-stu-id="e4b48-207">HelloApp.g.en-US.resources:window1.baml</span></span>|<span data-ttu-id="e4b48-208">Stack1:System.Windows.Controls.StackPanel.$Content</span><span class="sxs-lookup"><span data-stu-id="e4b48-208">Text2:System.Windows.Controls.TextBlock.$Content</span></span>|<span data-ttu-id="e4b48-209">なし</span><span class="sxs-lookup"><span data-stu-id="e4b48-209">None</span></span>|<span data-ttu-id="e4b48-210">TRUE</span><span class="sxs-lookup"><span data-stu-id="e4b48-210">TRUE</span></span>|<span data-ttu-id="e4b48-211">TRUE</span><span class="sxs-lookup"><span data-stu-id="e4b48-211">TRUE</span></span>||<span data-ttu-id="e4b48-212">Goodbye World</span><span class="sxs-lookup"><span data-stu-id="e4b48-212">Goodbye World</span></span>|
  
   <span data-ttu-id="e4b48-213">**[コメント]** フィールドのすべての値に値が含まれていないことに注意してください。フィールドに値がない場合は、空になります。</span><span class="sxs-lookup"><span data-stu-id="e4b48-213">Notice that all the values for the **Comments** field contain no values; if a field doesn't have a value, it is empty.</span></span> <span data-ttu-id="e4b48-214">また、最初の行の項目は読み取りも変更もできませんが、**その Category**値として "Ignore" が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e4b48-214">Also notice that the item in the first row is neither readable nor modifiable, and has "Ignore" as its **Category** value, all of which indicates that the value is not localizable.</span></span>  
  
4. <span data-ttu-id="e4b48-215">解析されたファイル (特に大きなファイル) でローカライズ可能なアイテムを簡単に検出するには、**カテゴリ**、**読みやすさ**、および**変更可能性**を使用してアイテムを並べ替えたり、フィルタ処理したりできます。</span><span class="sxs-lookup"><span data-stu-id="e4b48-215">To facilitate discovery of localizable items in parsed files, particularly in large files, you can sort or filter the items by **Category**, **Readability**, and **Modifiability**.</span></span> <span data-ttu-id="e4b48-216">たとえば、読み取りも変更もできない値をフィルター処理することができます。</span><span class="sxs-lookup"><span data-stu-id="e4b48-216">For example, you can filter out unreadable and unmodifiable values.</span></span>  
  
<a name="translate_loc_content"></a>
## <a name="translate-the-localizable-content"></a><span data-ttu-id="e4b48-217">ローカライズ可能なコンテンツを翻訳する</span><span class="sxs-lookup"><span data-stu-id="e4b48-217">Translate the Localizable Content</span></span>  
 <span data-ttu-id="e4b48-218">抽出されたコンテンツを翻訳するために使用可能な任意のツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="e4b48-218">Use any tool that you have available to translate the extracted content.</span></span> <span data-ttu-id="e4b48-219">これを行う良い方法は、リソースを .csv ファイルに書き込み、Microsoft Excel で表示し、最後の列 (値) に変換を変更することです。</span><span class="sxs-lookup"><span data-stu-id="e4b48-219">A good way to do this is to write the resources to a .csv file and view them in Microsoft Excel, making translation changes to the last column (value).</span></span>  
  
<a name="merge_translations"></a>
## <a name="use-locbaml-to-generate-a-new-resourcesdll-file"></a><span data-ttu-id="e4b48-220">LocBaml を使用して新しい .resources.dll ファイルを生成する</span><span class="sxs-lookup"><span data-stu-id="e4b48-220">Use LocBaml to Generate a New .resources.dll File</span></span>  
 <span data-ttu-id="e4b48-221">LocBaml で HelloApp.resources.dll を解析して識別されたコンテンツは翻訳済みであり、元のアプリケーションにマージする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4b48-221">The content that was identified by parsing HelloApp.resources.dll with LocBaml has been translated and must be merged back into the original application.</span></span> <span data-ttu-id="e4b48-222">新しい .resources.dll ファイルを生成するには、**生成**オプションまたは **-g**オプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="e4b48-222">Use the **generate** or **-g** option to generate a new .resources.dll file.</span></span>  
  
1. <span data-ttu-id="e4b48-223">新しい HelloApp.resources.dll ファイルを生成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="e4b48-223">Use the following syntax to generate a new HelloApp.resources.dll file.</span></span> <span data-ttu-id="e4b48-224">カルチャを en-US (/cul:en-US) としてマークします。</span><span class="sxs-lookup"><span data-stu-id="e4b48-224">Mark the culture as en-US (/cul:en-US).</span></span>  
  
     <span data-ttu-id="e4b48-225">**ロックバml.exe /生成ハローアプリ.リソース.dll /トランス:こんにちは.csv /出力:c:\ /cul:en-US**</span><span class="sxs-lookup"><span data-stu-id="e4b48-225">**LocBaml.exe /generate HelloApp.resources.dll /trans:Hello.csv /out:c:\ /cul:en-US**</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="e4b48-226">入力ファイル Hello.csv が実行可能ファイル LocBaml.exe と同じディレクトリに存在しない場合は、いずれかのファイルを移動して、両方のファイルが同じディレクトリにあるようにします。</span><span class="sxs-lookup"><span data-stu-id="e4b48-226">If the input file, Hello.csv, is not in the same directory as the executable, LocBaml.exe, move one of the files so that both files are in the same directory.</span></span>  
  
2. <span data-ttu-id="e4b48-227">C:\HelloApp\Bin\Debug\en-US\HelloApp.resources.dll ディレクトリにある古い HelloApp.resources.dll ファイルを新規作成した HelloApp.resources.dll ファイルに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="e4b48-227">Replace the old HelloApp.resources.dll file in the C:\HelloApp\Bin\Debug\en-US\HelloApp.resources.dll directory with your newly created HelloApp.resources.dll file.</span></span>  
  
3. <span data-ttu-id="e4b48-228">ここで "Hello World" と "Goodbye World" をアプリケーション内で翻訳する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4b48-228">"Hello World" and "Goodbye World" should now be translated in your application.</span></span>  
  
4. <span data-ttu-id="e4b48-229">別のカルチャに翻訳するには、翻訳先の言語のカルチャを使用します。</span><span class="sxs-lookup"><span data-stu-id="e4b48-229">To translate to a different culture, use the culture of the language that you are translating to.</span></span> <span data-ttu-id="e4b48-230">フランス語 (カナダ) に翻訳する方法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="e4b48-230">The following example shows how to translate to French-Canadian:</span></span>  
  
     <span data-ttu-id="e4b48-231">**LocBaml.exe /generate HelloApp.resources.dll /trans:Hellofr-CA.csv /out:c:\ /cul:fr-CA**</span><span class="sxs-lookup"><span data-stu-id="e4b48-231">**LocBaml.exe /generate HelloApp.resources.dll /trans:Hellofr-CA.csv /out:c:\ /cul:fr-CA**</span></span>  
  
5. <span data-ttu-id="e4b48-232">メイン アプリケーション アセンブリと同じアセンブリで、新しいサテライト アセンブリを格納するために、新しいカルチャ固有のフォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="e4b48-232">In the same assembly as the main application assembly, create a new culture-specific folder to house the new satellite assembly.</span></span> <span data-ttu-id="e4b48-233">フランス語 (カナダ) のフォルダーは "fr-CA" となります。</span><span class="sxs-lookup"><span data-stu-id="e4b48-233">For French-Canadian, the folder would be fr-CA.</span></span>  
  
6. <span data-ttu-id="e4b48-234">新しいフォルダーに生成されたサテライト アセンブリをコピーします。</span><span class="sxs-lookup"><span data-stu-id="e4b48-234">Copy the generated satellite assembly to the new folder.</span></span>  
  
7. <span data-ttu-id="e4b48-235">新しいサテライト アセンブリをテストするには、アプリケーションが実行するカルチャを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4b48-235">To test the new satellite assembly, you need to change the culture under which your application will run.</span></span> <span data-ttu-id="e4b48-236">これは、次の 2 つの方法のいずれかで行うことができます。</span><span class="sxs-lookup"><span data-stu-id="e4b48-236">You can do this in one of two ways:</span></span>  
  
    - <span data-ttu-id="e4b48-237">オペレーティング システムの地域設定を変更する (**コントロール パネル**&#124; [**地域と言語のオプション**] &#124; [ コントロール パネル ] を**クリック**します)。</span><span class="sxs-lookup"><span data-stu-id="e4b48-237">Change your operating system's regional settings (**Start** &#124; **Control Panel** &#124; **Regional and Language Options**).</span></span>  
  
    - <span data-ttu-id="e4b48-238">アプリケーションで、次のコードを App.xaml.cs に追加します。</span><span class="sxs-lookup"><span data-stu-id="e4b48-238">In your application, add the following code to App.xaml.cs:</span></span>  
  
   [!code-xaml[LocBamlChangeCultureSnippets#LocBamlChangeCultureMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/LocBamlChangeCultureSnippets/CSharp/App.xaml#locbamlchangeculturemarkup)]
   [!code-csharp[LocBamlChangeCultureSnippets#LocBamlChangeCultureCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/LocBamlChangeCultureSnippets/CSharp/App.xaml.cs#locbamlchangeculturecodebehind)]
   [!code-vb[LocBamlChangeCultureSnippets#LocBamlChangeCultureCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/LocBamlChangeCultureSnippets/VisualBasic/Application.xaml.vb#locbamlchangeculturecodebehind)]  
  
<a name="Some_Tips_for_Using_LocBaml"></a>
## <a name="some-tips-for-using-locbaml"></a><span data-ttu-id="e4b48-239">LocBaml を使用するためのヒント</span><span class="sxs-lookup"><span data-stu-id="e4b48-239">Some Tips for Using LocBaml</span></span>  
  
- <span data-ttu-id="e4b48-240">カスタム コントロールを定義するすべての依存アセンブリを LocBaml のローカル ディレクトリにコピーするか、GAC にインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4b48-240">All dependent assemblies that define custom controls must be copied into the local directory of LocBaml or installed into the GAC.</span></span> <span data-ttu-id="e4b48-241">これは、ローカライズ API がバイナリ XAML (BAML) を読み取るときに依存アセンブリにアクセスする必要があるため、必要です。</span><span class="sxs-lookup"><span data-stu-id="e4b48-241">This is necessary because the localization API must have access to the dependent assemblies when it reads the binary XAML (BAML).</span></span>  
  
- <span data-ttu-id="e4b48-242">メインのアセンブリが署名済みの場合は、生成されたリソース DLL も読み込むために署名されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4b48-242">If the main assembly is signed, the generated resource DLL must also be signed in order for it to be loaded.</span></span>  
  
- <span data-ttu-id="e4b48-243">ローカライズされたリソースの DLL は、メインのアセンブリと同期する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4b48-243">The version of the localized resource DLL needs to be synchronized with the main assembly.</span></span>  
  
<a name="Whats_Next"></a>
## <a name="whats-next"></a><span data-ttu-id="e4b48-244">参照トピック</span><span class="sxs-lookup"><span data-stu-id="e4b48-244">What's Next</span></span>  
 <span data-ttu-id="e4b48-245">これで、LocBaml ツールの使用方法に関する基本的な知識が得られました。</span><span class="sxs-lookup"><span data-stu-id="e4b48-245">You should now have a basic understanding of how to use the LocBaml tool.</span></span>  <span data-ttu-id="e4b48-246">UID を含むファイルを作成できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="e4b48-246">You should be able to make a file that contains Uids.</span></span> <span data-ttu-id="e4b48-247">LocBaml ツールを使用することで、ローカライズ可能なコンテンツを抽出するファイルを解析できます。コンテンツを翻訳すると、翻訳済みのコンテンツをマージする .resources.dll ファイルを生成できます。</span><span class="sxs-lookup"><span data-stu-id="e4b48-247">By using the LocBaml tool, you should be able to parse a file to extract the localizable content, and after the content is translated, you should be able to generate a .resources.dll file that merges the translated content.</span></span> <span data-ttu-id="e4b48-248">このトピックには、可能性のあるすべての詳細情報は含まれていませんが、LocBaml を使用してアプリケーションをローカライズするために必要な知識は得られました。</span><span class="sxs-lookup"><span data-stu-id="e4b48-248">This topic does not include every possible detail, but you now have the knowledge necessary to use LocBaml for localizing your applications.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4b48-249">関連項目</span><span class="sxs-lookup"><span data-stu-id="e4b48-249">See also</span></span>

- [<span data-ttu-id="e4b48-250">WPF のグローバリゼーション</span><span class="sxs-lookup"><span data-stu-id="e4b48-250">Globalization for WPF</span></span>](globalization-for-wpf.md)
- [<span data-ttu-id="e4b48-251">自動レイアウトの使用の概要</span><span class="sxs-lookup"><span data-stu-id="e4b48-251">Use Automatic Layout Overview</span></span>](use-automatic-layout-overview.md)
