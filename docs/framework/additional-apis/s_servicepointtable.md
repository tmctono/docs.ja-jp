---
title: ServicePointManager. s_ServicePointTable フィールド
description: .NET の ServicePointManager. s_ServicePointTable フィールドについて確認します。 このハッシュテーブルフィールドには、AppDomain 内のアクティブな HTTP 接続 (ServicePoints) が含まれています。
ms.date: 05/01/2017
topic_type:
- apiref
api_name:
- System.Net.ServicePointManager.s_ServicePointTable
api_location:
- System.dll
api_type:
- Assembly
ms.assetid: 24459679-291c-401a-9def-e42b29466fcf
ms.openlocfilehash: 9462ae10125dd37706f786a1f2cef78e62fbabcc
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2020
ms.locfileid: "84989547"
---
# <a name="servicepointmanagers_servicepointtable-field"></a><span data-ttu-id="33ca5-104">ServicePointManager. s \_ servicepointmanager フィールド</span><span class="sxs-lookup"><span data-stu-id="33ca5-104">ServicePointManager.s\_ServicePointTable Field</span></span>

<span data-ttu-id="33ca5-105">`ServicePointManager.s_ServicePointTable`にある <xref:System.Collections.Hashtable> アクティブな HTTP 接続の一覧を含むです <xref:System.Net.ServicePoint> <xref:System.AppDomain> 。</span><span class="sxs-lookup"><span data-stu-id="33ca5-105">`ServicePointManager.s_ServicePointTable` is a <xref:System.Collections.Hashtable> that contains the list of active HTTP connections (<xref:System.Net.ServicePoint>s) in the <xref:System.AppDomain>.</span></span>

## <a name="syntax"></a><span data-ttu-id="33ca5-106">構文</span><span class="sxs-lookup"><span data-stu-id="33ca5-106">Syntax</span></span>
  
```csharp  
private static Hashtable s_ServicePointTable
```

> [!WARNING]
> <span data-ttu-id="33ca5-107">`ServicePointManager.s_ServicePointTable`フィールドはプライベートであり、コードで直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="33ca5-107">The `ServicePointManager.s_ServicePointTable` field is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="33ca5-108">Microsoft では、どのような状況でも、実稼働アプリケーションでのこのフィールドの使用はサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="33ca5-108">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="33ca5-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="33ca5-109">Requirements</span></span>

<span data-ttu-id="33ca5-110">**名前空間:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="33ca5-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="33ca5-111">**アセンブリ:** システム (System.dll)</span><span class="sxs-lookup"><span data-stu-id="33ca5-111">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="33ca5-112">**.NET Framework のバージョン:** 2.0 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="33ca5-112">**.NET Framework versions:** Available since 2.0.</span></span>
