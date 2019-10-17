---
title: 追加のクラス ライブラリと API
ms.date: 10/09/2019
helpviewer_keywords:
- Additional class libraries
- Additional managed libraries
- .NET Framework out-of-band releases
- out-of-band releases
ms.assetid: cf2d9006-b631-4e5d-81cd-20aab78c60f1
author: mairaw
ms.author: mairaw
ms.topic: conceptual
ms.openlocfilehash: b869ca2f5e17db9a204a8b757b5e24ebb209d7c5
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395659"
---
# <a name="additional-class-libraries-and-apis"></a><span data-ttu-id="d9927-102">追加のクラス ライブラリと API</span><span class="sxs-lookup"><span data-stu-id="d9927-102">Additional class libraries and APIs</span></span>

<span data-ttu-id="d9927-103">.NET Framework は絶えず進化しています。</span><span class="sxs-lookup"><span data-stu-id="d9927-103">The .NET Framework is constantly evolving.</span></span> <span data-ttu-id="d9927-104">クロスプラットフォームの開発を改善し、新しい機能を早期に導入するために、新機能がアウトオブバンド (OOB) でリリースされます。</span><span class="sxs-lookup"><span data-stu-id="d9927-104">To improve cross-platform development and introduce new functionality early, new features are released out of band (OOB).</span></span> <span data-ttu-id="d9927-105">ここでは、ドキュメントが用意されている OOB プロジェクトの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="d9927-105">This topic lists the OOB projects that we provide documentation for.</span></span>  
  
<span data-ttu-id="d9927-106">さらに、いくつかのライブラリは、特定のプラットフォームまたは .NET Framework の実装を対象にしています。</span><span class="sxs-lookup"><span data-stu-id="d9927-106">In addition, some libraries target specific platforms or implementations of the .NET Framework.</span></span> <span data-ttu-id="d9927-107">たとえば、<xref:System.Text.CodePagesEncodingProvider> クラスは、.NET Framework を使用して開発された UWP アプリでコードページエンコーディングを使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="d9927-107">For example, the <xref:System.Text.CodePagesEncodingProvider> class makes code page encodings available to UWP apps developed using the .NET Framework.</span></span> <span data-ttu-id="d9927-108">ここでは、これらのライブラリの一覧も示します。</span><span class="sxs-lookup"><span data-stu-id="d9927-108">This topic lists these libraries as well.</span></span>  
  
## <a name="oob-projects"></a><span data-ttu-id="d9927-109">OOB プロジェクト</span><span class="sxs-lookup"><span data-stu-id="d9927-109">OOB projects</span></span>
  
| <span data-ttu-id="d9927-110">[プロジェクト]</span><span class="sxs-lookup"><span data-stu-id="d9927-110">Project</span></span> | <span data-ttu-id="d9927-111">説明</span><span class="sxs-lookup"><span data-stu-id="d9927-111">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Collections.Immutable> | <span data-ttu-id="d9927-112">スレッド セーフであり、内容が変更されないことが保証されているコレクションを提供します。</span><span class="sxs-lookup"><span data-stu-id="d9927-112">Provides collections that are thread safe and guaranteed to never change their contents.</span></span> |
| <xref:System.Net.Http.WinHttpHandler> | <span data-ttu-id="d9927-113">Windows の WinHTTP インターフェイスに基づいた <xref:System.Net.Http.HttpClient> のメッセージ ハンドラーを提供します。</span><span class="sxs-lookup"><span data-stu-id="d9927-113">Provides a message handler for <xref:System.Net.Http.HttpClient> based on the WinHTTP interface of Windows.</span></span> |
| <xref:System.Numerics> | <span data-ttu-id="d9927-114">SIMD ハードウェア ベースのアクセラレータを利用できるベクター型のライブラリを提供します。</span><span class="sxs-lookup"><span data-stu-id="d9927-114">Provides a library of vector types that can take advantage of SIMD hardware-based acceleration.</span></span>| 
| <xref:System.Threading.Tasks.Dataflow> | <span data-ttu-id="d9927-115">TPL データフロー ライブラリはデータ フロー コンポーネントを提供し、コンカレンシー対応アプリケーションの堅牢性を強化します。</span><span class="sxs-lookup"><span data-stu-id="d9927-115">The TPL Dataflow Library provides dataflow components to help increase the robustness of concurrency-enabled applications.</span></span> |  

## <a name="platform-specific-libraries"></a><span data-ttu-id="d9927-116">プラットフォーム固有のライブラリ</span><span class="sxs-lookup"><span data-stu-id="d9927-116">Platform-specific libraries</span></span>
  
| <span data-ttu-id="d9927-117">[プロジェクト]</span><span class="sxs-lookup"><span data-stu-id="d9927-117">Project</span></span> | <span data-ttu-id="d9927-118">説明</span><span class="sxs-lookup"><span data-stu-id="d9927-118">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Text.CodePagesEncodingProvider> | <span data-ttu-id="d9927-119">@No__t-0 クラスを拡張して、ユニバーサル Windows プラットフォームを対象とするアプリでコードページエンコーディングを使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="d9927-119">Extends the <xref:System.Text.EncodingProvider> class to make code page encodings available to apps that target the Universal Windows Platform.</span></span> |  
  
## <a name="private-apis"></a><span data-ttu-id="d9927-120">プライベート API</span><span class="sxs-lookup"><span data-stu-id="d9927-120">Private APIs</span></span>  

<span data-ttu-id="d9927-121">この API は製品インフラストラクチャをサポートします。コードから直接使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="d9927-121">These APIs support the product infrastructure and are not intended/supported to be used directly from your code.</span></span>  
  
* [<span data-ttu-id="d9927-122">SmiOrderProperty プロパティの値です。</span><span class="sxs-lookup"><span data-stu-id="d9927-122">Microsoft.SqlServer.Server.SmiOrderProperty.Item Property</span></span>](microsoft.sqlserver.server.smiorderproperty.item.md)
* [<span data-ttu-id="d9927-123">PrepForRemoting メソッド</span><span class="sxs-lookup"><span data-stu-id="d9927-123">System.Exception.PrepForRemoting Method</span></span>](system.exception.prepforremoting.md)
* [<span data-ttu-id="d9927-124">SqlTypes プロパティ (system.object のプロパティ)</span><span class="sxs-lookup"><span data-stu-id="d9927-124">System.Data.SqlTypes.SqlChars.Stream Property</span></span>](system.data.sqltypes.sqlchars.stream.md)
* [<span data-ttu-id="d9927-125">SqlTypes. SqlStreamChars コンストラクター</span><span class="sxs-lookup"><span data-stu-id="d9927-125">System.Data.SqlTypes.SqlStreamChars Constructor</span></span>](system.data.sqltypes.sqlstreamchars.-ctor.md)
* [<span data-ttu-id="d9927-126">SqlTypes プロパティの値を検索します。</span><span class="sxs-lookup"><span data-stu-id="d9927-126">System.Data.SqlTypes.SqlStreamChars.CanSeek Property</span></span>](system.data.sqltypes.sqlstreamchars.canseek.md)
* [<span data-ttu-id="d9927-127">SqlTypes プロパティの値を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="d9927-127">System.Data.SqlTypes.SqlStreamChars.IsNull Property</span></span>](system.data.sqltypes.sqlstreamchars.isnull.md)
* [<span data-ttu-id="d9927-128">SqlTypes プロパティ ("system.string" プロパティ)</span><span class="sxs-lookup"><span data-stu-id="d9927-128">System.Data.SqlTypes.SqlStreamChars.Length Property</span></span>](system.data.sqltypes.sqlstreamchars.length.md)
* [<span data-ttu-id="d9927-129">SqlTypes メソッドを削除してください。</span><span class="sxs-lookup"><span data-stu-id="d9927-129">System.Data.SqlTypes.SqlStreamChars.Close Method</span></span>](system.data.sqltypes.sqlstreamchars.close.md)
* [<span data-ttu-id="d9927-130">SqlTypes メソッド (system.object の置換メソッド)</span><span class="sxs-lookup"><span data-stu-id="d9927-130">System.Data.SqlTypes.SqlStreamChars.Dispose Method</span></span>](system.data.sqltypes.sqlstreamchars.dispose.md)
* [<span data-ttu-id="d9927-131">System.string メソッド (SqlTypes...)</span><span class="sxs-lookup"><span data-stu-id="d9927-131">System.Data.SqlTypes.SqlStreamChars.Flush Method</span></span>](system.data.sqltypes.sqlstreamchars.flush.md)
* [<span data-ttu-id="d9927-132">SqlTypes メソッドを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9927-132">System.Data.SqlTypes.SqlStreamChars.Read Method</span></span>](system.data.sqltypes.sqlstreamchars.read.md)
* [<span data-ttu-id="d9927-133">SqlTypes (システムのデータ. Seek メソッド)</span><span class="sxs-lookup"><span data-stu-id="d9927-133">System.Data.SqlTypes.SqlStreamChars.Seek Method</span></span>](system.data.sqltypes.sqlstreamchars.seek.md)
* [<span data-ttu-id="d9927-134">SetLength メソッドを SqlTypes しています。</span><span class="sxs-lookup"><span data-stu-id="d9927-134">System.Data.SqlTypes.SqlStreamChars.SetLength Method</span></span>](system.data.sqltypes.sqlstreamchars.setlength.md)
* [<span data-ttu-id="d9927-135">SqlTypes メソッドを作成してください。</span><span class="sxs-lookup"><span data-stu-id="d9927-135">System.Data.SqlTypes.SqlStreamChars.Write Method</span></span>](system.data.sqltypes.sqlstreamchars.write.md)
* [<span data-ttu-id="d9927-136">System .Net. Connection クラス</span><span class="sxs-lookup"><span data-stu-id="d9927-136">System.Net.Connection Class</span></span>](connection.md)
* [<span data-ttu-id="d9927-137">System .Net. 接続. m @ no__t-1WriteList フィールド</span><span class="sxs-lookup"><span data-stu-id="d9927-137">System.Net.Connection.m\_WriteList Field</span></span>](m_writelist.md)
* [<span data-ttu-id="d9927-138">システム .Net. ConnectionGroup クラス</span><span class="sxs-lookup"><span data-stu-id="d9927-138">System.Net.ConnectionGroup Class</span></span>](connectiongroup.md)
* [<span data-ttu-id="d9927-139">System .Net. ConnectionGroup. m @ no__t-1ConnectionList フィールド</span><span class="sxs-lookup"><span data-stu-id="d9927-139">System.Net.ConnectionGroup.m\_ConnectionList Field</span></span>](m_connectionlist.md)
* [<span data-ttu-id="d9927-140">CoreResponseData クラス</span><span class="sxs-lookup"><span data-stu-id="d9927-140">System.Net.CoreResponseData Class</span></span>](coreresponsedata.md)
* [<span data-ttu-id="d9927-141">System CoreResponseData @ no__t-1ResponseHeaders フィールド</span><span class="sxs-lookup"><span data-stu-id="d9927-141">System.Net.CoreResponseData.m\_ResponseHeaders Field</span></span>](coreresponsedata_m_responseheaders.md)
* [<span data-ttu-id="d9927-142">System CoreResponseData @ no__t-1StatusCode フィールド</span><span class="sxs-lookup"><span data-stu-id="d9927-142">System.Net.CoreResponseData.m\_StatusCode Field</span></span>](coreresponsedata_m_statuscode.md)
* [<span data-ttu-id="d9927-143">@No__t HttpWebRequest-1 の自動入力フィールド</span><span class="sxs-lookup"><span data-stu-id="d9927-143">System.Net.HttpWebRequest.\_AutoRedirects Field</span></span>](_autoredirects.md)
* [<span data-ttu-id="d9927-144">HttpWebRequest @no__t.-1CoreResponse フィールド</span><span class="sxs-lookup"><span data-stu-id="d9927-144">System.Net.HttpWebRequest.\_CoreResponse Field</span></span>](httpwebrequest__coreresponse.md)
* [<span data-ttu-id="d9927-145">HttpWebRequest @no__t.-1HttpResponse フィールド</span><span class="sxs-lookup"><span data-stu-id="d9927-145">System.Net.HttpWebRequest.\_HttpResponse Field</span></span>](_httpresponse.md)
* [<span data-ttu-id="d9927-146">System .Net. ServicePoint. m @ no__t-1ConnectionGroupList フィールド</span><span class="sxs-lookup"><span data-stu-id="d9927-146">System.Net.ServicePoint.m\_ConnectionGroupList Field</span></span>](m_connectiongrouplist.md)
* [<span data-ttu-id="d9927-147">System .Net. ServicePointManager. s @ no__t-1ServicePointTable フィールド</span><span class="sxs-lookup"><span data-stu-id="d9927-147">System.Net.ServicePointManager.s\_ServicePointTable Field</span></span>](s_servicepointtable.md)
* [<span data-ttu-id="d9927-148">No__t-1isDebuggerCheckDisabledForTestPurposes フィールドを入力してください。</span><span class="sxs-lookup"><span data-stu-id="d9927-148">System.Windows.Diagnostics.VisualDiagnostics.s\_isDebuggerCheckDisabledForTestPurposes Field</span></span>](s-isdebuggercheckdisabledfortestpurposes-field.md)
* [<span data-ttu-id="d9927-149">System.string クラス (DataMemberFieldEditor クラス)</span><span class="sxs-lookup"><span data-stu-id="d9927-149">System.Windows.Forms.Design.DataMemberFieldEditor Class</span></span>](datamemberfieldeditor-class.md)
* [<span data-ttu-id="d9927-150">System.string クラス (DataMemberListEditor クラス)</span><span class="sxs-lookup"><span data-stu-id="d9927-150">System.Windows.Forms.Design.DataMemberListEditor Class</span></span>](datamemberlisteditor-class.md)
* [<span data-ttu-id="d9927-151">adodb.recordset.接続インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d9927-151">adodb.Connection Interface</span></span>](adodb.connection.md)
* [<span data-ttu-id="d9927-152">adodb.recordset.EventReason 列挙型</span><span class="sxs-lookup"><span data-stu-id="d9927-152">adodb.EventReason Enum</span></span>](adodb.eventreasonenum.md)
* [<span data-ttu-id="d9927-153">adodb.recordset.EventStatus 列挙型</span><span class="sxs-lookup"><span data-stu-id="d9927-153">adodb.EventStatus Enum</span></span>](adodb.eventstatusenum.md)
* [<span data-ttu-id="d9927-154">stdole.DISPPARAMS 構造体</span><span class="sxs-lookup"><span data-stu-id="d9927-154">stdole.DISPPARAMS Structure</span></span>](stdole.dispparams.md)
* [<span data-ttu-id="d9927-155">stdole.EXCEPINFO 構造体</span><span class="sxs-lookup"><span data-stu-id="d9927-155">stdole.EXCEPINFO Structure</span></span>](stdole.excepinfo.md)
* [<span data-ttu-id="d9927-156">stdole.IFont.Name プロパティ</span><span class="sxs-lookup"><span data-stu-id="d9927-156">stdole.IFont.Name Property</span></span>](stdole.ifont.name.md)
* [<span data-ttu-id="d9927-157">stdole.IFontDisp インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d9927-157">stdole.IFontDisp Interface</span></span>](stdole.ifontdisp.md)
* [<span data-ttu-id="d9927-158">stdole.IPicture. Handle プロパティ</span><span class="sxs-lookup"><span data-stu-id="d9927-158">stdole.IPicture.Handle Property</span></span>](stdole.ipicture.handle.md)
* [<span data-ttu-id="d9927-159">stdole.IPictureDisp プロパティ</span><span class="sxs-lookup"><span data-stu-id="d9927-159">stdole.IPictureDisp.Handle Property</span></span>](stdole.ipicturedisp.handle.md)
* [<span data-ttu-id="d9927-160">stdole.StdFont インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d9927-160">stdole.StdFont Interface</span></span>](stdole.stdfont.md)
* [<span data-ttu-id="d9927-161">stdole.StdPicture インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d9927-161">stdole.StdPicture Interface</span></span>](stdole.stdpicture.md)
  
## <a name="see-also"></a><span data-ttu-id="d9927-162">関連項目</span><span class="sxs-lookup"><span data-stu-id="d9927-162">See also</span></span>

* [<span data-ttu-id="d9927-163">NET Framework および特別なリリース</span><span class="sxs-lookup"><span data-stu-id="d9927-163">The .NET Framework and Out-of-Band Releases</span></span>](../get-started/the-net-framework-and-out-of-band-releases.md)
