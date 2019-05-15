---
title: SqlStreamChars.Close メソッド (System.Data.SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Close
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 942ee987f1c56abe2cb1718347886dd397e7217e
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65634341"
---
# <a name="sqlstreamcharsclose-method"></a><span data-ttu-id="3a709-102">SqlStreamChars.Close メソッド</span><span class="sxs-lookup"><span data-stu-id="3a709-102">SqlStreamChars.Close Method</span></span>

<span data-ttu-id="3a709-103">現在のストリームを終了し、ストリームに関連付けられているすべてのシステム リソースを解放します。</span><span class="sxs-lookup"><span data-stu-id="3a709-103">Closes the current stream and releases any system resources associated with the stream.</span></span> <span data-ttu-id="3a709-104">このメソッドを含むアセンブリには、SQLAccess.dll で友人関係があります。</span><span class="sxs-lookup"><span data-stu-id="3a709-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="3a709-105">SQL Server で使用するものでは。</span><span class="sxs-lookup"><span data-stu-id="3a709-105">It's intended for use by SQL Server.</span></span><span data-ttu-id="3a709-106"> その他のデータベースには、そのデータベースによって提供されるホスティング メカニズムを使用します。</span><span class="sxs-lookup"><span data-stu-id="3a709-106"> For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public virtual void Close ();
```

## <a name="remarks"></a><span data-ttu-id="3a709-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="3a709-107">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="3a709-108">`SqlStreamChars.Close`メソッドはプライベートであり、コード内で直接使用するものではありません。</span><span class="sxs-lookup"><span data-stu-id="3a709-108">The `SqlStreamChars.Close` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="3a709-109">Microsoft はいかなる運用アプリケーションでこのフィールドの使用をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="3a709-109">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="3a709-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="3a709-110">Requirements</span></span>

<span data-ttu-id="3a709-111">**名前空間:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="3a709-111">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="3a709-112">**アセンブリ:** System.Data (system.data.dll 内)</span><span class="sxs-lookup"><span data-stu-id="3a709-112">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="3a709-113">**.NET framework のバージョン:** 2.0 以降で使用可能です。</span><span class="sxs-lookup"><span data-stu-id="3a709-113">**.NET Framework versions:** Available since 2.0.</span></span>
