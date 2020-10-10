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
# <a name="findheaderbycolumn-method"></a><span data-ttu-id="0f5a9-103">FindHeaderByColumn メソッド</span><span class="sxs-lookup"><span data-stu-id="0f5a9-103">FindHeaderByColumn method</span></span>

<span data-ttu-id="0f5a9-104">ビジュアルツリー内の指定された列の列ヘッダーを検索します。</span><span class="sxs-lookup"><span data-stu-id="0f5a9-104">Finds the column header for the specified column in the visual tree.</span></span>

```csharp
private GridViewColumnHeader FindHeaderByColumn(GridViewColumn column)
```

> [!WARNING]
> <span data-ttu-id="0f5a9-105">このメソッドはプライベートであり、コード内で直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="0f5a9-105">This method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="0f5a9-106">Microsoft では、どのような状況でも、実稼働アプリケーションでこの方法を使用することはサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="0f5a9-106">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="parameters"></a><span data-ttu-id="0f5a9-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0f5a9-107">Parameters</span></span>

<span data-ttu-id="0f5a9-108">`column` <xref:System.Windows.Controls.GridViewColumn></span><span class="sxs-lookup"><span data-stu-id="0f5a9-108">`column` <xref:System.Windows.Controls.GridViewColumn></span></span>\
<span data-ttu-id="0f5a9-109">ヘッダーを検索して返す必要がある列。</span><span class="sxs-lookup"><span data-stu-id="0f5a9-109">The column whose header should be found and returned.</span></span>

## <a name="return-value"></a><span data-ttu-id="0f5a9-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="0f5a9-110">Return value</span></span>

<xref:System.Windows.Controls.GridViewColumnHeader>\
<span data-ttu-id="0f5a9-111">指定された列のヘッダー `null` 。指定された列が存在しない場合は。</span><span class="sxs-lookup"><span data-stu-id="0f5a9-111">The header of the specified column, or `null` if the specified column doesn't exist.</span></span>

## <a name="requirements"></a><span data-ttu-id="0f5a9-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="0f5a9-112">Requirements</span></span>

<span data-ttu-id="0f5a9-113">**名前空間:** <xref:System.Windows.Controls></span><span class="sxs-lookup"><span data-stu-id="0f5a9-113">**Namespace:** <xref:System.Windows.Controls></span></span>

<span data-ttu-id="0f5a9-114">**アセンブリ:** PresentationFramework.dll</span><span class="sxs-lookup"><span data-stu-id="0f5a9-114">**Assembly:** PresentationFramework.dll</span></span>

## <a name="see-also"></a><span data-ttu-id="0f5a9-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="0f5a9-115">See also</span></span>

- <xref:System.Windows.Controls.GridViewHeaderRowPresenter>
