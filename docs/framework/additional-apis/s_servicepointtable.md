---
title: ServicePointManager.s_ServicePointTable フィールド
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
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: 840d068d282e3ba35df5aee6a11ff96d9e6bfdbd
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66301393"
---
# <a name="servicepointmanagersservicepointtable-field"></a><span data-ttu-id="a6adb-102">ServicePointManager.s\_ServicePointTable フィールド</span><span class="sxs-lookup"><span data-stu-id="a6adb-102">ServicePointManager.s\_ServicePointTable Field</span></span>

<span data-ttu-id="a6adb-103">`ServicePointManager.s_ServicePointTable` <xref:System.Collections.Hashtable> HTTP のアクティブな接続の一覧を格納している (<xref:System.Net.ServicePoint>秒) で、<xref:System.AppDomain>します。</span><span class="sxs-lookup"><span data-stu-id="a6adb-103">`ServicePointManager.s_ServicePointTable` is a <xref:System.Collections.Hashtable> that contains the list of active HTTP connections (<xref:System.Net.ServicePoint>s) in the <xref:System.AppDomain>.</span></span>

## <a name="syntax"></a><span data-ttu-id="a6adb-104">構文</span><span class="sxs-lookup"><span data-stu-id="a6adb-104">Syntax</span></span>
  
```csharp  
private static Hashtable s_ServicePointTable
```

> [!WARNING]
> <span data-ttu-id="a6adb-105">`ServicePointManager.s_ServicePointTable`フィールドはプライベートであり、コード内で直接使用するものではありません。</span><span class="sxs-lookup"><span data-stu-id="a6adb-105">The `ServicePointManager.s_ServicePointTable` field is private and is not meant to be used directly in your code.</span></span>
> 
> <span data-ttu-id="a6adb-106">Microsoft はいかなる運用アプリケーションでこのフィールドの使用をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="a6adb-106">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="a6adb-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="a6adb-107">Requirements</span></span>

<span data-ttu-id="a6adb-108">**名前空間:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="a6adb-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="a6adb-109">**アセンブリ:** (System.dll) のシステム</span><span class="sxs-lookup"><span data-stu-id="a6adb-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="a6adb-110">**.NET framework のバージョン:** 2.0 以降で使用可能です。</span><span class="sxs-lookup"><span data-stu-id="a6adb-110">**.NET Framework versions:** Available since 2.0.</span></span>
