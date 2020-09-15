---
ms.openlocfilehash: 53d74db1a77e62cc64250658281fd3e4706fe494
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614636"
---
### <a name="allow-unicode-bidirectional-control-characters-in-uris"></a><span data-ttu-id="c8462-101">URI での Unicode の双方向制御文字の許可</span><span class="sxs-lookup"><span data-stu-id="c8462-101">Allow Unicode Bidirectional Control Characters in URIs</span></span>

#### <a name="details"></a><span data-ttu-id="c8462-102">説明</span><span class="sxs-lookup"><span data-stu-id="c8462-102">Details</span></span>

<span data-ttu-id="c8462-103">Unicode では、テキストの方向を指定するために使用される特殊な制御文字をいくつか指定します。</span><span class="sxs-lookup"><span data-stu-id="c8462-103">Unicode specifies several special control characters used to specify the orientation of text.</span></span> <span data-ttu-id="c8462-104">以前のバージョンの .NET Framework では、これらの文字は、パーセントでエンコードされたフォームに存在する場合でも、すべての URI から正しく削除されませんでした。</span><span class="sxs-lookup"><span data-stu-id="c8462-104">In previous versions of the .NET Framework, these characters were incorrectly stripped from all URIs even if they were present in their percent-encoded form.</span></span> <span data-ttu-id="c8462-105">[RFC 3987](https://tools.ietf.org/html/rfc3987) により適切に従うために、これらの文字を URI で使用できるようにしました。</span><span class="sxs-lookup"><span data-stu-id="c8462-105">In order to better follow [RFC 3987](https://tools.ietf.org/html/rfc3987), we now allow these characters in URIs.</span></span> <span data-ttu-id="c8462-106">これらの文字は、URI でエンコードされていないことがわかった場合、パーセントでエンコードされます。</span><span class="sxs-lookup"><span data-stu-id="c8462-106">When found unencoded in a URI, they are percent-encoded.</span></span> <span data-ttu-id="c8462-107">パーセントでエンコードされていることがわかった場合は、そのままです。</span><span class="sxs-lookup"><span data-stu-id="c8462-107">When found percent-encoded they are left as-is.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="c8462-108">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="c8462-108">Suggestion</span></span>

<span data-ttu-id="c8462-109">4\.7.2 以降のバージョンの .NET Framework を対象とするアプリケーションの場合は、Unicode の双方向文字のサポートが既定で有効になります。</span><span class="sxs-lookup"><span data-stu-id="c8462-109">For applications that target versions of .NET Framework starting with 4.7.2, support for Unicode bidirectional characters is enabled by default.</span></span> <span data-ttu-id="c8462-110">この変更が望ましくない場合、アプリケーションの構成ファイルの `<runtime>` セクションに次の [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) スイッチを追加することで無効にできます。</span><span class="sxs-lookup"><span data-stu-id="c8462-110">If this change is undesirable, you can disable it by adding the following [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) switch to the `<runtime>` section of the application configuration file:</span></span>

```xml
<runtime>
<AppContextSwitchOverrides value="Switch.System.Uri.DontKeepUnicodeBidiFormattingCharacters=true" />
</runtime>
```

<span data-ttu-id="c8462-111">以前のバージョンの .NET Framework を対象とするが、.NET Framework 4.7.2 以降のバージョンで実行するアプリケーションの場合、Unicode の双方向文字のサポートが既定で無効になります。</span><span class="sxs-lookup"><span data-stu-id="c8462-111">For applications that target earlier versions of the .NET Framework but are running under versions starting with .NET Framework 4.7.2, support for Unicode bidirectional characters is disabled by default.</span></span> <span data-ttu-id="c8462-112">アプリケーションの構成ファイルの `<runtime>` セクションに次の [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) スイッチを追加することで有効にできます。</span><span class="sxs-lookup"><span data-stu-id="c8462-112">You can enable it by adding the following [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) switch to the `<runtime>` section of the application configuration file::</span></span>

```xml
<runtime>
<AppContextSwitchOverrides value="Switch.System.Uri.DontKeepUnicodeBidiFormattingCharacters=false" />
</runtime>
```

| <span data-ttu-id="c8462-113">名前</span><span class="sxs-lookup"><span data-stu-id="c8462-113">Name</span></span>    | <span data-ttu-id="c8462-114">[値]</span><span class="sxs-lookup"><span data-stu-id="c8462-114">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="c8462-115">スコープ</span><span class="sxs-lookup"><span data-stu-id="c8462-115">Scope</span></span>   | <span data-ttu-id="c8462-116">マイナー</span><span class="sxs-lookup"><span data-stu-id="c8462-116">Minor</span></span>       |
| <span data-ttu-id="c8462-117">バージョン</span><span class="sxs-lookup"><span data-stu-id="c8462-117">Version</span></span> | <span data-ttu-id="c8462-118">4.7.2</span><span class="sxs-lookup"><span data-stu-id="c8462-118">4.7.2</span></span>       |
| <span data-ttu-id="c8462-119">種類</span><span class="sxs-lookup"><span data-stu-id="c8462-119">Type</span></span>    | <span data-ttu-id="c8462-120">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="c8462-120">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="c8462-121">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="c8462-121">Affected APIs</span></span>

- <xref:System.Uri?displayProperty=nameWithType>
