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
ms.sourcegitcommit: d938c39afb9216db377d0f0ecdaa53936a851059
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/29/2019
ms.locfileid: "58633947"
---
# <a name="sqlstreamcharssetlengthint64-method"></a><span data-ttu-id="73e74-102">SqlStreamChars.SetLength(Int64) メソッド</span><span class="sxs-lookup"><span data-stu-id="73e74-102">SqlStreamChars.SetLength(Int64) Method</span></span>

<span data-ttu-id="73e74-103">派生クラスでオーバーライドされると、ストリームで使用されるリソースを解放します。</span><span class="sxs-lookup"><span data-stu-id="73e74-103">When overridden in a derived class, releases the resources used by the stream.</span></span> <span data-ttu-id="73e74-104">このメソッドを含むアセンブリには、SQLAccess.dll で友人関係があります。</span><span class="sxs-lookup"><span data-stu-id="73e74-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="73e74-105">SQL Server で使用するものでは。</span><span class="sxs-lookup"><span data-stu-id="73e74-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="73e74-106">その他のデータベースには、そのデータベースによって提供されるホスティング メカニズムを使用します。</span><span class="sxs-lookup"><span data-stu-id="73e74-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public abstract void SetLength (long value);
```

## <a name="parameters"></a><span data-ttu-id="73e74-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="73e74-107">Parameters</span></span>

`value`\
<span data-ttu-id="73e74-108">現在のストリームの希望の長さ (バイト数)。</span><span class="sxs-lookup"><span data-stu-id="73e74-108">The desired length of the current stream in bytes.</span></span>

## <a name="remarks"></a><span data-ttu-id="73e74-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="73e74-109">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="73e74-110">`SqlStreamChars.SetLength`メソッドはプライベートであり、コード内で直接使用するものではありません。</span><span class="sxs-lookup"><span data-stu-id="73e74-110">The `SqlStreamChars.SetLength` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="73e74-111">Microsoft はいかなる運用アプリケーションでこのフィールドの使用をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="73e74-111">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="73e74-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="73e74-112">Requirements</span></span>

<span data-ttu-id="73e74-113">**名前空間:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="73e74-113">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="73e74-114">**アセンブリ:** System.Data (system.data.dll 内)</span><span class="sxs-lookup"><span data-stu-id="73e74-114">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="73e74-115">**.NET framework のバージョン:** 2.0 以降で使用可能です。</span><span class="sxs-lookup"><span data-stu-id="73e74-115">**.NET Framework versions:** Available since 2.0.</span></span>