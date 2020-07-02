---
ms.openlocfilehash: 4b5c886ad35afbbf0a68e03b3174ab9ea1f5524f
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614768"
---
### <a name="cspparametersparentwindowhandle-now-expects-hwnd-value"></a><span data-ttu-id="300e8-101">CspParameters.ParentWindowHandle が HWND 値を受け取るようになる</span><span class="sxs-lookup"><span data-stu-id="300e8-101">CspParameters.ParentWindowHandle now expects HWND value</span></span>

#### <a name="details"></a><span data-ttu-id="300e8-102">説明</span><span class="sxs-lookup"><span data-stu-id="300e8-102">Details</span></span>

<span data-ttu-id="300e8-103">.NET Framework 2.0 で導入された <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle> 値をアプリケーションに使用すると、親ウィンドウのハンドル値を登録できます。これを利用して、キーにアクセスする必要がある UI (PIN プロンプトや同意を求めるダイアログなど) を、指定したウィンドウの子のモーダルとして開くことができます。 .NET Framework 4.7 を対象とするアプリ以降では、Windows フォーム アプリケーションは、次のようなコードを使用して、<xref:System.Security.Cryptography.CspParameters.ParentWindowHandle> プロパティを設定できます。</span><span class="sxs-lookup"><span data-stu-id="300e8-103">The <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle> value, introduced in .NET Framework 2.0, allows an application to register a parent window handle value such that any UI required to access the key (such as a PIN prompt or consent dialog) opens as a modal child to the specified window.Starting with apps that target the .NET Framework 4.7, a Windows Forms application can set the <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle> property with code like the following:</span></span>

```csharp
cspParameters.ParentWindowHandle = form.Handle;
```

<span data-ttu-id="300e8-104">以前のバージョンの .NET Framework では、[HWND](https://docs.microsoft.com/windows/desktop/WinProg/windows-data-types#HWND) 値が置かれているメモリ内の場所を表す <xref:System.IntPtr?displayProperty=fullName> が値として必要でした。</span><span class="sxs-lookup"><span data-stu-id="300e8-104">In previous versions of the .NET Framework, the value was expected to be an <xref:System.IntPtr?displayProperty=fullName> representing a location in memory where the [HWND](https://docs.microsoft.com/windows/desktop/WinProg/windows-data-types#HWND) value resided.</span></span> <span data-ttu-id="300e8-105">Windows 7 以前のバージョンでこのプロパティを form.Handle に設定しても影響はありませんでしたが、Windows 8 以降のバージョンでは、&quot;<xref:System.Security.Cryptography.CryptographicException?displayProperty=fullName>:パラメーターが正しくありません&quot; が表示されます。</span><span class="sxs-lookup"><span data-stu-id="300e8-105">Setting the property to form.Handle on Windows 7 and earlier versions had no effect, but on Windows 8 and later versions, it results in a &quot;<xref:System.Security.Cryptography.CryptographicException?displayProperty=fullName>: The parameter is incorrect.&quot;</span></span>

#### <a name="suggestion"></a><span data-ttu-id="300e8-106">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="300e8-106">Suggestion</span></span>

<span data-ttu-id="300e8-107">.NET Framework 4.7 以降をターゲットとするアプリケーションで親ウィンドウの関係を登録する場合、次のように単純な形式を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="300e8-107">Applications targeting .NET Framework 4.7 or higher wishing to register a parent window relationship are encouraged to use the simplified form:</span></span>

```csharp
cspParameters.ParentWindowHandle = form.Handle;
```

<span data-ttu-id="300e8-108">渡すべき正しい値は、値 `form.Handle` が保持されているメモリ内の場所のアドレスであることがわかっていた場合は、AppContext スイッチ `Switch.System.Security.Cryptography.DoNotAddrOfCspParentWindowHandle` を `true` に設定して、動作変更を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="300e8-108">Users who had identified that the correct value to pass was the address of a memory location which held the value `form.Handle` can opt out of the behavior change by setting the AppContext switch `Switch.System.Security.Cryptography.DoNotAddrOfCspParentWindowHandle` to `true`:</span></span>

- <span data-ttu-id="300e8-109">プログラムで AppContext の互換性スイッチを設定する (説明は[こちらに](https://devblogs.microsoft.com/dotnet/net-announcements-at-build-2015/#dotnet46)あります)。</span><span class="sxs-lookup"><span data-stu-id="300e8-109">By programmatically setting compat switches on the AppContext, as explained [here](https://devblogs.microsoft.com/dotnet/net-announcements-at-build-2015/#dotnet46).</span></span>
- <span data-ttu-id="300e8-110">app.config ファイルの `<runtime>` セクションに以下の行を追加する:</span><span class="sxs-lookup"><span data-stu-id="300e8-110">By adding the following line to the `<runtime>` section of the app.config file:</span></span>

```xml
<runtime>
 <AppContextSwitchOverrides value="Switch.System.Security.Cryptography.DoNotAddrOfCspParentWindowHandle=true"/>
</runtime>
```

<span data-ttu-id="300e8-111">逆に、アプリケーションが以前のバージョンの .NET Framework の下で読み込むとき、.NET Framework 4.7 ランタイムで新しい動作を選択する場合、AppContext スイッチを `false` に設定できます。</span><span class="sxs-lookup"><span data-stu-id="300e8-111">Conversely, users who wish to opt in to the new behavior on the .NET Framework 4.7 runtime when the application loads under older .NET Framework versions can set the AppContext switch to `false`.</span></span>

| <span data-ttu-id="300e8-112">名前</span><span class="sxs-lookup"><span data-stu-id="300e8-112">Name</span></span>    | <span data-ttu-id="300e8-113">値</span><span class="sxs-lookup"><span data-stu-id="300e8-113">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="300e8-114">スコープ</span><span class="sxs-lookup"><span data-stu-id="300e8-114">Scope</span></span>   | <span data-ttu-id="300e8-115">マイナー</span><span class="sxs-lookup"><span data-stu-id="300e8-115">Minor</span></span>       |
| <span data-ttu-id="300e8-116">バージョン</span><span class="sxs-lookup"><span data-stu-id="300e8-116">Version</span></span> | <span data-ttu-id="300e8-117">4.7</span><span class="sxs-lookup"><span data-stu-id="300e8-117">4.7</span></span>         |
| <span data-ttu-id="300e8-118">種類</span><span class="sxs-lookup"><span data-stu-id="300e8-118">Type</span></span>    | <span data-ttu-id="300e8-119">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="300e8-119">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="300e8-120">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="300e8-120">Affected APIs</span></span>

- <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle?displayProperty=nameWithType>
