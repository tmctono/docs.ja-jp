---
ms.openlocfilehash: 96f3ef0160144322f77413995c842b745bb5bb1e
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2020
ms.locfileid: "76920737"
---

<span data-ttu-id="576b6-101">.NET Core パッケージのインストール中に、`signature verification failed for file 'repomd.xml' from repository 'packages-microsoft-com-prod'` のようなエラーが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="576b6-101">While installing the .NET Core package, you may see an error similar to `signature verification failed for file 'repomd.xml' from repository 'packages-microsoft-com-prod'`.</span></span> <span data-ttu-id="576b6-102">一般に、このエラーは、.NET Core のパッケージ フィードが新しいバージョンのパッケージでアップグレード中であり、後でもう一度試す必要があることを意味しています。</span><span class="sxs-lookup"><span data-stu-id="576b6-102">Generally speaking, this error means that the package feed for .NET Core is being upgraded with newer package versions, and that you should try again later.</span></span> <span data-ttu-id="576b6-103">アップグレード中は、2 時間以上パッケージ フィードを利用できません。</span><span class="sxs-lookup"><span data-stu-id="576b6-103">During an upgrade, the package feed should not be unavailable for more than 2 hours.</span></span> <span data-ttu-id="576b6-104">2 時間以上このエラーが継続的に発生する場合は、<https://github.com/dotnet/core/issues> でイシューを報告してください。</span><span class="sxs-lookup"><span data-stu-id="576b6-104">If you continually receive this error for more than 2 hours, please file an issue at <https://github.com/dotnet/core/issues>.</span></span>
