---
title: '.NET Framework 4.8、4.7、4.6、4.5 移行ガイド '
ms.custom: updateeachrelease
ms.date: 04/18/2019
helpviewer_keywords:
- .NET Framework, migrating applications to
- migration, .NET Framework
ms.assetid: 02d55147-9b3a-4557-a45f-fa936fadae3b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9b1cda82125a2d4a6eb3102b01bea639a4f3e3df
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65636085"
---
# <a name="migration-guide-to-the-net-framework-48-47-46-and-45"></a><span data-ttu-id="4b8b0-102">.NET Framework 4.8、4.7、4.6、4.5 移行ガイド</span><span class="sxs-lookup"><span data-stu-id="4b8b0-102">Migration Guide to the .NET Framework 4.8, 4.7, 4.6, and 4.5</span></span>

<span data-ttu-id="4b8b0-103">旧バージョンの .NET Framework を使用してアプリを作成した場合、通常は .NET Framework 4.5 とそのポイント リリース (4.5.1 と 4.5.2)、.NET Framework 4.6 とそのポイント リリース (4.6.1 と 4.6.2)、.NET Framework 4.7 とそのポイント リリース (4.7.1 および 4.7.2)、または .NET Framework 4.8 へ簡単にアップグレードできます。</span><span class="sxs-lookup"><span data-stu-id="4b8b0-103">If you created your app using an earlier version of the .NET Framework, you can generally upgrade it to .NET Framework 4.5 and its point releases (4.5.1 and 4.5.2), .NET Framework 4.6 and its point releases (4.6.1 and 4.6.2), .NET Framework 4.7 and its point releases (4.7.1 and 4.7.2), or .NET Framework 4.8 easily.</span></span> <span data-ttu-id="4b8b0-104">Visual Studio でプロジェクトを開きます。</span><span class="sxs-lookup"><span data-stu-id="4b8b0-104">Open your project in Visual Studio.</span></span> <span data-ttu-id="4b8b0-105">プロジェクトが旧バージョンの Visual Studio で作成されている場合は、**[Project Compatibility]\(プロジェクト互換性\)** ダイアログ ボックスが自動的に開きます。</span><span class="sxs-lookup"><span data-stu-id="4b8b0-105">If your project was created in an earlier version of Visual Studio, the **Project Compatibility** dialog box automatically opens.</span></span> <span data-ttu-id="4b8b0-106">Visual Studio におけるプロジェクトのアップグレードの詳細については、「[Visual Studio プロジェクトのポート、移行、アップグレード](/visualstudio/porting/port-migrate-and-upgrade-visual-studio-projects)」と「[Visual Studio 2019 の対象プラットフォームと互換性](/visualstudio/releases/2019/compatibility)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4b8b0-106">For more information about upgrading a project in Visual Studio, see [Port, Migrate, and Upgrade Visual Studio Projects](/visualstudio/porting/port-migrate-and-upgrade-visual-studio-projects) and [Visual Studio 2019 Platform Targeting and Compatibility](/visualstudio/releases/2019/compatibility).</span></span>

 <span data-ttu-id="4b8b0-107">ただし、.NET Framework で行われたいくつかの変更により、コードを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4b8b0-107">However, some changes in the .NET Framework require changes to your code.</span></span> <span data-ttu-id="4b8b0-108">.NET Framework 4.5 とそのポイント リリース、.NET Framework 4.6 とそのポイント リリース、.NET Framework 4.7 とそのポイント リリース、または .NET Framework 4.8 の新しい機能を利用することもできます。</span><span class="sxs-lookup"><span data-stu-id="4b8b0-108">You may also want to take advantage of functionality that is new in .NET Framework 4.5 and its point releases, in .NET Framework 4.6 and its point releases, in .NET Framework 4.7 and its point releases, or in .NET Framework 4.8.</span></span> <span data-ttu-id="4b8b0-109">.NET Framework の新しいバージョンに対応するためのアプリに対するこの種の変更は、一般に*移行*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="4b8b0-109">Making these types of changes to your app for a new version of the .NET Framework is typically referred to as *migration*.</span></span> <span data-ttu-id="4b8b0-110">アプリを移行する必要がない場合、アプリは再コンパイルなしで .NET Framework 4.5 またはそれ以降のバージョンで実行できます。</span><span class="sxs-lookup"><span data-stu-id="4b8b0-110">If your app doesn't have to be migrated, you can run it in the .NET Framework 4.5 or a later version without recompiling it.</span></span>

## <a name="migration-resources"></a><span data-ttu-id="4b8b0-111">移行のためのリソース</span><span class="sxs-lookup"><span data-stu-id="4b8b0-111">Migration resources</span></span>

<span data-ttu-id="4b8b0-112">アプリを .NET Framework の旧バージョンからバージョン 4.5、4.5.1、4.5.2、4.6、4.6.1、4.6.2、4.7、4.7.1、4.7.2、または 4.8 に移行する前に、次のドキュメントを確認してください。</span><span class="sxs-lookup"><span data-stu-id="4b8b0-112">Review the following documents before you migrate your app from earlier versions of the .NET Framework to version 4.5, 4.5.1, 4.5.2, 4.6, 4.6.1, 4.6.2, 4.7, 4.7.1, 4.7.2, or 4.8:</span></span>

- <span data-ttu-id="4b8b0-113">[バージョンおよび依存関係](versions-and-dependencies.md)に関するページで、.NET Framework の各バージョンの基になる CLR バージョンの詳細と、アプリを正しくターゲットするためのガイドラインを確認してください。</span><span class="sxs-lookup"><span data-stu-id="4b8b0-113">See [Versions and Dependencies](versions-and-dependencies.md) to understand the CLR version underlying each version of the .NET Framework and to review guidelines for targeting your apps successfully.</span></span>

- <span data-ttu-id="4b8b0-114">[アプリケーションの互換性](application-compatibility.md)に関するページで、アプリに影響を与える可能性のあるランタイムの変更と再ターゲットの変更、およびそれらの処理方法について確認してください。</span><span class="sxs-lookup"><span data-stu-id="4b8b0-114">Review [Application Compatibility](application-compatibility.md) to find out about runtime and retargeting changes that might affect your app and how to handle them.</span></span>

- <span data-ttu-id="4b8b0-115">[クラス ライブラリの互換性のために残されている機能](../whats-new/whats-obsolete.md)に関するページで、コード内の互換性のために残されている型またはメンバーと、推奨される代替の型またはメンバーを確認してください。</span><span class="sxs-lookup"><span data-stu-id="4b8b0-115">Review [What's Obsolete in the Class Library](../whats-new/whats-obsolete.md) to determine any types or members in your code that have been made obsolete, and the recommended alternatives.</span></span>

- <span data-ttu-id="4b8b0-116">[新機能](../whats-new/index.md)に関するページで、アプリに追加できる可能性のある新機能の説明を確認してください。</span><span class="sxs-lookup"><span data-stu-id="4b8b0-116">See [What's New](../whats-new/index.md) for descriptions of new features that you may want to add to your app.</span></span>

## <a name="see-also"></a><span data-ttu-id="4b8b0-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="4b8b0-117">See also</span></span>

- [<span data-ttu-id="4b8b0-118">アプリケーションの互換性</span><span class="sxs-lookup"><span data-stu-id="4b8b0-118">Application Compatibility</span></span>](application-compatibility.md)
- [<span data-ttu-id="4b8b0-119">.NET Framework 1.1 からの移行</span><span class="sxs-lookup"><span data-stu-id="4b8b0-119">Migrating from the .NET Framework 1.1</span></span>](migrating-from-the-net-framework-1-1.md)
- [<span data-ttu-id="4b8b0-120">バージョンの互換性</span><span class="sxs-lookup"><span data-stu-id="4b8b0-120">Version Compatibility</span></span>](version-compatibility.md)
- [<span data-ttu-id="4b8b0-121">バージョンおよび依存関係</span><span class="sxs-lookup"><span data-stu-id="4b8b0-121">Versions and Dependencies</span></span>](versions-and-dependencies.md)
- [<span data-ttu-id="4b8b0-122">方法: .NET Framework 4 以降のバージョンをサポートするアプリを構成する</span><span class="sxs-lookup"><span data-stu-id="4b8b0-122">How to: Configure an app to support .NET Framework 4 or later versions</span></span>](how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
- [<span data-ttu-id="4b8b0-123">新機能</span><span class="sxs-lookup"><span data-stu-id="4b8b0-123">What's New</span></span>](../whats-new/index.md)
- [<span data-ttu-id="4b8b0-124">クラス ライブラリの互換性のために残されている機能</span><span class="sxs-lookup"><span data-stu-id="4b8b0-124">What's Obsolete in the Class Library</span></span>](../whats-new/whats-obsolete.md)
- [<span data-ttu-id="4b8b0-125">.NET Framework のバージョンとアセンブリ情報</span><span class="sxs-lookup"><span data-stu-id="4b8b0-125">.NET Framework Version and Assembly Information</span></span>](https://go.microsoft.com/fwlink/?LinkId=201701)
- [<span data-ttu-id="4b8b0-126">Microsoft .NET Framework のサポート ライフサイクル ポリシー</span><span class="sxs-lookup"><span data-stu-id="4b8b0-126">Microsoft .NET Framework Support Lifecycle Policy</span></span>](https://go.microsoft.com/fwlink/?LinkId=196607)
- [<span data-ttu-id="4b8b0-127">.NET Framework 4 の移行の問題</span><span class="sxs-lookup"><span data-stu-id="4b8b0-127">.NET Framework 4 migration issues</span></span>](net-framework-4-migration-issues.md)
