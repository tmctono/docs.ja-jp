---
title: FindHeaderByColumn のメソッド (GridViewHeaderRowPresenter)
description: FindHeaderByColumn と呼ばれるプライベート WPF メソッドについて説明します。
ms.date: 09/25/2020
ms.technology: dotnet-wpf
topic_type:
- apiref
api_name:
- System.Windows.Controls.GridViewHeaderRowPresenter.FindHeaderByColumn
api_location:
- PresentationFramework.dll
api_type:
- Assembly
ms.openlocfilehash: 88ed2928f86602d1078488354de6d5267c0311f5
ms.sourcegitcommit: eb7e87496f42361b1da98562dd75b516c9d58bbc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/09/2020
ms.locfileid: "91878114"
---
# <a name="findheaderbycolumn-method"></a>FindHeaderByColumn メソッド

ビジュアルツリー内の指定された列の列ヘッダーを検索します。

```csharp
private GridViewColumnHeader FindHeaderByColumn(GridViewColumn column)
```

> [!WARNING]
> このメソッドはプライベートであり、コード内で直接使用するためのものではありません。
>
> Microsoft では、どのような状況でも、実稼働アプリケーションでこの方法を使用することはサポートしていません。

## <a name="parameters"></a>パラメーター

`column` <xref:System.Windows.Controls.GridViewColumn>\
ヘッダーを検索して返す必要がある列。

## <a name="return-value"></a>戻り値

<xref:System.Windows.Controls.GridViewColumnHeader>\
指定された列のヘッダー `null` 。指定された列が存在しない場合は。

## <a name="requirements"></a>必要条件

**名前空間:** <xref:System.Windows.Controls>

**アセンブリ:** PresentationFramework.dll

## <a name="see-also"></a>関連項目

- <xref:System.Windows.Controls.GridViewHeaderRowPresenter>
