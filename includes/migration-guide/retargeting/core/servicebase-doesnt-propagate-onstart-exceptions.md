---
ms.openlocfilehash: 519de92ca4201d199941afe6382ddf9fc480fbbd
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614780"
---
### <a name="servicebase-doesnt-propagate-onstart-exceptions"></a><span data-ttu-id="b8cca-101">ServiceBase で OnStart 例外を伝達させない</span><span class="sxs-lookup"><span data-stu-id="b8cca-101">ServiceBase doesn't propagate OnStart exceptions</span></span>

#### <a name="details"></a><span data-ttu-id="b8cca-102">説明</span><span class="sxs-lookup"><span data-stu-id="b8cca-102">Details</span></span>

<span data-ttu-id="b8cca-103">.NET Framework 4.7 以前のバージョンでは、サービス起動時にスローされた例外は <xref:System.ServiceProcess.ServiceBase.Run%2A?displayProperty=nameWithType> の呼び出し元に伝達されません。</span><span class="sxs-lookup"><span data-stu-id="b8cca-103">In the .NET Framework 4.7 and earlier versions, exceptions thrown on service startup are not propagated to the caller of <xref:System.ServiceProcess.ServiceBase.Run%2A?displayProperty=nameWithType>.</span></span><br/><span data-ttu-id="b8cca-104">.NET Framework 4.7.1 を対象とするアプリケーション以降では、起動できなかったサービスに関して、ランタイムによって例外が <xref:System.ServiceProcess.ServiceBase.Run%2A?displayProperty=nameWithType> に伝達されます。</span><span class="sxs-lookup"><span data-stu-id="b8cca-104">Starting with applications that target the .NET Framework 4.7.1, the runtime propagates exceptions to <xref:System.ServiceProcess.ServiceBase.Run%2A?displayProperty=nameWithType> for services that fail to start.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="b8cca-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="b8cca-105">Suggestion</span></span>

<span data-ttu-id="b8cca-106">サービスの起動時、例外が存在する場合、その例外は伝達されます。</span><span class="sxs-lookup"><span data-stu-id="b8cca-106">On service start, if there is an exception, that exception will be propagated.</span></span> <span data-ttu-id="b8cca-107">サービスを起動できなかったとき、診断に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="b8cca-107">This should help diagnose cases where services fail to start.</span></span> <br/><span data-ttu-id="b8cca-108">この動作が望ましくない場合、アプリケーション構成ファイルの &lt;runtime&gt; セクションに次の &lt;AppContextSwitchOverrides&gt; 要素を追加することで無効化できます。</span><span class="sxs-lookup"><span data-stu-id="b8cca-108">If this behavior is undesirable, you can opt out of it by adding the following &lt;AppContextSwitchOverrides&gt; element to the &lt;runtime&gt; section of your application configuration file:</span></span>

```xml
<AppContextSwitchOverrides value="Switch.System.ServiceProcess.DontThrowExceptionsOnStart=true" />
```

<span data-ttu-id="b8cca-109">4.7.1 より前のバージョンを対象とするアプリケーションでこの動作を望む場合、アプリケーション構成ファイルの &lt;runtime&gt; セクションに次の &lt;AppContextSwitchOverrides&gt; 要素を追加してください。</span><span class="sxs-lookup"><span data-stu-id="b8cca-109">If your application targets an earlier version than 4.7.1 but you want to have this behavior, add the following &lt;AppContextSwitchOverrides&gt; element to the &lt;runtime&gt; section of your application configuration file:</span></span>

```xml
<AppContextSwitchOverrides value="Switch.System.ServiceProcess.DontThrowExceptionsOnStart=false" />
```

| <span data-ttu-id="b8cca-110">名前</span><span class="sxs-lookup"><span data-stu-id="b8cca-110">Name</span></span>    | <span data-ttu-id="b8cca-111">値</span><span class="sxs-lookup"><span data-stu-id="b8cca-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="b8cca-112">スコープ</span><span class="sxs-lookup"><span data-stu-id="b8cca-112">Scope</span></span>   | <span data-ttu-id="b8cca-113">マイナー</span><span class="sxs-lookup"><span data-stu-id="b8cca-113">Minor</span></span>       |
| <span data-ttu-id="b8cca-114">バージョン</span><span class="sxs-lookup"><span data-stu-id="b8cca-114">Version</span></span> | <span data-ttu-id="b8cca-115">4.7.1</span><span class="sxs-lookup"><span data-stu-id="b8cca-115">4.7.1</span></span>       |
| <span data-ttu-id="b8cca-116">種類</span><span class="sxs-lookup"><span data-stu-id="b8cca-116">Type</span></span>    | <span data-ttu-id="b8cca-117">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="b8cca-117">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="b8cca-118">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="b8cca-118">Affected APIs</span></span>

- <xref:System.ServiceProcess.ServiceBase.Run(System.ServiceProcess.ServiceBase)?displayProperty=nameWithType>
- <xref:System.ServiceProcess.ServiceBase.Run(System.ServiceProcess.ServiceBase[])?displayProperty=nameWithType>
