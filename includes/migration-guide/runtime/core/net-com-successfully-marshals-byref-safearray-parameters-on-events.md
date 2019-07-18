---
ms.openlocfilehash: 2f4f92c8615b328caee2ad0b90028c76048026f4
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2019
ms.locfileid: "67802654"
---
### <a name="net-com-successfully-marshals-byref-safearray-parameters-on-events"></a><span data-ttu-id="7ae45-101">.NET COM では、イベント時に ByRef SafeArray パラメーターを正常にマーシャリングします。</span><span class="sxs-lookup"><span data-stu-id="7ae45-101">.NET COM successfully marshals ByRef SafeArray parameters on events</span></span>

|   |   |
|---|---|
|<span data-ttu-id="7ae45-102">説明</span><span class="sxs-lookup"><span data-stu-id="7ae45-102">Details</span></span>|<span data-ttu-id="7ae45-103">.NET Framework 4.7.2 以前のバージョンでは、COM イベントでの ByRef [SafeArray](https://docs.microsoft.com/en-us/windows/desktop/api/oaidl/ns-oaidl-safearray) パラメータ―は、ネイティブ コードに戻ってマーシャリングすることはできません。</span><span class="sxs-lookup"><span data-stu-id="7ae45-103">In the .NET Framework 4.7.2 and earlier versions, a ByRef [SafeArray](https://docs.microsoft.com/en-us/windows/desktop/api/oaidl/ns-oaidl-safearray) parameter on a COM event would fail to marshal back to native code.</span></span>  <span data-ttu-id="7ae45-104">この変更により、[SafeArray](https://docs.microsoft.com/en-us/windows/desktop/api/oaidl/ns-oaidl-safearray) が正常にマーシャリングされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="7ae45-104">With this change the [SafeArray](https://docs.microsoft.com/en-us/windows/desktop/api/oaidl/ns-oaidl-safearray) is now marshalled successfully.</span></span><ul><li><span data-ttu-id="7ae45-105">[ x ] 後方互換</span><span class="sxs-lookup"><span data-stu-id="7ae45-105">[ x ] Quirked</span></span></li></ul>|
|<span data-ttu-id="7ae45-106">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="7ae45-106">Suggestion</span></span>|<span data-ttu-id="7ae45-107">COM イベント時に ByRef SafeArray パラメーターを正常にマーシャリングすると、実行が中断されてしまう場合は、アプリケーション構成に次の構成スイッチを追加して、このコードを無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="7ae45-107">If properly marshalling ByRef SafeArray parameters on COM Events breaks execution, you can disable this code by adding the following configuration switch to your application config:</span></span><pre><code class="lang-xml">&lt;appSettings&gt;&#13;&#10;&lt;add key=&quot;Switch.System.Runtime.InteropServices.DoNotMarshalOutByrefSafeArrayOnInvoke&quot; value=&quot;true&quot; /&gt;&#13;&#10;&lt;/appSettings&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="7ae45-108">スコープ</span><span class="sxs-lookup"><span data-stu-id="7ae45-108">Scope</span></span>|<span data-ttu-id="7ae45-109">マイナー</span><span class="sxs-lookup"><span data-stu-id="7ae45-109">Minor</span></span>|
|<span data-ttu-id="7ae45-110">Version</span><span class="sxs-lookup"><span data-stu-id="7ae45-110">Version</span></span>|<span data-ttu-id="7ae45-111">4.8</span><span class="sxs-lookup"><span data-stu-id="7ae45-111">4.8</span></span>|
|<span data-ttu-id="7ae45-112">型</span><span class="sxs-lookup"><span data-stu-id="7ae45-112">Type</span></span>|<span data-ttu-id="7ae45-113">ランタイム</span><span class="sxs-lookup"><span data-stu-id="7ae45-113">Runtime</span></span>|

