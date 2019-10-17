---
title: SqlStreamChars. Seek (Int64, SeekOrigin) メソッド (SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Seek
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: db8aba0a86c140ba62af8056011226532d415951
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395597"
---
# <a name="sqlstreamcharsseekint64-seekorigin-method"></a><span data-ttu-id="5d4ee-102">SqlStreamChars. Seek (Int64, SeekOrigin) メソッド</span><span class="sxs-lookup"><span data-stu-id="5d4ee-102">SqlStreamChars.Seek(Int64, SeekOrigin) Method</span></span>

<span data-ttu-id="5d4ee-103">派生クラスでオーバーライドされた場合は、現在のストリーム内の位置を設定します。</span><span class="sxs-lookup"><span data-stu-id="5d4ee-103">When overridden in a derived class, sets the position within the current stream.</span></span> <span data-ttu-id="5d4ee-104">このメソッドを含むアセンブリには、SQLAccess .dll とのフレンド関係があります。</span><span class="sxs-lookup"><span data-stu-id="5d4ee-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="5d4ee-105">SQL Server での使用を目的としています。</span><span class="sxs-lookup"><span data-stu-id="5d4ee-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="5d4ee-106">他のデータベースの場合は、そのデータベースによって提供されるホスティングメカニズムを使用します。</span><span class="sxs-lookup"><span data-stu-id="5d4ee-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public abstract long Seek (long offset, System.IO.SeekOrigin origin);
```

## <a name="parameters"></a><span data-ttu-id="5d4ee-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5d4ee-107">Parameters</span></span>

`offset`\
<span data-ttu-id="5d4ee-108">@No__t-0 を基準とするバイトオフセット。</span><span class="sxs-lookup"><span data-stu-id="5d4ee-108">A byte offset relative to `origin`.</span></span>

`origin`\
<span data-ttu-id="5d4ee-109">新しい位置を取得する参照ポイントを示す列挙値の1つ。</span><span class="sxs-lookup"><span data-stu-id="5d4ee-109">One of the enumeration values that indicates the reference point from which to obtain the new position.</span></span>

## <a name="returns"></a><span data-ttu-id="5d4ee-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="5d4ee-110">Returns</span></span>

<xref:System.Int32>\
<span data-ttu-id="5d4ee-111">現在のストリーム内の新しい位置。</span><span class="sxs-lookup"><span data-stu-id="5d4ee-111">The new position within the current stream.</span></span>

## <a name="remarks"></a><span data-ttu-id="5d4ee-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="5d4ee-112">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="5d4ee-113">@No__t-0 メソッドはプライベートであり、コード内で直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="5d4ee-113">The `SqlStreamChars.Seek` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="5d4ee-114">Microsoft では、どのような状況でも、実稼働アプリケーションでこの方法を使用することはサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="5d4ee-114">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="5d4ee-115">［要件］</span><span class="sxs-lookup"><span data-stu-id="5d4ee-115">Requirements</span></span>

<span data-ttu-id="5d4ee-116">**名前空間:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="5d4ee-116">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="5d4ee-117">**アセンブリ:** System.string (System. Data. .dll)</span><span class="sxs-lookup"><span data-stu-id="5d4ee-117">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="5d4ee-118">**.NET Framework のバージョン:** 2.0 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="5d4ee-118">**.NET Framework versions:** Available since 2.0.</span></span>
