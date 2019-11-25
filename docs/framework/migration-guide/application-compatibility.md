---
title: ランタイムの変更と再ターゲットの変更 - .NET Framework
ms.date: 10/29/2019
helpviewer_keywords:
- application compatibility
- .NET Framework application compatibility
- .NET Framework changes
ms.assetid: c4ba3ff2-fe59-4c5d-9e0b-86bba3cd865c
ms.openlocfilehash: c46f781d495b87a4f24e77935df7c4814c8567ae
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2019
ms.locfileid: "73196701"
---
# <a name="application-compatibility-in-the-net-framework"></a><span data-ttu-id="6c0bc-102">.NET Framework のアプリケーションの互換性</span><span class="sxs-lookup"><span data-stu-id="6c0bc-102">Application compatibility in the .NET Framework</span></span>

<span data-ttu-id="6c0bc-103">.NET の各リリースにおいて、互換性は重要な目標です。</span><span class="sxs-lookup"><span data-stu-id="6c0bc-103">Compatibility is an important goal of each .NET release.</span></span> <span data-ttu-id="6c0bc-104">各バージョンが付加的な場合は互換性が確保され、以前のバージョンも引き続き動作します。</span><span class="sxs-lookup"><span data-stu-id="6c0bc-104">Compatibility ensures that each version is additive, so previous versions will continue to work.</span></span> <span data-ttu-id="6c0bc-105">一方、以前の機能に変更が生じた場合 (パフォーマンスの向上、セキュリティ上の問題の解決、またはバグの修正などを目的とした)、既存のコードまたは既存のアプリケーションを以降のバージョンで実行すると互換性に問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6c0bc-105">On the other hand, changes to previous functionality (for example, to improve performance, address security issues, or fix bugs) can cause compatibility problems in existing code or existing applications that run under a later version.</span></span>

<span data-ttu-id="6c0bc-106">各アプリは、.NET Framework の特定のバージョンをターゲットとします。バージョンを特定する方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6c0bc-106">Each app targets a specific version of the .NET Framework by:</span></span>

- <span data-ttu-id="6c0bc-107">Visual Studio でターゲット フレームワークを定義する。</span><span class="sxs-lookup"><span data-stu-id="6c0bc-107">Defining a target framework in Visual Studio.</span></span>
- <span data-ttu-id="6c0bc-108">プロジェクト ファイルでターゲット フレームワークを指定する。</span><span class="sxs-lookup"><span data-stu-id="6c0bc-108">Specifying the target framework in a project file.</span></span>
- <span data-ttu-id="6c0bc-109"><xref:System.Runtime.Versioning.TargetFrameworkAttribute> をソース コードに適用する。</span><span class="sxs-lookup"><span data-stu-id="6c0bc-109">Applying a <xref:System.Runtime.Versioning.TargetFrameworkAttribute> to the source code.</span></span>

<span data-ttu-id="6c0bc-110">.NET Framework のあるバージョンを別のバージョンに移行する場合、考慮する変更には、次の 2 種類があります。</span><span class="sxs-lookup"><span data-stu-id="6c0bc-110">When migrating from one version of the .NET Framework to another, there are two types of changes to consider:</span></span>

- [<span data-ttu-id="6c0bc-111">ランタイムの変更点</span><span class="sxs-lookup"><span data-stu-id="6c0bc-111">Runtime changes</span></span>](#runtime-changes)
- [<span data-ttu-id="6c0bc-112">変更の再ターゲット</span><span class="sxs-lookup"><span data-stu-id="6c0bc-112">Retargeting changes</span></span>](#retargeting-changes)

## <a name="runtime-changes"></a><span data-ttu-id="6c0bc-113">ランタイムの変更</span><span class="sxs-lookup"><span data-stu-id="6c0bc-113">Runtime changes</span></span>

<span data-ttu-id="6c0bc-114">ランタイムの問題とは、コンピューターに新しいランタイムを配置し、アプリの動作が変更された場合に発生する問題です。</span><span class="sxs-lookup"><span data-stu-id="6c0bc-114">Runtime issues are those that arise when a new runtime is placed on a machine and an app's behavior changes.</span></span> <span data-ttu-id="6c0bc-115">ターゲットに指定されたバージョンより新しいバージョンでアプリが実行されると、.NET Framework は*後方互換*動作によって、ターゲットに指定されている古いバージョンを模倣します。</span><span class="sxs-lookup"><span data-stu-id="6c0bc-115">When running on a newer version than what was targeted, the .NET Framework uses *quirked* behavior to mimic the older targeted version.</span></span> <span data-ttu-id="6c0bc-116">アプリは新しいバージョンで実行されますが、古いバージョンで実行される場合と同様に動作します。</span><span class="sxs-lookup"><span data-stu-id="6c0bc-116">The app runs on the newer version but acts as if it's running on the older version.</span></span> <span data-ttu-id="6c0bc-117">.NET Framework のバージョン間の互換性の問題の多くは、この後方互換モデルを通して対応されます。</span><span class="sxs-lookup"><span data-stu-id="6c0bc-117">Many of the compatibility issues between versions of the .NET Framework are mitigated through this quirking model.</span></span> <span data-ttu-id="6c0bc-118">たとえば、.NET Framework 4.0 向けにコンパイルされたバイナリを、.NET Framework 4.5 以降がインストールされたコンピューターで実行する場合、.NET Framework 4.0 互換モードで実行されます。</span><span class="sxs-lookup"><span data-stu-id="6c0bc-118">For example, if a binary was compiled for .NET Framework 4.0 but runs on a machine with .NET Framework 4.5 or later, it runs in .NET Framework 4.0 compatibility mode.</span></span> <span data-ttu-id="6c0bc-119">つまり、4.5 以降のバージョンの変更の多くは、そのバイナリには影響しません。</span><span class="sxs-lookup"><span data-stu-id="6c0bc-119">This means that many of the changes in the later version don't affect the binary.</span></span>

<span data-ttu-id="6c0bc-120">アプリケーションがターゲットとする .NET Framework のバージョンは、コードが実行されるアプリケーション ドメインのエントリ アセンブリのターゲット バージョンによって決まります。</span><span class="sxs-lookup"><span data-stu-id="6c0bc-120">The version of the .NET Framework that an application targets is determined by the target version of the entry assembly for the application domain that the code runs in.</span></span> <span data-ttu-id="6c0bc-121">そのアプリケーション ドメインに読み込まれたすべての追加アセンブリは、そのバージョンをターゲットとします。</span><span class="sxs-lookup"><span data-stu-id="6c0bc-121">All additional assemblies loaded in that application domain target that version.</span></span> <span data-ttu-id="6c0bc-122">たとえば、実行可能ファイルの場合、実行可能ファイルのターゲットとなるフレームワークは、そのアプリケーション ドメイン内のすべてのアセンブリが実行される互換モードになります。</span><span class="sxs-lookup"><span data-stu-id="6c0bc-122">For example, in the case of an executable, the version that the executable targets is the compatibility mode all assemblies in that application domain run under.</span></span>

<span data-ttu-id="6c0bc-123">ご使用の環境に適用されるランタイムの変更の一覧を表示するには、現在ターゲットとしている NET Framework のバージョンを選択した後、移行先のバージョンを選択します。</span><span class="sxs-lookup"><span data-stu-id="6c0bc-123">To see a list of runtime changes that apply to your environment, select the .NET Framework version you're currently targeting and then the version you wish to migrate to:</span></span>

[!INCLUDE[versionselector](../../../includes/migration-guide/runtime/versionselector.md)]

## <a name="retargeting-changes"></a><span data-ttu-id="6c0bc-124">変更の再ターゲット</span><span class="sxs-lookup"><span data-stu-id="6c0bc-124">Retargeting changes</span></span>

<span data-ttu-id="6c0bc-125">再ターゲットの変更とは、アセンブリを再コンパイルして新しいバージョンをターゲットとする場合に生じる変更です。</span><span class="sxs-lookup"><span data-stu-id="6c0bc-125">Retargeting changes are those that arise when an assembly is recompiled to target a newer version.</span></span> <span data-ttu-id="6c0bc-126">新しいバージョンにターゲットするということは、アセンブリで新しい機能が選択されるだけでなく、古い機能との互換性の問題が発生する可能性があることも意味します。</span><span class="sxs-lookup"><span data-stu-id="6c0bc-126">Targeting a newer version means the assembly opts into the new features as well as potential compatibility issues for old features.</span></span>

<span data-ttu-id="6c0bc-127">ご使用の環境に適用される再ターゲットの変更の一覧を表示するには、現在ターゲットとしている NET Framework のバージョンを選択した後、移行先のバージョンを選択します。</span><span class="sxs-lookup"><span data-stu-id="6c0bc-127">To see a list of retargeting changes that apply to your environment, select the .NET Framework version you're currently targeting and then the version you wish to migrate to:</span></span>

[!INCLUDE[versionselector](../../../includes/migration-guide/retargeting/versionselector.md)]

## <a name="impact-classification"></a><span data-ttu-id="6c0bc-128">影響の分類</span><span class="sxs-lookup"><span data-stu-id="6c0bc-128">Impact classification</span></span>

<span data-ttu-id="6c0bc-129">ランタイムの変更および再ターゲットの変更について説明するトピック (たとえば、「[.NET Framework 4.7.2 から 4.8 への移行に関する再ターゲットの変更](retargeting/4.7.2-4.8.md)」) では、個々の項目を、次のような予想される影響別に分類しています。</span><span class="sxs-lookup"><span data-stu-id="6c0bc-129">In the topics that describe runtime and retargeting changes, for example, [Retargeting changes for migrating from 4.7.2 to 4.8](retargeting/4.7.2-4.8.md), individual items are classified by their expected impact as follows:</span></span>

<span data-ttu-id="6c0bc-130">**Major**</span><span class="sxs-lookup"><span data-stu-id="6c0bc-130">**Major**</span></span>\
<span data-ttu-id="6c0bc-131">多数のアプリに影響するか、またはコードに大幅な変更が必要な、重大な変更。</span><span class="sxs-lookup"><span data-stu-id="6c0bc-131">A significant change that affects a large number of apps or that requires substantial modification of code.</span></span>

<span data-ttu-id="6c0bc-132">**Minor**</span><span class="sxs-lookup"><span data-stu-id="6c0bc-132">**Minor**</span></span>\
<span data-ttu-id="6c0bc-133">少数のアプリに影響するか、コードにわずかな変更を加える必要がある変更。</span><span class="sxs-lookup"><span data-stu-id="6c0bc-133">A change that affects a small number of apps or that requires minor modification of code.</span></span>

<span data-ttu-id="6c0bc-134">**エッジ ケース**</span><span class="sxs-lookup"><span data-stu-id="6c0bc-134">**Edge case**</span></span>\
<span data-ttu-id="6c0bc-135">一般的ではない特定のシナリオでアプリに影響を与える変更。</span><span class="sxs-lookup"><span data-stu-id="6c0bc-135">A change that affects apps under very specific scenarios that are not common.</span></span>

<span data-ttu-id="6c0bc-136">**透明**</span><span class="sxs-lookup"><span data-stu-id="6c0bc-136">**Transparent**</span></span>\
<span data-ttu-id="6c0bc-137">アプリの開発者やユーザーには大きな影響を及ぼさない変更。</span><span class="sxs-lookup"><span data-stu-id="6c0bc-137">A change that has no noticeable effect on the app's developer or user.</span></span> <span data-ttu-id="6c0bc-138">アプリはこの変更のために変更を加える必要はありません。</span><span class="sxs-lookup"><span data-stu-id="6c0bc-138">The app should not require modification because of this change.</span></span>

## <a name="see-also"></a><span data-ttu-id="6c0bc-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="6c0bc-139">See also</span></span>

- [<span data-ttu-id="6c0bc-140">バージョンおよび依存関係</span><span class="sxs-lookup"><span data-stu-id="6c0bc-140">Versions and dependencies</span></span>](versions-and-dependencies.md)
- [<span data-ttu-id="6c0bc-141">新機能</span><span class="sxs-lookup"><span data-stu-id="6c0bc-141">What's new</span></span>](../whats-new/index.md)
- [<span data-ttu-id="6c0bc-142">廃止になった機能</span><span class="sxs-lookup"><span data-stu-id="6c0bc-142">What's obsolete</span></span>](../whats-new/whats-obsolete.md)
