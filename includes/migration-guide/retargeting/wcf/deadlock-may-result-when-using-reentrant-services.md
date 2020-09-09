---
ms.openlocfilehash: f61cf21f9f30662cc8e383bb3aeb5c642f1665b8
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497784"
---
### <a name="deadlock-may-result-when-using-reentrant-services"></a>再入可能なサービスを使用していると、デッドロックが発生する可能性がある

#### <a name="details"></a>説明

サービスのインスタンスの実行が一度に 1 つのスレッドに制限される再入可能なサービスでは、デッドロックが発生します。 この問題が発生しやすいサービスのコードには、次の <xref:System.ServiceModel.ServiceBehaviorAttribute> が含まれています。

```csharp
[ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Reentrant)]
```

#### <a name="suggestion"></a>提案される解決策

この問題に対処するために、次の操作を行うことができます。

- サービスのコンカレンシー モードを <xref:System.ServiceModel.ConcurrencyMode.Single?displayProperty=nameWithType> または <xref:System.ServiceModel.ConcurrencyMode.Multiple?displayProperty=nameWithType> に設定します。 次に例を示します。

```csharp
[ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Reentrant)]
```

- 最新の更新プログラムを .NET framework 4.6.2 にインストールするか、最新バージョンの .NET Framework にアップグレードします。 これにより、<xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> の <xref:System.Threading.ExecutionContext> のフローが無効になります。 この動作は構成可能です。構成ファイルに次のアプリ設定を追加することと同じです。

```xml
<appSettings>
  <add key="Switch.System.ServiceModel.DisableOperationContextAsyncFlow" value="true" />
</appSettings>
```

Reentrant サービスの場合、`Switch.System.ServiceModel.DisableOperationContextAsyncFlow` の値は `false` に設定しないでください。

| 名前    | [値]       |
|:--------|:------------|
| スコープ   | マイナー       |
| バージョン | 4.6.2       |
| 種類    | 再ターゲット中 |

#### <a name="affected-apis"></a>影響を受ける API

- <xref:System.ServiceModel.ServiceBehaviorAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.ConcurrencyMode.Reentrant?displayProperty=nameWithType>
