---
ms.openlocfilehash: 0358450024607a985f38564ec9743ba964949e8f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2020
ms.locfileid: "67804581"
---
### <a name="clickonce-supports-sha-256-on-40-targeted-apps"></a><span data-ttu-id="ca25d-101">4\.0 を対象とするアプリの ClickOnce が SHA-256 に対応</span><span class="sxs-lookup"><span data-stu-id="ca25d-101">ClickOnce supports SHA-256 on 4.0-targeted apps</span></span>

|   |   |
|---|---|
|<span data-ttu-id="ca25d-102">説明</span><span class="sxs-lookup"><span data-stu-id="ca25d-102">Details</span></span>|<span data-ttu-id="ca25d-103">以前は、SHA-256 で署名された証明書が与えられた ClickOnce アプリには、アプリの対象が 4.0 の場合でも、.NET Framework 4.5 以降が必要でした。</span><span class="sxs-lookup"><span data-stu-id="ca25d-103">Previously, a ClickOnce app with a certificate signed with SHA-256 would require .NET Framework 4.5 or later to be present, even if the app targeted 4.0.</span></span> <span data-ttu-id="ca25d-104">それが今では、SHA-256 で署名されている場合でも、.NET Framework 4.0 を対象とする ClickOnce アプリを .NET Framework 4.0 で実行できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="ca25d-104">Now, .NET Framework 4.0-targeted ClickOnce apps can run on .NET Framework 4.0, even if signed with SHA-256.</span></span>|
|<span data-ttu-id="ca25d-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="ca25d-105">Suggestion</span></span>|<span data-ttu-id="ca25d-106">この変更により、その依存関係がなくなったので、.NET Framework 4 以前のバージョンを対象とする ClickOnce アプリの署名に SAH-256 証明書が使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="ca25d-106">This change removes that dependency and allows SHA-256 certificates to be used to sign ClickOnce apps that target .NET Framework 4 and earlier versions.</span></span>|
|<span data-ttu-id="ca25d-107">スコープ</span><span class="sxs-lookup"><span data-stu-id="ca25d-107">Scope</span></span>|<span data-ttu-id="ca25d-108">Minor</span><span class="sxs-lookup"><span data-stu-id="ca25d-108">Minor</span></span>|
|<span data-ttu-id="ca25d-109">バージョン</span><span class="sxs-lookup"><span data-stu-id="ca25d-109">Version</span></span>|<span data-ttu-id="ca25d-110">4.6</span><span class="sxs-lookup"><span data-stu-id="ca25d-110">4.6</span></span>|
|<span data-ttu-id="ca25d-111">[種類]</span><span class="sxs-lookup"><span data-stu-id="ca25d-111">Type</span></span>|<span data-ttu-id="ca25d-112">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="ca25d-112">Retargeting</span></span>|
