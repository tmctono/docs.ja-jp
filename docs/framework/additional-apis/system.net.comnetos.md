---
title: ComNetOS クラス (System.Net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.ComNetOS
- System.Net.ComNetOS.IsWin7orLater
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: ed2b970d07df2c338870b386e75c1688703f1d68
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990546"
---
# <a name="comnetos-class"></a><span data-ttu-id="6fbf4-102">ComNetOS クラス</span><span class="sxs-lookup"><span data-stu-id="6fbf4-102">ComNetOS class</span></span>

<span data-ttu-id="6fbf4-103">バージョンやインストールの種類 (クライアントまたはサーバー) など、現在のオペレーティングシステムに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="6fbf4-103">Provides information about the current operating system, such as its version and installation type (client or server).</span></span> <span data-ttu-id="6fbf4-104">このクラスは継承できません。</span><span class="sxs-lookup"><span data-stu-id="6fbf4-104">This class cannot be inherited.</span></span>
  
```csharp  
internal static class ComNetOS
```

> [!WARNING]
> <span data-ttu-id="6fbf4-105">このクラスは内部的なものであり、コードで直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="6fbf4-105">This class is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="6fbf4-106">Microsoft では、どのような状況でも、実稼働アプリケーションでのこのクラスの使用はサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="6fbf4-106">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="iswin7orlater-field"></a><span data-ttu-id="6fbf4-107">IsWin7orLater フィールド</span><span class="sxs-lookup"><span data-stu-id="6fbf4-107">IsWin7orLater field</span></span>

<span data-ttu-id="6fbf4-108">オペレーティングシステムのバージョンが Windows 7 以降であるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="6fbf4-108">Specifies whether the operating system version is Windows 7 or later.</span></span>

```csharp
internal static readonly bool IsWin7orLater
```

## <a name="requirements"></a><span data-ttu-id="6fbf4-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="6fbf4-109">Requirements</span></span>

<span data-ttu-id="6fbf4-110">**名前空間:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="6fbf4-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="6fbf4-111">**アセンブリ:** システム (System.dll)</span><span class="sxs-lookup"><span data-stu-id="6fbf4-111">**Assembly:** System (in System.dll)</span></span>
