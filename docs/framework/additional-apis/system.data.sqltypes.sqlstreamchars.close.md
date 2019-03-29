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
ms.openlocfilehash: d0c29bbc5c6bea98cf36e3c2b6bf7825d6843ccc
ms.sourcegitcommit: d938c39afb9216db377d0f0ecdaa53936a851059
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/29/2019
ms.locfileid: "58634025"
---
# <a name="sqlstreamcharsclose-method"></a><span data-ttu-id="93cb8-102">SqlStreamChars.Close メソッド</span><span class="sxs-lookup"><span data-stu-id="93cb8-102">SqlStreamChars.Close Method</span></span>

<span data-ttu-id="93cb8-103">現在のストリームを終了し、ストリームに関連付けられているすべてのシステム リソースを解放します。</span><span class="sxs-lookup"><span data-stu-id="93cb8-103">Closes the current stream and releases any system resources associated with the stream.</span></span> <span data-ttu-id="93cb8-104">このメソッドを含むアセンブリには、SQLAccess.dll で友人関係があります。</span><span class="sxs-lookup"><span data-stu-id="93cb8-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="93cb8-105">SQL Server で使用するものでは。</span><span class="sxs-lookup"><span data-stu-id="93cb8-105">It's intended for use by SQL Server.</span></span><span data-ttu-id="93cb8-106"> その他のデータベースには、そのデータベースによって提供されるホスティング メカニズムを使用します。</span><span class="sxs-lookup"><span data-stu-id="93cb8-106"> For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public virtual void Close ();
```

## <a name="remarks"></a><span data-ttu-id="93cb8-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="93cb8-107">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="93cb8-108">`SqlStreamChars.Close`メソッドはプライベートであり、コード内で直接使用するものではありません。</span><span class="sxs-lookup"><span data-stu-id="93cb8-108">The `SqlStreamChars.Close` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="93cb8-109">Microsoft はいかなる運用アプリケーションでこのフィールドの使用をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="93cb8-109">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="93cb8-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="93cb8-110">Requirements</span></span>

<span data-ttu-id="93cb8-111">**名前空間:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="93cb8-111">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="93cb8-112">**アセンブリ:** System.Data (system.data.dll 内)</span><span class="sxs-lookup"><span data-stu-id="93cb8-112">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="93cb8-113">**.NET framework のバージョン:** 2.0 以降で使用可能です。</span><span class="sxs-lookup"><span data-stu-id="93cb8-113">**.NET Framework versions:** Available since 2.0.</span></span>