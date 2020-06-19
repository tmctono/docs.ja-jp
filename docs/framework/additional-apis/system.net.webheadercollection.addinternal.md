---
title: WebHeaderCollection. AddInternal メソッド (System.Net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.WebHeaderCollection.AddInternal
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: fd7b13ccd1baad48ab99a85d80ccd6154651c608
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990532"
---
# <a name="webheadercollectionaddinternal-method"></a><span data-ttu-id="8f0f7-102">WebHeaderCollection. AddInternal メソッド</span><span class="sxs-lookup"><span data-stu-id="8f0f7-102">WebHeaderCollection.AddInternal method</span></span>

<span data-ttu-id="8f0f7-103">指定された名前と値を持つ新しいヘッダーをコレクションに追加し、チェックをバイパスします。</span><span class="sxs-lookup"><span data-stu-id="8f0f7-103">Adds a new header with the specified name and value to the collection, bypassing checks.</span></span>

```csharp
internal void AddInternal(string name, string value)
```

> [!WARNING]
> <span data-ttu-id="8f0f7-104">このメソッドは内部であり、コードで直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="8f0f7-104">This method is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="8f0f7-105">Microsoft では、どのような状況でも、実稼働アプリケーションでこの方法を使用することはサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="8f0f7-105">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="parameters"></a><span data-ttu-id="8f0f7-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8f0f7-106">Parameters</span></span>

- <span data-ttu-id="8f0f7-107">`name` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="8f0f7-107">`name` <xref:System.String></span></span>

  <span data-ttu-id="8f0f7-108">ヘッダーの名前。</span><span class="sxs-lookup"><span data-stu-id="8f0f7-108">The name of the header.</span></span>

- <span data-ttu-id="8f0f7-109">`value` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="8f0f7-109">`value` <xref:System.String></span></span>

  <span data-ttu-id="8f0f7-110">ヘッダーの値です。</span><span class="sxs-lookup"><span data-stu-id="8f0f7-110">The value of the header.</span></span>

## <a name="requirements"></a><span data-ttu-id="8f0f7-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="8f0f7-111">Requirements</span></span>

<span data-ttu-id="8f0f7-112">**名前空間:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="8f0f7-112">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="8f0f7-113">**アセンブリ:** システム (System.dll)</span><span class="sxs-lookup"><span data-stu-id="8f0f7-113">**Assembly:** System (in System.dll)</span></span>
