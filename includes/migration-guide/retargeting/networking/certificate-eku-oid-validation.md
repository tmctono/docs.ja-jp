---
ms.openlocfilehash: c996dafcf65b1fd428be908be346de603ead6e0b
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615681"
---
### <a name="certificate-eku-oid-validation"></a><span data-ttu-id="25d2f-101">証明書 EKU OID の検証</span><span class="sxs-lookup"><span data-stu-id="25d2f-101">Certificate EKU OID validation</span></span>

#### <a name="details"></a><span data-ttu-id="25d2f-102">説明</span><span class="sxs-lookup"><span data-stu-id="25d2f-102">Details</span></span>

<span data-ttu-id="25d2f-103">.NET Framework 4.6 以降、<xref:System.Net.Security.SslStream> または <xref:System.Net.ServicePointManager> クラスで EKU (拡張キー使用法) の OID (オブジェクト識別子) が検証されます。</span><span class="sxs-lookup"><span data-stu-id="25d2f-103">Starting with .NET Framework 4.6, the <xref:System.Net.Security.SslStream> or <xref:System.Net.ServicePointManager> classes perform enhanced key use (EKU) object identifier (OID) validation.</span></span> <span data-ttu-id="25d2f-104">EKU (拡張キー使用法) 拡張は、キーを使用するアプリケーションを示すオブジェクト識別子 (OID) の集まりです。</span><span class="sxs-lookup"><span data-stu-id="25d2f-104">An enhanced key usage (EKU) extension is a collection of object identifiers (OIDs) that indicate the applications that use the key.</span></span> <span data-ttu-id="25d2f-105">EKU OID 検証では、リモート証明書に意図している目的にかなった OID が与えられるようにリモート証明書コールバックが使用されます。</span><span class="sxs-lookup"><span data-stu-id="25d2f-105">EKU OID validation uses remote certificate callbacks to ensure that the remote certificate has the correct OIDs for the intended purpose.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="25d2f-106">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="25d2f-106">Suggestion</span></span>

<span data-ttu-id="25d2f-107">この変更が望ましくない場合は、アプリ構成ファイルの [\`](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) の [\<AppContextSwitchOverrides>](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) に次のスイッチを追加することで、証明書 EKU OID の検証を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="25d2f-107">If this change is undesirable, you can disable certificate EKU OID validation by adding the following switch to the [\<AppContextSwitchOverrides>](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) in the [\`](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) of your app configuration file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Net.DontCheckCertificateEKUs=true" />
</runtime>
```

> [!IMPORTANT]
> <span data-ttu-id="25d2f-108">この設定は下位互換性のためにのみ提供されます。</span><span class="sxs-lookup"><span data-stu-id="25d2f-108">This setting is provided for backward compatibility only.</span></span> <span data-ttu-id="25d2f-109">それ以外の目的での使用はお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="25d2f-109">Its use is otherwise not recommended.</span></span>

| <span data-ttu-id="25d2f-110">名前</span><span class="sxs-lookup"><span data-stu-id="25d2f-110">Name</span></span>    | <span data-ttu-id="25d2f-111">[値]</span><span class="sxs-lookup"><span data-stu-id="25d2f-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="25d2f-112">スコープ</span><span class="sxs-lookup"><span data-stu-id="25d2f-112">Scope</span></span>   | <span data-ttu-id="25d2f-113">マイナー</span><span class="sxs-lookup"><span data-stu-id="25d2f-113">Minor</span></span>       |
| <span data-ttu-id="25d2f-114">バージョン</span><span class="sxs-lookup"><span data-stu-id="25d2f-114">Version</span></span> | <span data-ttu-id="25d2f-115">4.6</span><span class="sxs-lookup"><span data-stu-id="25d2f-115">4.6</span></span>         |
| <span data-ttu-id="25d2f-116">種類</span><span class="sxs-lookup"><span data-stu-id="25d2f-116">Type</span></span>    | <span data-ttu-id="25d2f-117">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="25d2f-117">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="25d2f-118">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="25d2f-118">Affected APIs</span></span>

- <xref:System.Net.Security.SslStream?displayProperty=nameWithType>
- <xref:System.Net.ServicePointManager?displayProperty=nameWithType>
- <xref:System.Net.Http.HttpClient?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.HttpWebRequest?displayProperty=nameWithType>
- <xref:System.Net.FtpWebRequest?displayProperty=nameWithType>
