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
ms.openlocfilehash: 640a925c3aec86b4743b1b2b62eb3793af1cc0bb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61675417"
---
# <a name="coreresponsedata-class"></a><span data-ttu-id="4f26f-102">CoreResponseData クラス</span><span class="sxs-lookup"><span data-stu-id="4f26f-102">CoreResponseData Class</span></span>

<span data-ttu-id="4f26f-103">`CoreResponseData`クラスは、HTTP ヘッダーおよび応答本文の解析を表します。</span><span class="sxs-lookup"><span data-stu-id="4f26f-103">The `CoreResponseData` class represents the parsing of the HTTP headers and the response body.</span></span>

## <a name="syntax"></a><span data-ttu-id="4f26f-104">構文</span><span class="sxs-lookup"><span data-stu-id="4f26f-104">Syntax</span></span>
  
```csharp
internal class CoreResponseData
```

> [!WARNING]
> <span data-ttu-id="4f26f-105">この API は、内部、およびコード内で直接使用するものではありません。</span><span class="sxs-lookup"><span data-stu-id="4f26f-105">This API is internal, and it is not meant to be used directly in your code.</span></span> <span data-ttu-id="4f26f-106">代わりに、使用する必要があります、<xref:System.Diagnostics.DiagnosticSource>ネットワーク用のコードをフックします。</span><span class="sxs-lookup"><span data-stu-id="4f26f-106">Instead, you should use a <xref:System.Diagnostics.DiagnosticSource> to hook networking code.</span></span> <span data-ttu-id="4f26f-107">参照してください[DiagnosticSource ユーザー ガイド](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md)します。</span><span class="sxs-lookup"><span data-stu-id="4f26f-107">See [DiagnosticSource User's Guide](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span></span>
> 
> <span data-ttu-id="4f26f-108">Microsoft はいかなる運用アプリケーションでこのクラスの使用をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="4f26f-108">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="4f26f-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="4f26f-109">Requirements</span></span>

<span data-ttu-id="4f26f-110">**名前空間:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="4f26f-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="4f26f-111">**アセンブリ:**(System.dll) のシステム</span><span class="sxs-lookup"><span data-stu-id="4f26f-111">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="4f26f-112">**.NET framework のバージョン:** 2.0 以降で使用可能です。</span><span class="sxs-lookup"><span data-stu-id="4f26f-112">**.NET Framework versions:** Available since 2.0.</span></span>
