---
ms.openlocfilehash: 15418d1ac3ade6a0fa35ca61a02134e20af1baea
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602742"
---

<span data-ttu-id="06cf4-101">.NET Core パッケージのインストール中に、`Failed to fetch ... File has unexpected size ... Mirror sync in progress?` のようなエラーが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="06cf4-101">While installing the .NET Core package, you may see an error similar to `Failed to fetch ... File has unexpected size ... Mirror sync in progress?`.</span></span> <span data-ttu-id="06cf4-102">このエラーは、.NET Core のパッケージ フィードが新しいバージョンのパッケージでアップグレード中であり、後でもう一度試す必要があることを意味している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="06cf4-102">This error could mean that the package feed for .NET Core is being upgraded with newer package versions, and that you should try again later.</span></span> <span data-ttu-id="06cf4-103">アップグレード中は、30 分以上パッケージ フィードを利用できません。</span><span class="sxs-lookup"><span data-stu-id="06cf4-103">During an upgrade, the package feed shouldn't be unavailable for more than 30 minutes.</span></span> <span data-ttu-id="06cf4-104">30 分以上このエラーが継続的に発生する場合は、<https://github.com/dotnet/core/issues> でイシューを報告してください。</span><span class="sxs-lookup"><span data-stu-id="06cf4-104">If you continually receive this error for more than 30 minutes, please file an issue at <https://github.com/dotnet/core/issues>.</span></span>
