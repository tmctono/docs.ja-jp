---
title: アセンブリの場所
description: .NET アセンブリの場所によって、CLR が検出する方法と、他のアセンブリと共有できるかどうかが決まります。
ms.date: 08/20/2019
helpviewer_keywords:
- locating assemblies
- assemblies [.NET Framework], location
ms.assetid: 9f1f41a7-2954-49d3-a2c0-62b6ef4d40ab
ms.openlocfilehash: 7ab3804b14b586e1430d654f4da32a310bcb6cc9
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379893"
---
# <a name="assembly-location"></a><span data-ttu-id="07a7b-103">アセンブリの場所</span><span class="sxs-lookup"><span data-stu-id="07a7b-103">Assembly location</span></span>
<span data-ttu-id="07a7b-104">アセンブリの場所は、参照時に共通言語ランタイムがそれを見つけることができるかどうかを決定します。また、アセンブリをその他のアセンブリと共有できるかどうかも決定できます。</span><span class="sxs-lookup"><span data-stu-id="07a7b-104">An assembly's location determines whether the common language runtime can locate it when referenced, and can also determine whether the assembly can be shared with other assemblies.</span></span> <span data-ttu-id="07a7b-105">次の場所にアセンブリを展開することができます。</span><span class="sxs-lookup"><span data-stu-id="07a7b-105">You can deploy an assembly in the following locations:</span></span>

- <span data-ttu-id="07a7b-106">アプリケーションのディレクトリまたはサブディレクトリ</span><span class="sxs-lookup"><span data-stu-id="07a7b-106">The application's directory or subdirectories.</span></span>

     <span data-ttu-id="07a7b-107">これは、アセンブリを展開する最も一般的な場所です。</span><span class="sxs-lookup"><span data-stu-id="07a7b-107">This is the most common location for deploying an assembly.</span></span> <span data-ttu-id="07a7b-108">アプリケーションのルート ディレクトリのサブディレクトリは、言語またはカルチャを基にすることができます。</span><span class="sxs-lookup"><span data-stu-id="07a7b-108">The subdirectories of an application's root directory can be based on language or culture.</span></span> <span data-ttu-id="07a7b-109">アセンブリにカルチャ属性の情報がある場合は、アプリケーション ディレクトリの下のサブディレクトリに、そのカルチャの名前で存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07a7b-109">If an assembly has information in the culture attribute, it must be in a subdirectory under the application directory with that culture's name.</span></span>

- <span data-ttu-id="07a7b-110">グローバル アセンブリ キャッシュ</span><span class="sxs-lookup"><span data-stu-id="07a7b-110">The global assembly cache.</span></span>

     <span data-ttu-id="07a7b-111">これは、共通言語ランタイムをインストールしている場所にインストールされている、コンピューター全体で使用できるコード キャッシュです。</span><span class="sxs-lookup"><span data-stu-id="07a7b-111">This is a machine-wide code cache that is installed wherever the common language runtime is installed.</span></span> <span data-ttu-id="07a7b-112">ほとんどの場合、あるアセンブリを複数のアプリケーションで共有する場合は、そのアセンブリをグローバル アセンブリ キャッシュ内に展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07a7b-112">In most cases, if you intend to share an assembly with multiple applications, you should deploy it into the global assembly cache.</span></span>

- <span data-ttu-id="07a7b-113">HTTP サーバー上</span><span class="sxs-lookup"><span data-stu-id="07a7b-113">On an HTTP server.</span></span>

     <span data-ttu-id="07a7b-114">HTTP サーバーに展開されているアセンブリは、厳密な名前を持つ必要があります。アプリケーションの構成ファイルのコードベース セクションにあるアセンブリをポイントします。</span><span class="sxs-lookup"><span data-stu-id="07a7b-114">An assembly deployed on an HTTP server must have a strong name; you point to the assembly in the codebase section of the application's configuration file.</span></span>

## <a name="see-also"></a><span data-ttu-id="07a7b-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="07a7b-115">See also</span></span>

- [<span data-ttu-id="07a7b-116">アセンブリを作成する</span><span class="sxs-lookup"><span data-stu-id="07a7b-116">Create assemblies</span></span>](create.md)
- [<span data-ttu-id="07a7b-117">グローバル アセンブリ キャッシュ</span><span class="sxs-lookup"><span data-stu-id="07a7b-117">Global assembly cache</span></span>](../../framework/app-domains/gac.md)
- [<span data-ttu-id="07a7b-118">ランタイムがアセンブリを検索する方法</span><span class="sxs-lookup"><span data-stu-id="07a7b-118">How the runtime locates assemblies</span></span>](../../framework/deployment/how-the-runtime-locates-assemblies.md)
