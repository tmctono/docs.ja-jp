---
ms.openlocfilehash: 67e3ff5000ebd38064ed8a57e4fe561afa31f8d8
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614709"
---
### <a name="long-path-support"></a><span data-ttu-id="6343c-101">長いパスのサポート</span><span class="sxs-lookup"><span data-stu-id="6343c-101">Long path support</span></span>

#### <a name="details"></a><span data-ttu-id="6343c-102">説明</span><span class="sxs-lookup"><span data-stu-id="6343c-102">Details</span></span>

<span data-ttu-id="6343c-103">以降とするアプリをターゲットとする .NET Framework 4.6.2、長いパス (最大 32 K の文字) がサポートされている、および 260 文字 (または`MAX_PATH`) パスの長さの制限がなくなりました。 .NET Framework 4.6.2 を対象として再コンパイルされたアプリの場合は、コードをスローした以前のパス、 <xref:System.IO.PathTooLongException?displayProperty=fullName> 260 文字をスローがパスを超えたため、<xref:System.IO.PathTooLongException?displayProperty=fullName>次の条件下でのみ。</span><span class="sxs-lookup"><span data-stu-id="6343c-103">Starting with apps that target the .NET Framework 4.6.2, long paths (of up to 32K characters) are supported, and the 260-character (or `MAX_PATH`) limitation on path lengths has been removed.For apps that are recompiled to target the .NET Framework 4.6.2, code paths that previously threw a <xref:System.IO.PathTooLongException?displayProperty=fullName> because a path exceeded 260 characters will now throw a <xref:System.IO.PathTooLongException?displayProperty=fullName> only under the following conditions:</span></span>

- <span data-ttu-id="6343c-104">パスの長さが <xref:System.Int16.MaxValue> (32,767) 文字を超えている。</span><span class="sxs-lookup"><span data-stu-id="6343c-104">The length of the path is greater than <xref:System.Int16.MaxValue> (32,767) characters.</span></span>
- <span data-ttu-id="6343c-105">オペレーティング システムが `COR_E_PATHTOOLONG` またはそれと同等のものを返す。</span><span class="sxs-lookup"><span data-stu-id="6343c-105">The operating system returns `COR_E_PATHTOOLONG` or its equivalent.</span></span>
<span data-ttu-id="6343c-106">.NET Framework 4.6.1 以前を対象とするアプリの場合、パスが 260 文字を超えるたびにランタイムで自動的に <xref:System.IO.PathTooLongException?displayProperty=fullName> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="6343c-106">For apps that target the .NET Framework 4.6.1 and earlier versions, the runtime automatically throws a <xref:System.IO.PathTooLongException?displayProperty=fullName> whenever a path exceeds 260 characters.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="6343c-107">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="6343c-107">Suggestion</span></span>

<span data-ttu-id="6343c-108">.NET Framework 4.6.2 を対象とするアプリケーションの場合、長いパスが望ましくないときは、`app.config` ファイルの `<runtime>` セクションに次を追加することで長いパスのサポートを無効にできます。</span><span class="sxs-lookup"><span data-stu-id="6343c-108">For apps that target the .NET Framework 4.6.2, you can opt out of long path support if it is not desirable by adding the following to the `<runtime>` section of your `app.config` file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.BlockLongPaths=true" />
</runtime>
```

<span data-ttu-id="6343c-109">以前のバージョンの .NET Framework を対象とするが、.NET Framework 4.6.2 以降で実行するアプリの場合、`app.config` ファイルの `<runtime>` セクションに次を追加することで長いパスのサポートを選択できます。</span><span class="sxs-lookup"><span data-stu-id="6343c-109">For apps that target earlier versions of the .NET Framework but run on the .NET Framework 4.6.2 or later, you can opt in to long path support by adding the following to the `<runtime>` section of your `app.config` file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.BlockLongPaths=false" />
</runtime>
```

| <span data-ttu-id="6343c-110">名前</span><span class="sxs-lookup"><span data-stu-id="6343c-110">Name</span></span>    | <span data-ttu-id="6343c-111">値</span><span class="sxs-lookup"><span data-stu-id="6343c-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="6343c-112">スコープ</span><span class="sxs-lookup"><span data-stu-id="6343c-112">Scope</span></span>   | <span data-ttu-id="6343c-113">マイナー</span><span class="sxs-lookup"><span data-stu-id="6343c-113">Minor</span></span>       |
| <span data-ttu-id="6343c-114">バージョン</span><span class="sxs-lookup"><span data-stu-id="6343c-114">Version</span></span> | <span data-ttu-id="6343c-115">4.6.2</span><span class="sxs-lookup"><span data-stu-id="6343c-115">4.6.2</span></span>       |
| <span data-ttu-id="6343c-116">種類</span><span class="sxs-lookup"><span data-stu-id="6343c-116">Type</span></span>    | <span data-ttu-id="6343c-117">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="6343c-117">Retargeting</span></span> |
