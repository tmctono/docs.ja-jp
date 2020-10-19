---
title: 'NETSDK1145: ターゲットまたは apphost のパックが見つからない'
description: NuGet パッケージの復元がサポートされていないときにターゲット パックが見つからない問題を解決する方法
author: wli3
ms.topic: error-reference
ms.date: 09/14/2020
f1_keywords:
- NETSDK1145
ms.openlocfilehash: c343952582cafb63eae388fd216769e6c67d4741
ms.sourcegitcommit: 636af37170ae75a11c4f7d1ecd770820e7dfe7bd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2020
ms.locfileid: "91805308"
---
# <a name="netsdk1145-targeting-or-apphost-pack-missing"></a>NETSDK1145: ターゲットまたは apphost のパックが見つからない

**この記事の対象:**  ✔️ .NET 5.0.100 SDK 以降のバージョン

.NET SDK でエラー NETSDK1145 が発生すると、ターゲットまたは apphost のパックがインストールされず、NuGet パッケージの復元がサポートされません。 これは通常、Visual Studio for C++/CLI プロジェクトに含まれているものよりも新しい SDK が原因で発生します。 Visual Studio をアップグレードし、特定の SDK バージョンが指定されている場合は _global.json_ を削除して、新しい方の SDK をアンインストールします。 または、ターゲットまたは apphost のバージョンをオーバーライドすることもできます。 エラー メッセージから、パックのディレクトリの下に存在し、プロジェクトのターゲット フレームワークと一致するバージョンを見つけます。 次をプロジェクトに追加します。

apphost パックの場合

```xml
<ItemGroup>
  <KnownAppHostPack Update="@(KnownAppHostPack)">
    <AppHostPackVersion Condition="'%(TargetFramework)' == 'TARGETFRAMEWORK'">EXISTINGVERSION</AppHostPackVersion>
  </KnownAppHostPack>
</ItemGroup>
```

ターゲット パックの場合

```xml
<ItemGroup>
  <KnownAppHostPack Update="@(KnownAppHostPack)">
    <AppHostPackVersion Condition="'%(TargetFramework)' == 'TARGETFRAMEWORK'">EXISTINGVERSION</AppHostPackVersion>
  </KnownAppHostPack>
</ItemGroup>
```
