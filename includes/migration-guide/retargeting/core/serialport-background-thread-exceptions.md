---
ms.openlocfilehash: e66a5c2a33a4ab5cf35013c1843936ffd01f90a2
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614745"
---
### <a name="serialport-background-thread-exceptions"></a><span data-ttu-id="30b94-101">SerialPort バックグラウンド スレッドの例外</span><span class="sxs-lookup"><span data-stu-id="30b94-101">SerialPort background thread exceptions</span></span>

#### <a name="details"></a><span data-ttu-id="30b94-102">説明</span><span class="sxs-lookup"><span data-stu-id="30b94-102">Details</span></span>

<span data-ttu-id="30b94-103">OS 例外がスローされたとき、<xref:System.IO.Ports.SerialPort> ストリームで作成されたバックグラウンド スレッドによってプロセスが終了することがなくなりました。</span><span class="sxs-lookup"><span data-stu-id="30b94-103">Background threads created with <xref:System.IO.Ports.SerialPort> streams no longer terminate the process when OS exceptions are thrown.</span></span> <br/><span data-ttu-id="30b94-104">.NET Framework 4.7 以前のバージョンを対象とするアプリケーションでは、<xref:System.IO.Ports.SerialPort> ストリームで作成されたバックグラウンド スレッドでオペレーティング システム例外がスローされたとき、プロセスが終了します。</span><span class="sxs-lookup"><span data-stu-id="30b94-104">In applications that target the .NET Framework 4.7 and earlier versions, a process is terminated when an operating system exception is thrown on a background thread created with a <xref:System.IO.Ports.SerialPort> stream.</span></span> <br/><span data-ttu-id="30b94-105">.NET Framework 4.7.1 以降のバージョンを対象とするアプリケーションでは、バックグラウンド スレッドはアクティブなシリアル ポートに関連付けられている OS イベントを待ち、シリアル ポートが急に削除されるなどした場合にクラッシュすることがあります。</span><span class="sxs-lookup"><span data-stu-id="30b94-105">In applications that target the .NET Framework 4.7.1 or a later version, background threads wait for OS events related to the active serial port and could crash in some cases, such as sudden removal of the serial port.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="30b94-106">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="30b94-106">Suggestion</span></span>

<span data-ttu-id="30b94-107">.NET Framework 4.7.1 を対象とするアプリケーションの場合、例外処理が望ましくないときは、`app.config` ファイルの `<runtime>` セクションに次を追加することで例外処理を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="30b94-107">For apps that target the .NET Framework 4.7.1, you can opt out of the exception handling if it is not desirable by adding the following to the `<runtime>` section of your `app.config` file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.Ports.DoNotCatchSerialStreamThreadExceptions=true" />
</runtime>
```

<span data-ttu-id="30b94-108">以前のバージョンの .NET Framework を対象とするが、.NET Framework 4.7.1 以降で実行するアプリの場合、`app.config` ファイルの `<runtime>` セクションに次を追加することで例外処理を選択できます。</span><span class="sxs-lookup"><span data-stu-id="30b94-108">For apps that target earlier versions of the .NET Framework but run on the .NET Framework 4.7.1 or later, you can opt in to the exception handling by adding the following to the `<runtime>` section of your `app.config` file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.Ports.DoNotCatchSerialStreamThreadExceptions=false" />
</runtime>
```

| <span data-ttu-id="30b94-109">名前</span><span class="sxs-lookup"><span data-stu-id="30b94-109">Name</span></span>    | <span data-ttu-id="30b94-110">値</span><span class="sxs-lookup"><span data-stu-id="30b94-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="30b94-111">スコープ</span><span class="sxs-lookup"><span data-stu-id="30b94-111">Scope</span></span>   | <span data-ttu-id="30b94-112">マイナー</span><span class="sxs-lookup"><span data-stu-id="30b94-112">Minor</span></span>       |
| <span data-ttu-id="30b94-113">バージョン</span><span class="sxs-lookup"><span data-stu-id="30b94-113">Version</span></span> | <span data-ttu-id="30b94-114">4.7.1</span><span class="sxs-lookup"><span data-stu-id="30b94-114">4.7.1</span></span>       |
| <span data-ttu-id="30b94-115">種類</span><span class="sxs-lookup"><span data-stu-id="30b94-115">Type</span></span>    | <span data-ttu-id="30b94-116">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="30b94-116">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="30b94-117">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="30b94-117">Affected APIs</span></span>

- <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType>
