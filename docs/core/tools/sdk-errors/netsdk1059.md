---
title: NETSDK1059:プロジェクトに古い .NET CLI ツールが含まれています
description: プロジェクトに古い .NET CLI ツールが含まれている問題を解決する方法。
author: sfoslund
ms.topic: error-reference
ms.date: 10/09/2020
f1_keywords:
- NETSDK1059
ms.openlocfilehash: 2960b9255dab9e61a84e49bc029666753d8c9a1e
ms.sourcegitcommit: b59237ca4ec763969a0dd775a3f8f39f8c59fe24
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/12/2020
ms.locfileid: "91957100"
---
# <a name="netsdk1059-project-contains-obsolete-net-cli-tool"></a><span data-ttu-id="8a566-103">NETSDK1059:プロジェクトに古い .NET CLI ツールが含まれています</span><span class="sxs-lookup"><span data-stu-id="8a566-103">NETSDK1059: Project contains obsolete .NET CLI tool</span></span>

<span data-ttu-id="8a566-104">**この記事の対象:**  ✔️ .NET 2.1.100 SDK 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="8a566-104">**This article applies to:** ✔️ .NET 2.1.100 SDK and later versions</span></span>

<span data-ttu-id="8a566-105">.NET SDK によって警告 NETSDK1059 が発行される場合、プロジェクトには古い .NET CLI ツールが含まれています。</span><span class="sxs-lookup"><span data-stu-id="8a566-105">When the .NET SDK issues warning NETSDK1059, your project contains an obsolete .NET CLI tool.</span></span> <span data-ttu-id="8a566-106">.NET 2.1 では、これらのツールは .NET SDK に含まれており、プロジェクトによって明示的に参照される必要はありません。</span><span class="sxs-lookup"><span data-stu-id="8a566-106">As of .NET 2.1, these tools are included in the .NET SDK and do not need to be explicitly referenced by the project.</span></span> <span data-ttu-id="8a566-107">.NET 2.1 への移行の詳細については、[こちら](https://aka.ms/dotnetclitools-in-box)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a566-107">More information for migrating to .NET 2.1 can be found [here](https://aka.ms/dotnetclitools-in-box).</span></span>
