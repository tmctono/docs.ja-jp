---
title: SqlStreamChars.IsNull プロパティ (System.Data.SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/19/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.IsNull
- System.Data.SqlTypes.SqlStreamChars.get_IsNull
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 03b702b0ffe258eb8cad0a1ece5314b363f9a0d0
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65634612"
---
# <a name="sqlstreamcharsisnull-property"></a><span data-ttu-id="123ec-102">SqlStreamChars.IsNull プロパティ</span><span class="sxs-lookup"><span data-stu-id="123ec-102">SqlStreamChars.IsNull Property</span></span>

<span data-ttu-id="123ec-103">派生クラスでオーバーライドされると、ストリームがあるかどうかを示す値を取得します。`null`します。</span><span class="sxs-lookup"><span data-stu-id="123ec-103">When overridden in a derived class, gets a value that indicates whether the stream is `null`.</span></span> <span data-ttu-id="123ec-104">このプロパティが含まれるアセンブリには、SQLAccess.dll で友人関係があります。</span><span class="sxs-lookup"><span data-stu-id="123ec-104">The assembly that contains this property has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="123ec-105">SQL Server で使用するものでは。</span><span class="sxs-lookup"><span data-stu-id="123ec-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="123ec-106">その他のデータベースには、そのデータベースによって提供されるホスティング メカニズムを使用します。</span><span class="sxs-lookup"><span data-stu-id="123ec-106">For other databases, use the hosting mechanism provided by that database.</span></span>

## <a name="syntax"></a><span data-ttu-id="123ec-107">構文</span><span class="sxs-lookup"><span data-stu-id="123ec-107">Syntax</span></span>

```csharp
public abstract bool IsNull { get; }
```

## <a name="property-value"></a><span data-ttu-id="123ec-108">プロパティの値</span><span class="sxs-lookup"><span data-stu-id="123ec-108">Property value</span></span>

<xref:System.Boolean>\
<span data-ttu-id="123ec-109">`true` ストリームの場合`null`、それ以外の`false`します。</span><span class="sxs-lookup"><span data-stu-id="123ec-109">`true` if the stream is `null`; otherwise, `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="123ec-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="123ec-110">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="123ec-111">`SqlStreamChars.IsNull`プロパティはプライベートであり、コード内で直接使用するものではありません。</span><span class="sxs-lookup"><span data-stu-id="123ec-111">The `SqlStreamChars.IsNull` property is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="123ec-112">Microsoft はいかなる運用アプリケーションでこのフィールドの使用をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="123ec-112">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="123ec-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="123ec-113">Requirements</span></span>

<span data-ttu-id="123ec-114">**名前空間:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="123ec-114">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="123ec-115">**アセンブリ:** System.Data (system.data.dll 内)</span><span class="sxs-lookup"><span data-stu-id="123ec-115">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="123ec-116">**.NET framework のバージョン:** 2.0 以降で使用可能です。</span><span class="sxs-lookup"><span data-stu-id="123ec-116">**.NET Framework versions:** Available since 2.0.</span></span>
