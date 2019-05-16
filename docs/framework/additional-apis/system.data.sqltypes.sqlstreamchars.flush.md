---
title: SqlStreamChars.Flush メソッド (System.Data.SqlTypes)
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
ms.openlocfilehash: 411bd0036de904dd485d9fb54fa5fd45e3b55dbb
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65634331"
---
# <a name="sqlstreamcharsflush-method"></a><span data-ttu-id="6fa05-102">SqlStreamChars.Flush メソッド</span><span class="sxs-lookup"><span data-stu-id="6fa05-102">SqlStreamChars.Flush Method</span></span>

<span data-ttu-id="6fa05-103">派生クラスによってオーバーライドされた場合は、ストリームに対応するすべてのバッファーをクリアし、バッファー内のデータを基になるデバイスに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="6fa05-103">When overridden in a derived class, clears all buffers for this stream and causes any buffered data to be written to the underlying device.</span></span> <span data-ttu-id="6fa05-104">このメソッドを含むアセンブリには、SQLAccess.dll で友人関係があります。</span><span class="sxs-lookup"><span data-stu-id="6fa05-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="6fa05-105">SQL Server で使用するものでは。</span><span class="sxs-lookup"><span data-stu-id="6fa05-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="6fa05-106">その他のデータベースには、そのデータベースによって提供されるホスティング メカニズムを使用します。</span><span class="sxs-lookup"><span data-stu-id="6fa05-106">For other databases, use the hosting mechanism provided by that database.</span></span>

## <a name="syntax"></a><span data-ttu-id="6fa05-107">構文</span><span class="sxs-lookup"><span data-stu-id="6fa05-107">Syntax</span></span>

```csharp
public abstract void Flush ();
```

## <a name="remarks"></a><span data-ttu-id="6fa05-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="6fa05-108">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="6fa05-109">`SqlStreamChars.Flush`メソッドはプライベートであり、コード内で直接使用するものではありません。</span><span class="sxs-lookup"><span data-stu-id="6fa05-109">The `SqlStreamChars.Flush` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="6fa05-110">Microsoft はいかなる運用アプリケーションでこのフィールドの使用をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="6fa05-110">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="6fa05-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="6fa05-111">Requirements</span></span>

<span data-ttu-id="6fa05-112">**名前空間:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="6fa05-112">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="6fa05-113">**アセンブリ:** System.Data (system.data.dll 内)</span><span class="sxs-lookup"><span data-stu-id="6fa05-113">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="6fa05-114">**.NET framework のバージョン:** 2.0 以降で使用可能です。</span><span class="sxs-lookup"><span data-stu-id="6fa05-114">**.NET Framework versions:** Available since 2.0.</span></span>
