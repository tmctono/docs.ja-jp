---
ms.openlocfilehash: 2c44c2e1658f8de556d3f7222de3fa6d4594163a
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497489"
---
### <a name="deserialization-of-mailmessage-objects-serialized-under-the-net-framework-45-may-fail"></a>.NET Framework 4.5 でシリアル化された MailMessage オブジェクトの逆シリアル化が失敗する可能性がある

#### <a name="details"></a>説明

.NET Framework 4.5 以降では、<xref:System.Web.Mail.MailMessage> オブジェクトに非 ASCII 文字を含めることができます。 .NET Framework 4 では、ASCII 文字しかサポートされていません。 非 ASCII 文字が含まれ、.NET Framework 4.5 以降でシリアル化された <xref:System.Web.Mail.MailMessage> オブジェクトは、.NET Framework 4 で逆シリアル化することはできません。

#### <a name="suggestion"></a>提案される解決策

<xref:System.Web.Mail.MailMessage> オブジェクトの逆シリアル化時に、コードで例外処理が提供されることを確認します。

| 名前    | [値]       |
|:--------|:------------|
| スコープ   |マイナー|
|バージョン|4.5|
|種類|ランタイム|

#### <a name="affected-apis"></a>影響を受ける API

- <xref:System.Web.Mail.MailMessage?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:System.Web.Mail.MailMessage`

-->
