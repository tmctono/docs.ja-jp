---
title: Connection クラス
ms.date: 05/01/2017
topic_type:
- apiref
api_name:
- System.Net.Connection
api_location:
- System.dll
api_type:
- Assembly
ms.assetid: 6f0b8902-f31c-4ab9-a8c9-de43228995ec
author: guardrex
ms.author: mairaw
ms.openlocfilehash: ed1fce1d16f9ddbe3a3ede91fecb1a3ca6b3d407
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61675456"
---
# <a name="connection-class"></a><span data-ttu-id="94bea-102">Connection クラス</span><span class="sxs-lookup"><span data-stu-id="94bea-102">Connection Class</span></span>

<span data-ttu-id="94bea-103">`Connection`クラス解析サーバーの応答、要求をキュー、およびパイプライン要求。</span><span class="sxs-lookup"><span data-stu-id="94bea-103">The `Connection` class parses server responses, queue requests, and pipeline requests.</span></span>

## <a name="syntax"></a><span data-ttu-id="94bea-104">構文</span><span class="sxs-lookup"><span data-stu-id="94bea-104">Syntax</span></span>
  
```csharp  
internal class Connection : PooledStream
```

> [!WARNING]
> <span data-ttu-id="94bea-105">`Connection`クラスは内部であり、コード内で直接使用するものではありません。</span><span class="sxs-lookup"><span data-stu-id="94bea-105">The `Connection` class is internal and is not meant to be used directly in your code.</span></span>
> 
> <span data-ttu-id="94bea-106">Microsoft はいかなる運用アプリケーションでこのクラスの使用をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="94bea-106">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="94bea-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="94bea-107">Requirements</span></span>

<span data-ttu-id="94bea-108">**名前空間:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="94bea-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="94bea-109">**アセンブリ:**(System.dll) のシステム</span><span class="sxs-lookup"><span data-stu-id="94bea-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="94bea-110">**.NET framework のバージョン:** 2.0 以降で使用可能です。</span><span class="sxs-lookup"><span data-stu-id="94bea-110">**.NET Framework versions:** Available since 2.0.</span></span>
