---
ms.openlocfilehash: 0a3dc43ebdc58d54675f2264a8ee56d9f4358cd8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804413"
---
### <a name="wcf-message-security-now-is-able-to-use-tls11-and-tls12"></a><span data-ttu-id="79728-101">WCF メッセージ セキュリティで TLS1.1 と TLS1.2 が使用可能に</span><span class="sxs-lookup"><span data-stu-id="79728-101">WCF message security now is able to use TLS1.1 and TLS1.2</span></span>

|   |   |
|---|---|
|<span data-ttu-id="79728-102">説明</span><span class="sxs-lookup"><span data-stu-id="79728-102">Details</span></span>|<span data-ttu-id="79728-103">.NET Framework 4.7 以降、顧客はアプリケーション構成設定を介し、SSL3.0 と TLS1.0 に加え、WCF メッセージ セキュリティで TLS1.1 または TLS1.2 を構成できます。</span><span class="sxs-lookup"><span data-stu-id="79728-103">Starting in the .NET Framework 4.7, customers can configure either TLS1.1 or TLS1.2 in WCF message security in addition to SSL3.0 and TLS1.0 through application configuration settings.</span></span>|
|<span data-ttu-id="79728-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="79728-104">Suggestion</span></span>|<span data-ttu-id="79728-105">.NET Framework 4.7 では、WCF メッセージ セキュリティの TLS1.1 と TLS1.2 のサポートは既定で無効になっています。</span><span class="sxs-lookup"><span data-stu-id="79728-105">In the .NET Framework 4.7, support for TLS1.1 and TLS1.2 in WCF message security is disabled by default.</span></span> <span data-ttu-id="79728-106">app.config または web.config ファイルの <code>&lt;runtime&gt;</code> セクションに次の行を追加することで有効にできます。</span><span class="sxs-lookup"><span data-stu-id="79728-106">You can enable it by adding the following line to the <code>&lt;runtime&gt;</code> section of the app.config or web.config file:</span></span><pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.DisableUsingServicePointManagerSecurityProtocols=false;Switch.System.Net.DontEnableSchUseStrongCrypto=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="79728-107">スコープ</span><span class="sxs-lookup"><span data-stu-id="79728-107">Scope</span></span>|<span data-ttu-id="79728-108">エッジ</span><span class="sxs-lookup"><span data-stu-id="79728-108">Edge</span></span>|
|<span data-ttu-id="79728-109">Version</span><span class="sxs-lookup"><span data-stu-id="79728-109">Version</span></span>|<span data-ttu-id="79728-110">4.7</span><span class="sxs-lookup"><span data-stu-id="79728-110">4.7</span></span>|
|<span data-ttu-id="79728-111">型</span><span class="sxs-lookup"><span data-stu-id="79728-111">Type</span></span>|<span data-ttu-id="79728-112">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="79728-112">Retargeting</span></span>|
