---
title: SqlStreamChars. Write (Char [], Int32, Int32) メソッド (SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Write
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 9d952041122ceb3824712bd81cab7ce4789c9db8
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395585"
---
# <a name="sqlstreamcharswritechar-int32-int32-method"></a><span data-ttu-id="cbce3-102">SqlStreamChars. Write (Char [], Int32, Int32) メソッド</span><span class="sxs-lookup"><span data-stu-id="cbce3-102">SqlStreamChars.Write(Char[], Int32, Int32) Method</span></span>

<span data-ttu-id="cbce3-103">派生クラスでオーバーライドされた場合、現在のストリームに文字シーケンスを書き込み、書き込んだ文字数だけストリーム内の現在位置を進めます。</span><span class="sxs-lookup"><span data-stu-id="cbce3-103">When overridden in a derived class, writes a sequence of characters to the current stream and advances the current position within this stream by the number of characters written.</span></span> <span data-ttu-id="cbce3-104">このメソッドを含むアセンブリには、SQLAccess .dll とのフレンド関係があります。</span><span class="sxs-lookup"><span data-stu-id="cbce3-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="cbce3-105">SQL Server での使用を目的としています。</span><span class="sxs-lookup"><span data-stu-id="cbce3-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="cbce3-106">他のデータベースの場合は、そのデータベースによって提供されるホスティングメカニズムを使用します。</span><span class="sxs-lookup"><span data-stu-id="cbce3-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public abstract void Write (char[] buffer, int offset, int count);
```

## <a name="parameters"></a><span data-ttu-id="cbce3-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="cbce3-107">Parameters</span></span>

`buffer`  
<span data-ttu-id="cbce3-108">書き込む文字配列。</span><span class="sxs-lookup"><span data-stu-id="cbce3-108">A char array to write.</span></span>

`offset`  
<span data-ttu-id="cbce3-109">Origin を基準とするオフセット。</span><span class="sxs-lookup"><span data-stu-id="cbce3-109">An offset relative to origin.</span></span>

`count`  
<span data-ttu-id="cbce3-110">現在のストリームに書き込む文字数。</span><span class="sxs-lookup"><span data-stu-id="cbce3-110">The number of characters to be written to the current stream.</span></span>

## <a name="remarks"></a><span data-ttu-id="cbce3-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="cbce3-111">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="cbce3-112">@No__t-0 メソッドはプライベートであり、コード内で直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="cbce3-112">The `SqlStreamChars.Write` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="cbce3-113">Microsoft では、この方法を使用した運用アプリケーションの作成をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="cbce3-113">Microsoft does not support the use of this method write in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="cbce3-114">［要件］</span><span class="sxs-lookup"><span data-stu-id="cbce3-114">Requirements</span></span>

<span data-ttu-id="cbce3-115">**名前空間:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="cbce3-115">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="cbce3-116">**アセンブリ:** System.string (System. Data. .dll)</span><span class="sxs-lookup"><span data-stu-id="cbce3-116">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="cbce3-117">**.NET Framework のバージョン:** 2.0 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="cbce3-117">**.NET Framework versions:** Available since 2.0.</span></span>
