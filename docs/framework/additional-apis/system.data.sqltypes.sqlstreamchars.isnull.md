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
ms.openlocfilehash: ec00b0afa1597c3ae6488c12fe5a0667dad70e2d
ms.sourcegitcommit: d938c39afb9216db377d0f0ecdaa53936a851059
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/29/2019
ms.locfileid: "58634337"
---
# <a name="sqlstreamcharsisnull-property"></a><span data-ttu-id="60a57-102">SqlStreamChars.IsNull プロパティ</span><span class="sxs-lookup"><span data-stu-id="60a57-102">SqlStreamChars.IsNull Property</span></span>

<span data-ttu-id="60a57-103">派生クラスでオーバーライドされると、ストリームがあるかどうかを示す値を取得します。`null`します。</span><span class="sxs-lookup"><span data-stu-id="60a57-103">When overridden in a derived class, gets a value that indicates whether the stream is `null`.</span></span> <span data-ttu-id="60a57-104">このプロパティが含まれるアセンブリには、SQLAccess.dll で友人関係があります。</span><span class="sxs-lookup"><span data-stu-id="60a57-104">The assembly that contains this property has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="60a57-105">SQL Server で使用するものでは。</span><span class="sxs-lookup"><span data-stu-id="60a57-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="60a57-106">その他のデータベースには、そのデータベースによって提供されるホスティング メカニズムを使用します。</span><span class="sxs-lookup"><span data-stu-id="60a57-106">For other databases, use the hosting mechanism provided by that database.</span></span>

## <a name="syntax"></a><span data-ttu-id="60a57-107">構文</span><span class="sxs-lookup"><span data-stu-id="60a57-107">Syntax</span></span>

```csharp
public abstract bool IsNull { get; }
```

## <a name="property-value"></a><span data-ttu-id="60a57-108">プロパティの値</span><span class="sxs-lookup"><span data-stu-id="60a57-108">Property value</span></span>

<xref:System.Boolean>\
<span data-ttu-id="60a57-109">`true` ストリームの場合`null`、それ以外の`false`します。</span><span class="sxs-lookup"><span data-stu-id="60a57-109">`true` if the stream is `null`; otherwise, `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="60a57-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="60a57-110">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="60a57-111">`SqlStreamChars.IsNull`プロパティはプライベートであり、コード内で直接使用するものではありません。</span><span class="sxs-lookup"><span data-stu-id="60a57-111">The `SqlStreamChars.IsNull` property is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="60a57-112">Microsoft はいかなる運用アプリケーションでこのフィールドの使用をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="60a57-112">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="60a57-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="60a57-113">Requirements</span></span>

<span data-ttu-id="60a57-114">**名前空間:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="60a57-114">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="60a57-115">**アセンブリ:** System.Data (system.data.dll 内)</span><span class="sxs-lookup"><span data-stu-id="60a57-115">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="60a57-116">**.NET framework のバージョン:** 2.0 以降で使用可能です。</span><span class="sxs-lookup"><span data-stu-id="60a57-116">**.NET Framework versions:** Available since 2.0.</span></span>