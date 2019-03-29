---
title: SmiOrderProperty.Item プロパティ (Microsoft.SqlServer.Server)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- Microsoft.SqlServer.Server.SmiOrderProperty.Item
- Microsoft.SqlServer.Server.SmiOrderProperty.get_Item
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 499522a11cac744c14ac32cf3bfe485a46b19d93
ms.sourcegitcommit: d938c39afb9216db377d0f0ecdaa53936a851059
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/29/2019
ms.locfileid: "58634324"
---
# <a name="smiorderpropertyitem-property"></a><span data-ttu-id="5462c-102">SmiOrderProperty.Item プロパティ</span><span class="sxs-lookup"><span data-stu-id="5462c-102">SmiOrderProperty.Item Property</span></span>

<span data-ttu-id="5462c-103">エンティティの列の順序を取得します。</span><span class="sxs-lookup"><span data-stu-id="5462c-103">Gets the column order for the entity.</span></span> <span data-ttu-id="5462c-104">このプロパティが含まれるアセンブリには、SQLAccess.dll で友人関係があります。</span><span class="sxs-lookup"><span data-stu-id="5462c-104">The assembly that contains this property has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="5462c-105">SQL Server で使用するものでは。</span><span class="sxs-lookup"><span data-stu-id="5462c-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="5462c-106">その他のデータベースには、そのデータベースによって提供されるホスティング メカニズムを使用します。</span><span class="sxs-lookup"><span data-stu-id="5462c-106">For other databases, use the hosting mechanism provided by that database.</span></span>

## <a name="syntax"></a><span data-ttu-id="5462c-107">構文</span><span class="sxs-lookup"><span data-stu-id="5462c-107">Syntax</span></span>

```csharp
internal SmiColumnOrder Item { get; }
```

## <a name="property-value"></a><span data-ttu-id="5462c-108">プロパティの値</span><span class="sxs-lookup"><span data-stu-id="5462c-108">Property value</span></span>

<span data-ttu-id="5462c-109">列の順序。</span><span class="sxs-lookup"><span data-stu-id="5462c-109">The column order.</span></span>

## <a name="remarks"></a><span data-ttu-id="5462c-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="5462c-110">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="5462c-111">`SmiOrderProperty.Item`プロパティは内部であり、コード内で直接使用するものではありません。</span><span class="sxs-lookup"><span data-stu-id="5462c-111">The `SmiOrderProperty.Item` property is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="5462c-112">Microsoft はいかなる運用アプリケーションでこのプロパティの使用をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="5462c-112">Microsoft does not support the use of this property in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="5462c-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="5462c-113">Requirements</span></span>

<span data-ttu-id="5462c-114">**名前空間:** <xref:Microsoft.SqlServer.Server></span><span class="sxs-lookup"><span data-stu-id="5462c-114">**Namespace:** <xref:Microsoft.SqlServer.Server></span></span>

<span data-ttu-id="5462c-115">**アセンブリ:** System.Data (system.data.dll 内)</span><span class="sxs-lookup"><span data-stu-id="5462c-115">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="5462c-116">**.NET framework のバージョン:** 2.0 以降で使用可能です。</span><span class="sxs-lookup"><span data-stu-id="5462c-116">**.NET Framework versions:** Available since 2.0.</span></span>