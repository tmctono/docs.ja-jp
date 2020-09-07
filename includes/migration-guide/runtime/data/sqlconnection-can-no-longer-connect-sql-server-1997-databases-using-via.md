---
ms.openlocfilehash: 8dc947f584d3433f0638a72f4db86ac2680c8dbf
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496813"
---
### <a name="sqlconnection-can-no-longer-connect-to-sql-server-1997-or-databases-using-the-via-adapter"></a>SqlConnection は VIA アダプターを使用して SQL Server 1997 またはデータベースに接続できなくなりました

#### <a name="details"></a>説明

[仮想インターフェイス アダプター (VIA) プロトコル](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms191229(v=sql.105))を使用した SQL Server データベースへの接続はサポートされなくなりました。 SQL Server データベースへの接続に使用されるプロトコルは、接続文字列で表示されます。 VIA 接続には via:&lt;servername&gt; が含まれます。 このアプリが VIA 以外のプロトコル (tcp: や np: など) を介して SQL に接続している場合、破壊的変更は発生しません。 また、SQL Server 7 (1997) への接続はサポートされなくなりました。

#### <a name="suggestion"></a>提案される解決策

VIA プロトコルは推奨されていないので、SQL データベースに接続するには別のプロトコルを使用する必要があります。 最も一般的に使用されるプロトコルは TCP/IP です。 TCP/IP での接続の詳細については、「[方法: データベース インスタンスの TCP/IP プロトコルを有効にする](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/bb909712(v=vs.90))」を参照してください。 データベースへのアクセスがイントラネット内からに限定されていて、ネットワーク速度が遅い場合は、共有パイプ プロトコルがより優れたパフォーマンスを提供する可能性があります。

| 名前    | [値]       |
|:--------|:------------|
| スコープ   |エッジ|
|バージョン|4.5|
|種類|ランタイム|

#### <a name="affected-apis"></a>影響を受ける API

- <xref:System.Data.SqlClient.SqlConnection.%23ctor(System.String)>
- <xref:System.Data.SqlClient.SqlConnection.%23ctor(System.String,System.Data.SqlClient.SqlCredential)>

<!--

#### Affected APIs

- `M:System.Data.SqlClient.SqlConnection.#ctor(System.String)`
- `M:System.Data.SqlClient.SqlConnection.#ctor(System.String,System.Data.SqlClient.SqlCredential)`

-->
