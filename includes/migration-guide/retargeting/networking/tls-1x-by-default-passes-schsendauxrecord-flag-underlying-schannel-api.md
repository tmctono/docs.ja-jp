---
ms.openlocfilehash: e7f690030a5cb5605645f1ca42a6f08dcdd214f5
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615700"
---
### <a name="tls-1x-by-default-passes-the-sch_send_aux_record-flag-to-the-underlying-schannel-api"></a><span data-ttu-id="0c419-101">TLS 1.x は既定で SCH_SEND_AUX_RECORD フラグを基になる SCHANNEL API に渡す</span><span class="sxs-lookup"><span data-stu-id="0c419-101">TLS 1.x by default passes the SCH_SEND_AUX_RECORD flag to the underlying SCHANNEL API</span></span>

#### <a name="details"></a><span data-ttu-id="0c419-102">説明</span><span class="sxs-lookup"><span data-stu-id="0c419-102">Details</span></span>

<span data-ttu-id="0c419-103">TLS 1.x を使用するとき、.NET Framework は基になる Windows SCHANNEL API に依存します。</span><span class="sxs-lookup"><span data-stu-id="0c419-103">When using TLS 1.x, the .NET Framework relies on the underlying Windows SCHANNEL API.</span></span> <span data-ttu-id="0c419-104">.NET Framework 4.6 以降、[SCH_SEND_AUX_RECORD](https://docs.microsoft.com/windows/win32/api/schannel/ns-schannel-schannel_cred) フラグは既定で SCHANNEL に渡されます。</span><span class="sxs-lookup"><span data-stu-id="0c419-104">Starting with .NET Framework 4.6, the [SCH_SEND_AUX_RECORD](https://docs.microsoft.com/windows/win32/api/schannel/ns-schannel-schannel_cred) flag is passed by default to SCHANNEL.</span></span> <span data-ttu-id="0c419-105">SCHANNEL によって、暗号化するデータが 2 つの別個のレコードに分割されます。1 つ目のレコードはシングル バイトで、2 つ目のレコードは <em>n</em>-1 バイトです。その結果、まれに、データがシングル レコードに置かれていると想定する既存サーバーとクライアントの間の通信が途切れることがあります。</span><span class="sxs-lookup"><span data-stu-id="0c419-105">This causes SCHANNEL to split data to be encrypted into two separate records, the first as a single byte and the second as <em>n</em>-1 bytes.In rare cases, this breaks communication between clients and existing servers that make the assumption that the data resides in a single record.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="0c419-106">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="0c419-106">Suggestion</span></span>

<span data-ttu-id="0c419-107">この変更によって既存サーバーとの接続が途切れる場合、[SCH_SEND_AUX_RECORD](https://docs.microsoft.com/windows/win32/api/schannel/ns-schannel-schannel_cred) フラグの送信を無効にし、アプリ構成ファイルの [<](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) セクションで次のスイッチを [<](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) 要素に追加することで、データを別個のレコードに分割しない、以前の動作に復元できます。</span><span class="sxs-lookup"><span data-stu-id="0c419-107">If this change breaks communication with an existing server, you can disable sending the [SCH_SEND_AUX_RECORD](https://docs.microsoft.com/windows/win32/api/schannel/ns-schannel-schannel_cred) flag and restore the previous behavior of not splitting data into separate records by adding the following switch to the [<](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [<](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of your app configuration file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Net.DontEnableSchSendAuxRecord=true" />
</runtime>
```

> [!IMPORTANT]
> <span data-ttu-id="0c419-108">この設定は下位互換性のためにのみ提供されます。</span><span class="sxs-lookup"><span data-stu-id="0c419-108">This setting is provided for backward compatibility only.</span></span> <span data-ttu-id="0c419-109">それ以外の目的での使用はお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="0c419-109">Its use is otherwise not recommended.</span></span>

| <span data-ttu-id="0c419-110">名前</span><span class="sxs-lookup"><span data-stu-id="0c419-110">Name</span></span>    | <span data-ttu-id="0c419-111">値</span><span class="sxs-lookup"><span data-stu-id="0c419-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="0c419-112">スコープ</span><span class="sxs-lookup"><span data-stu-id="0c419-112">Scope</span></span>   | <span data-ttu-id="0c419-113">エッジ</span><span class="sxs-lookup"><span data-stu-id="0c419-113">Edge</span></span>        |
| <span data-ttu-id="0c419-114">バージョン</span><span class="sxs-lookup"><span data-stu-id="0c419-114">Version</span></span> | <span data-ttu-id="0c419-115">4.6</span><span class="sxs-lookup"><span data-stu-id="0c419-115">4.6</span></span>         |
| <span data-ttu-id="0c419-116">種類</span><span class="sxs-lookup"><span data-stu-id="0c419-116">Type</span></span>    | <span data-ttu-id="0c419-117">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="0c419-117">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="0c419-118">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="0c419-118">Affected APIs</span></span>

- <xref:System.Net.Security.SslStream?displayProperty=nameWithType>
- <xref:System.Net.ServicePointManager?displayProperty=nameWithType>
- <xref:System.Net.Http.HttpClient?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.HttpWebRequest?displayProperty=nameWithType>
- <xref:System.Net.FtpWebRequest?displayProperty=nameWithType>
