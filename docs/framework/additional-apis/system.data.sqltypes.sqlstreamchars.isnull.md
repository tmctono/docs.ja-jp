---
title: SqlStreamChars. IsNull プロパティ (SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/19/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.IsNull
- System.Data.SqlTypes.SqlStreamChars.get_IsNull
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: d80f653724b3ef0a1cadb69a5f72b1d9455597d6
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395736"
---
# <a name="sqlstreamcharsisnull-property"></a><span data-ttu-id="30936-102">SqlStreamChars. IsNull プロパティ</span><span class="sxs-lookup"><span data-stu-id="30936-102">SqlStreamChars.IsNull Property</span></span>

<span data-ttu-id="30936-103">派生クラスでオーバーライドされた場合、ストリームが @no__t 0 かどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="30936-103">When overridden in a derived class, gets a value that indicates whether the stream is `null`.</span></span> <span data-ttu-id="30936-104">このプロパティを含むアセンブリには、SQLAccess .dll とのフレンド関係があります。</span><span class="sxs-lookup"><span data-stu-id="30936-104">The assembly that contains this property has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="30936-105">SQL Server での使用を目的としています。</span><span class="sxs-lookup"><span data-stu-id="30936-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="30936-106">他のデータベースの場合は、そのデータベースによって提供されるホスティングメカニズムを使用します。</span><span class="sxs-lookup"><span data-stu-id="30936-106">For other databases, use the hosting mechanism provided by that database.</span></span>

## <a name="syntax"></a><span data-ttu-id="30936-107">構文</span><span class="sxs-lookup"><span data-stu-id="30936-107">Syntax</span></span>

```csharp
public abstract bool IsNull { get; }
```

## <a name="property-value"></a><span data-ttu-id="30936-108">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="30936-108">Property value</span></span>

<xref:System.Boolean>\
<span data-ttu-id="30936-109">`true` の場合、ストリームが `null` です。それ以外の場合は、`false` です。</span><span class="sxs-lookup"><span data-stu-id="30936-109">`true` if the stream is `null`; otherwise, `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="30936-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="30936-110">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="30936-111">@No__t-0 プロパティはプライベートであり、コードで直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="30936-111">The `SqlStreamChars.IsNull` property is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="30936-112">Microsoft では、どのような状況でも、実稼働アプリケーションでのこのプロパティの使用はサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="30936-112">Microsoft does not support the use of this property in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="30936-113">［要件］</span><span class="sxs-lookup"><span data-stu-id="30936-113">Requirements</span></span>

<span data-ttu-id="30936-114">**名前空間:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="30936-114">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="30936-115">**アセンブリ:** System.string (System. Data. .dll)</span><span class="sxs-lookup"><span data-stu-id="30936-115">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="30936-116">**.NET Framework のバージョン:** 2.0 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="30936-116">**.NET Framework versions:** Available since 2.0.</span></span>
