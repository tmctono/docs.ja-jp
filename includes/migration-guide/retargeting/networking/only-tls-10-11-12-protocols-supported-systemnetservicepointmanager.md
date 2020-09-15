---
ms.openlocfilehash: 87dc93ece10eaedbfbabddb5f857d0bcd12e05c4
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615695"
---
### <a name="only-tls-10-11-and-12-protocols-supported-in-systemnetservicepointmanager-and-systemnetsecuritysslstream"></a><span data-ttu-id="bf9b1-101">System.Net.ServicePointManager と System.Net.Security.SslStream で TLS 1.0、1.1、1.2 プロトコルのみサポート</span><span class="sxs-lookup"><span data-stu-id="bf9b1-101">Only Tls 1.0, 1.1 and 1.2 protocols supported in System.Net.ServicePointManager and System.Net.Security.SslStream</span></span>

#### <a name="details"></a><span data-ttu-id="bf9b1-102">説明</span><span class="sxs-lookup"><span data-stu-id="bf9b1-102">Details</span></span>

<span data-ttu-id="bf9b1-103">.NET Framework 4.6 から、<xref:System.Net.ServicePointManager> クラスと <xref:System.Net.Security.SslStream> クラスには、Tls1.0、Tls1.1、Tls 1.2 という 3 つのプロトコルのいずれかを使用することのみが許可されます。</span><span class="sxs-lookup"><span data-stu-id="bf9b1-103">Starting with the .NET Framework 4.6, the <xref:System.Net.ServicePointManager> and <xref:System.Net.Security.SslStream> classes are only allowed to use one of the following three protocols: Tls1.0, Tls1.1, or Tls1.2.</span></span> <span data-ttu-id="bf9b1-104">SSL3.0 プロトコルと RC4 の暗号化はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="bf9b1-104">The SSL3.0 protocol and RC4 cipher are not supported.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="bf9b1-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="bf9b1-105">Suggestion</span></span>

<span data-ttu-id="bf9b1-106">推奨される軽減策はサーバー側のアプリを Tls1.0、Tls1.1、または Tls1.2 にアップグレードすることです。</span><span class="sxs-lookup"><span data-stu-id="bf9b1-106">The recommended mitigation is to upgrade the sever-side app to Tls1.0, Tls1.1, or Tls1.2.</span></span> <span data-ttu-id="bf9b1-107">これが現実的でない場合、またはクライアント アプリが破損している場合は、次の 2 つの方法のいずれかにより、<xref:System.AppContext?displayProperty=fullName> クラスを使用してこの機能を除外できます。</span><span class="sxs-lookup"><span data-stu-id="bf9b1-107">If this is not feasible, or if client apps are broken, the <xref:System.AppContext?displayProperty=fullName> class can be used to opt out of this feature in either of two ways:</span></span>

- <span data-ttu-id="bf9b1-108">プログラムで <xref:System.AppContext?displayProperty=fullName> の互換性スイッチを設定する (説明は[こちら](https://devblogs.microsoft.com/dotnet/net-announcements-at-build-2015/#dotnet46)にあります)。</span><span class="sxs-lookup"><span data-stu-id="bf9b1-108">By programmatically setting compat switches on the <xref:System.AppContext?displayProperty=fullName>, as explained [here](https://devblogs.microsoft.com/dotnet/net-announcements-at-build-2015/#dotnet46).</span></span>
- <span data-ttu-id="bf9b1-109">app.config ファイルの `<runtime>` セクションに以下の行を追加する。</span><span class="sxs-lookup"><span data-stu-id="bf9b1-109">By adding the following line to the `<runtime>` section of the app.config file:</span></span>

```xml
<AppContextSwitchOverrides value="Switch.System.Net.DontEnableSchUseStrongCrypto=true"/>
```

| <span data-ttu-id="bf9b1-110">名前</span><span class="sxs-lookup"><span data-stu-id="bf9b1-110">Name</span></span>    | <span data-ttu-id="bf9b1-111">値</span><span class="sxs-lookup"><span data-stu-id="bf9b1-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="bf9b1-112">スコープ</span><span class="sxs-lookup"><span data-stu-id="bf9b1-112">Scope</span></span>   | <span data-ttu-id="bf9b1-113">マイナー</span><span class="sxs-lookup"><span data-stu-id="bf9b1-113">Minor</span></span>       |
| <span data-ttu-id="bf9b1-114">バージョン</span><span class="sxs-lookup"><span data-stu-id="bf9b1-114">Version</span></span> | <span data-ttu-id="bf9b1-115">4.6</span><span class="sxs-lookup"><span data-stu-id="bf9b1-115">4.6</span></span>         |
| <span data-ttu-id="bf9b1-116">種類</span><span class="sxs-lookup"><span data-stu-id="bf9b1-116">Type</span></span>    | <span data-ttu-id="bf9b1-117">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="bf9b1-117">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="bf9b1-118">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="bf9b1-118">Affected APIs</span></span>

- <xref:System.Net.SecurityProtocolType.Ssl3?displayProperty=nameWithType>
- <xref:System.Security.Authentication.SslProtocols.None?displayProperty=nameWithType>
- <xref:System.Security.Authentication.SslProtocols.Ssl2?displayProperty=nameWithType>
- <xref:System.Security.Authentication.SslProtocols.Ssl3?displayProperty=nameWithType>
