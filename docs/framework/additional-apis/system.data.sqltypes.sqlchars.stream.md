---
title: SqlChars.Stream プロパティ (System.Data.SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/19/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlChars.Stream
- System.Data.SqlTypes.SqlChars.get_Stream
- System.Data.SqlTypes.SqlChars.set_Stream
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 4858d9f8878e5b56a0811edf92a2faa729775156
ms.sourcegitcommit: d938c39afb9216db377d0f0ecdaa53936a851059
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/29/2019
ms.locfileid: "58633999"
---
# <a name="sqlcharsstream-property"></a><span data-ttu-id="853e8-102">SqlChars.Stream プロパティ</span><span class="sxs-lookup"><span data-stu-id="853e8-102">SqlChars.Stream Property</span></span>

<span data-ttu-id="853e8-103">取得または文字のストリームを設定します。</span><span class="sxs-lookup"><span data-stu-id="853e8-103">Gets or sets the character stream.</span></span> <span data-ttu-id="853e8-104">このプロパティが含まれるアセンブリには、SQLAccess.dll で友人関係があります。</span><span class="sxs-lookup"><span data-stu-id="853e8-104">The assembly that contains this property has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="853e8-105">SQL Server で使用するものでは。</span><span class="sxs-lookup"><span data-stu-id="853e8-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="853e8-106">その他のデータベースには、そのデータベースによって提供されるホスティング メカニズムを使用します。</span><span class="sxs-lookup"><span data-stu-id="853e8-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
internal SqlStreamChars Stream { get; set; }
```

## <a name="property-value"></a><span data-ttu-id="853e8-107">プロパティの値</span><span class="sxs-lookup"><span data-stu-id="853e8-107">Property value</span></span>

`System.Data.SqlTypes.SqlStreamChars`\
<span data-ttu-id="853e8-108">文字のストリーム。</span><span class="sxs-lookup"><span data-stu-id="853e8-108">The character stream.</span></span>

## <a name="remarks"></a><span data-ttu-id="853e8-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="853e8-109">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="853e8-110">`SqlChars.Stream`プロパティは内部であり、コード内で直接使用するものではありません。</span><span class="sxs-lookup"><span data-stu-id="853e8-110">The `SqlChars.Stream` property is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="853e8-111">Microsoft はいかなる運用アプリケーションでこのプロパティの使用をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="853e8-111">Microsoft does not support the use of this property in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="853e8-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="853e8-112">Requirements</span></span>

<span data-ttu-id="853e8-113">**名前空間:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="853e8-113">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="853e8-114">**アセンブリ:** System.Data (system.data.dll 内)</span><span class="sxs-lookup"><span data-stu-id="853e8-114">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="853e8-115">**.NET framework のバージョン:** 2.0 以降で使用可能です。</span><span class="sxs-lookup"><span data-stu-id="853e8-115">**.NET Framework versions:** Available since 2.0.</span></span>