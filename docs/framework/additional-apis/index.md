---
title: 追加のクラス ライブラリと API
ms.date: 01/29/2018
helpviewer_keywords:
- Additional class libraries
- Additional managed libraries
- .NET Framework out-of-band releases
- out-of-band releases
ms.assetid: cf2d9006-b631-4e5d-81cd-20aab78c60f1
author: mairaw
ms.author: mairaw
ms.topic: conceptual
ms.openlocfilehash: 0aed6f32bbd3ffdc9446e9d17be2d90c62444ee1
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053242"
---
# <a name="additional-class-libraries-and-apis"></a><span data-ttu-id="d410e-102">追加のクラス ライブラリと API</span><span class="sxs-lookup"><span data-stu-id="d410e-102">Additional class libraries and APIs</span></span>

<span data-ttu-id="d410e-103">.NET Framework は絶えず進化しています。</span><span class="sxs-lookup"><span data-stu-id="d410e-103">The .NET Framework is constantly evolving.</span></span> <span data-ttu-id="d410e-104">クロスプラットフォームの開発を改善し、新しい機能を早期に導入するために、新機能がアウトオブバンド (OOB) でリリースされます。</span><span class="sxs-lookup"><span data-stu-id="d410e-104">To improve cross-platform development and introduce new functionality early, new features are released out of band (OOB).</span></span> <span data-ttu-id="d410e-105">ここでは、ドキュメントが用意されている OOB プロジェクトの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="d410e-105">This topic lists the OOB projects that we provide documentation for.</span></span>  
  
<span data-ttu-id="d410e-106">さらに、いくつかのライブラリは、特定のプラットフォームまたは .NET Framework の実装を対象にしています。</span><span class="sxs-lookup"><span data-stu-id="d410e-106">In addition, some libraries target specific platforms or implementations of the .NET Framework.</span></span> <span data-ttu-id="d410e-107">たとえば<xref:System.Text.CodePagesEncodingProvider> 、クラスを使用すると、.NET Framework を使用して開発された UWP アプリでコードページエンコーディングを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="d410e-107">For example, the <xref:System.Text.CodePagesEncodingProvider> class makes code page encodings available to UWP apps developed using the .NET Framework.</span></span> <span data-ttu-id="d410e-108">ここでは、これらのライブラリの一覧も示します。</span><span class="sxs-lookup"><span data-stu-id="d410e-108">This topic lists these libraries as well.</span></span>  
  
## <a name="oob-projects"></a><span data-ttu-id="d410e-109">OOB プロジェクト</span><span class="sxs-lookup"><span data-stu-id="d410e-109">OOB projects</span></span>
  
| <span data-ttu-id="d410e-110">プロジェクト</span><span class="sxs-lookup"><span data-stu-id="d410e-110">Project</span></span> | <span data-ttu-id="d410e-111">説明</span><span class="sxs-lookup"><span data-stu-id="d410e-111">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Collections.Immutable> | <span data-ttu-id="d410e-112">スレッド セーフであり、内容が変更されないことが保証されているコレクションを提供します。</span><span class="sxs-lookup"><span data-stu-id="d410e-112">Provides collections that are thread safe and guaranteed to never change their contents.</span></span> |
| <xref:System.Net.Http.WinHttpHandler> | <span data-ttu-id="d410e-113">Windows の WinHTTP インターフェイスに基づいた <xref:System.Net.Http.HttpClient> のメッセージ ハンドラーを提供します。</span><span class="sxs-lookup"><span data-stu-id="d410e-113">Provides a message handler for <xref:System.Net.Http.HttpClient> based on the WinHTTP interface of Windows.</span></span> |
| <xref:System.Numerics> | <span data-ttu-id="d410e-114">SIMD ハードウェア ベースのアクセラレータを利用できるベクター型のライブラリを提供します。</span><span class="sxs-lookup"><span data-stu-id="d410e-114">Provides a library of vector types that can take advantage of SIMD hardware-based acceleration.</span></span>| 
| <xref:System.Threading.Tasks.Dataflow> | <span data-ttu-id="d410e-115">TPL データフロー ライブラリはデータ フロー コンポーネントを提供し、コンカレンシー対応アプリケーションの堅牢性を強化します。</span><span class="sxs-lookup"><span data-stu-id="d410e-115">The TPL Dataflow Library provides dataflow components to help increase the robustness of concurrency-enabled applications.</span></span> |  

## <a name="platform-specific-libraries"></a><span data-ttu-id="d410e-116">プラットフォーム固有のライブラリ</span><span class="sxs-lookup"><span data-stu-id="d410e-116">Platform-specific libraries</span></span>
  
| <span data-ttu-id="d410e-117">プロジェクト</span><span class="sxs-lookup"><span data-stu-id="d410e-117">Project</span></span> | <span data-ttu-id="d410e-118">説明</span><span class="sxs-lookup"><span data-stu-id="d410e-118">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Text.CodePagesEncodingProvider> | <span data-ttu-id="d410e-119"><xref:System.Text.EncodingProvider>クラスを拡張して、ユニバーサル Windows プラットフォームを対象とするアプリでコードページエンコーディングを使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="d410e-119">Extends the <xref:System.Text.EncodingProvider> class to make code page encodings available to apps that target the Universal Windows Platform.</span></span> |  
  
## <a name="private-apis"></a><span data-ttu-id="d410e-120">プライベート API</span><span class="sxs-lookup"><span data-stu-id="d410e-120">Private APIs</span></span>  

<span data-ttu-id="d410e-121">この API は製品インフラストラクチャをサポートします。コードから直接使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="d410e-121">These APIs support the product infrastructure and are not intended/supported to be used directly from your code.</span></span>  
  
| <span data-ttu-id="d410e-122">API 名</span><span class="sxs-lookup"><span data-stu-id="d410e-122">API Name</span></span> |
| -------- |
| [<span data-ttu-id="d410e-123">System .Net. Connection クラス</span><span class="sxs-lookup"><span data-stu-id="d410e-123">System.Net.Connection Class</span></span>](connection.md) |
| [<span data-ttu-id="d410e-124">System .net. 接続. m\_writelist フィールド</span><span class="sxs-lookup"><span data-stu-id="d410e-124">System.Net.Connection.m\_WriteList Field</span></span>](m_writelist.md) |
| [<span data-ttu-id="d410e-125">システム .Net. ConnectionGroup クラス</span><span class="sxs-lookup"><span data-stu-id="d410e-125">System.Net.ConnectionGroup Class</span></span>](connectiongroup.md) |
| [<span data-ttu-id="d410e-126">System .net. connectiongroup. m\_connectiongroup フィールド</span><span class="sxs-lookup"><span data-stu-id="d410e-126">System.Net.ConnectionGroup.m\_ConnectionList Field</span></span>](m_connectionlist.md) |
| [<span data-ttu-id="d410e-127">CoreResponseData クラス</span><span class="sxs-lookup"><span data-stu-id="d410e-127">System.Net.CoreResponseData Class</span></span>](coreresponsedata.md) |
| [<span data-ttu-id="d410e-128">System.Net.CoreResponseData.m\_ResponseHeaders Field</span><span class="sxs-lookup"><span data-stu-id="d410e-128">System.Net.CoreResponseData.m\_ResponseHeaders Field</span></span>](coreresponsedata_m_responseheaders.md) |
| [<span data-ttu-id="d410e-129">CoreResponseData の\_StatusCode フィールド</span><span class="sxs-lookup"><span data-stu-id="d410e-129">System.Net.CoreResponseData.m\_StatusCode Field</span></span>](coreresponsedata_m_statuscode.md) |
| [<span data-ttu-id="d410e-130">HttpWebRequest。\_Autoredirects フィールド</span><span class="sxs-lookup"><span data-stu-id="d410e-130">System.Net.HttpWebRequest.\_AutoRedirects Field</span></span>](_autoredirects.md) |
| [<span data-ttu-id="d410e-131">HttpWebRequest。\_CoreResponse フィールド</span><span class="sxs-lookup"><span data-stu-id="d410e-131">System.Net.HttpWebRequest.\_CoreResponse Field</span></span>](httpwebrequest__coreresponse.md) |
| [<span data-ttu-id="d410e-132">HttpWebRequest。\_Httpresponse.cache フィールド</span><span class="sxs-lookup"><span data-stu-id="d410e-132">System.Net.HttpWebRequest.\_HttpResponse Field</span></span>](_httpresponse.md) |
| [<span data-ttu-id="d410e-133">System.Net.ServicePoint.m\_ConnectionGroupList Field</span><span class="sxs-lookup"><span data-stu-id="d410e-133">System.Net.ServicePoint.m\_ConnectionGroupList Field</span></span>](m_connectiongrouplist.md) |
| [<span data-ttu-id="d410e-134">System.Net.ServicePointManager.s\_ServicePointTable Field</span><span class="sxs-lookup"><span data-stu-id="d410e-134">System.Net.ServicePointManager.s\_ServicePointTable Field</span></span>](s_servicepointtable.md) |
| [<span data-ttu-id="d410e-135">System.Windows.Diagnostics.VisualDiagnostics.s\_isDebuggerCheckDisabledForTestPurposes Field</span><span class="sxs-lookup"><span data-stu-id="d410e-135">System.Windows.Diagnostics.VisualDiagnostics.s\_isDebuggerCheckDisabledForTestPurposes Field</span></span>](s-isdebuggercheckdisabledfortestpurposes-field.md) |
| [<span data-ttu-id="d410e-136">System.Windows.Forms.Design.DataMemberFieldEditor Class</span><span class="sxs-lookup"><span data-stu-id="d410e-136">System.Windows.Forms.Design.DataMemberFieldEditor Class</span></span>](datamemberfieldeditor-class.md) |
| [<span data-ttu-id="d410e-137">System.Windows.Forms.Design.DataMemberListEditor Class</span><span class="sxs-lookup"><span data-stu-id="d410e-137">System.Windows.Forms.Design.DataMemberListEditor Class</span></span>](datamemberlisteditor-class.md) |
  
## <a name="see-also"></a><span data-ttu-id="d410e-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="d410e-138">See also</span></span>

- [<span data-ttu-id="d410e-139">NET Framework および特別なリリース</span><span class="sxs-lookup"><span data-stu-id="d410e-139">The .NET Framework and Out-of-Band Releases</span></span>](../get-started/the-net-framework-and-out-of-band-releases.md)
