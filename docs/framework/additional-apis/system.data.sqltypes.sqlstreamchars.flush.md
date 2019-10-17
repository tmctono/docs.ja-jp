---
title: SqlStreamChars. Flush メソッド (SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Flush
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 38ade5ce38cfe5003b2d06c0d8bb2db1a20bc05b
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395623"
---
# <a name="sqlstreamcharsflush-method"></a><span data-ttu-id="f9555-102">SqlStreamChars. Flush メソッド</span><span class="sxs-lookup"><span data-stu-id="f9555-102">SqlStreamChars.Flush Method</span></span>

<span data-ttu-id="f9555-103">派生クラスによってオーバーライドされた場合は、ストリームに対応するすべてのバッファーをクリアし、バッファー内のデータを基になるデバイスに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="f9555-103">When overridden in a derived class, clears all buffers for this stream and causes any buffered data to be written to the underlying device.</span></span> <span data-ttu-id="f9555-104">このメソッドを含むアセンブリには、SQLAccess .dll とのフレンド関係があります。</span><span class="sxs-lookup"><span data-stu-id="f9555-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="f9555-105">SQL Server での使用を目的としています。</span><span class="sxs-lookup"><span data-stu-id="f9555-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="f9555-106">他のデータベースの場合は、そのデータベースによって提供されるホスティングメカニズムを使用します。</span><span class="sxs-lookup"><span data-stu-id="f9555-106">For other databases, use the hosting mechanism provided by that database.</span></span>

## <a name="syntax"></a><span data-ttu-id="f9555-107">構文</span><span class="sxs-lookup"><span data-stu-id="f9555-107">Syntax</span></span>

```csharp
public abstract void Flush ();
```

## <a name="remarks"></a><span data-ttu-id="f9555-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="f9555-108">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="f9555-109">@No__t-0 メソッドはプライベートであり、コード内で直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="f9555-109">The `SqlStreamChars.Flush` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="f9555-110">Microsoft では、どのような状況でも、実稼働アプリケーションでこの方法を使用することはサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="f9555-110">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="f9555-111">［要件］</span><span class="sxs-lookup"><span data-stu-id="f9555-111">Requirements</span></span>

<span data-ttu-id="f9555-112">**名前空間:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="f9555-112">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="f9555-113">**アセンブリ:** System.string (System. Data. .dll)</span><span class="sxs-lookup"><span data-stu-id="f9555-113">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="f9555-114">**.NET Framework のバージョン:** 2.0 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="f9555-114">**.NET Framework versions:** Available since 2.0.</span></span>
