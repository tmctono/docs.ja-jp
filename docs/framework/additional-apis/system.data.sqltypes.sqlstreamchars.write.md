---
title: SqlStreamChars.Write (Char、Int32, Int32) メソッド (System.Data.SqlTypes)
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
ms.openlocfilehash: 4084c7161eaa91d78eab32f1c14624e0032cdfcf
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/30/2019
ms.locfileid: "58675758"
---
# <a name="sqlstreamcharswritechar-int32-int32-method"></a><span data-ttu-id="f1789-102">SqlStreamChars.Write (Char、Int32, Int32) メソッド</span><span class="sxs-lookup"><span data-stu-id="f1789-102">SqlStreamChars.Write(Char[], Int32, Int32) Method</span></span>

<span data-ttu-id="f1789-103">派生クラスでオーバーライドされると、現在のストリームに文字のシーケンスを書き込みし、書き込まれた文字数がこのストリーム内の現在位置を進めます。</span><span class="sxs-lookup"><span data-stu-id="f1789-103">When overridden in a derived class, writes a sequence of characters to the current stream and advances the current position within this stream by the number of characters written.</span></span> <span data-ttu-id="f1789-104">このメソッドを含むアセンブリには、SQLAccess.dll で友人関係があります。</span><span class="sxs-lookup"><span data-stu-id="f1789-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="f1789-105">SQL Server で使用するものでは。</span><span class="sxs-lookup"><span data-stu-id="f1789-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="f1789-106">その他のデータベースには、そのデータベースによって提供されるホスティング メカニズムを使用します。</span><span class="sxs-lookup"><span data-stu-id="f1789-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public abstract void Write (char[] buffer, int offset, int count);
```

## <a name="parameters"></a><span data-ttu-id="f1789-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f1789-107">Parameters</span></span>

`buffer`  
<span data-ttu-id="f1789-108">書き込む文字配列。</span><span class="sxs-lookup"><span data-stu-id="f1789-108">A char array to write.</span></span>

`offset`  
<span data-ttu-id="f1789-109">原点からのオフセット。</span><span class="sxs-lookup"><span data-stu-id="f1789-109">An offset relative to origin.</span></span>

`count`  
<span data-ttu-id="f1789-110">現在のストリームに書き込む文字数。</span><span class="sxs-lookup"><span data-stu-id="f1789-110">The number of characters to be written to the current stream.</span></span>

## <a name="remarks"></a><span data-ttu-id="f1789-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="f1789-111">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="f1789-112">`SqlStreamChars.Write`メソッドはプライベートであり、コード内で直接使用するものではありません。</span><span class="sxs-lookup"><span data-stu-id="f1789-112">The `SqlStreamChars.Write` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="f1789-113">Microsoft はいかなる運用アプリケーションでこのフィールドの使用をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="f1789-113">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="f1789-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="f1789-114">Requirements</span></span>

<span data-ttu-id="f1789-115">**名前空間:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="f1789-115">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="f1789-116">**アセンブリ:** System.Data (system.data.dll 内)</span><span class="sxs-lookup"><span data-stu-id="f1789-116">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="f1789-117">**.NET framework のバージョン:** 2.0 以降で使用可能です。</span><span class="sxs-lookup"><span data-stu-id="f1789-117">**.NET Framework versions:** Available since 2.0.</span></span>
