---
title: ServicePoint. m_ConnectionGroupList フィールド
description: ServicePoint. m_ConnectionGroupList フィールドについて説明します。これは、各接続グループのハッシュテーブルであり、それぞれが .NET の ServicePoint URI の接続を保持します。
ms.date: 05/01/2017
topic_type:
- apiref
api_name:
- System.Net.ServicePoint.m_ConnectionGroupList
api_location:
- System.dll
api_type:
- Assembly
ms.assetid: df8afb59-f0f6-4ddc-b3c1-839b9fc601d8
ms.openlocfilehash: 0ebfeb782147f21abfde536b8053fa15b1e1a602
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2020
ms.locfileid: "84989708"
---
# <a name="servicepointm_connectiongrouplist-field"></a><span data-ttu-id="3a72c-103">ServicePoint. m \_ connectiongrouplist フィールド</span><span class="sxs-lookup"><span data-stu-id="3a72c-103">ServicePoint.m\_ConnectionGroupList Field</span></span>

<span data-ttu-id="3a72c-104">`ServicePoint.m_ConnectionGroupList`は、 <xref:System.Collections.Hashtable> それぞれの URI の接続を保持する接続グループのです <xref:System.Net.ServicePoint> 。</span><span class="sxs-lookup"><span data-stu-id="3a72c-104">`ServicePoint.m_ConnectionGroupList` is a <xref:System.Collections.Hashtable> of connection groups, each holding a connection for the <xref:System.Net.ServicePoint>'s URI.</span></span>

## <a name="syntax"></a><span data-ttu-id="3a72c-105">構文</span><span class="sxs-lookup"><span data-stu-id="3a72c-105">Syntax</span></span>
  
```csharp  
private Hashtable m_ConnectionGroupList
```

> [!WARNING]
> <span data-ttu-id="3a72c-106">`ServicePoint.m_ConnectionGroupList`フィールドはプライベートであり、コードで直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="3a72c-106">The `ServicePoint.m_ConnectionGroupList` field is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="3a72c-107">Microsoft では、どのような状況でも、実稼働アプリケーションでのこのフィールドの使用はサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="3a72c-107">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="3a72c-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="3a72c-108">Requirements</span></span>

<span data-ttu-id="3a72c-109">**名前空間:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="3a72c-109">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="3a72c-110">**アセンブリ:** システム (System.dll)</span><span class="sxs-lookup"><span data-stu-id="3a72c-110">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="3a72c-111">**.NET Framework のバージョン:** 2.0 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="3a72c-111">**.NET Framework versions:** Available since 2.0.</span></span>
