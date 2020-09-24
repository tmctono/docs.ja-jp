---
ms.openlocfilehash: 7c0227980aa5d90f3788783088bcd7cd9509ed66
ms.sourcegitcommit: 261e0c98a111357692b3b63c596edf0cacf72991
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2020
ms.locfileid: "90770899"
---
### <a name="wcf-msmqsecurehashalgorithm-default-value-is-now-sha256"></a><span data-ttu-id="8f339-101">WCF MsmqSecureHashAlgorithm の既定値が SHA256 になった</span><span class="sxs-lookup"><span data-stu-id="8f339-101">WCF MsmqSecureHashAlgorithm default value is now SHA256</span></span>

#### <a name="details"></a><span data-ttu-id="8f339-102">説明</span><span class="sxs-lookup"><span data-stu-id="8f339-102">Details</span></span>

<span data-ttu-id="8f339-103">.NET Framework 4.7.1 以降では、Msmq メッセージの WCF での既定のメッセージ署名アルゴリズムは SHA256 です。</span><span class="sxs-lookup"><span data-stu-id="8f339-103">Starting with the .NET Framework 4.7.1, the default message signing algorithm in WCF for Msmq messages is SHA256.</span></span> <span data-ttu-id="8f339-104">.NET Framework 4.7 以前のバージョンでは、既定のメッセージ署名アルゴリズムは SHA1 です。</span><span class="sxs-lookup"><span data-stu-id="8f339-104">In the .NET Framework 4.7 and earlier versions, the default message signing algorithm is SHA1.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="8f339-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="8f339-105">Suggestion</span></span>

<span data-ttu-id="8f339-106">.NET Framework 4.7.1 以降でこの変更に関する互換性の問題が発生した場合は、次の行を app.config ファイルの `<runtime>` セクションに追加することで、変更を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="8f339-106">If you run into compatibility issues with this change on the .NET Framework 4.7.1 or later, you can opt-out the change by adding the following line to the `<runtime>` section of your app.config file:</span></span>

```xml
<configuration>
  <runtime>
    <AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.UseSha1InMsmqEncryptionAlgorithm=true&quot; />
  </runtime>
</configuration>
```

| <span data-ttu-id="8f339-107">名前</span><span class="sxs-lookup"><span data-stu-id="8f339-107">Name</span></span>    | <span data-ttu-id="8f339-108">値</span><span class="sxs-lookup"><span data-stu-id="8f339-108">Value</span></span>   |
|:--------|:--------|
| <span data-ttu-id="8f339-109">スコープ</span><span class="sxs-lookup"><span data-stu-id="8f339-109">Scope</span></span>   | <span data-ttu-id="8f339-110">マイナー</span><span class="sxs-lookup"><span data-stu-id="8f339-110">Minor</span></span>   |
| <span data-ttu-id="8f339-111">バージョン</span><span class="sxs-lookup"><span data-stu-id="8f339-111">Version</span></span> | <span data-ttu-id="8f339-112">4.7.1</span><span class="sxs-lookup"><span data-stu-id="8f339-112">4.7.1</span></span>   |
| <span data-ttu-id="8f339-113">種類</span><span class="sxs-lookup"><span data-stu-id="8f339-113">Type</span></span>    | <span data-ttu-id="8f339-114">ランタイム</span><span class="sxs-lookup"><span data-stu-id="8f339-114">Runtime</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="8f339-115">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="8f339-115">Affected APIs</span></span>

<span data-ttu-id="8f339-116">API 分析では検出できません。</span><span class="sxs-lookup"><span data-stu-id="8f339-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
