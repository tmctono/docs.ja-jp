---
title: _CoreResponse HttpWebRequest フィールド
ms.date: 01/29/2018
topic_type:
- apiref
api_name:
- System.Net.HttpWebRequest._CoreResponse
api_location:
- System.dll
api_type:
- Assembly
author: stevewhims
ms.openlocfilehash: d16936f6984e73a886f5f48e05b53501ced63c1b
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740450"
---
# <a name="httpwebrequest_coreresponse-field"></a><span data-ttu-id="7d2f7-102">HttpWebRequest.\_CoreResponse フィールド</span><span class="sxs-lookup"><span data-stu-id="7d2f7-102">HttpWebRequest.\_CoreResponse Field</span></span>

<span data-ttu-id="7d2f7-103">`HttpWebRequest._CoreResponse` は、HTTP 応答の解析結果を含むオブジェクト ( [CoreResponseData](coreresponsedata.md)または <xref:System.Exception>) です。</span><span class="sxs-lookup"><span data-stu-id="7d2f7-103">`HttpWebRequest._CoreResponse` is an object (either a [CoreResponseData](coreresponsedata.md) or an <xref:System.Exception>) containing the result of HTTP response parsing.</span></span>

## <a name="syntax"></a><span data-ttu-id="7d2f7-104">構文</span><span class="sxs-lookup"><span data-stu-id="7d2f7-104">Syntax</span></span>
  
```csharp
private object _CoreResponse
```

> [!WARNING]
> <span data-ttu-id="7d2f7-105">この API は、コード内で直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="7d2f7-105">This API is not meant to be used directly in your code.</span></span> <span data-ttu-id="7d2f7-106">代わりに、<xref:System.Diagnostics.DiagnosticSource> を使用してネットワークコードをフックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d2f7-106">Instead, you should use a <xref:System.Diagnostics.DiagnosticSource> to hook networking code.</span></span> <span data-ttu-id="7d2f7-107">「 [DiagnosticSource User'S Guide](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d2f7-107">See [DiagnosticSource User's Guide](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span></span>
> 
> <span data-ttu-id="7d2f7-108">Microsoft では、どのような状況でも、実稼働アプリケーションでのこのクラスの使用はサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="7d2f7-108">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="7d2f7-109">要件</span><span class="sxs-lookup"><span data-stu-id="7d2f7-109">Requirements</span></span>

<span data-ttu-id="7d2f7-110">**名前空間:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="7d2f7-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="7d2f7-111">**アセンブリ:** システム (.dll 内)</span><span class="sxs-lookup"><span data-stu-id="7d2f7-111">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="7d2f7-112">**.NET Framework のバージョン:** 2.0 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="7d2f7-112">**.NET Framework versions:** Available since 2.0.</span></span>
