---
ms.openlocfilehash: c967a5b09b5e9ffeee7bff046f0c96469bc7fb02
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615655"
---
### <a name="clickonce-supports-sha-256-on-40-targeted-apps"></a><span data-ttu-id="13906-101">4\.0 を対象とするアプリの ClickOnce が SHA-256 に対応</span><span class="sxs-lookup"><span data-stu-id="13906-101">ClickOnce supports SHA-256 on 4.0-targeted apps</span></span>

#### <a name="details"></a><span data-ttu-id="13906-102">説明</span><span class="sxs-lookup"><span data-stu-id="13906-102">Details</span></span>

<span data-ttu-id="13906-103">以前は、SHA-256 で署名された証明書が与えられた ClickOnce アプリには、アプリの対象が 4.0 の場合でも、.NET Framework 4.5 以降が必要でした。</span><span class="sxs-lookup"><span data-stu-id="13906-103">Previously, a ClickOnce app with a certificate signed with SHA-256 would require .NET Framework 4.5 or later to be present, even if the app targeted 4.0.</span></span> <span data-ttu-id="13906-104">それが今では、SHA-256 で署名されている場合でも、.NET Framework 4.0 を対象とする ClickOnce アプリを .NET Framework 4.0 で実行できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="13906-104">Now, .NET Framework 4.0-targeted ClickOnce apps can run on .NET Framework 4.0, even if signed with SHA-256.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="13906-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="13906-105">Suggestion</span></span>

<span data-ttu-id="13906-106">この変更により、その依存関係がなくなったので、.NET Framework 4 以前のバージョンを対象とする ClickOnce アプリの署名に SAH-256 証明書が使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="13906-106">This change removes that dependency and allows SHA-256 certificates to be used to sign ClickOnce apps that target .NET Framework 4 and earlier versions.</span></span>

| <span data-ttu-id="13906-107">名前</span><span class="sxs-lookup"><span data-stu-id="13906-107">Name</span></span>    | <span data-ttu-id="13906-108">値</span><span class="sxs-lookup"><span data-stu-id="13906-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="13906-109">スコープ</span><span class="sxs-lookup"><span data-stu-id="13906-109">Scope</span></span>   | <span data-ttu-id="13906-110">マイナー</span><span class="sxs-lookup"><span data-stu-id="13906-110">Minor</span></span>       |
| <span data-ttu-id="13906-111">バージョン</span><span class="sxs-lookup"><span data-stu-id="13906-111">Version</span></span> | <span data-ttu-id="13906-112">4.6</span><span class="sxs-lookup"><span data-stu-id="13906-112">4.6</span></span>         |
| <span data-ttu-id="13906-113">種類</span><span class="sxs-lookup"><span data-stu-id="13906-113">Type</span></span>    | <span data-ttu-id="13906-114">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="13906-114">Retargeting</span></span> |
