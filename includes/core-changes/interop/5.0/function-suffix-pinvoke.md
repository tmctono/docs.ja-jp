---
ms.openlocfilehash: e128bdb5735b3e4844356ad4807cc092f6f2b105
ms.sourcegitcommit: 7476c20d2f911a834a00b8a7f5e8926bae6804d9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/11/2020
ms.locfileid: "88062427"
---
### <a name="no-aw-suffix-probing-on-non-windows-platforms"></a>Windows 以外のプラットフォームでは A/W サフィックスのプローブは行われません

.NET ランタイムでは、Windows 以外のプラットフォームにおいて P/Invoke のプローブ中に関数エクスポート名に `A` または `W` サフィックスを追加しなくなりました。

#### <a name="version-introduced"></a>導入されたバージョン

5.0 Preview 4

#### <a name="change-description"></a>変更の説明

[Windows には、Windows コードページと Unicode バージョンに対応する `A` または `W` サフィックスを Windows SDK 関数名に追加するという ](/windows/win32/intl/conventions-for-function-prototypes) 規約があります。

以前のバージョンの .NET では、CoreCLR と Mono の両方のランタイムによって、"*すべてのプラットフォームでの*" P/Invoke のエクスポートの検出時に、エクスポート名に `A` または `W` サフィックスが追加されます。

.NET 5.0 以降のバージョンでは、"*Windows のみでの*" エクスポートの検出時に `A` または `W` サフィックスがエクスポート名に追加されます。 Unix プラットフォームでは、サフィックスは追加されません。 Windows プラットフォーム上の両方のランタイムのセマンティクスは変更されません。

#### <a name="reason-for-change"></a>変更理由

この変更は、クロスプラットフォームのプローブを簡素化するために行われました。 Windows 以外のプラットフォームにはこのセマンティックが含まれていないため、オーバーヘッドが発生することはありません。

#### <a name="recommended-action"></a>推奨アクション

変更を軽減するには、Windows 以外のプラットフォームに必要なサフィックスを手動で追加します。 次に例を示します。

```csharp
[DllImport(...)]
extern static void SetWindowTextW();
```

#### <a name="category"></a>カテゴリ

Interop

#### <a name="affected-apis"></a>影響を受ける API

- <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Runtime.InteropServices.DllImportAttribute`

-->
