---
ms.openlocfilehash: 072ed716910e2e1f1f98dbddc56d5bd097b75acc
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/04/2020
ms.locfileid: "87555912"
---
### <a name="microsoftvisualbasicconstantsvbnewline-is-obsolete"></a>Microsoft.VisualBasic.Constants.vbNewLine は古い

<xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> 定数は、.NET Core 3.0 以降では[\[古い\]](xref:System.ObsoleteAttribute)としてマークされています。

#### <a name="version-introduced"></a>導入されたバージョン

3.0

#### <a name="change-description"></a>変更の説明

.NET Core 3.0 以降では、[廃止](xref:System.ObsoleteAttribute)属性が <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> 定数に適用されています。 その定数を使用すると、コンパイラの警告が発生します。 .NET Framework と .NET Core の以前のリリースでは、古いとしてマークされていませんでした。

この変更は、Visual Basic をマルチプラットフォーム開発用の言語としてサポートするために行われました。 <xref:Microsoft.VisualBasic.Constants.vbNewLine> 定数は、Windows での改行文字シーケンスである `\r\n` と同等です。 Unix ベースのシステムでは、改行文字は `\n` です。

#### <a name="recommended-action"></a>推奨アクション

<xref:Microsoft.VisualBasic.Constants.vbNewLine> に対する[廃止](xref:System.ObsoleteAttribute)属性メッセージには、次の推奨事項が含まれています。

キャリッジ リターンとライン フィードの場合は、<xref:Microsoft.VisualBasic.Constants.vbCrLf> を使用します。 現在のプラットフォームの改行の場合は、<xref:System.Environment.NewLine?displayProperty=nameWithType> を使用します。

#### <a name="category"></a>カテゴリ

Visual Basic

#### <a name="affected-apis"></a>影響を受ける API

- <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName>

<!--

#### Affected APIs

- `F:Microsoft.VisualBasic.Constants.vbNewLine`

-->
