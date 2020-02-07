---
ms.openlocfilehash: 98ec28fc1f91512a61f64a36f7749379e864fea1
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2020
ms.locfileid: "76920643"
---

<span data-ttu-id="ae9e5-101">.NET Core パッケージのインストール中に、`Failed to fetch ... File has unexpected size ... Mirror sync in progress?` のようなエラーが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="ae9e5-101">While installing the .NET Core package, you may see an error similar to `Failed to fetch ... File has unexpected size ... Mirror sync in progress?`.</span></span> <span data-ttu-id="ae9e5-102">一般に、このエラーは、.NET Core のパッケージ フィードが新しいバージョンのパッケージでアップグレード中であり、後でもう一度試す必要があることを意味しています。</span><span class="sxs-lookup"><span data-stu-id="ae9e5-102">Generally speaking, this error means that the package feed for .NET Core is being upgraded with newer package versions, and that you should try again later.</span></span> <span data-ttu-id="ae9e5-103">アップグレード中は、30 分以上パッケージ フィードを利用できません。</span><span class="sxs-lookup"><span data-stu-id="ae9e5-103">During an upgrade, the package feed should not be unavailable for more than 30 minutes.</span></span> <span data-ttu-id="ae9e5-104">30 分以上このエラーが継続的に発生する場合は、<https://github.com/dotnet/core/issues> でイシューを報告してください。</span><span class="sxs-lookup"><span data-stu-id="ae9e5-104">If you continually receive this error for more than 30 minutes, please file an issue at <https://github.com/dotnet/core/issues>.</span></span>
