---
title: .NET Framework 1.1 からの移行
description: Windows 7 以降で .NET Framework 1.1 を使用してコンパイルされたアプリケーションを実行するために必要な手順について説明します。
ms.date: 03/30/2017
helpviewer_keywords:
- .NET Framework 4.5, migrating from 1.1
- .NET Framework 1.1, migrating to .NET Framework 4.5
ms.assetid: 7ead0cb3-3b19-414a-8417-a1c1fa198d9e
ms.openlocfilehash: 7312de7d812aa714447a60f5aa04cb48890e40e8
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90553728"
---
# <a name="migrate-from-the-net-framework-11"></a><span data-ttu-id="69c7b-103">.NET Framework 1.1 からの移行</span><span class="sxs-lookup"><span data-stu-id="69c7b-103">Migrate from the .NET Framework 1.1</span></span>

<span data-ttu-id="69c7b-104">Windows 7 以降のバージョンの Windows オペレーティング システムでは、.NET Framework 1.1 はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="69c7b-104">Windows 7 and later versions of the Windows operating system do not support the .NET Framework 1.1.</span></span> <span data-ttu-id="69c7b-105">このため、.NET Framework 1.1 を対象とするアプリケーションは変更を行わないと、Windows 7 以降のバージョンのオペレーティング システムでは実行できません。</span><span class="sxs-lookup"><span data-stu-id="69c7b-105">As a result, applications that target the .NET Framework 1.1 will not run without modification on Windows 7 or later operating system versions.</span></span> <span data-ttu-id="69c7b-106">このトピックでは、.NET Framework 1.1 を対象とするアプリケーションを Windows 7 以降のバージョンの Windows オペレーティング システムで実行するために必要な手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="69c7b-106">This topic discusses the steps required to run an application that targets the .NET Framework 1.1 under Windows 7 and later versions of the Windows operating system.</span></span> <span data-ttu-id="69c7b-107">.NET Framework 1.1 と Windows 8 の詳細については、[Windows 8 以降のバージョンでの .NET Framework 1.1 アプリの実行](../install/run-net-framework-1-1-apps.md)に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69c7b-107">For more information about the .NET Framework 1.1 and Windows 8, see [Run .NET Framework 1.1 Apps on Windows 8 and later versions](../install/run-net-framework-1-1-apps.md).</span></span>

## <a name="retarget-or-recompile"></a><span data-ttu-id="69c7b-108">再ターゲットまたは再コンパイル</span><span class="sxs-lookup"><span data-stu-id="69c7b-108">Retarget or recompile</span></span>

<span data-ttu-id="69c7b-109">.NET Framework 1.1 を使用してコンパイルしたアプリケーションを Windows 7 以降のバージョンの Windows オペレーティング システムで実行するには、次の 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="69c7b-109">There are two ways to get an application that was compiled using the .NET Framework 1.1 to run on Windows 7 or a later Windows operating system:</span></span>

- <span data-ttu-id="69c7b-110">.NET Framework 4 以降のバージョンで動作するようにアプリケーションのターゲットを変更します。</span><span class="sxs-lookup"><span data-stu-id="69c7b-110">Retarget the application to run under .NET Framework 4 and later versions.</span></span> <span data-ttu-id="69c7b-111">再ターゲットするには、[\<supportedRuntime>](../configure-apps/file-schema/startup/supportedruntime-element.md) 要素をアプリケーションの構成ファイルに追加して .NET Framework 4 以降のバージョンで動作できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="69c7b-111">Retargeting requires that you add a [\<supportedRuntime>](../configure-apps/file-schema/startup/supportedruntime-element.md) element to the application's configuration file that allows it to run under .NET Framework 4 and later versions.</span></span> <span data-ttu-id="69c7b-112">そのための構成ファイルの形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="69c7b-112">Such a configuration file takes the following form:</span></span>

    ```xml
    <configuration>
       <startup>
          <supportedRuntime version="v4.0"/>
       </startup>
    </configuration>
    ```

- <span data-ttu-id="69c7b-113">.NET Framework 4 以降のバージョンをターゲットとするコンパイラでアプリケーションを再コンパイルします。</span><span class="sxs-lookup"><span data-stu-id="69c7b-113">Recompile the application with a compiler that targets the .NET Framework 4 or a later version.</span></span> <span data-ttu-id="69c7b-114">最初に Visual Studio 2003 を使用してソリューションを開発およびコンパイルした場合は、ソリューションを Visual Studio 2010 で (そしておそらく以降のバージョンでも) で開くことができます。また、 **[Project Compatibility]\(プロジェクト互換性\)** ダイアログ ボックスを使用して、ソリューションおよびプロジェクト ファイルを Visual Studio 2003 で使用される形式から Microsoft Build Engine (MSBuild) 形式に変換することができます。</span><span class="sxs-lookup"><span data-stu-id="69c7b-114">If you originally used Visual Studio 2003 to develop and compile your solution, you can open the solution in Visual Studio 2010 (and possibly later versions too) and use the **Project Compatibility** dialog box to convert the solution and project files from the formats used by Visual Studio 2003 to the Microsoft Build Engine (MSBuild) format.</span></span>

<span data-ttu-id="69c7b-115">再コンパイルまたは再ターゲットのいずれを選択するかに関係なく、アプリケーションが .NET Framework の新しいバージョンで導入された変更の影響を受けるかどうかを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69c7b-115">Regardless of whether you prefer to recompile or retarget your application, you must determine whether your application is affected by any changes introduced in later versions of the .NET Framework.</span></span> <span data-ttu-id="69c7b-116">変更には次の 2 種類があります。</span><span class="sxs-lookup"><span data-stu-id="69c7b-116">These changes are of two kinds:</span></span>

- <span data-ttu-id="69c7b-117">.NET Framework 1.1 とより新しいバージョンの .NET Framework の間で行われた破壊的変更。</span><span class="sxs-lookup"><span data-stu-id="69c7b-117">Breaking changes that occurred between the .NET Framework 1.1 and later versions of the .NET Framework.</span></span>

- <span data-ttu-id="69c7b-118">.NET Framework 1.1 とより新しいバージョンの .NET Framework の間で非推奨または旧形式とマークされた型と型のメンバー。</span><span class="sxs-lookup"><span data-stu-id="69c7b-118">Types and type members that have been marked as deprecated or obsolete between the .NET Framework 1.1 and later versions of the .NET Framework.</span></span>

<span data-ttu-id="69c7b-119">アプリケーションを再ターゲットするか、再コンパイルするかに関係なく、.NET Framework 1.1 より後にリリースされた .NET Framework の各バージョンについては、破壊的変更と旧式の型およびメンバーを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69c7b-119">Whether you retarget your application or recompile it, you should review both the breaking changes and the obsolete types and members for each version of the .NET Framework that was released after .NET Framework 1.1.</span></span>

## <a name="breaking-changes"></a><span data-ttu-id="69c7b-120">互換性に影響する変更</span><span class="sxs-lookup"><span data-stu-id="69c7b-120">Breaking changes</span></span>

<span data-ttu-id="69c7b-121">互換性に影響する変更が行われた場合は、変更内容に応じて、アプリケーションの再ターゲットおよび再コンパイル時の回避策が提示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="69c7b-121">When a breaking change occurs, depending on the specific change, a workaround may be available both for retargeted and recompiled applications.</span></span> <span data-ttu-id="69c7b-122">場合によっては、アプリケーションの構成ファイルの [\<runtime>](../configure-apps/file-schema/startup/supportedruntime-element.md) 要素に子要素を追加することで、以前の動作を復元できます。</span><span class="sxs-lookup"><span data-stu-id="69c7b-122">In some cases, you can add a child element to the [\<runtime>](../configure-apps/file-schema/startup/supportedruntime-element.md) element of your application's configuration file to restore the previous behavior.</span></span> <span data-ttu-id="69c7b-123">たとえば、次の構成ファイルでは .NET Framework 1.1 で使用される文字列の並べ替えおよび比較の動作が復元され、アプリケーションの再ターゲットまたは再コンパイルのいずれにも使用できます。</span><span class="sxs-lookup"><span data-stu-id="69c7b-123">For example, the following configuration file restores the string sorting and comparison behavior used in the .NET Framework 1.1 and can be used either with a retargeted or a recompiled application.</span></span>

```xml
<configuration>
   <runtime>
      <CompatSortNLSVersion enabled="4096"/>
   </runtime>
</configuration>
```

<span data-ttu-id="69c7b-124">ただし、ソース コードの変更とアプリケーションの再コンパイルが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="69c7b-124">However, in some cases, you may have to modify your source code and recompile your application.</span></span>

<span data-ttu-id="69c7b-125">互換性に影響する可能性がある変更点がアプリケーションに与える影響を評価するには、次の変更一覧を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69c7b-125">To assess the impact of possible breaking changes on your application, you must review the following lists of changes:</span></span>

- <span data-ttu-id="69c7b-126">「[Breaking Changes in .NET Framework 2.0](/previous-versions/aa570326(v=msdn.10))」 (.NET Framework 2.0 での破壊的変更) に記載されている .NET Framework 1.1 を対象とするアプリケーションに影響する可能性がある .NET Framework 2.0 SP1 の変更点。</span><span class="sxs-lookup"><span data-stu-id="69c7b-126">[Breaking Changes in .NET Framework 2.0](/previous-versions/aa570326(v=msdn.10)) documents changes in .NET Framework 2.0 SP1 that can affect an application that targets .NET Framework 1.1.</span></span>

- <span data-ttu-id="69c7b-127">「[.NET Framework 3.5 SP1 の変更点](/previous-versions/dotnet/articles/dd310284(v=msdn.10))」に記載されている .NET Framework 3.5 と .NET Framework 3.5 SP1 間の変更点。</span><span class="sxs-lookup"><span data-stu-id="69c7b-127">[Changes in .NET Framework 3.5 SP1](/previous-versions/dotnet/articles/dd310284(v=msdn.10)) documents changes between the .NET Framework 3.5 and the .NET Framework 3.5 SP1.</span></span>

- <span data-ttu-id="69c7b-128">「[.NET Framework 4 への移行に関する問題](net-framework-4-migration-issues.md)」に記載されている .NET Framework 3.5 SP1 と .NET Framework 4 間の変更点。</span><span class="sxs-lookup"><span data-stu-id="69c7b-128">[.NET Framework 4 Migration Issues](net-framework-4-migration-issues.md) documents changes between the .NET Framework 3.5 SP1 and the .NET Framework 4.</span></span>

## <a name="obsolete-types-and-members"></a><span data-ttu-id="69c7b-129">旧式の型およびメンバー</span><span class="sxs-lookup"><span data-stu-id="69c7b-129">Obsolete types and members</span></span>

<span data-ttu-id="69c7b-130">非推奨の型およびメンバーの影響は、アプリケーションを再ターゲットする場合と再コンパイルする場合とでは若干異なります。</span><span class="sxs-lookup"><span data-stu-id="69c7b-130">The impact of deprecated types and members is somewhat different for retargeted applications and recompiled applications.</span></span> <span data-ttu-id="69c7b-131">旧式の型およびメンバーを使用しても、その型およびメンバーをアセンブリから物理的に削除しない限り、再ターゲットしたアプリケーションには影響しません。</span><span class="sxs-lookup"><span data-stu-id="69c7b-131">The use of obsolete types and members will not affect a retargeted application unless the obsolete type or member has been physically removed from its assembly.</span></span> <span data-ttu-id="69c7b-132">旧式の型およびメンバーを使用してアプリケーションを再コンパイルすると、通常はコンパイラ エラーではなく、コンパイラの警告が発生します。</span><span class="sxs-lookup"><span data-stu-id="69c7b-132">Recompiling an application that uses obsolete types or members usually produces a compiler warning rather than a compiler error.</span></span> <span data-ttu-id="69c7b-133">ただし、場合によってはコンパイラ エラーが発生し、旧式の型またはメンバーを使用したコードをコンパイルできないことがあります。</span><span class="sxs-lookup"><span data-stu-id="69c7b-133">However, in some cases, it produces a compiler error, and code that uses the obsolete type or member does not compile successfully.</span></span> <span data-ttu-id="69c7b-134">その場合は、旧式の型またはメンバーを呼び出すソース コードを変更してからアプリケーションを再コンパイルする必要があります。</span><span class="sxs-lookup"><span data-stu-id="69c7b-134">In this case, you must rewrite the source code that calls the obsolete type or member before you recompile your application.</span></span> <span data-ttu-id="69c7b-135">旧式の型およびメンバーの詳細については、「[.NET Framework クラス ライブラリの互換性のために残されている機能](../whats-new/whats-obsolete.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69c7b-135">For more information about obsolete types and members, see [What's Obsolete in the Class Library](../whats-new/whats-obsolete.md).</span></span>

<span data-ttu-id="69c7b-136">.NET Framework 2.0 SP1 のリリース以後に非推奨になった型およびメンバーの影響を評価するには、[クラス ライブラリの互換性のために残されている機能](../whats-new/whats-obsolete.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="69c7b-136">To assess the impact of types and members that have been deprecated since the release of the .NET Framework 2.0 SP1, see [What's Obsolete in the Class Library](../whats-new/whats-obsolete.md).</span></span> <span data-ttu-id="69c7b-137">.NET Framework 2.0 SP1、.NET Framework 3.5、.NET Framework 4 については、旧式の型およびメンバーの一覧を確認してください。</span><span class="sxs-lookup"><span data-stu-id="69c7b-137">Review the lists of obsolete types and member for the .NET Framework 2.0 SP1, the .NET Framework 3.5, and the .NET Framework 4.</span></span>
