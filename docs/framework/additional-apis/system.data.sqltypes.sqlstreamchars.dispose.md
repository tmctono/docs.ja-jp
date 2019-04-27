---
title: SqlStreamChars.Dispose(Boolean) メソッド (System.Data.SqlTypes)
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
ms.openlocfilehash: cc8df68a608000d89dd322b0d396504483bbf372
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61675157"
---
# <a name="sqlstreamcharsdisposeboolean-method"></a><span data-ttu-id="02b37-102">SqlStreamChars.Dispose(Boolean) メソッド</span><span class="sxs-lookup"><span data-stu-id="02b37-102">SqlStreamChars.Dispose(Boolean) Method</span></span>

<span data-ttu-id="02b37-103">派生クラスでオーバーライドされると、ストリームで使用されるリソースを解放します。</span><span class="sxs-lookup"><span data-stu-id="02b37-103">When overridden in a derived class, releases the resources used by the stream.</span></span> <span data-ttu-id="02b37-104">このメソッドを含むアセンブリには、SQLAccess.dll で友人関係があります。</span><span class="sxs-lookup"><span data-stu-id="02b37-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="02b37-105">SQL Server で使用するものでは。</span><span class="sxs-lookup"><span data-stu-id="02b37-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="02b37-106">その他のデータベースには、そのデータベースによって提供されるホスティング メカニズムを使用します。</span><span class="sxs-lookup"><span data-stu-id="02b37-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
protected virtual void Dispose (bool disposing);
```

## <a name="parameters"></a><span data-ttu-id="02b37-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="02b37-107">Parameters</span></span>

`disposing`\
<span data-ttu-id="02b37-108">マネージド リソースとアンマネージド リソースの両方を解放する場合は `true`。アンマネージド リソースだけを解放する場合は `false`。</span><span class="sxs-lookup"><span data-stu-id="02b37-108">`true` to release both managed and unmanaged resources; `false` to release only unmanaged resources.</span></span>

## <a name="remarks"></a><span data-ttu-id="02b37-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="02b37-109">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="02b37-110">`SqlStreamChars.Dispose`メソッドはプライベートであり、コード内で直接使用するものではありません。</span><span class="sxs-lookup"><span data-stu-id="02b37-110">The `SqlStreamChars.Dispose` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="02b37-111">Microsoft はいかなる運用アプリケーションでこのフィールドの使用をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="02b37-111">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="02b37-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="02b37-112">Requirements</span></span>

<span data-ttu-id="02b37-113">**名前空間:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="02b37-113">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="02b37-114">**アセンブリ:** System.Data (system.data.dll 内)</span><span class="sxs-lookup"><span data-stu-id="02b37-114">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="02b37-115">**.NET framework のバージョン:** 2.0 以降で使用可能です。</span><span class="sxs-lookup"><span data-stu-id="02b37-115">**.NET Framework versions:** Available since 2.0.</span></span>