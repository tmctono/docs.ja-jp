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
ms.openlocfilehash: a48a145cd337a18c4ce63b281e1c82032d0532e7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61675365"
---
# <a name="additional-class-libraries-and-apis"></a><span data-ttu-id="df8b7-102">追加のクラス ライブラリと API</span><span class="sxs-lookup"><span data-stu-id="df8b7-102">Additional class libraries and APIs</span></span>

<span data-ttu-id="df8b7-103">.NET Framework は絶えず進化しています。</span><span class="sxs-lookup"><span data-stu-id="df8b7-103">The .NET Framework is constantly evolving.</span></span> <span data-ttu-id="df8b7-104">クロス プラットフォーム開発を向上させ、新しい機能を早期導入、新機能はアウトオブ バンド (OOB) リリースします。</span><span class="sxs-lookup"><span data-stu-id="df8b7-104">To improve cross-platform development and introduce new functionality early, new features are released out of band (OOB).</span></span> <span data-ttu-id="df8b7-105">ここでは、ドキュメントが用意されている OOB プロジェクトの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="df8b7-105">This topic lists the OOB projects that we provide documentation for.</span></span>  
  
<span data-ttu-id="df8b7-106">さらに、いくつかのライブラリは、特定のプラットフォームまたは .NET Framework の実装を対象にしています。</span><span class="sxs-lookup"><span data-stu-id="df8b7-106">In addition, some libraries target specific platforms or implementations of the .NET Framework.</span></span> <span data-ttu-id="df8b7-107">たとえば、<xref:System.Text.CodePagesEncodingProvider>クラスが .NET Framework を使用して開発された UWP アプリで使用できるコード ページ エンコーディングを使用します。</span><span class="sxs-lookup"><span data-stu-id="df8b7-107">For example, the <xref:System.Text.CodePagesEncodingProvider> class makes code page encodings available to UWP apps developed using the .NET Framework.</span></span> <span data-ttu-id="df8b7-108">ここでは、これらのライブラリの一覧も示します。</span><span class="sxs-lookup"><span data-stu-id="df8b7-108">This topic lists these libraries as well.</span></span>  
  
## <a name="oob-projects"></a><span data-ttu-id="df8b7-109">OOB プロジェクト</span><span class="sxs-lookup"><span data-stu-id="df8b7-109">OOB projects</span></span>
  
| <span data-ttu-id="df8b7-110">プロジェクト</span><span class="sxs-lookup"><span data-stu-id="df8b7-110">Project</span></span> | <span data-ttu-id="df8b7-111">説明</span><span class="sxs-lookup"><span data-stu-id="df8b7-111">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Collections.Immutable> | <span data-ttu-id="df8b7-112">スレッド セーフであり、内容が変更されないことが保証されているコレクションを提供します。</span><span class="sxs-lookup"><span data-stu-id="df8b7-112">Provides collections that are thread safe and guaranteed to never change their contents.</span></span> |
| <xref:System.Net.Http.WinHttpHandler> | <span data-ttu-id="df8b7-113">Windows の WinHTTP インターフェイスに基づいた <xref:System.Net.Http.HttpClient> のメッセージ ハンドラーを提供します。</span><span class="sxs-lookup"><span data-stu-id="df8b7-113">Provides a message handler for <xref:System.Net.Http.HttpClient> based on the WinHTTP interface of Windows.</span></span> |
| <xref:System.Numerics> | <span data-ttu-id="df8b7-114">SIMD ハードウェア ベースのアクセラレータを利用できるベクター型のライブラリを提供します。</span><span class="sxs-lookup"><span data-stu-id="df8b7-114">Provides a library of vector types that can take advantage of SIMD hardware-based acceleration.</span></span>| 
| <xref:System.Threading.Tasks.Dataflow> | <span data-ttu-id="df8b7-115">TPL データフロー ライブラリはデータ フロー コンポーネントを提供し、コンカレンシー対応アプリケーションの堅牢性を強化します。</span><span class="sxs-lookup"><span data-stu-id="df8b7-115">The TPL Dataflow Library provides dataflow components to help increase the robustness of concurrency-enabled applications.</span></span> |  

## <a name="platform-specific-libraries"></a><span data-ttu-id="df8b7-116">プラットフォーム固有のライブラリ</span><span class="sxs-lookup"><span data-stu-id="df8b7-116">Platform-specific libraries</span></span>
  
| <span data-ttu-id="df8b7-117">プロジェクト</span><span class="sxs-lookup"><span data-stu-id="df8b7-117">Project</span></span> | <span data-ttu-id="df8b7-118">説明</span><span class="sxs-lookup"><span data-stu-id="df8b7-118">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Text.CodePagesEncodingProvider> | <span data-ttu-id="df8b7-119">拡張、<xref:System.Text.EncodingProvider>クラスのコード ページ エンコーディングをユニバーサル Windows プラットフォームを対象とするアプリを使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="df8b7-119">Extends the <xref:System.Text.EncodingProvider> class to make code page encodings available to apps that target the Universal Windows Platform.</span></span> |  
  
## <a name="private-apis"></a><span data-ttu-id="df8b7-120">プライベート API</span><span class="sxs-lookup"><span data-stu-id="df8b7-120">Private APIs</span></span>  

<span data-ttu-id="df8b7-121">この API は製品インフラストラクチャをサポートします。コードから直接使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="df8b7-121">These APIs support the product infrastructure and are not intended/supported to be used directly from your code.</span></span>  
  
| <span data-ttu-id="df8b7-122">API 名</span><span class="sxs-lookup"><span data-stu-id="df8b7-122">API Name</span></span> |
| -------- |
| [<span data-ttu-id="df8b7-123">System.Net.Connection クラス</span><span class="sxs-lookup"><span data-stu-id="df8b7-123">System.Net.Connection Class</span></span>](../../../docs/framework/additional-apis/connection.md) |
| [<span data-ttu-id="df8b7-124">System.Net.Connection.m\_WriteList フィールド</span><span class="sxs-lookup"><span data-stu-id="df8b7-124">System.Net.Connection.m\_WriteList Field</span></span>](../../../docs/framework/additional-apis/m_writelist.md) |
| [<span data-ttu-id="df8b7-125">System.Net.ConnectionGroup クラス</span><span class="sxs-lookup"><span data-stu-id="df8b7-125">System.Net.ConnectionGroup Class</span></span>](../../../docs/framework/additional-apis/connectiongroup.md) |
| [<span data-ttu-id="df8b7-126">System.Net.ConnectionGroup.m\_ConnectionList フィールド</span><span class="sxs-lookup"><span data-stu-id="df8b7-126">System.Net.ConnectionGroup.m\_ConnectionList Field</span></span>](../../../docs/framework/additional-apis/m_connectionlist.md) |
| [<span data-ttu-id="df8b7-127">System.Net.CoreResponseData クラス</span><span class="sxs-lookup"><span data-stu-id="df8b7-127">System.Net.CoreResponseData Class</span></span>](../../../docs/framework/additional-apis/coreresponsedata.md) |
| [<span data-ttu-id="df8b7-128">System.Net.CoreResponseData.m\_ResponseHeaders Field</span><span class="sxs-lookup"><span data-stu-id="df8b7-128">System.Net.CoreResponseData.m\_ResponseHeaders Field</span></span>](../../../docs/framework/additional-apis/coreresponsedata_m_responseheaders.md) |
| [<span data-ttu-id="df8b7-129">System.Net.CoreResponseData.m\_StatusCode フィールド</span><span class="sxs-lookup"><span data-stu-id="df8b7-129">System.Net.CoreResponseData.m\_StatusCode Field</span></span>](../../../docs/framework/additional-apis/coreresponsedata_m_statuscode.md) |
| [<span data-ttu-id="df8b7-130">System.Net.HttpWebRequest します。\_AutoRedirects フィールド</span><span class="sxs-lookup"><span data-stu-id="df8b7-130">System.Net.HttpWebRequest.\_AutoRedirects Field</span></span>](../../../docs/framework/additional-apis/_autoredirects.md) |
| [<span data-ttu-id="df8b7-131">System.Net.HttpWebRequest します。\_CoreResponse フィールド</span><span class="sxs-lookup"><span data-stu-id="df8b7-131">System.Net.HttpWebRequest.\_CoreResponse Field</span></span>](../../../docs/framework/additional-apis/httpwebrequest__coreresponse.md) |
| [<span data-ttu-id="df8b7-132">System.Net.HttpWebRequest します。\_HttpResponse フィールド</span><span class="sxs-lookup"><span data-stu-id="df8b7-132">System.Net.HttpWebRequest.\_HttpResponse Field</span></span>](../../../docs/framework/additional-apis/_httpresponse.md) |
| [<span data-ttu-id="df8b7-133">System.Net.ServicePoint.m\_ConnectionGroupList Field</span><span class="sxs-lookup"><span data-stu-id="df8b7-133">System.Net.ServicePoint.m\_ConnectionGroupList Field</span></span>](../../../docs/framework/additional-apis/m_connectiongrouplist.md) |
| [<span data-ttu-id="df8b7-134">System.Net.ServicePointManager.s\_ServicePointTable Field</span><span class="sxs-lookup"><span data-stu-id="df8b7-134">System.Net.ServicePointManager.s\_ServicePointTable Field</span></span>](../../../docs/framework/additional-apis/s_servicepointtable.md) |
| [<span data-ttu-id="df8b7-135">System.Windows.Diagnostics.VisualDiagnostics.s\_isDebuggerCheckDisabledForTestPurposes Field</span><span class="sxs-lookup"><span data-stu-id="df8b7-135">System.Windows.Diagnostics.VisualDiagnostics.s\_isDebuggerCheckDisabledForTestPurposes Field</span></span>](../../../docs/framework/additional-apis/s-isdebuggercheckdisabledfortestpurposes-field.md) |
| [<span data-ttu-id="df8b7-136">System.Windows.Forms.Design.DataMemberFieldEditor Class</span><span class="sxs-lookup"><span data-stu-id="df8b7-136">System.Windows.Forms.Design.DataMemberFieldEditor Class</span></span>](../../../docs/framework/additional-apis/datamemberfieldeditor-class.md) |
| [<span data-ttu-id="df8b7-137">System.Windows.Forms.Design.DataMemberListEditor Class</span><span class="sxs-lookup"><span data-stu-id="df8b7-137">System.Windows.Forms.Design.DataMemberListEditor Class</span></span>](../../../docs/framework/additional-apis/datamemberlisteditor-class.md) |
  
## <a name="see-also"></a><span data-ttu-id="df8b7-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="df8b7-138">See also</span></span>

- [<span data-ttu-id="df8b7-139">NET Framework および特別なリリース</span><span class="sxs-lookup"><span data-stu-id="df8b7-139">The .NET Framework and Out-of-Band Releases</span></span>](../../../docs/framework/get-started/the-net-framework-and-out-of-band-releases.md)
