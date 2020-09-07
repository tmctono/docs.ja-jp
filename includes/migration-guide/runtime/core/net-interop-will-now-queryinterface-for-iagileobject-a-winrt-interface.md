---
ms.openlocfilehash: 65fa5d8629ce8e426cf1623590a056e5cad0b91f
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497669"
---
### <a name="net-interop-will-now-queryinterface-for-iagileobject-a-winrt-interface"></a><span data-ttu-id="75715-101">.NET 相互運用で IAgileObject に対して QueryInterface が呼び出されるようになる (WinRT インターフェイス)</span><span class="sxs-lookup"><span data-stu-id="75715-101">.NET Interop will now QueryInterface for IAgileObject (a WinRT interface)</span></span>

#### <a name="details"></a><span data-ttu-id="75715-102">説明</span><span class="sxs-lookup"><span data-stu-id="75715-102">Details</span></span>

<span data-ttu-id="75715-103">.NET デリゲートで WinRT イベントを使用する場合、.NET Framework 4.8 以降では、Windows で IAgileObject に対して QI が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="75715-103">When using a WinRT event with a .NET delegate, Windows will QI for IAgileObject starting with the .NET Framework 4.8.</span></span>  <span data-ttu-id="75715-104">.NET Framework の以前のバージョンでは、ランタイムでその QI が失敗し、イベントをサブスクライブできませんでした。</span><span class="sxs-lookup"><span data-stu-id="75715-104">In previous versions of the .NET Framework, the runtime would fail that QI, and the event could not be subscribed.</span></span><ul><li><span data-ttu-id="75715-105">[ x ] 後方互換</span><span class="sxs-lookup"><span data-stu-id="75715-105">[ x ] Quirked</span></span></li></ul>

#### <a name="suggestion"></a><span data-ttu-id="75715-106">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="75715-106">Suggestion</span></span>

<span data-ttu-id="75715-107">IAgileObject に対して QI を有効にすると実行が中断される場合は、次の構成を設定し、このコードを無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="75715-107">If enabling the QI for IAgileObject breaks execution, you can disable this code by setting the following configuration.</span></span> <h4><span data-ttu-id="75715-108">方法 1:環境変数</span><span class="sxs-lookup"><span data-stu-id="75715-108">Method 1: Environment variable</span></span></h4> <span data-ttu-id="75715-109">環境変数を COMPLUS_DisableCCWSupportIAgileObject=1 に設定します。この方法は、この環境変数を継承するすべての環境に影響します。</span><span class="sxs-lookup"><span data-stu-id="75715-109">Set the following environment variable:COMPLUS_DisableCCWSupportIAgileObject=1This method affects any environment that inherits this environment variable.</span></span> <span data-ttu-id="75715-110">この場合、コンソール セッションが 1 つのみになる可能性があります。あるいは、環境変数をグローバルに設定した場合、コンピューター全体に影響する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="75715-110">This might be just a single console session, or it might affect the entire machine if you set the environment variable globally.</span></span> <span data-ttu-id="75715-111">環境変数の名前では大文字と小文字は区別されません。</span><span class="sxs-lookup"><span data-stu-id="75715-111">The environment variable name is not case-sensitive.</span></span> <h4><span data-ttu-id="75715-112">方法 2:レジストリ</span><span class="sxs-lookup"><span data-stu-id="75715-112">Method 2: Registry</span></span></h4> <span data-ttu-id="75715-113">レジストリ エディター (regedit.exe) を使用して、サブキーの HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft.NETFramework または HKEY_CURRENT_USER\SOFTWARE\Microsoft.NETFramework を見つけます。その後、次のように追加します。値の名前:DisableCCWSupportIAgileObject 種類:DWORD (32 ビット) 値 (REG_WORD ともいう) 値:1。Windows REG.EXE ツールを使用して、コマンド ラインまたはスクリプト環境から、この値を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="75715-113">Using Registry Editor (regedit.exe), find either of the following subkeys:HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft.NETFramework HKEY_CURRENT_USER\SOFTWARE\Microsoft.NETFrameworkThen add the following:Value name: DisableCCWSupportIAgileObject Type: DWORD (32-bit) Value (also called REG_WORD) Value: 1You can use the Windows REG.EXE tool to add this value from a command-line or scripting environment.</span></span> <span data-ttu-id="75715-114">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="75715-114">For example:</span></span><pre><code class="lang-console">reg add HKLM\SOFTWARE\Microsoft\.NETFramework /v DisableCCWSupportIAgileObject /t REG_DWORD /d 1&#13;&#10;</code></pre><span data-ttu-id="75715-115">ここでは、<code>HKLM</code> が <code>HKEY_LOCAL_MACHINE</code> の代わりに使用されています。</span><span class="sxs-lookup"><span data-stu-id="75715-115">In this case, <code>HKLM</code> is used instead of <code>HKEY_LOCAL_MACHINE</code>.</span></span> <span data-ttu-id="75715-116">この構文のヘルプを表示するには、<code>reg add /?</code> を使用します。</span><span class="sxs-lookup"><span data-stu-id="75715-116">Use <code>reg add /?</code> to see help on this syntax.</span></span> <span data-ttu-id="75715-117">レジストリ値の名前では大文字と小文字は区別されません。</span><span class="sxs-lookup"><span data-stu-id="75715-117">The registry value name is not case-sensitive.</span></span>

| <span data-ttu-id="75715-118">名前</span><span class="sxs-lookup"><span data-stu-id="75715-118">Name</span></span>    | <span data-ttu-id="75715-119">[値]</span><span class="sxs-lookup"><span data-stu-id="75715-119">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="75715-120">スコープ</span><span class="sxs-lookup"><span data-stu-id="75715-120">Scope</span></span>   |<span data-ttu-id="75715-121">エッジ</span><span class="sxs-lookup"><span data-stu-id="75715-121">Edge</span></span>|
|<span data-ttu-id="75715-122">バージョン</span><span class="sxs-lookup"><span data-stu-id="75715-122">Version</span></span>|<span data-ttu-id="75715-123">4.8</span><span class="sxs-lookup"><span data-stu-id="75715-123">4.8</span></span>|
|<span data-ttu-id="75715-124">種類</span><span class="sxs-lookup"><span data-stu-id="75715-124">Type</span></span>|<span data-ttu-id="75715-125">ランタイム</span><span class="sxs-lookup"><span data-stu-id="75715-125">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="75715-126">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="75715-126">Affected APIs</span></span>

<span data-ttu-id="75715-127">API 分析では検出できません。</span><span class="sxs-lookup"><span data-stu-id="75715-127">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
