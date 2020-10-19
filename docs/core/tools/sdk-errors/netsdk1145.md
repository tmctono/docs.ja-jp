---
title: 'NETSDK1145: ターゲットまたは apphost のパックが見つからない'
description: NuGet パッケージの復元がサポートされていないときにターゲット パックが見つからない問題を解決する方法
author: wli3
ms.topic: error-reference
ms.date: 09/14/2020
f1_keywords:
- NETSDK1145
ms.openlocfilehash: c343952582cafb63eae388fd216769e6c67d4741
ms.sourcegitcommit: 636af37170ae75a11c4f7d1ecd770820e7dfe7bd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2020
ms.locfileid: "91805308"
---
# <a name="netsdk1145-targeting-or-apphost-pack-missing"></a><span data-ttu-id="bfa31-103">NETSDK1145: ターゲットまたは apphost のパックが見つからない</span><span class="sxs-lookup"><span data-stu-id="bfa31-103">NETSDK1145: Targeting or apphost pack missing</span></span>

<span data-ttu-id="bfa31-104">**この記事の対象:**  ✔️ .NET 5.0.100 SDK 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="bfa31-104">**This article applies to:** ✔️ .NET 5.0.100 SDK and later versions</span></span>

<span data-ttu-id="bfa31-105">.NET SDK でエラー NETSDK1145 が発生すると、ターゲットまたは apphost のパックがインストールされず、NuGet パッケージの復元がサポートされません。</span><span class="sxs-lookup"><span data-stu-id="bfa31-105">When the .NET SDK issues error NETSDK1145, the targeting or apphost pack is not installed and NuGet package restore is not supported.</span></span> <span data-ttu-id="bfa31-106">これは通常、Visual Studio for C++/CLI プロジェクトに含まれているものよりも新しい SDK が原因で発生します。</span><span class="sxs-lookup"><span data-stu-id="bfa31-106">This is typically caused by having a newer SDK than the one included in Visual Studio for C++/CLI projects.</span></span> <span data-ttu-id="bfa31-107">Visual Studio をアップグレードし、特定の SDK バージョンが指定されている場合は _global.json_ を削除して、新しい方の SDK をアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="bfa31-107">Upgrade Visual Studio, remove _global.json_ if it specifies a certain SDK version, and uninstall the newer SDK.</span></span> <span data-ttu-id="bfa31-108">または、ターゲットまたは apphost のバージョンをオーバーライドすることもできます。</span><span class="sxs-lookup"><span data-stu-id="bfa31-108">Alternatively, you could override the targeting or apphost version.</span></span> <span data-ttu-id="bfa31-109">エラー メッセージから、パックのディレクトリの下に存在し、プロジェクトのターゲット フレームワークと一致するバージョンを見つけます。</span><span class="sxs-lookup"><span data-stu-id="bfa31-109">Find the version that exists under the pack directory from the error message and matches the target framework of the project.</span></span> <span data-ttu-id="bfa31-110">次をプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="bfa31-110">Add the following to the project:</span></span>

<span data-ttu-id="bfa31-111">apphost パックの場合</span><span class="sxs-lookup"><span data-stu-id="bfa31-111">For apphost pack</span></span>

```xml
<ItemGroup>
  <KnownAppHostPack Update="@(KnownAppHostPack)">
    <AppHostPackVersion Condition="'%(TargetFramework)' == 'TARGETFRAMEWORK'">EXISTINGVERSION</AppHostPackVersion>
  </KnownAppHostPack>
</ItemGroup>
```

<span data-ttu-id="bfa31-112">ターゲット パックの場合</span><span class="sxs-lookup"><span data-stu-id="bfa31-112">For targeting pack</span></span>

```xml
<ItemGroup>
  <KnownAppHostPack Update="@(KnownAppHostPack)">
    <AppHostPackVersion Condition="'%(TargetFramework)' == 'TARGETFRAMEWORK'">EXISTINGVERSION</AppHostPackVersion>
  </KnownAppHostPack>
</ItemGroup>
```
