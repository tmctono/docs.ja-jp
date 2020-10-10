---
title: MakeParentItemsControlGotFocus のメソッド (GridViewHeaderRowPresenter)
description: MakeParentItemsControlGotFocus と呼ばれるプライベート WPF メソッドについて説明します。
ms.date: 09/25/2020
ms.technology: dotnet-wpf
topic_type:
- apiref
api_name:
- System.Windows.Controls.GridViewHeaderRowPresenter.MakeParentItemsControlGotFocus
api_location:
- PresentationFramework.dll
api_type:
- Assembly
ms.openlocfilehash: aea534e2f6a46353562d095329ffd869df88e513
ms.sourcegitcommit: eb7e87496f42361b1da98562dd75b516c9d58bbc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/09/2020
ms.locfileid: "91878113"
---
# <a name="makeparentitemscontrolgotfocus-method"></a><span data-ttu-id="30b05-103">MakeParentItemsControlGotFocus メソッド</span><span class="sxs-lookup"><span data-stu-id="30b05-103">MakeParentItemsControlGotFocus method</span></span>

<span data-ttu-id="30b05-104">項目の親コントロールにフォーカスを与えます。</span><span class="sxs-lookup"><span data-stu-id="30b05-104">Gives focus to the parent control of the item.</span></span> <span data-ttu-id="30b05-105">親コントロールがの場合は、 <xref:System.Windows.Controls.ListBox> で最後にアクセスした項目にフォーカスを移動し <xref:System.Windows.Controls.ListBox> ます。</span><span class="sxs-lookup"><span data-stu-id="30b05-105">If the parent control is a <xref:System.Windows.Controls.ListBox>, gives focus to the most recently accessed item in the <xref:System.Windows.Controls.ListBox>.</span></span>

```csharp
internal void MakeParentItemsControlGotFocus()
```

> [!WARNING]
> <span data-ttu-id="30b05-106">このメソッドは内部であり、コードで直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="30b05-106">This method is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="30b05-107">Microsoft では、どのような状況でも、実稼働アプリケーションでこの方法を使用することはサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="30b05-107">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="30b05-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="30b05-108">Requirements</span></span>

<span data-ttu-id="30b05-109">**名前空間:** <xref:System.Windows.Controls></span><span class="sxs-lookup"><span data-stu-id="30b05-109">**Namespace:** <xref:System.Windows.Controls></span></span>

<span data-ttu-id="30b05-110">**アセンブリ:** PresentationFramework.dll</span><span class="sxs-lookup"><span data-stu-id="30b05-110">**Assembly:** PresentationFramework.dll</span></span>

## <a name="see-also"></a><span data-ttu-id="30b05-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="30b05-111">See also</span></span>

- <xref:System.Windows.Controls.GridViewHeaderRowPresenter>
