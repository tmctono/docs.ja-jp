---
title: SqlStreamChars. Dispose (Boolean) メソッド (SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Dispose
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 44dc97835b8a7141064e8de4d2d5325c40be5a34
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395767"
---
# <a name="sqlstreamcharsdisposeboolean-method"></a><span data-ttu-id="34caa-102">SqlStreamChars. Dispose (Boolean) メソッド</span><span class="sxs-lookup"><span data-stu-id="34caa-102">SqlStreamChars.Dispose(Boolean) Method</span></span>

<span data-ttu-id="34caa-103">派生クラスでオーバーライドされると、ストリームによって使用されるリソースを解放します。</span><span class="sxs-lookup"><span data-stu-id="34caa-103">When overridden in a derived class, releases the resources used by the stream.</span></span> <span data-ttu-id="34caa-104">このメソッドを含むアセンブリには、SQLAccess .dll とのフレンド関係があります。</span><span class="sxs-lookup"><span data-stu-id="34caa-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="34caa-105">SQL Server での使用を目的としています。</span><span class="sxs-lookup"><span data-stu-id="34caa-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="34caa-106">他のデータベースの場合は、そのデータベースによって提供されるホスティングメカニズムを使用します。</span><span class="sxs-lookup"><span data-stu-id="34caa-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
protected virtual void Dispose (bool disposing);
```

## <a name="parameters"></a><span data-ttu-id="34caa-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="34caa-107">Parameters</span></span>

`disposing`\
<span data-ttu-id="34caa-108">マネージド リソースとアンマネージド リソースの両方を解放する場合は `true`。アンマネージド リソースだけを解放する場合は `false`。</span><span class="sxs-lookup"><span data-stu-id="34caa-108">`true` to release both managed and unmanaged resources; `false` to release only unmanaged resources.</span></span>

## <a name="remarks"></a><span data-ttu-id="34caa-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="34caa-109">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="34caa-110">@No__t-0 メソッドはプライベートであり、コード内で直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="34caa-110">The `SqlStreamChars.Dispose` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="34caa-111">Microsoft では、どのような状況でも、実稼働アプリケーションでこの方法を使用することはサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="34caa-111">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="34caa-112">［要件］</span><span class="sxs-lookup"><span data-stu-id="34caa-112">Requirements</span></span>

<span data-ttu-id="34caa-113">**名前空間:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="34caa-113">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="34caa-114">**アセンブリ:** System.string (System. Data. .dll)</span><span class="sxs-lookup"><span data-stu-id="34caa-114">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="34caa-115">**.NET Framework のバージョン:** 2.0 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="34caa-115">**.NET Framework versions:** Available since 2.0.</span></span>
