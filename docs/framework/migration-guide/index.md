---
title: .NET Framework 4.8、4.7、4.6、4.5 移行ガイド
description: 新機能とアプリケーションの互換性のためのリソースを含む .NET Framework の新しいバージョンに移行するためのガイドです。
ms.date: 04/18/2019
helpviewer_keywords:
- .NET Framework, migrating applications to
- migration, .NET Framework
ms.assetid: 02d55147-9b3a-4557-a45f-fa936fadae3b
ms.openlocfilehash: c597f6e7b67e190ffe61a425506a1a34f254942c
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/18/2020
ms.locfileid: "88558505"
---
# <a name="migrate-to-net-framework-48-47-46-and-45"></a><span data-ttu-id="b1655-103">.NET Framework 4.8、4.7、4.6、4.5 への移行</span><span class="sxs-lookup"><span data-stu-id="b1655-103">Migrate to .NET Framework 4.8, 4.7, 4.6, and 4.5</span></span>

<span data-ttu-id="b1655-104">旧バージョンの .NET Framework を使用してアプリを作成した場合、通常は .NET Framework 4.5 とそのポイント リリース (4.5.1 と 4.5.2)、.NET Framework 4.6 とそのポイント リリース (4.6.1 と 4.6.2)、.NET Framework 4.7 とそのポイント リリース (4.7.1 および 4.7.2)、または .NET Framework 4.8 へ簡単にアップグレードできます。</span><span class="sxs-lookup"><span data-stu-id="b1655-104">If you created your app using an earlier version of .NET Framework, you can generally upgrade it to .NET Framework 4.5 and its point releases (4.5.1 and 4.5.2), .NET Framework 4.6 and its point releases (4.6.1 and 4.6.2), .NET Framework 4.7 and its point releases (4.7.1 and 4.7.2), or .NET Framework 4.8 easily.</span></span> <span data-ttu-id="b1655-105">Visual Studio でプロジェクトを開きます。</span><span class="sxs-lookup"><span data-stu-id="b1655-105">Open your project in Visual Studio.</span></span> <span data-ttu-id="b1655-106">プロジェクトが旧バージョンの Visual Studio で作成されている場合は、 **[Project Compatibility]\(プロジェクト互換性\)** ダイアログ ボックスが自動的に開きます。</span><span class="sxs-lookup"><span data-stu-id="b1655-106">If your project was created in an earlier version of Visual Studio, the **Project Compatibility** dialog box automatically opens.</span></span> <span data-ttu-id="b1655-107">Visual Studio におけるプロジェクトのアップグレードの詳細については、「[Visual Studio プロジェクトのポート、移行、アップグレード](/visualstudio/porting/port-migrate-and-upgrade-visual-studio-projects)」と「[Visual Studio 2019 の対象プラットフォームと互換性](/visualstudio/releases/2019/compatibility)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1655-107">For more information about upgrading a project in Visual Studio, see [Port, Migrate, and Upgrade Visual Studio Projects](/visualstudio/porting/port-migrate-and-upgrade-visual-studio-projects) and [Visual Studio 2019 Platform Targeting and Compatibility](/visualstudio/releases/2019/compatibility).</span></span>

 <span data-ttu-id="b1655-108">ただし、.NET Framework で行われたいくつかの変更により、コードの変更が必要になります。</span><span class="sxs-lookup"><span data-stu-id="b1655-108">However, some changes in .NET Framework require changes to your code.</span></span> <span data-ttu-id="b1655-109">.NET Framework 4.5 とそのポイント リリース、.NET Framework 4.6 とそのポイント リリース、.NET Framework 4.7 とそのポイント リリース、または .NET Framework 4.8 の新しい機能を利用することもできます。</span><span class="sxs-lookup"><span data-stu-id="b1655-109">You may also want to take advantage of functionality that is new in .NET Framework 4.5 and its point releases, in .NET Framework 4.6 and its point releases, in .NET Framework 4.7 and its point releases, or in .NET Framework 4.8.</span></span> <span data-ttu-id="b1655-110">.NET Framework の新しいバージョンに対応するために行う、アプリに対するこの種の変更は、一般に "*移行*" と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="b1655-110">Making these types of changes to your app for a new version of .NET Framework is typically referred to as *migration*.</span></span> <span data-ttu-id="b1655-111">アプリを移行する必要がない場合、アプリは再コンパイルなしで .NET Framework 4.5 またはそれ以降のバージョンで実行できます。</span><span class="sxs-lookup"><span data-stu-id="b1655-111">If your app doesn't have to be migrated, you can run it in .NET Framework 4.5 or a later version without recompiling it.</span></span>

## <a name="migration-resources"></a><span data-ttu-id="b1655-112">移行のためのリソース</span><span class="sxs-lookup"><span data-stu-id="b1655-112">Migration resources</span></span>

<span data-ttu-id="b1655-113">アプリを .NET Framework の旧バージョンからバージョン 4.5、4.5.1、4.5.2、4.6、4.6.1、4.6.2、4.7、4.7.1、4.7.2、または 4.8 に移行する前に、次のドキュメントを確認してください。</span><span class="sxs-lookup"><span data-stu-id="b1655-113">Review the following documents before you migrate your app from earlier versions of .NET Framework to version 4.5, 4.5.1, 4.5.2, 4.6, 4.6.1, 4.6.2, 4.7, 4.7.1, 4.7.2, or 4.8:</span></span>

- <span data-ttu-id="b1655-114">[バージョンおよび依存関係](versions-and-dependencies.md)に関するページで、.NET Framework の各バージョンの基になる CLR バージョンの詳細と、アプリを正しくターゲットするためのガイドラインを確認してください。</span><span class="sxs-lookup"><span data-stu-id="b1655-114">See [Versions and Dependencies](versions-and-dependencies.md) to understand the CLR version underlying each version of the .NET Framework and to review guidelines for targeting your apps successfully.</span></span>

- <span data-ttu-id="b1655-115">[アプリケーションの互換性](application-compatibility.md)に関するページで、アプリに影響を与える可能性のあるランタイムの変更と再ターゲットの変更、およびそれらの処理方法について確認してください。</span><span class="sxs-lookup"><span data-stu-id="b1655-115">Review [Application compatibility](application-compatibility.md) to find out about runtime and retargeting changes that might affect your app and how to handle them.</span></span>

- <span data-ttu-id="b1655-116">[クラス ライブラリの互換性のために残されている機能](../whats-new/whats-obsolete.md)に関するページで、コード内の互換性のために残されている型またはメンバーと、推奨される代替の型またはメンバーを確認してください。</span><span class="sxs-lookup"><span data-stu-id="b1655-116">Review [What's Obsolete in the Class Library](../whats-new/whats-obsolete.md) to determine any types or members in your code that have been made obsolete, and the recommended alternatives.</span></span>

- <span data-ttu-id="b1655-117">[新機能](../whats-new/index.md)に関するページで、アプリに追加できる可能性のある新機能の説明を確認してください。</span><span class="sxs-lookup"><span data-stu-id="b1655-117">See [What's New](../whats-new/index.md) for descriptions of new features that you may want to add to your app.</span></span>

## <a name="see-also"></a><span data-ttu-id="b1655-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="b1655-118">See also</span></span>

- [<span data-ttu-id="b1655-119">アプリケーションの互換性</span><span class="sxs-lookup"><span data-stu-id="b1655-119">Application compatibility</span></span>](application-compatibility.md)
- [<span data-ttu-id="b1655-120">.NET Framework 1.1 からの移行</span><span class="sxs-lookup"><span data-stu-id="b1655-120">Migrating from the .NET Framework 1.1</span></span>](migrating-from-the-net-framework-1-1.md)
- [<span data-ttu-id="b1655-121">バージョンの互換性</span><span class="sxs-lookup"><span data-stu-id="b1655-121">Version Compatibility</span></span>](version-compatibility.md)
- [<span data-ttu-id="b1655-122">バージョンおよび依存関係</span><span class="sxs-lookup"><span data-stu-id="b1655-122">Versions and Dependencies</span></span>](versions-and-dependencies.md)
- [<span data-ttu-id="b1655-123">方法: .NET Framework 4 以降のバージョンをサポートするアプリを構成する</span><span class="sxs-lookup"><span data-stu-id="b1655-123">How to: Configure an app to support .NET Framework 4 or later versions</span></span>](how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
- [<span data-ttu-id="b1655-124">新機能</span><span class="sxs-lookup"><span data-stu-id="b1655-124">What's New</span></span>](../whats-new/index.md)
- [<span data-ttu-id="b1655-125">クラス ライブラリ内にある旧版のもの</span><span class="sxs-lookup"><span data-stu-id="b1655-125">What's Obsolete in the Class Library</span></span>](../whats-new/whats-obsolete.md)
- [<span data-ttu-id="b1655-126">.NET Framework の公式サポート ポリシー</span><span class="sxs-lookup"><span data-stu-id="b1655-126">.NET Framework official support policy</span></span>](https://dotnet.microsoft.com/platform/support/policy/dotnet-framework)
- [<span data-ttu-id="b1655-127">.NET Framework 4 の移行の問題</span><span class="sxs-lookup"><span data-stu-id="b1655-127">.NET Framework 4 migration issues</span></span>](net-framework-4-migration-issues.md)
