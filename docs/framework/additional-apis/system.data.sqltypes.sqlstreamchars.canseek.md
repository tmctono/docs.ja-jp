---
title: SqlStreamChars. CanSeek プロパティ (SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/19/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.CanSeek
- System.Data.SqlTypes.SqlStreamChars.get_CanSeek
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: eb32978f62b7d46f0abf715e2bca347592c0fda8
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395774"
---
# <a name="sqlstreamcharscanseek-property"></a><span data-ttu-id="5d4ed-102">SqlStreamChars. CanSeek プロパティ</span><span class="sxs-lookup"><span data-stu-id="5d4ed-102">SqlStreamChars.CanSeek Property</span></span>

<span data-ttu-id="5d4ed-103">派生クラスでオーバーライドされた場合、現在のストリームがシーク操作をサポートしているかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="5d4ed-103">When overridden in a derived class, gets a value that indicates whether the current steam supports the seek operation.</span></span> <span data-ttu-id="5d4ed-104">このプロパティを含むアセンブリには、SQLAccess .dll とのフレンド関係があります。</span><span class="sxs-lookup"><span data-stu-id="5d4ed-104">The assembly that contains this property has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="5d4ed-105">SQL Server での使用を目的としています。</span><span class="sxs-lookup"><span data-stu-id="5d4ed-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="5d4ed-106">他のデータベースの場合は、そのデータベースによって提供されるホスティングメカニズムを使用します。</span><span class="sxs-lookup"><span data-stu-id="5d4ed-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public abstract bool CanSeek { get; }
```

## <a name="property-value"></a><span data-ttu-id="5d4ed-107">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="5d4ed-107">Property value</span></span>

<xref:System.Boolean>\
<span data-ttu-id="5d4ed-108">現在のストリームがシーク操作をサポートしている場合は `true`。それ以外の場合は、`false` です。</span><span class="sxs-lookup"><span data-stu-id="5d4ed-108">`true` if the current steam supports the seek operation; otherwise, `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="5d4ed-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="5d4ed-109">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="5d4ed-110">@No__t-0 プロパティはプライベートであり、コードで直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="5d4ed-110">The `SqlStreamChars.CanSeek` property is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="5d4ed-111">Microsoft では、どのような状況でも、実稼働アプリケーションでのこのプロパティの使用はサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="5d4ed-111">Microsoft does not support the use of this property in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="5d4ed-112">［要件］</span><span class="sxs-lookup"><span data-stu-id="5d4ed-112">Requirements</span></span>

<span data-ttu-id="5d4ed-113">**名前空間:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="5d4ed-113">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="5d4ed-114">**アセンブリ:** System.string (System. Data. .dll)</span><span class="sxs-lookup"><span data-stu-id="5d4ed-114">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="5d4ed-115">**.NET Framework のバージョン:** 2.0 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="5d4ed-115">**.NET Framework versions:** Available since 2.0.</span></span>
