---
ms.openlocfilehash: 1907c9b82c9685899d328f67da8001c0fa4fb697
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497155"
---
### <a name="net-com-successfully-marshals-byref-safearray-parameters-on-events"></a><span data-ttu-id="8ae77-101">.NET COM では、イベント時に ByRef SafeArray パラメーターを正常にマーシャリングします。</span><span class="sxs-lookup"><span data-stu-id="8ae77-101">.NET COM successfully marshals ByRef SafeArray parameters on events</span></span>

#### <a name="details"></a><span data-ttu-id="8ae77-102">説明</span><span class="sxs-lookup"><span data-stu-id="8ae77-102">Details</span></span>

<span data-ttu-id="8ae77-103">.NET Framework 4.7.2 以前のバージョンでは、COM イベントでの ByRef [SafeArray](https://docs.microsoft.com/windows/desktop/api/oaidl/ns-oaidl-safearray) パラメータ―は、ネイティブ コードに戻ってマーシャリングすることはできません。</span><span class="sxs-lookup"><span data-stu-id="8ae77-103">In the .NET Framework 4.7.2 and earlier versions, a ByRef [SafeArray](https://docs.microsoft.com/windows/desktop/api/oaidl/ns-oaidl-safearray) parameter on a COM event would fail to marshal back to native code.</span></span>  <span data-ttu-id="8ae77-104">この変更により、[SafeArray](https://docs.microsoft.com/windows/desktop/api/oaidl/ns-oaidl-safearray) が正常にマーシャリングされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="8ae77-104">With this change the [SafeArray](https://docs.microsoft.com/windows/desktop/api/oaidl/ns-oaidl-safearray) is now marshalled successfully.</span></span><ul><li><span data-ttu-id="8ae77-105">[ x ] 後方互換</span><span class="sxs-lookup"><span data-stu-id="8ae77-105">[ x ] Quirked</span></span></li></ul>

#### <a name="suggestion"></a><span data-ttu-id="8ae77-106">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="8ae77-106">Suggestion</span></span>

<span data-ttu-id="8ae77-107">COM イベント時に ByRef SafeArray パラメーターを正常にマーシャリングすると、実行が中断されてしまう場合は、アプリケーション構成に次の構成スイッチを追加して、このコードを無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="8ae77-107">If properly marshalling ByRef SafeArray parameters on COM Events breaks execution, you can disable this code by adding the following configuration switch to your application config:</span></span><pre><code class="lang-xml">&lt;appSettings&gt;&#13;&#10;&lt;add key=&quot;Switch.System.Runtime.InteropServices.DoNotMarshalOutByrefSafeArrayOnInvoke&quot; value=&quot;true&quot; /&gt;&#13;&#10;&lt;/appSettings&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="8ae77-108">名前</span><span class="sxs-lookup"><span data-stu-id="8ae77-108">Name</span></span>    | <span data-ttu-id="8ae77-109">[値]</span><span class="sxs-lookup"><span data-stu-id="8ae77-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="8ae77-110">スコープ</span><span class="sxs-lookup"><span data-stu-id="8ae77-110">Scope</span></span>   |<span data-ttu-id="8ae77-111">マイナー</span><span class="sxs-lookup"><span data-stu-id="8ae77-111">Minor</span></span>|
|<span data-ttu-id="8ae77-112">バージョン</span><span class="sxs-lookup"><span data-stu-id="8ae77-112">Version</span></span>|<span data-ttu-id="8ae77-113">4.8</span><span class="sxs-lookup"><span data-stu-id="8ae77-113">4.8</span></span>|
|<span data-ttu-id="8ae77-114">種類</span><span class="sxs-lookup"><span data-stu-id="8ae77-114">Type</span></span>|<span data-ttu-id="8ae77-115">ランタイム</span><span class="sxs-lookup"><span data-stu-id="8ae77-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="8ae77-116">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="8ae77-116">Affected APIs</span></span>

<span data-ttu-id="8ae77-117">API 分析では検出できません。</span><span class="sxs-lookup"><span data-stu-id="8ae77-117">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
