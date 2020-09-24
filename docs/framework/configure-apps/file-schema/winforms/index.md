---
title: Windows フォームの構成セクション
ms.date: 04/07/2017
ms.assetid: 6eb142d5-fc98-40e2-9d90-84733f2a27ba
ms.openlocfilehash: 2d518ec03602580f3c5d00ef2901ff7d7ac1d81b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148504"
---
# <a name="windows-forms-configuration-section"></a>Windows フォームの構成セクション

Windows フォームの構成設定により、カスタマイズされたアプリケーション設定に関する情報 (マルチ モニターや高 DPI のサポート、その他の定義済みの構成設定など) を Windows フォームのアプリで格納したり、取得したりできます。

Windows フォームのアプリケーション構成設定は、アプリケーション構成ファイルの `System.Windows.Forms.ApplicationConfigurationSection` 要素に格納されます。

## <a name="syntax"></a>構文

```xml
<configuration>
  <System.Windows.Forms.ApplicationConfigurationSection>
  ...
  </System.Windows.Forms.ApplicationConfigurationSection>
</configuration>
```

## <a name="attributes-and-elements"></a>属性と要素

以降のセクションでは、属性、子要素、および親要素について説明します。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

要素  |説明 |
---------|---------|
[`<add>`](windows-forms-add-configuration-element.md) | 指定した値を持つ構成設定キーを追加します |

### <a name="parent-elements"></a>親要素

要素  |説明 |
---------|---------|
[\<configuration>](../configuration-element.md) | 共通言語ランタイムと Windows フォームのアプリケーションで使用されるすべての構成ファイルのルート要素です |

## <a name="remarks"></a>解説

.NET Framework 4.7 を使用すれば、.NET Framework の最近のリリースで追加された機能が利用できる Windows フォームのアプリケーションを、`<System.Windows.Forms.ApplicationConfigurationSection>` 要素で構成できます。

要素には `<System.Windows.Forms.ApplicationConfigurationSection>` 1 つ以上の子要素を含めることができ [`<add>`](windows-forms-add-configuration-element.md) 、それぞれが特定の構成設定を定義します。

## <a name="see-also"></a>関連項目

- [構成ファイル スキーマ](../index.md)
- [Windows フォームでの高 DPI サポート](/dotnet/desktop/winforms/high-dpi-support-in-windows-forms)
