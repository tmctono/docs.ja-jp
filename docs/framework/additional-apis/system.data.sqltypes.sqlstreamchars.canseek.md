---
title: SqlStreamChars.CanSeek プロパティ (System.Data.SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/19/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.CanSeek
- System.Data.SqlTypes.SqlStreamChars.get_CanSeek
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: b85e21c6bc89d2a00ff8d302f67a3d074d5e7b8f
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65634384"
---
# <a name="sqlstreamcharscanseek-property"></a><span data-ttu-id="5a6a9-102">SqlStreamChars.CanSeek プロパティ</span><span class="sxs-lookup"><span data-stu-id="5a6a9-102">SqlStreamChars.CanSeek Property</span></span>

<span data-ttu-id="5a6a9-103">派生クラスでオーバーライドされると、現在のストリームがシーク操作をサポートしているかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="5a6a9-103">When overridden in a derived class, gets a value that indicates whether the current steam supports the seek operation.</span></span> <span data-ttu-id="5a6a9-104">このプロパティが含まれるアセンブリには、SQLAccess.dll で友人関係があります。</span><span class="sxs-lookup"><span data-stu-id="5a6a9-104">The assembly that contains this property has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="5a6a9-105">SQL Server で使用するものでは。</span><span class="sxs-lookup"><span data-stu-id="5a6a9-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="5a6a9-106">その他のデータベースには、そのデータベースによって提供されるホスティング メカニズムを使用します。</span><span class="sxs-lookup"><span data-stu-id="5a6a9-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public abstract bool CanSeek { get; }
```

## <a name="property-value"></a><span data-ttu-id="5a6a9-107">プロパティの値</span><span class="sxs-lookup"><span data-stu-id="5a6a9-107">Property value</span></span>

<xref:System.Boolean>\
<span data-ttu-id="5a6a9-108">`true` 現在のストリームがシーク操作をサポートしている場合それ以外の場合、`false`します。</span><span class="sxs-lookup"><span data-stu-id="5a6a9-108">`true` if the current steam supports the seek operation; otherwise, `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="5a6a9-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="5a6a9-109">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="5a6a9-110">`SqlStreamChars.CanSeek`プロパティはプライベートであり、コード内で直接使用するものではありません。</span><span class="sxs-lookup"><span data-stu-id="5a6a9-110">The `SqlStreamChars.CanSeek` property is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="5a6a9-111">Microsoft はいかなる運用アプリケーションでこのフィールドの使用をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="5a6a9-111">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="5a6a9-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="5a6a9-112">Requirements</span></span>

<span data-ttu-id="5a6a9-113">**名前空間:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="5a6a9-113">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="5a6a9-114">**アセンブリ:** System.Data (system.data.dll 内)</span><span class="sxs-lookup"><span data-stu-id="5a6a9-114">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="5a6a9-115">**.NET framework のバージョン:** 2.0 以降で使用可能です。</span><span class="sxs-lookup"><span data-stu-id="5a6a9-115">**.NET Framework versions:** Available since 2.0.</span></span>
