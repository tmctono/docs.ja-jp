---
title: ServicePointManager. CloseConnectionGroups メソッド (System.Net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.ServicePointManager.CloseConnectionGroups
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: aae9a389ae35e249d43c9dc830a68ec32cf4afef
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990535"
---
# <a name="servicepointmanagercloseconnectiongroups-method"></a><span data-ttu-id="2b0e5-102">ServicePointManager. CloseConnectionGroups メソッド</span><span class="sxs-lookup"><span data-stu-id="2b0e5-102">ServicePointManager.CloseConnectionGroups method</span></span>

<span data-ttu-id="2b0e5-103">すべてのサービスポイントを反復処理し、指定された名前の接続グループを閉じます。</span><span class="sxs-lookup"><span data-stu-id="2b0e5-103">Iterates through all service points and closes connection groups that have the specified name.</span></span>

```csharp
internal static void CloseConnectionGroups(string connectionGroupName)
```

> [!WARNING]
> <span data-ttu-id="2b0e5-104">このメソッドは内部であり、コードで直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="2b0e5-104">This method is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="2b0e5-105">Microsoft では、どのような状況でも、実稼働アプリケーションでこの方法を使用することはサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="2b0e5-105">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="parameters"></a><span data-ttu-id="2b0e5-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2b0e5-106">Parameters</span></span>

<span data-ttu-id="2b0e5-107">`connectionGroupName` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="2b0e5-107">`connectionGroupName` <xref:System.String></span></span>

<span data-ttu-id="2b0e5-108">閉じる接続グループの名前。</span><span class="sxs-lookup"><span data-stu-id="2b0e5-108">The name of the connection group to close.</span></span>

## <a name="requirements"></a><span data-ttu-id="2b0e5-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="2b0e5-109">Requirements</span></span>

<span data-ttu-id="2b0e5-110">**名前空間:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="2b0e5-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="2b0e5-111">**アセンブリ:** システム (System.dll)</span><span class="sxs-lookup"><span data-stu-id="2b0e5-111">**Assembly:** System (in System.dll)</span></span>
