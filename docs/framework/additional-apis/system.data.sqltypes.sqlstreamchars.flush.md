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
ms.openlocfilehash: 8cd24a5ca420552f283da61ecd4edcad02965403
ms.sourcegitcommit: d938c39afb9216db377d0f0ecdaa53936a851059
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/29/2019
ms.locfileid: "58634194"
---
# <a name="sqlstreamcharsflush-method"></a><span data-ttu-id="bf41c-102">SqlStreamChars.Flush メソッド</span><span class="sxs-lookup"><span data-stu-id="bf41c-102">SqlStreamChars.Flush Method</span></span>

<span data-ttu-id="bf41c-103">派生クラスによってオーバーライドされた場合は、ストリームに対応するすべてのバッファーをクリアし、バッファー内のデータを基になるデバイスに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="bf41c-103">When overridden in a derived class, clears all buffers for this stream and causes any buffered data to be written to the underlying device.</span></span> <span data-ttu-id="bf41c-104">このメソッドを含むアセンブリには、SQLAccess.dll で友人関係があります。</span><span class="sxs-lookup"><span data-stu-id="bf41c-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="bf41c-105">SQL Server で使用するものでは。</span><span class="sxs-lookup"><span data-stu-id="bf41c-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="bf41c-106">その他のデータベースには、そのデータベースによって提供されるホスティング メカニズムを使用します。</span><span class="sxs-lookup"><span data-stu-id="bf41c-106">For other databases, use the hosting mechanism provided by that database.</span></span>

## <a name="syntax"></a><span data-ttu-id="bf41c-107">構文</span><span class="sxs-lookup"><span data-stu-id="bf41c-107">Syntax</span></span>

```csharp
public abstract void Flush ();
```

## <a name="remarks"></a><span data-ttu-id="bf41c-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="bf41c-108">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="bf41c-109">`SqlStreamChars.Flush`メソッドはプライベートであり、コード内で直接使用するものではありません。</span><span class="sxs-lookup"><span data-stu-id="bf41c-109">The `SqlStreamChars.Flush` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="bf41c-110">Microsoft はいかなる運用アプリケーションでこのフィールドの使用をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="bf41c-110">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="bf41c-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="bf41c-111">Requirements</span></span>

<span data-ttu-id="bf41c-112">**名前空間:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="bf41c-112">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="bf41c-113">**アセンブリ:** System.Data (system.data.dll 内)</span><span class="sxs-lookup"><span data-stu-id="bf41c-113">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="bf41c-114">**.NET framework のバージョン:** 2.0 以降で使用可能です。</span><span class="sxs-lookup"><span data-stu-id="bf41c-114">**.NET Framework versions:** Available since 2.0.</span></span>