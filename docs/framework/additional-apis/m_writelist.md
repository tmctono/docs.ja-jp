---
title: 接続. m_WriteList フィールド
description: .NET の m_WriteList フィールドに関する情報を取得します。 この ArrayList フィールドには、HTTP 経由で送信するためにキューに登録されている HttpWebRequest オブジェクトがあります。
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
ms.openlocfilehash: a627cb062036e3ab098c2d6e97f9a77ebfa75a33
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2020
ms.locfileid: "84989592"
---
# <a name="connectionm_writelist-field"></a><span data-ttu-id="46dbf-104">接続. m \_ writelist フィールド</span><span class="sxs-lookup"><span data-stu-id="46dbf-104">Connection.m\_WriteList Field</span></span>

<span data-ttu-id="46dbf-105">`Connection.m_WriteList`は、 <xref:System.Collections.ArrayList> <xref:System.Net.HttpWebRequest> HTTP 経由で送信されるようにキューに登録されているオブジェクトのです。</span><span class="sxs-lookup"><span data-stu-id="46dbf-105">`Connection.m_WriteList` is an <xref:System.Collections.ArrayList> of <xref:System.Net.HttpWebRequest> objects that are queued up to be sent over HTTP.</span></span>

## <a name="syntax"></a><span data-ttu-id="46dbf-106">構文</span><span class="sxs-lookup"><span data-stu-id="46dbf-106">Syntax</span></span>
  
```csharp  
private ArrayList m_WriteList
```

> [!WARNING]
> <span data-ttu-id="46dbf-107">`Connection.m_WriteList`フィールドはプライベートであり、コードで直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="46dbf-107">The `Connection.m_WriteList` field is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="46dbf-108">Microsoft では、どのような状況でも、実稼働アプリケーションでのこのフィールドの使用はサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="46dbf-108">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="46dbf-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="46dbf-109">Requirements</span></span>

<span data-ttu-id="46dbf-110">**名前空間:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="46dbf-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="46dbf-111">**アセンブリ:** システム (System.dll)</span><span class="sxs-lookup"><span data-stu-id="46dbf-111">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="46dbf-112">**.NET Framework のバージョン:** 2.0 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="46dbf-112">**.NET Framework versions:** Available since 2.0.</span></span>
