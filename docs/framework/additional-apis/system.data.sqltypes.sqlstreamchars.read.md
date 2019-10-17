---
title: SqlStreamChars. Read (Char [], Int32, Int32) メソッド (SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Read
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 9c8a1526e75fdc304022e74a7cc52506762489ea
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395751"
---
# <a name="sqlstreamcharsreadchar-int32-int32-method"></a><span data-ttu-id="4ed58-102">SqlStreamChars. Read (Char [], Int32, Int32) メソッド</span><span class="sxs-lookup"><span data-stu-id="4ed58-102">SqlStreamChars.Read(Char[], Int32, Int32) Method</span></span>

<span data-ttu-id="4ed58-103">派生クラスでオーバーライドされると、入力ストリームから次の文字セットを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="4ed58-103">When overridden in a derived class, reads the next set of characters from the input stream.</span></span> <span data-ttu-id="4ed58-104">このメソッドを含むアセンブリには、SQLAccess .dll とのフレンド関係があります。</span><span class="sxs-lookup"><span data-stu-id="4ed58-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="4ed58-105">SQL Server での使用を目的としています。</span><span class="sxs-lookup"><span data-stu-id="4ed58-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="4ed58-106">他のデータベースの場合は、そのデータベースによって提供されるホスティングメカニズムを使用します。</span><span class="sxs-lookup"><span data-stu-id="4ed58-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public abstract int Read (char[] buffer, int offset, int count);
```

## <a name="parameters"></a><span data-ttu-id="4ed58-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4ed58-107">Parameters</span></span>

`buffer`\
<span data-ttu-id="4ed58-108">読み取る文字配列。</span><span class="sxs-lookup"><span data-stu-id="4ed58-108">A char array to read.</span></span>

`offset`\
<span data-ttu-id="4ed58-109">Origin を基準とするオフセット。</span><span class="sxs-lookup"><span data-stu-id="4ed58-109">An offset relative to origin.</span></span>

`count`\
<span data-ttu-id="4ed58-110">現在のストリームから読み取る文字数。</span><span class="sxs-lookup"><span data-stu-id="4ed58-110">The number of characters to be read from the current stream.</span></span>

## <a name="returns"></a><span data-ttu-id="4ed58-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="4ed58-111">Returns</span></span>

<xref:System.Int32>\
<span data-ttu-id="4ed58-112">バッファーに読み取られた合計文字数。</span><span class="sxs-lookup"><span data-stu-id="4ed58-112">The total number of characters read into the buffer.</span></span>

## <a name="remarks"></a><span data-ttu-id="4ed58-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="4ed58-113">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="4ed58-114">@No__t-0 メソッドはプライベートであり、コード内で直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="4ed58-114">The `SqlStreamChars.Read` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="4ed58-115">Microsoft では、どのような状況でも、実稼働アプリケーションでこの方法を使用することはサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="4ed58-115">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="4ed58-116">［要件］</span><span class="sxs-lookup"><span data-stu-id="4ed58-116">Requirements</span></span>

<span data-ttu-id="4ed58-117">**名前空間:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="4ed58-117">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="4ed58-118">**アセンブリ:** System.string (System. Data. .dll)</span><span class="sxs-lookup"><span data-stu-id="4ed58-118">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="4ed58-119">**.NET Framework のバージョン:** 2.0 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="4ed58-119">**.NET Framework versions:** Available since 2.0.</span></span>
