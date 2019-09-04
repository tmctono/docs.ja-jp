---
title: Windows 互換機能パックを使用してコードを .NET Core に移植する
description: Windows 互換機能パックとそれを使用して既存の .NET Framework コードを .NET Core に移植する方法について紹介します。
author: terrajobst
ms.date: 12/07/2018
ms.custom: seodec18
ms.openlocfilehash: 71e390881d4e9c7836622abeed49c0ea2e5f7526
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2019
ms.locfileid: "70202564"
---
# <a name="use-the-windows-compatibility-pack-to-port-code-to-net-core"></a><span data-ttu-id="2b911-103">Windows 互換機能パックを使用してコードを .NET Core に移植する</span><span class="sxs-lookup"><span data-stu-id="2b911-103">Use the Windows Compatibility Pack to port code to .NET Core</span></span>

<span data-ttu-id="2b911-104">既存のコードを .NET Core に移植する際に発生する最も一般的な問題の一部として、.NET Framework のみに存在する API およびテクノロジへの依存があります。</span><span class="sxs-lookup"><span data-stu-id="2b911-104">Some of the most common issues found when porting existing code to .NET Core are dependencies on APIs and technologies that are only found in the .NET Framework.</span></span> <span data-ttu-id="2b911-105">*Windows 互換機能パック*には、このようなテクノロジの多くが用意されているので、.NET Core アプリケーションと .NET Standard ライブラリをはるかに簡単に構築できます。</span><span class="sxs-lookup"><span data-stu-id="2b911-105">The *Windows Compatibility Pack* provides many of these technologies, so it's much easier to build .NET Core applications and .NET Standard libraries.</span></span>

<span data-ttu-id="2b911-106">このパッケージは論理 [.NET Standard 2.0 の拡張](../whats-new/dotnet-core-2-0.md#api-changes-and-library-support)であり、API セットを大幅に増やします。ほとんど変更なしで既存コードがコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="2b911-106">This package is a logical [extension of .NET Standard 2.0](../whats-new/dotnet-core-2-0.md#api-changes-and-library-support) that significantly increases API set and existing code compiles with almost no modifications.</span></span> <span data-ttu-id="2b911-107">ただし、.NET Standard の約束 ("これはあらゆる .NET 実装の API を集めたものである") を守る目的で、レジストリ、Windows Management Instrumentation (WMI)、リフレクション出力 API など、すべてのプラットフォームで動作しないテクノロジは含まれていません。</span><span class="sxs-lookup"><span data-stu-id="2b911-107">But in order to keep the promise of .NET Standard ("it is the set of APIs that all .NET implementations provide"), this didn't include technologies that can't work across all platforms, such as registry, Windows Management Instrumentation (WMI), or reflection emit APIs.</span></span>

<span data-ttu-id="2b911-108">*Windows 互換機能パック*は .NET Standard を基盤とし、Windows 専用のテクノロジを利用できます。</span><span class="sxs-lookup"><span data-stu-id="2b911-108">The *Windows Compatibility Pack* sits on top of .NET Standard and provides access to technologies that are Windows only.</span></span> <span data-ttu-id="2b911-109">.NET Core に移行したいが、最初の手順が Windows に留まることである顧客にとって特に便利です。</span><span class="sxs-lookup"><span data-stu-id="2b911-109">It's especially useful for customers that want to move to .NET Core but plan to stay on Windows as a first step.</span></span> <span data-ttu-id="2b911-110">そのようなシナリオでは、Windows 専用テクノロジを利用できないことが移行における唯一のハードルとなります。アーキテクチャ上の利点がありません。</span><span class="sxs-lookup"><span data-stu-id="2b911-110">In that scenario, not being able to use Windows-only technologies is only a migration hurdle with zero architectural benefits.</span></span>

## <a name="package-contents"></a><span data-ttu-id="2b911-111">パッケージの内容</span><span class="sxs-lookup"><span data-stu-id="2b911-111">Package contents</span></span>

<span data-ttu-id="2b911-112">*Windows 互換機能パック*は NuGet パッケージ [Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility) 経由で提供され、.NET Core または .NET Standard を対象とするプロジェクトから参照できます。</span><span class="sxs-lookup"><span data-stu-id="2b911-112">The *Windows Compatibility Pack* is provided via the NuGet Package [Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility) and can be referenced from projects targeting .NET Core or .NET Standard.</span></span>

<span data-ttu-id="2b911-113">Windows 専用 API やプラットフォーム非依存 API など、約 20,000 の API を提供します。テクノロジ領域には次のものがあります。</span><span class="sxs-lookup"><span data-stu-id="2b911-113">It provides about 20,000 APIs, including Windows-only as well as cross-platform APIs from the following technology areas:</span></span>

* <span data-ttu-id="2b911-114">コード ページ</span><span class="sxs-lookup"><span data-stu-id="2b911-114">Code Pages</span></span>
* <span data-ttu-id="2b911-115">CodeDom</span><span class="sxs-lookup"><span data-stu-id="2b911-115">CodeDom</span></span>
* <span data-ttu-id="2b911-116">構成</span><span class="sxs-lookup"><span data-stu-id="2b911-116">Configuration</span></span>
* <span data-ttu-id="2b911-117">ディレクトリ サービス</span><span class="sxs-lookup"><span data-stu-id="2b911-117">Directory Services</span></span>
* <span data-ttu-id="2b911-118">描画</span><span class="sxs-lookup"><span data-stu-id="2b911-118">Drawing</span></span>
* <span data-ttu-id="2b911-119">ODBC</span><span class="sxs-lookup"><span data-stu-id="2b911-119">ODBC</span></span>
* <span data-ttu-id="2b911-120">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="2b911-120">Permissions</span></span>
* <span data-ttu-id="2b911-121">ポート</span><span class="sxs-lookup"><span data-stu-id="2b911-121">Ports</span></span>
* <span data-ttu-id="2b911-122">Windows アクセス制御リスト (ACL)</span><span class="sxs-lookup"><span data-stu-id="2b911-122">Windows Access Control Lists (ACL)</span></span>
* <span data-ttu-id="2b911-123">Windows Communication Foundation (WCF)</span><span class="sxs-lookup"><span data-stu-id="2b911-123">Windows Communication Foundation (WCF)</span></span>
* <span data-ttu-id="2b911-124">Windows 暗号化</span><span class="sxs-lookup"><span data-stu-id="2b911-124">Windows Cryptography</span></span>
* <span data-ttu-id="2b911-125">Windows EventLog</span><span class="sxs-lookup"><span data-stu-id="2b911-125">Windows EventLog</span></span>
* <span data-ttu-id="2b911-126">WMI (Windows Management Instrumentation)</span><span class="sxs-lookup"><span data-stu-id="2b911-126">Windows Management Instrumentation (WMI)</span></span>
* <span data-ttu-id="2b911-127">Windows パフォーマンス カウンター</span><span class="sxs-lookup"><span data-stu-id="2b911-127">Windows Performance Counters</span></span>
* <span data-ttu-id="2b911-128">Windows レジストリ</span><span class="sxs-lookup"><span data-stu-id="2b911-128">Windows Registry</span></span>
* <span data-ttu-id="2b911-129">Windows ランタイム キャッシュ</span><span class="sxs-lookup"><span data-stu-id="2b911-129">Windows Runtime Caching</span></span>
* <span data-ttu-id="2b911-130">Windows サービス</span><span class="sxs-lookup"><span data-stu-id="2b911-130">Windows Services</span></span>

<span data-ttu-id="2b911-131">詳細については、[互換機能パックの仕様](https://github.com/dotnet/designs/blob/master/accepted/compat-pack/compat-pack.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b911-131">For more information, see the [specification of the compatibility pack](https://github.com/dotnet/designs/blob/master/accepted/compat-pack/compat-pack.md).</span></span>

## <a name="get-started"></a><span data-ttu-id="2b911-132">作業開始</span><span class="sxs-lookup"><span data-stu-id="2b911-132">Get started</span></span>

1. <span data-ttu-id="2b911-133">移植の前に、[移植プロセス](index.md)を確認してください。</span><span class="sxs-lookup"><span data-stu-id="2b911-133">Before porting, make sure to take a look at the [Porting Process](index.md).</span></span>

2. <span data-ttu-id="2b911-134">.NET Core または .NET Standard に既存のポートを移植するとき、NuGet パッケージ [Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="2b911-134">When porting existing code to .NET Core or .NET Standard, install the NuGet package [Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility).</span></span>

3. <span data-ttu-id="2b911-135">Windows に留まる場合、すでに用意はできています。</span><span class="sxs-lookup"><span data-stu-id="2b911-135">If you want to stay on Windows, you're all set.</span></span>

4. <span data-ttu-id="2b911-136">.NET Core アプリケーションまたは .NET Standard ライブラリを Linux または macOS で実行する場合、[API Analyzer](../../standard/analyzers/api-analyzer.md) を使用し、プラットフォーム非依存で機能しない API の使用を見つけます。</span><span class="sxs-lookup"><span data-stu-id="2b911-136">If you want to run the .NET Core application or .NET Standard library on Linux or macOS, use the [API Analyzer](../../standard/analyzers/api-analyzer.md) to find usage of APIs that won't work cross-platform.</span></span>

5. <span data-ttu-id="2b911-137">そのような API の使用を取り除くか、プラットフォーム非依存の代替で置換するか、プラットフォーム チェックで保護します (以下参照)。</span><span class="sxs-lookup"><span data-stu-id="2b911-137">Either remove the usages of those APIs, replace them with cross-platform alternatives, or guard them using a platform check, like:</span></span>

    ```csharp
    private static string GetLoggingPath()
    {
        // Verify the code is running on Windows.
        if (RuntimeInformation.IsOSPlatform(OSPlatform.Windows))
        {
            using (var key = Registry.CurrentUser.OpenSubKey(@"Software\Fabrikam\AssetManagement"))
            {
                if (key?.GetValue("LoggingDirectoryPath") is string configuredPath)
                    return configuredPath;
            }
        }

        // This is either not running on Windows or no logging path was configured,
        // so just use the path for non-roaming user-specific data files.
        var appDataPath = Environment.GetFolderPath(Environment.SpecialFolder.LocalApplicationData);
        return Path.Combine(appDataPath, "Fabrikam", "AssetManagement", "Logging");
    }
    ```

<span data-ttu-id="2b911-138">デモについては、[Windows 互換機能パックの Channel 9 動画](https://channel9.msdn.com/Events/Connect/2017/T123)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2b911-138">For a demo, check out the [Channel 9 video of the Windows Compatibility Pack](https://channel9.msdn.com/Events/Connect/2017/T123).</span></span>
