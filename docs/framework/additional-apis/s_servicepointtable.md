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
author: guardrex
ms.author: mairaw
ms.openlocfilehash: ebcf5c3f13b3bd30a8e091be09ae546eee1eaffe
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61675443"
---
# <a name="servicepointmanagersservicepointtable-field"></a><span data-ttu-id="b9c9a-102">ServicePointManager.s\_ServicePointTable フィールド</span><span class="sxs-lookup"><span data-stu-id="b9c9a-102">ServicePointManager.s\_ServicePointTable Field</span></span>

<span data-ttu-id="b9c9a-103">`ServicePointManager.s_ServicePointTable` <xref:System.Collections.Hashtable> HTTP のアクティブな接続の一覧を格納している (<xref:System.Net.ServicePoint>秒) で、<xref:System.AppDomain>します。</span><span class="sxs-lookup"><span data-stu-id="b9c9a-103">`ServicePointManager.s_ServicePointTable` is a <xref:System.Collections.Hashtable> that contains the list of active HTTP connections (<xref:System.Net.ServicePoint>s) in the <xref:System.AppDomain>.</span></span>

## <a name="syntax"></a><span data-ttu-id="b9c9a-104">構文</span><span class="sxs-lookup"><span data-stu-id="b9c9a-104">Syntax</span></span>
  
```csharp  
private static Hashtable s_ServicePointTable
```

> [!WARNING]
> <span data-ttu-id="b9c9a-105">`ServicePointManager.s_ServicePointTable`フィールドはプライベートであり、コード内で直接使用するものではありません。</span><span class="sxs-lookup"><span data-stu-id="b9c9a-105">The `ServicePointManager.s_ServicePointTable` field is private and is not meant to be used directly in your code.</span></span>
> 
> <span data-ttu-id="b9c9a-106">Microsoft はいかなる運用アプリケーションでこのフィールドの使用をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="b9c9a-106">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="b9c9a-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="b9c9a-107">Requirements</span></span>

<span data-ttu-id="b9c9a-108">**名前空間:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="b9c9a-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="b9c9a-109">**アセンブリ:**(System.dll) のシステム</span><span class="sxs-lookup"><span data-stu-id="b9c9a-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="b9c9a-110">**.NET framework のバージョン:** 2.0 以降で使用可能です。</span><span class="sxs-lookup"><span data-stu-id="b9c9a-110">**.NET Framework versions:** Available since 2.0.</span></span>
