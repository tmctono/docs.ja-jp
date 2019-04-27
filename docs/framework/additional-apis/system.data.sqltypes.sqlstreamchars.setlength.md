---
title: SqlStreamChars.SetLength(Int64) メソッド (System.Data.SqlTypes)
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
ms.openlocfilehash: 1283fea83cf77bbc898d460feedc72b898a65fb7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61675176"
---
# <a name="sqlstreamcharssetlengthint64-method"></a><span data-ttu-id="d548d-102">SqlStreamChars.SetLength(Int64) メソッド</span><span class="sxs-lookup"><span data-stu-id="d548d-102">SqlStreamChars.SetLength(Int64) Method</span></span>

<span data-ttu-id="d548d-103">派生クラスでオーバーライドされると、ストリームで使用されるリソースを解放します。</span><span class="sxs-lookup"><span data-stu-id="d548d-103">When overridden in a derived class, releases the resources used by the stream.</span></span> <span data-ttu-id="d548d-104">このメソッドを含むアセンブリには、SQLAccess.dll で友人関係があります。</span><span class="sxs-lookup"><span data-stu-id="d548d-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="d548d-105">SQL Server で使用するものでは。</span><span class="sxs-lookup"><span data-stu-id="d548d-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="d548d-106">その他のデータベースには、そのデータベースによって提供されるホスティング メカニズムを使用します。</span><span class="sxs-lookup"><span data-stu-id="d548d-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public abstract void SetLength (long value);
```

## <a name="parameters"></a><span data-ttu-id="d548d-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d548d-107">Parameters</span></span>

`value`\
<span data-ttu-id="d548d-108">現在のストリームの希望の長さ (バイト数)。</span><span class="sxs-lookup"><span data-stu-id="d548d-108">The desired length of the current stream in bytes.</span></span>

## <a name="remarks"></a><span data-ttu-id="d548d-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="d548d-109">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="d548d-110">`SqlStreamChars.SetLength`メソッドはプライベートであり、コード内で直接使用するものではありません。</span><span class="sxs-lookup"><span data-stu-id="d548d-110">The `SqlStreamChars.SetLength` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="d548d-111">Microsoft はいかなる運用アプリケーションでこのフィールドの使用をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="d548d-111">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="d548d-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="d548d-112">Requirements</span></span>

<span data-ttu-id="d548d-113">**名前空間:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="d548d-113">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="d548d-114">**アセンブリ:** System.Data (system.data.dll 内)</span><span class="sxs-lookup"><span data-stu-id="d548d-114">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="d548d-115">**.NET framework のバージョン:** 2.0 以降で使用可能です。</span><span class="sxs-lookup"><span data-stu-id="d548d-115">**.NET Framework versions:** Available since 2.0.</span></span>