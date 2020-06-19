---
title: ConnectionGroup. m_ConnectionList フィールド
description: .NET の ConnectionGroup. m_ConnectionList フィールドについて説明します。このフィールドには、同じ URI を提供し、他のプロパティの値を共有する接続オブジェクトが含まれています。
ms.date: 05/01/2017
topic_type:
- apiref
api_name:
- System.Net.ConnectionGroup.m_ConnectionList
api_location:
- System.dll
api_type:
- Assembly
ms.assetid: 186083cf-8dff-4600-a2ab-6fed4b4de6af
ms.openlocfilehash: 478b2441c062e8df6f4e718bd66d7af329f20f12
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2020
ms.locfileid: "84989725"
---
# <a name="connectiongroupm_connectionlist-field"></a><span data-ttu-id="67505-103">ConnectionGroup. m \_ connectiongroup フィールド</span><span class="sxs-lookup"><span data-stu-id="67505-103">ConnectionGroup.m\_ConnectionList Field</span></span>

<span data-ttu-id="67505-104">`ConnectionGroup.m_ConnectionList`は、 <xref:System.Collections.ArrayList> 同じ URI を提供し、有効期限や認証などの他のいくつかのプロパティで同じ値を共有する接続オブジェクトのです。</span><span class="sxs-lookup"><span data-stu-id="67505-104">`ConnectionGroup.m_ConnectionList` is an <xref:System.Collections.ArrayList> of connection objects that serves the same URI and share the same values for some other properties like expiration and authentication.</span></span>

## <a name="syntax"></a><span data-ttu-id="67505-105">構文</span><span class="sxs-lookup"><span data-stu-id="67505-105">Syntax</span></span>
  
```csharp  
private ArrayList m_ConnectionList
```

> [!WARNING]
> <span data-ttu-id="67505-106">`ConnectionGroup.m_ConnectionList`フィールドはプライベートであり、コードで直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="67505-106">The `ConnectionGroup.m_ConnectionList` field is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="67505-107">Microsoft では、どのような状況でも、実稼働アプリケーションでのこのフィールドの使用はサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="67505-107">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="67505-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="67505-108">Requirements</span></span>

<span data-ttu-id="67505-109">**名前空間:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="67505-109">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="67505-110">**アセンブリ:** システム (System.dll)</span><span class="sxs-lookup"><span data-stu-id="67505-110">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="67505-111">**.NET Framework のバージョン:** 2.0 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="67505-111">**.NET Framework versions:** Available since 2.0.</span></span>
