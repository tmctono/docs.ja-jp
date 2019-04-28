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
ms.openlocfilehash: 52f88a3551e20c74d7a1144c3cd6859a023980db
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61675183"
---
# <a name="sqlstreamcharscanseek-property"></a><span data-ttu-id="be9ab-102">SqlStreamChars.CanSeek プロパティ</span><span class="sxs-lookup"><span data-stu-id="be9ab-102">SqlStreamChars.CanSeek Property</span></span>

<span data-ttu-id="be9ab-103">派生クラスでオーバーライドされると、現在のストリームがシーク操作をサポートしているかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="be9ab-103">When overridden in a derived class, gets a value that indicates whether the current steam supports the seek operation.</span></span> <span data-ttu-id="be9ab-104">このプロパティが含まれるアセンブリには、SQLAccess.dll で友人関係があります。</span><span class="sxs-lookup"><span data-stu-id="be9ab-104">The assembly that contains this property has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="be9ab-105">SQL Server で使用するものでは。</span><span class="sxs-lookup"><span data-stu-id="be9ab-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="be9ab-106">その他のデータベースには、そのデータベースによって提供されるホスティング メカニズムを使用します。</span><span class="sxs-lookup"><span data-stu-id="be9ab-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public abstract bool CanSeek { get; }
```

## <a name="property-value"></a><span data-ttu-id="be9ab-107">プロパティの値</span><span class="sxs-lookup"><span data-stu-id="be9ab-107">Property value</span></span>

<xref:System.Boolean>\
<span data-ttu-id="be9ab-108">`true` 現在のストリームがシーク操作をサポートしている場合それ以外の場合、`false`します。</span><span class="sxs-lookup"><span data-stu-id="be9ab-108">`true` if the current steam supports the seek operation; otherwise, `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="be9ab-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="be9ab-109">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="be9ab-110">`SqlStreamChars.CanSeek`プロパティはプライベートであり、コード内で直接使用するものではありません。</span><span class="sxs-lookup"><span data-stu-id="be9ab-110">The `SqlStreamChars.CanSeek` property is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="be9ab-111">Microsoft はいかなる運用アプリケーションでこのフィールドの使用をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="be9ab-111">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="be9ab-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="be9ab-112">Requirements</span></span>

<span data-ttu-id="be9ab-113">**名前空間:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="be9ab-113">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="be9ab-114">**アセンブリ:** System.Data (system.data.dll 内)</span><span class="sxs-lookup"><span data-stu-id="be9ab-114">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="be9ab-115">**.NET framework のバージョン:** 2.0 以降で使用可能です。</span><span class="sxs-lookup"><span data-stu-id="be9ab-115">**.NET Framework versions:** Available since 2.0.</span></span>