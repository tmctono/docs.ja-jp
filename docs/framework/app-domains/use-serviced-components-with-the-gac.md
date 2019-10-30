---
title: サービス コンポーネントとグローバル アセンブリ キャッシュの使用
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- GAC (global assembly cache), serviced components
- serviced components, global assembly cache
- global assembly cache, serviced components
ms.assetid: 3423e5d9-234c-4571-8161-e35f6d130128
ms.openlocfilehash: 99627cb14088f037c58bfa1eec72bd4f88d06011
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73119764"
---
# <a name="using-serviced-components-with-the-global-assembly-cache"></a><span data-ttu-id="bef96-102">サービス コンポーネントとグローバル アセンブリ キャッシュの使用</span><span class="sxs-lookup"><span data-stu-id="bef96-102">Using Serviced Components with the Global Assembly Cache</span></span>
<span data-ttu-id="bef96-103">サービス コンポーネント (マネージド コード COM+ コンポーネント) はグローバル アセンブリ キャッシュに配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bef96-103">Serviced components (managed code COM+ components) should be put in the Global Assembly Cache.</span></span> <span data-ttu-id="bef96-104">共通言語ランタイムと COM+ サービスは、シナリオによって、グローバル アセンブリ キャッシュに配置されていないサービス コンポーネントを処理できる場合と、処理できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="bef96-104">In some scenarios, the Common Language Runtime and COM+ Services can handle serviced components that are not in the Global Assembly Cache; in other scenarios, they cannot.</span></span> <span data-ttu-id="bef96-105">これについて、次のシナリオで説明します。</span><span class="sxs-lookup"><span data-stu-id="bef96-105">The following scenarios illustrate this:</span></span>  
  
- <span data-ttu-id="bef96-106">COM+ サーバー アプリケーションのサービス コンポーネントの場合、コンポーネントを含むアセンブリがグローバル アセンブリ キャッシュに配置されている必要があります。これは、Dllhost.exe がサービス コンポーネントを格納するのと同じディレクトリで実行されないためです。</span><span class="sxs-lookup"><span data-stu-id="bef96-106">For serviced components in a COM+ Server application, the assembly containing the components must be in the Global Assembly Cache, because Dllhost.exe does not run in the same directory as the one that contains the serviced components.</span></span>  
  
- <span data-ttu-id="bef96-107">COM+ ライブラリ アプリケーションに含まれるサービス コンポーネントの場合、ランタイムと COM+ サービスは、現在のディレクトリで検索することにより、コンポーネントを含むアセンブリへの参照を解決できます。</span><span class="sxs-lookup"><span data-stu-id="bef96-107">For serviced components in a COM+ Library application, the runtime and COM+ Services can resolve the reference to the assembly containing the components by searching in the current directory.</span></span> <span data-ttu-id="bef96-108">この場合、アセンブリがグローバル アセンブリ キャッシュ内に配置されている必要はありません。</span><span class="sxs-lookup"><span data-stu-id="bef96-108">In this case, the assembly does not have to be in the global assembly cache.</span></span>  
  
- <span data-ttu-id="bef96-109">ASP.NET アプリケーションに含まれるサービス コンポーネントの場合、状況は異なります。</span><span class="sxs-lookup"><span data-stu-id="bef96-109">For serviced components in an ASP.NET application, the situation is different.</span></span> <span data-ttu-id="bef96-110">サービス コンポーネントを含むアセンブリをアプリケーション ベースの bin ディレクトリに配置し、オンデマンド登録を使用すると、アセンブリはダウンロード キャッシュにシャドウとしてコピーされます。これは、ASP.NET がランタイムのシャドウ機能を利用するためです。</span><span class="sxs-lookup"><span data-stu-id="bef96-110">If you place the assembly containing the serviced components in the bin directory of the application base and use on-demand registration, the assembly will be shadow-copied into the download cache because ASP.NET leverages the shadow capabilities of the runtime.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bef96-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="bef96-111">See also</span></span>

- [<span data-ttu-id="bef96-112">アセンブリとグローバル アセンブリ キャッシュの使用</span><span class="sxs-lookup"><span data-stu-id="bef96-112">Working with Assemblies and the Global Assembly Cache</span></span>](working-with-assemblies-and-the-gac.md)
- [<span data-ttu-id="bef96-113">Gacutil.exe (グローバル アセンブリ キャッシュ ツール)</span><span class="sxs-lookup"><span data-stu-id="bef96-113">Gacutil.exe (Global Assembly Cache Tool)</span></span>](../tools/gacutil-exe-gac-tool.md)
