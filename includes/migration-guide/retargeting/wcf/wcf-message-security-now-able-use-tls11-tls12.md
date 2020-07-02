---
ms.openlocfilehash: c646372104457e8bc5d418744847f3ee771c8d8b
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614807"
---
### <a name="wcf-message-security-now-is-able-to-use-tls11-and-tls12"></a><span data-ttu-id="b7bd6-101">WCF メッセージ セキュリティで TLS1.1 と TLS1.2 が使用可能に</span><span class="sxs-lookup"><span data-stu-id="b7bd6-101">WCF message security now is able to use TLS1.1 and TLS1.2</span></span>

#### <a name="details"></a><span data-ttu-id="b7bd6-102">説明</span><span class="sxs-lookup"><span data-stu-id="b7bd6-102">Details</span></span>

<span data-ttu-id="b7bd6-103">.NET Framework 4.7 以降、顧客はアプリケーション構成設定を介し、SSL3.0 と TLS1.0 に加え、WCF メッセージ セキュリティで TLS1.1 または TLS1.2 を構成できます。</span><span class="sxs-lookup"><span data-stu-id="b7bd6-103">Starting in the .NET Framework 4.7, customers can configure either TLS1.1 or TLS1.2 in WCF message security in addition to SSL3.0 and TLS1.0 through application configuration settings.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="b7bd6-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="b7bd6-104">Suggestion</span></span>

<span data-ttu-id="b7bd6-105">.NET Framework 4.7 では、WCF メッセージ セキュリティの TLS1.1 と TLS1.2 のサポートは既定で無効になっています。</span><span class="sxs-lookup"><span data-stu-id="b7bd6-105">In the .NET Framework 4.7, support for TLS1.1 and TLS1.2 in WCF message security is disabled by default.</span></span> <span data-ttu-id="b7bd6-106">app.config または web.config ファイルの `<runtime>` セクションに次の行を追加することで有効にできます。</span><span class="sxs-lookup"><span data-stu-id="b7bd6-106">You can enable it by adding the following line to the `<runtime>` section of the app.config or web.config file:</span></span>

```xml
<runtime>
<AppContextSwitchOverrides value="Switch.System.ServiceModel.DisableUsingServicePointManagerSecurityProtocols=false;Switch.System.Net.DontEnableSchUseStrongCrypto=false" />
</runtime>
```

| <span data-ttu-id="b7bd6-107">名前</span><span class="sxs-lookup"><span data-stu-id="b7bd6-107">Name</span></span>    | <span data-ttu-id="b7bd6-108">値</span><span class="sxs-lookup"><span data-stu-id="b7bd6-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="b7bd6-109">スコープ</span><span class="sxs-lookup"><span data-stu-id="b7bd6-109">Scope</span></span>   | <span data-ttu-id="b7bd6-110">エッジ</span><span class="sxs-lookup"><span data-stu-id="b7bd6-110">Edge</span></span>        |
| <span data-ttu-id="b7bd6-111">バージョン</span><span class="sxs-lookup"><span data-stu-id="b7bd6-111">Version</span></span> | <span data-ttu-id="b7bd6-112">4.7</span><span class="sxs-lookup"><span data-stu-id="b7bd6-112">4.7</span></span>         |
| <span data-ttu-id="b7bd6-113">種類</span><span class="sxs-lookup"><span data-stu-id="b7bd6-113">Type</span></span>    | <span data-ttu-id="b7bd6-114">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="b7bd6-114">Retargeting</span></span> |
