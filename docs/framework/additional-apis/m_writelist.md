---
title: M_WriteList フィールド
ms.date: 05/01/2017
topic_type:
- apiref
api_name:
- System.Net.Connection.m_WriteList
api_location:
- System.dll
api_type:
- Assembly
ms.assetid: 235503c1-1d01-4f59-895f-ae2cf15b3345
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9760e301e25bc6e69ab22b563894cb079a8d58bb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120027"
---
# <a name="connectionm_writelist-field"></a><span data-ttu-id="e11c1-102">接続. m\_WriteList フィールド</span><span class="sxs-lookup"><span data-stu-id="e11c1-102">Connection.m\_WriteList Field</span></span>

<span data-ttu-id="e11c1-103">`Connection.m_WriteList` は、HTTP 経由で送信されるようにキューに登録されている <xref:System.Net.HttpWebRequest> オブジェクトの <xref:System.Collections.ArrayList> です。</span><span class="sxs-lookup"><span data-stu-id="e11c1-103">`Connection.m_WriteList` is an <xref:System.Collections.ArrayList> of <xref:System.Net.HttpWebRequest> objects that are queued up to be sent over HTTP.</span></span>

## <a name="syntax"></a><span data-ttu-id="e11c1-104">構文</span><span class="sxs-lookup"><span data-stu-id="e11c1-104">Syntax</span></span>
  
```csharp  
private ArrayList m_WriteList
```

> [!WARNING]
> <span data-ttu-id="e11c1-105">`Connection.m_WriteList` フィールドはプライベートであり、コードで直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="e11c1-105">The `Connection.m_WriteList` field is private and is not meant to be used directly in your code.</span></span>
> 
> <span data-ttu-id="e11c1-106">Microsoft では、どのような状況でも、実稼働アプリケーションでのこのフィールドの使用はサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="e11c1-106">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="e11c1-107">［要件］</span><span class="sxs-lookup"><span data-stu-id="e11c1-107">Requirements</span></span>

<span data-ttu-id="e11c1-108">**名前空間:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="e11c1-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="e11c1-109">**アセンブリ:** システム (.dll 内)</span><span class="sxs-lookup"><span data-stu-id="e11c1-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="e11c1-110">**.NET Framework のバージョン:** 2.0 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="e11c1-110">**.NET Framework versions:** Available since 2.0.</span></span>
