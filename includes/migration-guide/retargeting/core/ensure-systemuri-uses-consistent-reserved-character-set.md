---
ms.openlocfilehash: 21921156295d89aad04f3197fef9fa322f3c8c87
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614661"
---
### <a name="ensure-systemuri-uses-a-consistent-reserved-character-set"></a><span data-ttu-id="d3e74-101">System.Uri で一貫した予約文字セットが確実に使用されるようになった</span><span class="sxs-lookup"><span data-stu-id="d3e74-101">Ensure System.Uri uses a consistent reserved character set</span></span>

#### <a name="details"></a><span data-ttu-id="d3e74-102">説明</span><span class="sxs-lookup"><span data-stu-id="d3e74-102">Details</span></span>

<span data-ttu-id="d3e74-103"><xref:System.Uri?displayProperty=fullName> では、場合によってはデコードされていたパーセントでエンコードされた特定の文字の状態が常に保たれるようになりました。</span><span class="sxs-lookup"><span data-stu-id="d3e74-103">In <xref:System.Uri?displayProperty=fullName>, certain percent-encoded characters that were sometimes decoded are now consistently left encoded.</span></span> <span data-ttu-id="d3e74-104">これは、URI のパス、クエリ、フラグメント、ユーザー情報コンポーネントにアクセスするプロパティやメソッド全体に適用されます。</span><span class="sxs-lookup"><span data-stu-id="d3e74-104">This occurs across the properties and methods that access the path, query, fragment, or userinfo components of the URI.</span></span> <span data-ttu-id="d3e74-105">以下の両方に該当する場合にのみ、動作が変わります。</span><span class="sxs-lookup"><span data-stu-id="d3e74-105">The behavior will change only when both of the following are true:</span></span>

- <span data-ttu-id="d3e74-106">`:`、`'`、`(`、`)`、`!`、`*` のいずれかの予約文字のエンコードされたフォームが URI に含まれている。</span><span class="sxs-lookup"><span data-stu-id="d3e74-106">The URI contains the encoded form of any of the following reserved characters: `:`, `'`, `(`, `)`, `!` or `*`.</span></span>
- <span data-ttu-id="d3e74-107">Unicode またはエンコードの予約されていない文字が URI に含まれている。</span><span class="sxs-lookup"><span data-stu-id="d3e74-107">The URI contains a Unicode or encoded non-reserved character.</span></span> <span data-ttu-id="d3e74-108">上記の両方に該当する場合、エンコードの予約文字はエンコードされたままです。</span><span class="sxs-lookup"><span data-stu-id="d3e74-108">If both of the above are true, the encoded reserved characters are left encoded.</span></span> <span data-ttu-id="d3e74-109">以前のバージョンの .NET Framework では、デコードされます。</span><span class="sxs-lookup"><span data-stu-id="d3e74-109">In previous versions of the .NET Framework, they are decoded.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="d3e74-110">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="d3e74-110">Suggestion</span></span>

<span data-ttu-id="d3e74-111">4\.7.2 以降のバージョンの .NET Framework を対象とするアプリケーションの場合は、新しいデコード動作が既定で有効になります。</span><span class="sxs-lookup"><span data-stu-id="d3e74-111">For applications that target versions of .NET Framework starting with 4.7.2, the new decoding behavior is enabled by default.</span></span> <span data-ttu-id="d3e74-112">この変更が望ましくない場合、アプリケーションの構成ファイルの `<runtime>` セクションに次の [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) スイッチを追加することで無効にできます。</span><span class="sxs-lookup"><span data-stu-id="d3e74-112">If this change is undesirable, you can disable it by adding the following [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) switch to the `<runtime>` section of the application configuration file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Uri.DontEnableStrictRFC3986ReservedCharacterSets=true" />
</runtime>
```

<span data-ttu-id="d3e74-113">以前のバージョンの .NET Framework を対象とするが、.NET Framework 4.7.2 以降のバージョンで実行するアプリケーションの場合、新しいデコード動作が既定で無効になります。</span><span class="sxs-lookup"><span data-stu-id="d3e74-113">For applications that target earlier versions of the .NET Framework but are running under versions starting with .NET Framework 4.7.2, the new decoding behavior is disabled by default.</span></span> <span data-ttu-id="d3e74-114">これを有効にするには、次の [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) スイッチをアプリケーション構成ファイルの `<runtime>` セクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="d3e74-114">You can enable it by adding the following [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) switch to the `<runtime>` section of the application configuration file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Uri.DontEnableStrictRFC3986ReservedCharacterSets=false" />
</runtime>
```

| <span data-ttu-id="d3e74-115">名前</span><span class="sxs-lookup"><span data-stu-id="d3e74-115">Name</span></span>    | <span data-ttu-id="d3e74-116">[値]</span><span class="sxs-lookup"><span data-stu-id="d3e74-116">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="d3e74-117">スコープ</span><span class="sxs-lookup"><span data-stu-id="d3e74-117">Scope</span></span>   | <span data-ttu-id="d3e74-118">マイナー</span><span class="sxs-lookup"><span data-stu-id="d3e74-118">Minor</span></span>       |
| <span data-ttu-id="d3e74-119">バージョン</span><span class="sxs-lookup"><span data-stu-id="d3e74-119">Version</span></span> | <span data-ttu-id="d3e74-120">4.7.2</span><span class="sxs-lookup"><span data-stu-id="d3e74-120">4.7.2</span></span>       |
| <span data-ttu-id="d3e74-121">種類</span><span class="sxs-lookup"><span data-stu-id="d3e74-121">Type</span></span>    | <span data-ttu-id="d3e74-122">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="d3e74-122">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="d3e74-123">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="d3e74-123">Affected APIs</span></span>

- <xref:System.Uri?displayProperty=nameWithType>
