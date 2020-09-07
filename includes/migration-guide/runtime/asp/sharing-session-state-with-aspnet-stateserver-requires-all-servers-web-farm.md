---
ms.openlocfilehash: 76425ca03c98cd6a23b8366257f9e0d53b486edb
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497501"
---
### <a name="sharing-session-state-with-aspnet-stateserver-requires-all-servers-in-the-web-farm-to-use-the-same-net-framework-version"></a>Asp.Net StateServer とセッション状態を共有するには、Web ファーム内のすべてのサーバーが同じ .NET Framework バージョンを使用する必要があります

#### <a name="details"></a>説明

<xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=fullName> セッション状態を有効にする場合、状態を正しく共有するには、指定の Web ファーム内のすべてのサーバーが同じバージョンの .NET Framework を使用する必要があります。

#### <a name="suggestion"></a>提案される解決策

同時に状態を共有する Web サーバー上で必ず .NET Framework バージョンのアップグレードを行います。

| 名前    | [値]       |
|:--------|:------------|
| スコープ   |エッジ|
|バージョン|4.5|
|種類|ランタイム

#### <a name="affected-apis"></a>影響を受ける API

- <xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=nameWithType>

<!--

#### Affected APIs

- `F:System.Web.SessionState.SessionStateMode.StateServer`

-->
