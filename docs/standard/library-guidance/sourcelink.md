---
title: ソース リンクと .NET ライブラリ
description: ソース リンクを使用して .NET ライブラリのデバッグ機能を改善するためのベスト プラクティス推奨事項。
ms.date: 01/15/2019
ms.openlocfilehash: 5dee2a6b1f77daa641351e02c1dd3e0a38f66550
ms.sourcegitcommit: 71b8f5a2108a0f1a4ef1d8d75c5b3e129ec5ca1e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2020
ms.locfileid: "84201984"
---
# <a name="source-link"></a><span data-ttu-id="ba6bb-103">ソース リンク</span><span class="sxs-lookup"><span data-stu-id="ba6bb-103">Source Link</span></span>

<span data-ttu-id="ba6bb-104">ソース リンクは NuGet からの .NET アセンブリのソース コードを開発者がデバッグすることを可能にするテクノロジです。</span><span class="sxs-lookup"><span data-stu-id="ba6bb-104">Source Link is a technology that enables source code debugging of .NET assemblies from NuGet by developers.</span></span> <span data-ttu-id="ba6bb-105">ソース リンクは NuGet パッケージの作成時に実行され、ソース コントロール メタデータをアセンブリとパッケージの内部に埋め込みます。</span><span class="sxs-lookup"><span data-stu-id="ba6bb-105">Source Link executes when creating the NuGet package and embeds source control metadata inside assemblies and the package.</span></span> <span data-ttu-id="ba6bb-106">パッケージをダウンロードし、Visual Studio でソース リンクを有効にした開発者は、そのソース コードにステップ インできます。</span><span class="sxs-lookup"><span data-stu-id="ba6bb-106">Developers who download the package and have Source Link enabled in Visual Studio can step into its source code.</span></span> <span data-ttu-id="ba6bb-107">ソース リンクからは、効率的なデバッグを可能にするソース コントロール メタデータが提供されます。</span><span class="sxs-lookup"><span data-stu-id="ba6bb-107">Source Link provides source control metadata to create a great debugging experience.</span></span>

## <a name="source-link-demo"></a><span data-ttu-id="ba6bb-108">ソース リンクのデモ</span><span class="sxs-lookup"><span data-stu-id="ba6bb-108">Source Link demo</span></span>

<!--markdownlint-disable MD034 -->
> [!VIDEO https://www.youtube.com/embed/gyRGhCQPkB4?start=61]

## <a name="using-source-link"></a><span data-ttu-id="ba6bb-109">ソース リンクを使用する</span><span class="sxs-lookup"><span data-stu-id="ba6bb-109">Using Source Link</span></span>

<span data-ttu-id="ba6bb-110">ソース リンクの使用方法は、[dotnet/sourcelink](https://github.com/dotnet/sourcelink/blob/master/README.md) GitHub リポジトリにあります。</span><span class="sxs-lookup"><span data-stu-id="ba6bb-110">Instructions for using Source Link can be found on the [dotnet/sourcelink](https://github.com/dotnet/sourcelink/blob/master/README.md) GitHub repository.</span></span>

<span data-ttu-id="ba6bb-111">[NuGet パッケージ エクスプローラー](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer)を使用すれば、ソース リンク メタデータがパッケージに正常に埋め込まれたことを確認できます。</span><span class="sxs-lookup"><span data-stu-id="ba6bb-111">You can use [NuGet Package Explorer](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer) to confirm that the Source Link metadata has been successfully embedded in the package.</span></span> <span data-ttu-id="ba6bb-112">`Repository` メタデータがコミット ID と共に存在すること、各ターゲットの .dll と共に .pdb ファイルが見つかることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ba6bb-112">Check the `Repository` metadata is present with a commit identifier and that .pdb files are located with each target's .dll.</span></span>

<span data-ttu-id="ba6bb-113">![NuGet パッケージ エクスプローラーのソース リンク](./media/sourcelink/nuget-package-explorer-sourcelink.png "NuGet パッケージ エクスプローラーのソース リンク")</span><span class="sxs-lookup"><span data-stu-id="ba6bb-113">![Source Link in NuGet Package Explorer](./media/sourcelink/nuget-package-explorer-sourcelink.png "Source Link in NuGet Package Explorer")</span></span>

<span data-ttu-id="ba6bb-114">✔️ 検討 ソース リンクを使用して、お使いのアセンブリと NuGet パッケージにソース管理のメタデータを追加する。</span><span class="sxs-lookup"><span data-stu-id="ba6bb-114">✔️ CONSIDER using Source Link to add source control metadata to your assemblies and NuGet packages.</span></span>

> [!TIP]
> <span data-ttu-id="ba6bb-115">デバッガー属性を型に追加することで開発者のデバッグ機能をさらに強化できます。</span><span class="sxs-lookup"><span data-stu-id="ba6bb-115">You can further enhance a developer's debugging experience by adding debugger attributes to your types.</span></span>
>
> * <span data-ttu-id="ba6bb-116"><xref:System.Diagnostics.DebuggerDisplayAttribute> では、デバッガーの変数ウィンドウでクラスやフィールドを表示する方法をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="ba6bb-116"><xref:System.Diagnostics.DebuggerDisplayAttribute> can customize how a class or field is displayed in the debugger variable windows.</span></span>
> * <span data-ttu-id="ba6bb-117"><xref:System.Diagnostics.DebuggerStepThroughAttribute> では、デバッガーに対してコードのステップ インではなくステップ実行が指示されます。</span><span class="sxs-lookup"><span data-stu-id="ba6bb-117"><xref:System.Diagnostics.DebuggerStepThroughAttribute> instructs the debugger to step through the code instead of stepping into the code.</span></span>
> * <span data-ttu-id="ba6bb-118"><xref:System.Diagnostics.DebuggerBrowsableAttribute> では、デバッガー変数ウィンドウにメンバーを表示するかどうかが制御されます。</span><span class="sxs-lookup"><span data-stu-id="ba6bb-118"><xref:System.Diagnostics.DebuggerBrowsableAttribute> controls whether a member is displayed in the debugger variable windows.</span></span>

<span data-ttu-id="ba6bb-119">✔️ 検討 シンボル ファイルを発行する (`*.pdb`)。</span><span class="sxs-lookup"><span data-stu-id="ba6bb-119">✔️ CONSIDER publishing symbol files (`*.pdb`).</span></span>

> <span data-ttu-id="ba6bb-120">デバッグのエクスペリエンスを最善にするには、ライブラリ上でシンボル ファイルを発行してソース リンクを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ba6bb-120">For the best debugging experience your library should publish symbol files as well as use Source Link.</span></span> <span data-ttu-id="ba6bb-121">シンボル ファイルとシンボル パッケージの詳細については、「[シンボル パッケージ](./nuget.md#symbol-packages)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ba6bb-121">For more information about symbol files and symbol packages, see [Symbol packages](./nuget.md#symbol-packages).</span></span>

<span data-ttu-id="ba6bb-122">✔️ 検討 決定論的ビルドを有効にする</span><span class="sxs-lookup"><span data-stu-id="ba6bb-122">✔️ CONSIDER enabling deterministic builds.</span></span>

> <span data-ttu-id="ba6bb-123">決定論的ビルドでは、結果として得られるバイナリが指定されたソースから構築され、追跡可能性を提供することの検証を可能にします。</span><span class="sxs-lookup"><span data-stu-id="ba6bb-123">Deterministic builds enable verification that the resulting binary was built from the specified source and provide traceability.</span></span> <span data-ttu-id="ba6bb-124">決定論的ビルドとそれを有効にするための手順の詳細については、[決定論的ビルド](https://github.com/clairernovotny/DeterministicBuilds)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ba6bb-124">For more information about deterministic builds and instructions for enabling them, see [Deterministic Builds](https://github.com/clairernovotny/DeterministicBuilds).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="ba6bb-125">[前へ](dependencies.md)
>[次へ](publish-nuget-package.md)</span><span class="sxs-lookup"><span data-stu-id="ba6bb-125">[Previous](dependencies.md)
[Next](publish-nuget-package.md)</span></span>
