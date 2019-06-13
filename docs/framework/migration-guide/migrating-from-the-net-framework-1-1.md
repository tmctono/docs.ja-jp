---
title: .NET Framework 1.1 からの移行
ms.date: 03/30/2017
helpviewer_keywords:
- .NET Framework 4.5, migrating from 1.1
- .NET Framework 1.1, migrating to .NET Framework 4.5
ms.assetid: 7ead0cb3-3b19-414a-8417-a1c1fa198d9e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 441a65f9a72dd0fcffb062710df74bb529767cef
ms.sourcegitcommit: 5ae6affa0b171be3bb5f4729fb68ea4fe799f959
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2019
ms.locfileid: "66816063"
---
# <a name="migrating-from-the-net-framework-11"></a><span data-ttu-id="213fc-102">.NET Framework 1.1 からの移行</span><span class="sxs-lookup"><span data-stu-id="213fc-102">Migrating from the .NET Framework 1.1</span></span>

[!INCLUDE[win7](../../../includes/win7-md.md)] <span data-ttu-id="213fc-103">以降のバージョンの Windows オペレーティング システムは、.NET Framework 1.1 をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="213fc-103">and later versions of the Windows operating system do not support the .NET Framework 1.1.</span></span> <span data-ttu-id="213fc-104">その結果、.NET Framework 1.1 を対象とするアプリケーションは実行されません変更せず[!INCLUDE[win7](../../../includes/win7-md.md)]以降のオペレーティング システムのバージョン。</span><span class="sxs-lookup"><span data-stu-id="213fc-104">As a result, applications that target the .NET Framework 1.1 will not run without modification on [!INCLUDE[win7](../../../includes/win7-md.md)] or later operating system versions.</span></span> <span data-ttu-id="213fc-105">このトピックでは、.NET Framework 1.1 を対象とするアプリケーションを実行するために必要な手順を説明します[!INCLUDE[win7](../../../includes/win7-md.md)]と以降のバージョンの Windows オペレーティング システム。</span><span class="sxs-lookup"><span data-stu-id="213fc-105">This topic discusses the steps required to run an application that targets the .NET Framework 1.1 under [!INCLUDE[win7](../../../includes/win7-md.md)] and later versions of the Windows operating system.</span></span> <span data-ttu-id="213fc-106">.NET Framework 1.1 の詳細については、[!INCLUDE[win8](../../../includes/win8-md.md)]を参照してください[Windows 8 およびそれ以降のバージョンの .NET Framework 1.1 アプリを実行している](../../../docs/framework/install/run-net-framework-1-1-apps.md)します。</span><span class="sxs-lookup"><span data-stu-id="213fc-106">For more information about the .NET Framework 1.1 and [!INCLUDE[win8](../../../includes/win8-md.md)], see [Running .NET Framework 1.1 Apps on Windows 8 and later versions](../../../docs/framework/install/run-net-framework-1-1-apps.md).</span></span>

## <a name="retargeting-or-recompiling"></a><span data-ttu-id="213fc-107">再ターゲットまたは再コンパイル</span><span class="sxs-lookup"><span data-stu-id="213fc-107">Retargeting or Recompiling</span></span>

<span data-ttu-id="213fc-108">2 つの方法で実行する .NET Framework 1.1 を使用してコンパイルされたアプリケーションを取得する[!INCLUDE[win7](../../../includes/win7-md.md)]以降の Windows オペレーティング システム。</span><span class="sxs-lookup"><span data-stu-id="213fc-108">There are two ways to get an application that was compiled using the .NET Framework 1.1 to run on [!INCLUDE[win7](../../../includes/win7-md.md)] or a later Windows operating system:</span></span>

- <span data-ttu-id="213fc-109">.NET Framework 4 以降のバージョンで動作するようにアプリケーションのターゲットを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="213fc-109">You can retarget the application to run under .NET Framework 4 and later versions.</span></span> <span data-ttu-id="213fc-110">再ターゲットするには、[\<supportedRuntime>](../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md) 要素をアプリケーションの構成ファイルに追加して .NET Framework 4 以降のバージョンで動作できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="213fc-110">Retargeting requires that you add a [\<supportedRuntime>](../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md) element to the application's configuration file that allows it to run under .NET Framework 4 and later versions.</span></span> <span data-ttu-id="213fc-111">そのための構成ファイルの形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="213fc-111">Such a configuration file takes the following form:</span></span>

    ```xml
    <configuration>
       <startup>
          <supportedRuntime version="v4.0"/>
       </startup>
    </configuration>
    ```

- <span data-ttu-id="213fc-112">.NET Framework 4 以降のバージョンをターゲットとするコンパイラでアプリケーションを再コンパイルできます。</span><span class="sxs-lookup"><span data-stu-id="213fc-112">You can recompile the application with a compiler that targets the .NET Framework 4 or a later version.</span></span> <span data-ttu-id="213fc-113">最初に Visual Studio 2003 を使用してソリューションを開発およびコンパイルした場合は、ソリューションを Visual Studio 2010 で (そしておそらく以降のバージョンでも) で開くことができます。また、 **[Project Compatibility]\(プロジェクト互換性\)** ダイアログ ボックスを使用して、ソリューションおよびプロジェクト ファイルを Visual Studio 2003 で使用される形式から Microsoft Build Engine (MSBuild) 形式に変換することができます。</span><span class="sxs-lookup"><span data-stu-id="213fc-113">If you originally used Visual Studio 2003 to develop and compile your solution, you can open the solution in Visual Studio 2010 (and possibly later versions too) and use the **Project Compatibility** dialog box to convert the solution and project files from the formats used by Visual Studio 2003 to the Microsoft Build Engine (MSBuild) format.</span></span>

<span data-ttu-id="213fc-114">再コンパイルまたは再ターゲットのいずれを選択するかに関係なく、アプリケーションが .NET Framework の新しいバージョンで導入された変更の影響を受けるかどうかを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="213fc-114">Regardless of whether you prefer to recompile or retarget your application, you must determine whether your application is affected by any changes introduced in later versions of the .NET Framework.</span></span> <span data-ttu-id="213fc-115">変更には次の 2 種類があります。</span><span class="sxs-lookup"><span data-stu-id="213fc-115">These changes are of two kinds:</span></span>

- <span data-ttu-id="213fc-116">.NET Framework 1.1 と .NET Framework の以降のバージョン間で発生した重大な変更。</span><span class="sxs-lookup"><span data-stu-id="213fc-116">Breaking changes that occurred between the .NET Framework 1.1 and later versions of the .NET Framework.</span></span>

- <span data-ttu-id="213fc-117">型と非推奨としてマークされている、または .NET Framework 1.1 と .NET Framework の以降のバージョン間で廃止された型のメンバー。</span><span class="sxs-lookup"><span data-stu-id="213fc-117">Types and type members that have been marked as deprecated or obsolete between the .NET Framework 1.1 and later versions of the .NET Framework.</span></span>

<span data-ttu-id="213fc-118">アプリケーションを再ターゲットまたは再コンパイルするかどうか、重大な変更と旧式の型および .NET Framework 1.1 にリリースされた .NET Framework のバージョンごとにメンバーを確認してください。</span><span class="sxs-lookup"><span data-stu-id="213fc-118">Whether you retarget your application or recompile it, you should review both the breaking changes and the obsolete types and members for each version of the .NET Framework that was released after .NET Framework 1.1.</span></span>

## <a name="breaking-changes"></a><span data-ttu-id="213fc-119">互換性に影響する変更点</span><span class="sxs-lookup"><span data-stu-id="213fc-119">Breaking Changes</span></span>

<span data-ttu-id="213fc-120">互換性に影響する変更が行われた場合は、変更内容に応じて、アプリケーションの再ターゲットおよび再コンパイル時の回避策が提示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="213fc-120">When a breaking change occurs, depending on the specific change, a workaround may be available both for retargeted and recompiled applications.</span></span> <span data-ttu-id="213fc-121">場合によっては、アプリケーションの構成ファイルの [\<runtime>](../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md) 要素に子要素を追加することで、以前の動作を復元できます。</span><span class="sxs-lookup"><span data-stu-id="213fc-121">In some cases, you can add a child element to the [\<runtime>](../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md) element of your application's configuration file to restore the previous behavior.</span></span> <span data-ttu-id="213fc-122">たとえば、次の構成ファイルは、文字列の並べ替えを復元し、比較の動作は、.NET Framework 1.1 で使用され、再ターゲットまたは再コンパイルされたアプリケーションで使用することができます。</span><span class="sxs-lookup"><span data-stu-id="213fc-122">For example, the following configuration file restores the string sorting and comparison behavior used in the .NET Framework 1.1 and can be used either with a retargeted or a recompiled application.</span></span>

```xml
<configuration>
   <runtime>
      <CompatSortNLSVersion enabled="4096"/>
   </runtime>
</configuration>
```

<span data-ttu-id="213fc-123">ただし、ソース コードの変更とアプリケーションの再コンパイルが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="213fc-123">However, in some cases, you may have to modify your source code and recompile your application.</span></span>

<span data-ttu-id="213fc-124">互換性に影響する可能性がある変更点がアプリケーションに与える影響を評価するには、次の変更一覧を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="213fc-124">To assess the impact of possible breaking changes on your application, you must review the following lists of changes:</span></span>

- <span data-ttu-id="213fc-125">[.NET Framework 2.0 における重大な変更](https://go.microsoft.com/fwlink/?LinkId=125263)を .NET Framework 1.1 を対象とするアプリケーションに影響を与える、.NET Framework 2.0 SP1 での変更について説明します。</span><span class="sxs-lookup"><span data-stu-id="213fc-125">[Breaking Changes in .NET Framework 2.0](https://go.microsoft.com/fwlink/?LinkId=125263) documents changes in .NET Framework 2.0 SP1 that can affect an application that targets .NET Framework 1.1.</span></span>

- <span data-ttu-id="213fc-126">[.NET Framework 3.5 SP1 で変更](https://go.microsoft.com/fwlink/?LinkID=186989)、.NET Framework 3.5 の間の変更について説明し、[!INCLUDE[net_v35SP1_short](../../../includes/net-v35sp1-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="213fc-126">[Changes in .NET Framework 3.5 SP1](https://go.microsoft.com/fwlink/?LinkID=186989) documents changes between the .NET Framework 3.5 and the [!INCLUDE[net_v35SP1_short](../../../includes/net-v35sp1-short-md.md)].</span></span>

- <span data-ttu-id="213fc-127">「[.NET Framework 4 への移行に関する問題](../../../docs/framework/migration-guide/net-framework-4-migration-issues.md)」に記載されている、[!INCLUDE[net_v35SP1_short](../../../includes/net-v35sp1-short-md.md)] から .NET Framework 4 の変更点。</span><span class="sxs-lookup"><span data-stu-id="213fc-127">[.NET Framework 4 Migration Issues](../../../docs/framework/migration-guide/net-framework-4-migration-issues.md) documents changes between the [!INCLUDE[net_v35SP1_short](../../../includes/net-v35sp1-short-md.md)] and the .NET Framework 4.</span></span>

## <a name="obsolete-types-and-members"></a><span data-ttu-id="213fc-128">旧式の型およびメンバー</span><span class="sxs-lookup"><span data-stu-id="213fc-128">Obsolete Types and Members</span></span>

<span data-ttu-id="213fc-129">非推奨の型およびメンバーの影響は、アプリケーションを再ターゲットする場合と再コンパイルする場合とでは若干異なります。</span><span class="sxs-lookup"><span data-stu-id="213fc-129">The impact of deprecated types and members is somewhat different for retargeted applications and recompiled applications.</span></span> <span data-ttu-id="213fc-130">旧式の型およびメンバーを使用しても、その型およびメンバーをアセンブリから物理的に削除しない限り、再ターゲットしたアプリケーションには影響しません。</span><span class="sxs-lookup"><span data-stu-id="213fc-130">The use of obsolete types and members will not affect a retargeted application unless the obsolete type or member has been physically removed from its assembly.</span></span> <span data-ttu-id="213fc-131">旧式の型およびメンバーを使用してアプリケーションを再コンパイルすると、通常はコンパイラ エラーではなく、コンパイラの警告が発生します。</span><span class="sxs-lookup"><span data-stu-id="213fc-131">Recompiling an application that uses obsolete types or members usually produces a compiler warning rather than a compiler error.</span></span> <span data-ttu-id="213fc-132">ただし、場合によってはコンパイラ エラーが発生し、旧式の型またはメンバーを使用したコードをコンパイルできないことがあります。</span><span class="sxs-lookup"><span data-stu-id="213fc-132">However, in some cases, it produces a compiler error, and code that uses the obsolete type or member does not compile successfully.</span></span> <span data-ttu-id="213fc-133">その場合は、旧式の型またはメンバーを呼び出すソース コードを変更してからアプリケーションを再コンパイルする必要があります。</span><span class="sxs-lookup"><span data-stu-id="213fc-133">In this case, you must rewrite the source code that calls the obsolete type or member before you recompile your application.</span></span> <span data-ttu-id="213fc-134">旧式の型およびメンバーの詳細については、「[.NET Framework クラス ライブラリの互換性のために残されている機能](../../../docs/framework/whats-new/whats-obsolete.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="213fc-134">For more information about obsolete types and members, see [What's Obsolete in the Class Library](../../../docs/framework/whats-new/whats-obsolete.md).</span></span>

<span data-ttu-id="213fc-135">型と .NET Framework 2.0 SP1 のリリース以降非推奨になったメンバーの影響を評価するには、次を参照してください。[クラス ライブラリで廃止は](../../../docs/framework/whats-new/whats-obsolete.md)します。</span><span class="sxs-lookup"><span data-stu-id="213fc-135">To assess the impact of types and members that have been deprecated since the release of the .NET Framework 2.0 SP1, see [What's Obsolete in the Class Library](../../../docs/framework/whats-new/whats-obsolete.md).</span></span> <span data-ttu-id="213fc-136">.NET Framework 2.0 SP1、.NET Framework 3.5 および .NET Framework 4 の旧式の型およびメンバーの一覧を確認します。</span><span class="sxs-lookup"><span data-stu-id="213fc-136">Review the lists of obsolete types and member for the .NET Framework 2.0 SP1, the .NET Framework 3.5, and the .NET Framework 4.</span></span>
