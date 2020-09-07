---
ms.openlocfilehash: 3c74d237f5540ef1a5bb362487337c81ae739ea1
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497892"
---
### <a name="systemnetpeertopeercollaboration-unavailable-on-windows-8"></a>Windows 8 で System.Net.PeerToPeer.Collaboration が使用できない

#### <a name="details"></a>説明

System.Net.PeerToPeer.Collaboration 名前空間は、Windows 8 以上では使用できません。

#### <a name="suggestion"></a>提案される解決策

Windows 8 以上をサポートするアプリは、この名前空間またはそのメンバーに依存しないように更新する必要があります。

| 名前    | [値]       |
|:--------|:------------|
| スコープ   |Major|
|バージョン|4.5|
|種類|ランタイム|

#### <a name="affected-apis"></a>影響を受ける API

- <xref:System.Net.PeerToPeer.Collaboration?displayProperty=nameWithType>

<!--

#### Affected APIs

- `N:System.Net.PeerToPeer.Collaboration`

-->
