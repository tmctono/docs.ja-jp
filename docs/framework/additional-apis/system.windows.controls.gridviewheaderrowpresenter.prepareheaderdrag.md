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
# <a name="prepareheaderdrag-method"></a><span data-ttu-id="f329c-103">/の Headerdrag メソッド</span><span class="sxs-lookup"><span data-stu-id="f329c-103">PrepareHeaderDrag method</span></span>

<span data-ttu-id="f329c-104">順序を変更するために、指定された列ヘッダーを準備します。</span><span class="sxs-lookup"><span data-stu-id="f329c-104">Prepares the specified column header for reordering.</span></span>

```csharp
private void PrepareHeaderDrag(GridViewColumnHeader header, Point pos, Point relativePos, bool cancelInvoke)
```

> [!WARNING]
> <span data-ttu-id="f329c-105">このメソッドはプライベートであり、コード内で直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="f329c-105">This method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="f329c-106">Microsoft では、どのような状況でも、実稼働アプリケーションでこの方法を使用することはサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="f329c-106">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="parameters"></a><span data-ttu-id="f329c-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f329c-107">Parameters</span></span>

<span data-ttu-id="f329c-108">`header` <xref:System.Windows.Controls.GridViewColumnHeader></span><span class="sxs-lookup"><span data-stu-id="f329c-108">`header` <xref:System.Windows.Controls.GridViewColumnHeader></span></span>\
<span data-ttu-id="f329c-109">順序を変更するための準備として使用する列ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="f329c-109">The column header to prepare for reordering.</span></span>

<span data-ttu-id="f329c-110">`pos` <xref:System.Windows.Point></span><span class="sxs-lookup"><span data-stu-id="f329c-110">`pos` <xref:System.Windows.Point></span></span>\
<span data-ttu-id="f329c-111">を基準とした、 <xref:System.Windows.Controls.GridViewHeaderRowPresenter> ドラッグの開始位置。</span><span class="sxs-lookup"><span data-stu-id="f329c-111">The position, relative to <xref:System.Windows.Controls.GridViewHeaderRowPresenter>, where the dragging starts.</span></span>

<span data-ttu-id="f329c-112">`relativePos` <xref:System.Windows.Point></span><span class="sxs-lookup"><span data-stu-id="f329c-112">`relativePos` <xref:System.Windows.Point></span></span>\
<span data-ttu-id="f329c-113">を基準とした、 `header` ドラッグの開始位置。</span><span class="sxs-lookup"><span data-stu-id="f329c-113">The position, relative to `header`, where the dragging starts.</span></span>

<span data-ttu-id="f329c-114">`cancelInvoke` <xref:System.Boolean></span><span class="sxs-lookup"><span data-stu-id="f329c-114">`cancelInvoke` <xref:System.Boolean></span></span>\
<span data-ttu-id="f329c-115">`true` 並べ替えをキャンセルする場合は。それ以外の場合は `false` 。</span><span class="sxs-lookup"><span data-stu-id="f329c-115">`true` to cancel the reordering; otherwise, `false`.</span></span>

## <a name="requirements"></a><span data-ttu-id="f329c-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="f329c-116">Requirements</span></span>

<span data-ttu-id="f329c-117">**名前空間:** <xref:System.Windows.Controls></span><span class="sxs-lookup"><span data-stu-id="f329c-117">**Namespace:** <xref:System.Windows.Controls></span></span>

<span data-ttu-id="f329c-118">**アセンブリ:** PresentationFramework.dll</span><span class="sxs-lookup"><span data-stu-id="f329c-118">**Assembly:** PresentationFramework.dll</span></span>

## <a name="see-also"></a><span data-ttu-id="f329c-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="f329c-119">See also</span></span>

- <xref:System.Windows.Controls.GridViewHeaderRowPresenter>
