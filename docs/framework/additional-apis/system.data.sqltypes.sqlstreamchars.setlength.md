---
title: SqlStreamChars. SetLength (Int64) メソッド (SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.SetLength
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 291d6e9395581f2370dafc728521a314d54a686d
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395726"
---
# <a name="sqlstreamcharssetlengthint64-method"></a><span data-ttu-id="6e4ed-102">SetLength (Int64) メソッド</span><span class="sxs-lookup"><span data-stu-id="6e4ed-102">SqlStreamChars.SetLength(Int64) Method</span></span>

<span data-ttu-id="6e4ed-103">派生クラスでオーバーライドされると、ストリームによって使用されるリソースを解放します。</span><span class="sxs-lookup"><span data-stu-id="6e4ed-103">When overridden in a derived class, releases the resources used by the stream.</span></span> <span data-ttu-id="6e4ed-104">このメソッドを含むアセンブリには、SQLAccess .dll とのフレンド関係があります。</span><span class="sxs-lookup"><span data-stu-id="6e4ed-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="6e4ed-105">SQL Server での使用を目的としています。</span><span class="sxs-lookup"><span data-stu-id="6e4ed-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="6e4ed-106">他のデータベースの場合は、そのデータベースによって提供されるホスティングメカニズムを使用します。</span><span class="sxs-lookup"><span data-stu-id="6e4ed-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public abstract void SetLength (long value);
```

## <a name="parameters"></a><span data-ttu-id="6e4ed-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6e4ed-107">Parameters</span></span>

`value`\
<span data-ttu-id="6e4ed-108">現在のストリームの希望の長さ (バイト数)。</span><span class="sxs-lookup"><span data-stu-id="6e4ed-108">The desired length of the current stream in bytes.</span></span>

## <a name="remarks"></a><span data-ttu-id="6e4ed-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="6e4ed-109">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="6e4ed-110">@No__t-0 メソッドはプライベートであり、コード内で直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="6e4ed-110">The `SqlStreamChars.SetLength` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="6e4ed-111">Microsoft では、どのような状況でも、実稼働アプリケーションでこの方法を使用することはサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="6e4ed-111">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="6e4ed-112">［要件］</span><span class="sxs-lookup"><span data-stu-id="6e4ed-112">Requirements</span></span>

<span data-ttu-id="6e4ed-113">**名前空間:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="6e4ed-113">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="6e4ed-114">**アセンブリ:** System.string (System. Data. .dll)</span><span class="sxs-lookup"><span data-stu-id="6e4ed-114">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="6e4ed-115">**.NET Framework のバージョン:** 2.0 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="6e4ed-115">**.NET Framework versions:** Available since 2.0.</span></span>
