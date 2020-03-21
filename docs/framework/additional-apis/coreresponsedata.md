---
title: CoreResponseData クラス
ms.date: 01/29/2018
topic_type:
- apiref
api_name:
- System.Net.CoreResponseData
api_location:
- System.dll
api_type:
- Assembly
author: stevewhims
ms.openlocfilehash: 39a14a3df5059cc47cd4879e4d4ba351cc7b655b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79156117"
---
# <a name="coreresponsedata-class"></a><span data-ttu-id="9d7a0-102">CoreResponseData クラス</span><span class="sxs-lookup"><span data-stu-id="9d7a0-102">CoreResponseData Class</span></span>

<span data-ttu-id="9d7a0-103">この`CoreResponseData`クラスは、HTTP ヘッダーと応答本文の解析を表します。</span><span class="sxs-lookup"><span data-stu-id="9d7a0-103">The `CoreResponseData` class represents the parsing of the HTTP headers and the response body.</span></span>

## <a name="syntax"></a><span data-ttu-id="9d7a0-104">構文</span><span class="sxs-lookup"><span data-stu-id="9d7a0-104">Syntax</span></span>
  
```csharp
internal class CoreResponseData
```

> [!WARNING]
> <span data-ttu-id="9d7a0-105">この API は内部であり、コード内で直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="9d7a0-105">This API is internal, and it is not meant to be used directly in your code.</span></span> <span data-ttu-id="9d7a0-106">代わりに、 を<xref:System.Diagnostics.DiagnosticSource>使用してネットワーク コードをフックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9d7a0-106">Instead, you should use a <xref:System.Diagnostics.DiagnosticSource> to hook networking code.</span></span> <span data-ttu-id="9d7a0-107">[診断ソースユーザーズガイドを](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="9d7a0-107">See [DiagnosticSource User's Guide](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span></span>
>
> <span data-ttu-id="9d7a0-108">マイクロソフトでは、どのような状況でも、運用環境のアプリケーションでこのクラスを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="9d7a0-108">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="9d7a0-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="9d7a0-109">Requirements</span></span>

<span data-ttu-id="9d7a0-110">**名前空間:**<xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="9d7a0-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="9d7a0-111">**アセンブリ:** システム (システム.dll 内)</span><span class="sxs-lookup"><span data-stu-id="9d7a0-111">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="9d7a0-112">**.NET フレームワークのバージョン:** 2.0 以降で利用可能。</span><span class="sxs-lookup"><span data-stu-id="9d7a0-112">**.NET Framework versions:** Available since 2.0.</span></span>
