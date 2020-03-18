---
ms.openlocfilehash: ce8e162e11802de1b06bfbc63d5c55de67ef23df
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2020
ms.locfileid: "67857271"
---
### <a name="wcf-msmqsecurehashalgorithm-default-value-is-now-sha256"></a><span data-ttu-id="b9998-101">WCF MsmqSecureHashAlgorithm の既定値が SHA256 になった</span><span class="sxs-lookup"><span data-stu-id="b9998-101">WCF MsmqSecureHashAlgorithm default value is now SHA256</span></span>

|   |   |
|---|---|
|<span data-ttu-id="b9998-102">説明</span><span class="sxs-lookup"><span data-stu-id="b9998-102">Details</span></span>|<span data-ttu-id="b9998-103">.NET Framework 4.7.1 以降では、Msmq メッセージの WCF での既定のメッセージ署名アルゴリズムは SHA256 です。</span><span class="sxs-lookup"><span data-stu-id="b9998-103">Starting with the .NET Framework 4.7.1, the default message signing algorithm in WCF for Msmq messages is SHA256.</span></span> <span data-ttu-id="b9998-104">.NET Framework 4.7 以前のバージョンでは、既定のメッセージ署名アルゴリズムは SHA1 です。</span><span class="sxs-lookup"><span data-stu-id="b9998-104">In the .NET Framework 4.7 and earlier versions, the default message signing algorithm is SHA1.</span></span>|
|<span data-ttu-id="b9998-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="b9998-105">Suggestion</span></span>|<span data-ttu-id="b9998-106">.NET Framework 4.7.1 以降でこの変更に関する互換性の問題が発生した場合は、次の行を app.config ファイルの <code>&lt;runtime&gt;</code> セクションに追加することで、変更を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="b9998-106">If you run into compatibility issues with this change on the .NET Framework 4.7.1 or later, you can opt-out the change by adding the following line to the <code>&lt;runtime&gt;</code>section of your app.config file:</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.UseSha1InMsmqEncryptionAlgorithm=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="b9998-107">スコープ</span><span class="sxs-lookup"><span data-stu-id="b9998-107">Scope</span></span>|<span data-ttu-id="b9998-108">Minor</span><span class="sxs-lookup"><span data-stu-id="b9998-108">Minor</span></span>|
|<span data-ttu-id="b9998-109">バージョン</span><span class="sxs-lookup"><span data-stu-id="b9998-109">Version</span></span>|<span data-ttu-id="b9998-110">4.7.1</span><span class="sxs-lookup"><span data-stu-id="b9998-110">4.7.1</span></span>|
|<span data-ttu-id="b9998-111">[種類]</span><span class="sxs-lookup"><span data-stu-id="b9998-111">Type</span></span>|<span data-ttu-id="b9998-112">ランタイム</span><span class="sxs-lookup"><span data-stu-id="b9998-112">Runtime</span></span>|
