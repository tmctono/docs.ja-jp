---
title: GridViewHeaderRowPresenter を設定する Headerdrag メソッド (system.string)
description: "\"のプライベート WPF メソッドについて説明します。"
ms.date: 09/25/2020
ms.technology: dotnet-wpf
topic_type:
- apiref
api_name:
- System.Windows.Controls.GridViewHeaderRowPresenter.PrepareHeaderDrag
api_location:
- PresentationFramework.dll
api_type:
- Assembly
ms.openlocfilehash: 6d806b8a50de3234cd04198f4ab86621dcd6ede1
ms.sourcegitcommit: eb7e87496f42361b1da98562dd75b516c9d58bbc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/09/2020
ms.locfileid: "91878111"
---
# <a name="prepareheaderdrag-method"></a>/の Headerdrag メソッド

順序を変更するために、指定された列ヘッダーを準備します。

```csharp
private void PrepareHeaderDrag(GridViewColumnHeader header, Point pos, Point relativePos, bool cancelInvoke)
```

> [!WARNING]
> このメソッドはプライベートであり、コード内で直接使用するためのものではありません。
>
> Microsoft では、どのような状況でも、実稼働アプリケーションでこの方法を使用することはサポートしていません。

## <a name="parameters"></a>パラメーター

`header` <xref:System.Windows.Controls.GridViewColumnHeader>\
順序を変更するための準備として使用する列ヘッダー。

`pos` <xref:System.Windows.Point>\
を基準とした、 <xref:System.Windows.Controls.GridViewHeaderRowPresenter> ドラッグの開始位置。

`relativePos` <xref:System.Windows.Point>\
を基準とした、 `header` ドラッグの開始位置。

`cancelInvoke` <xref:System.Boolean>\
`true` 並べ替えをキャンセルする場合は。それ以外の場合は `false` 。

## <a name="requirements"></a>必要条件

**名前空間:** <xref:System.Windows.Controls>

**アセンブリ:** PresentationFramework.dll

## <a name="see-also"></a>関連項目

- <xref:System.Windows.Controls.GridViewHeaderRowPresenter>
