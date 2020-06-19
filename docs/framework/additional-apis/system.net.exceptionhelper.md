---
title: ExceptionHelper クラス (System.Net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.ExceptionHelper
- System.Net.ExceptionHelper.WebPermissionUnrestricted
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: 14a6172f7a0321ba9b2dd1744799017271c4332c
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990545"
---
# <a name="exceptionhelper-class"></a><span data-ttu-id="17541-102">ExceptionHelper クラス</span><span class="sxs-lookup"><span data-stu-id="17541-102">ExceptionHelper class</span></span>

<span data-ttu-id="17541-103">標準化されたエラーメッセージと共に例外を提供します。</span><span class="sxs-lookup"><span data-stu-id="17541-103">Provides exceptions with standardized error messages.</span></span> <span data-ttu-id="17541-104">このクラスは継承できません。</span><span class="sxs-lookup"><span data-stu-id="17541-104">This class cannot be inherited.</span></span>

```csharp
internal static class ExceptionHelper
```

> [!WARNING]
> <span data-ttu-id="17541-105">このクラスは内部的なものであり、コードで直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="17541-105">This class is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="17541-106">Microsoft では、どのような状況でも、実稼働アプリケーションでのこのクラスの使用はサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="17541-106">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="webpermissionunrestricted-field"></a><span data-ttu-id="17541-107">WebPermissionUnrestricted フィールド</span><span class="sxs-lookup"><span data-stu-id="17541-107">WebPermissionUnrestricted field</span></span>

<span data-ttu-id="17541-108">アプリがインターネットリソースに接続できることを指定します。</span><span class="sxs-lookup"><span data-stu-id="17541-108">Specifies that the app can connect to internet resources.</span></span>

```csharp
internal static readonly WebPermission WebPermissionUnrestricted
```

## <a name="requirements"></a><span data-ttu-id="17541-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="17541-109">Requirements</span></span>

<span data-ttu-id="17541-110">**名前空間:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="17541-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="17541-111">**アセンブリ:** システム (System.dll)</span><span class="sxs-lookup"><span data-stu-id="17541-111">**Assembly:** System (in System.dll)</span></span>
