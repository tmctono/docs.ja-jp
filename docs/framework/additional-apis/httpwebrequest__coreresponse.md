---
title: _CoreResponse フィールド
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
ms.openlocfilehash: b275f3eece96ac8a9ae3fb0ebd030c8d79e21fc1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155922"
---
# <a name="httpwebrequest_coreresponse-field"></a><span data-ttu-id="7ca54-102">をクリックします。\_コアレスポンスフィールド</span><span class="sxs-lookup"><span data-stu-id="7ca54-102">HttpWebRequest.\_CoreResponse Field</span></span>

<span data-ttu-id="7ca54-103">`HttpWebRequest._CoreResponse`は、HTTP 応答解析の結果を<xref:System.Exception>含むオブジェクト ([コアレスポンスデータ](coreresponsedata.md)または) です。</span><span class="sxs-lookup"><span data-stu-id="7ca54-103">`HttpWebRequest._CoreResponse` is an object (either a [CoreResponseData](coreresponsedata.md) or an <xref:System.Exception>) containing the result of HTTP response parsing.</span></span>

## <a name="syntax"></a><span data-ttu-id="7ca54-104">構文</span><span class="sxs-lookup"><span data-stu-id="7ca54-104">Syntax</span></span>
  
```csharp
private object _CoreResponse
```

> [!WARNING]
> <span data-ttu-id="7ca54-105">この API は、コード内で直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="7ca54-105">This API is not meant to be used directly in your code.</span></span> <span data-ttu-id="7ca54-106">代わりに、 を<xref:System.Diagnostics.DiagnosticSource>使用してネットワーク コードをフックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7ca54-106">Instead, you should use a <xref:System.Diagnostics.DiagnosticSource> to hook networking code.</span></span> <span data-ttu-id="7ca54-107">[診断ソースユーザーズガイドを](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ca54-107">See [DiagnosticSource User's Guide](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span></span>
>
> <span data-ttu-id="7ca54-108">マイクロソフトでは、どのような状況でも、運用環境のアプリケーションでこのクラスを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="7ca54-108">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="7ca54-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="7ca54-109">Requirements</span></span>

<span data-ttu-id="7ca54-110">**名前空間:**<xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="7ca54-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="7ca54-111">**アセンブリ:** システム (システム.dll 内)</span><span class="sxs-lookup"><span data-stu-id="7ca54-111">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="7ca54-112">**.NET フレームワークのバージョン:** 2.0 以降で利用可能。</span><span class="sxs-lookup"><span data-stu-id="7ca54-112">**.NET Framework versions:** Available since 2.0.</span></span>
