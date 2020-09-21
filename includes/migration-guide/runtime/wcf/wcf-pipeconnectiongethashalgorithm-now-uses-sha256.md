---
ms.openlocfilehash: 3cf1740565343558a85fdfa68957773468c28231
ms.sourcegitcommit: 261e0c98a111357692b3b63c596edf0cacf72991
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2020
ms.locfileid: "90770768"
---
### <a name="wcf-pipeconnectiongethashalgorithm-now-uses-sha256"></a><span data-ttu-id="473bb-101">WCF PipeConnection.GetHashAlgorithm が SHA256 を使用するようになった</span><span class="sxs-lookup"><span data-stu-id="473bb-101">WCF PipeConnection.GetHashAlgorithm now uses SHA256</span></span>

#### <a name="details"></a><span data-ttu-id="473bb-102">説明</span><span class="sxs-lookup"><span data-stu-id="473bb-102">Details</span></span>

<span data-ttu-id="473bb-103">.NET Framework 4.7.1 以降の Windows Communication Foundation は、SHA256 ハッシュを使用して名前付きパイプ用のランダムな名前を生成します。</span><span class="sxs-lookup"><span data-stu-id="473bb-103">Starting with the .NET Framework 4.7.1, Windows Communication Foundation uses a SHA256 hash to generate random names for named pipes.</span></span> <span data-ttu-id="473bb-104">.NET Framework 4.7 以前のバージョンでは、SHA1 ハッシュを使っていました。</span><span class="sxs-lookup"><span data-stu-id="473bb-104">In the .NET Framework 4.7 and earlier versions, it used a SHA1 hash.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="473bb-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="473bb-105">Suggestion</span></span>

<span data-ttu-id="473bb-106">.NET Framework 4.7.1 以降でこの変更に関する互換性の問題が発生した場合は、次の行を app.config ファイルの `<runtime>` セクションに追加することで、変更を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="473bb-106">If you run into compatibility issue with this change on the .NET Framework 4.7.1 or later, you can opt-out it by adding the following line to the `<runtime>` section of your app.config file:</span></span>

```xml
<configuration>
  <runtime>
    <AppContextSwitchOverrides value="Switch.System.ServiceModel.UseSha1InPipeConnectionGetHashAlgorithm=true" />
  </runtime>
</configuration>

| Name    | Value   |
|:--------|:--------|
| Scope   | Minor   |
| Version | 4.7.1   |
| Type    | Runtime |

#### Affected APIs

Not detectable via API analysis.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
