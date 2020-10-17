---
title: NETSDK1073:FrameworkReference は認識されませんでした
description: FrameworkReference が見つからない問題を解決する方法。
author: marcpopMSFT
ms.topic: error-reference
ms.date: 10/9/2020
f1_keywords:
- NETSDK1073
ms.openlocfilehash: 59b5f63dcfe0115feabc2d87d24a09c6a650cc62
ms.sourcegitcommit: b59237ca4ec763969a0dd775a3f8f39f8c59fe24
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/12/2020
ms.locfileid: "91957097"
---
# <a name="netsdk1073-the-frameworkreference-was-not-recognized"></a><span data-ttu-id="ae0b5-103">NETSDK1073:FrameworkReference は認識されませんでした</span><span class="sxs-lookup"><span data-stu-id="ae0b5-103">NETSDK1073: The FrameworkReference was not recognized</span></span>

<span data-ttu-id="ae0b5-104">**この記事の対象:**  ✔️ .NET 2.1.100 SDK 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="ae0b5-104">**This article applies to:** ✔️ .NET 2.1.100 SDK and later versions</span></span>

<span data-ttu-id="ae0b5-105">このエラーは、通常、SDK が検出できない特定の FrameworkReference のバージョンがあることを意味します。</span><span class="sxs-lookup"><span data-stu-id="ae0b5-105">This error typically means there is a version of a particular FrameworkReference that the SDK cannot find.</span></span> <span data-ttu-id="ae0b5-106">*obj* と *bin* フォルダーを削除し、`dotnet restore` を実行して最新のターゲット パックを再ダウンロードしてみてください。</span><span class="sxs-lookup"><span data-stu-id="ae0b5-106">Try deleting your *obj* and *bin* folders and running `dotnet restore` to redownload the latest targeting packs.</span></span>

<span data-ttu-id="ae0b5-107">または、インストールに問題がある可能性があるため、最新バージョンの .NET と Visual Studio を使用していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="ae0b5-107">Alternatively, there could be an issue with your install, so ensure you're on the latest versions of .NET and Visual Studio</span></span>
