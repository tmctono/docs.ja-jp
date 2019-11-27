---
title: 追加のクラス ライブラリと API
ms.date: 11/19/2019
helpviewer_keywords:
- Additional class libraries
- Additional managed libraries
- .NET Framework out-of-band releases
- out-of-band releases
ms.assetid: cf2d9006-b631-4e5d-81cd-20aab78c60f1
author: mairaw
ms.author: mairaw
ms.topic: conceptual
ms.openlocfilehash: e1e2af584c73b1c0b2548cdd3fcbd8517dfa330d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74429345"
---
# <a name="additional-class-libraries-and-apis"></a><span data-ttu-id="8a877-102">追加のクラス ライブラリと API</span><span class="sxs-lookup"><span data-stu-id="8a877-102">Additional class libraries and APIs</span></span>

<span data-ttu-id="8a877-103">.NET Framework は絶えず進化しています。</span><span class="sxs-lookup"><span data-stu-id="8a877-103">The .NET Framework is constantly evolving.</span></span> <span data-ttu-id="8a877-104">クロスプラットフォームの開発を改善し、新しい機能を早期に導入するために、新機能がアウトオブバンド (OOB) でリリースされます。</span><span class="sxs-lookup"><span data-stu-id="8a877-104">To improve cross-platform development and introduce new functionality early, new features are released out of band (OOB).</span></span> <span data-ttu-id="8a877-105">ここでは、ドキュメントが用意されている OOB プロジェクトの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="8a877-105">This topic lists the OOB projects that we provide documentation for.</span></span>  
  
<span data-ttu-id="8a877-106">さらに、いくつかのライブラリは、特定のプラットフォームまたは .NET Framework の実装を対象にしています。</span><span class="sxs-lookup"><span data-stu-id="8a877-106">In addition, some libraries target specific platforms or implementations of the .NET Framework.</span></span> <span data-ttu-id="8a877-107">たとえば、<xref:System.Text.CodePagesEncodingProvider> クラスは、.NET Framework を使用して開発された UWP アプリでコードページエンコーディングを使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="8a877-107">For example, the <xref:System.Text.CodePagesEncodingProvider> class makes code page encodings available to UWP apps developed using the .NET Framework.</span></span> <span data-ttu-id="8a877-108">ここでは、これらのライブラリの一覧も示します。</span><span class="sxs-lookup"><span data-stu-id="8a877-108">This topic lists these libraries as well.</span></span>  
  
## <a name="oob-projects"></a><span data-ttu-id="8a877-109">OOB プロジェクト</span><span class="sxs-lookup"><span data-stu-id="8a877-109">OOB projects</span></span>
  
| <span data-ttu-id="8a877-110">プロジェクト</span><span class="sxs-lookup"><span data-stu-id="8a877-110">Project</span></span> | <span data-ttu-id="8a877-111">説明</span><span class="sxs-lookup"><span data-stu-id="8a877-111">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Collections.Immutable> | <span data-ttu-id="8a877-112">スレッド セーフであり、内容が変更されないことが保証されているコレクションを提供します。</span><span class="sxs-lookup"><span data-stu-id="8a877-112">Provides collections that are thread safe and guaranteed to never change their contents.</span></span> |
| <xref:System.Net.Http.WinHttpHandler> | <span data-ttu-id="8a877-113">Windows の WinHTTP インターフェイスに基づいた <xref:System.Net.Http.HttpClient> のメッセージ ハンドラーを提供します。</span><span class="sxs-lookup"><span data-stu-id="8a877-113">Provides a message handler for <xref:System.Net.Http.HttpClient> based on the WinHTTP interface of Windows.</span></span> |
| <xref:System.Numerics> | <span data-ttu-id="8a877-114">SIMD ハードウェア ベースのアクセラレータを利用できるベクター型のライブラリを提供します。</span><span class="sxs-lookup"><span data-stu-id="8a877-114">Provides a library of vector types that can take advantage of SIMD hardware-based acceleration.</span></span>| 
| <xref:System.Threading.Tasks.Dataflow> | <span data-ttu-id="8a877-115">TPL データフロー ライブラリはデータ フロー コンポーネントを提供し、コンカレンシー対応アプリケーションの堅牢性を強化します。</span><span class="sxs-lookup"><span data-stu-id="8a877-115">The TPL Dataflow Library provides dataflow components to help increase the robustness of concurrency-enabled applications.</span></span> |  

## <a name="platform-specific-libraries"></a><span data-ttu-id="8a877-116">プラットフォーム固有のライブラリ</span><span class="sxs-lookup"><span data-stu-id="8a877-116">Platform-specific libraries</span></span>
  
| <span data-ttu-id="8a877-117">プロジェクト</span><span class="sxs-lookup"><span data-stu-id="8a877-117">Project</span></span> | <span data-ttu-id="8a877-118">説明</span><span class="sxs-lookup"><span data-stu-id="8a877-118">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Text.CodePagesEncodingProvider> | <span data-ttu-id="8a877-119"><xref:System.Text.EncodingProvider> クラスを拡張して、ユニバーサル Windows プラットフォームを対象とするアプリでコードページエンコーディングを使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="8a877-119">Extends the <xref:System.Text.EncodingProvider> class to make code page encodings available to apps that target the Universal Windows Platform.</span></span> |  
  
## <a name="private-apis"></a><span data-ttu-id="8a877-120">プライベート API</span><span class="sxs-lookup"><span data-stu-id="8a877-120">Private APIs</span></span>  

<span data-ttu-id="8a877-121">この API は製品インフラストラクチャをサポートします。コードから直接使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="8a877-121">These APIs support the product infrastructure and are not intended/supported to be used directly from your code.</span></span>  
  
* [<span data-ttu-id="8a877-122">SmiOrderProperty プロパティの値です。</span><span class="sxs-lookup"><span data-stu-id="8a877-122">Microsoft.SqlServer.Server.SmiOrderProperty.Item Property</span></span>](microsoft.sqlserver.server.smiorderproperty.item.md)
* [<span data-ttu-id="8a877-123">PrepForRemoting メソッド</span><span class="sxs-lookup"><span data-stu-id="8a877-123">System.Exception.PrepForRemoting Method</span></span>](system.exception.prepforremoting.md)
* [<span data-ttu-id="8a877-124">SqlTypes プロパティ (system.object のプロパティ)</span><span class="sxs-lookup"><span data-stu-id="8a877-124">System.Data.SqlTypes.SqlChars.Stream Property</span></span>](system.data.sqltypes.sqlchars.stream.md)
* [<span data-ttu-id="8a877-125">SqlTypes. SqlStreamChars コンストラクター</span><span class="sxs-lookup"><span data-stu-id="8a877-125">System.Data.SqlTypes.SqlStreamChars Constructor</span></span>](system.data.sqltypes.sqlstreamchars.-ctor.md)
* [<span data-ttu-id="8a877-126">SqlTypes プロパティの値を検索します。</span><span class="sxs-lookup"><span data-stu-id="8a877-126">System.Data.SqlTypes.SqlStreamChars.CanSeek Property</span></span>](system.data.sqltypes.sqlstreamchars.canseek.md)
* [<span data-ttu-id="8a877-127">SqlTypes プロパティの値を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="8a877-127">System.Data.SqlTypes.SqlStreamChars.IsNull Property</span></span>](system.data.sqltypes.sqlstreamchars.isnull.md)
* [<span data-ttu-id="8a877-128">SqlTypes プロパティ ("system.string" プロパティ)</span><span class="sxs-lookup"><span data-stu-id="8a877-128">System.Data.SqlTypes.SqlStreamChars.Length Property</span></span>](system.data.sqltypes.sqlstreamchars.length.md)
* [<span data-ttu-id="8a877-129">SqlTypes メソッドを削除してください。</span><span class="sxs-lookup"><span data-stu-id="8a877-129">System.Data.SqlTypes.SqlStreamChars.Close Method</span></span>](system.data.sqltypes.sqlstreamchars.close.md)
* [<span data-ttu-id="8a877-130">SqlTypes メソッド (system.object の置換メソッド)</span><span class="sxs-lookup"><span data-stu-id="8a877-130">System.Data.SqlTypes.SqlStreamChars.Dispose Method</span></span>](system.data.sqltypes.sqlstreamchars.dispose.md)
* [<span data-ttu-id="8a877-131">System.string メソッド (SqlTypes...)</span><span class="sxs-lookup"><span data-stu-id="8a877-131">System.Data.SqlTypes.SqlStreamChars.Flush Method</span></span>](system.data.sqltypes.sqlstreamchars.flush.md)
* [<span data-ttu-id="8a877-132">SqlTypes メソッドを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a877-132">System.Data.SqlTypes.SqlStreamChars.Read Method</span></span>](system.data.sqltypes.sqlstreamchars.read.md)
* [<span data-ttu-id="8a877-133">SqlTypes (システムのデータ. Seek メソッド)</span><span class="sxs-lookup"><span data-stu-id="8a877-133">System.Data.SqlTypes.SqlStreamChars.Seek Method</span></span>](system.data.sqltypes.sqlstreamchars.seek.md)
* [<span data-ttu-id="8a877-134">SetLength メソッドを SqlTypes しています。</span><span class="sxs-lookup"><span data-stu-id="8a877-134">System.Data.SqlTypes.SqlStreamChars.SetLength Method</span></span>](system.data.sqltypes.sqlstreamchars.setlength.md)
* [<span data-ttu-id="8a877-135">SqlTypes メソッドを作成してください。</span><span class="sxs-lookup"><span data-stu-id="8a877-135">System.Data.SqlTypes.SqlStreamChars.Write Method</span></span>](system.data.sqltypes.sqlstreamchars.write.md)
* [<span data-ttu-id="8a877-136">MemoryStream メソッドの呼び出しを行います。</span><span class="sxs-lookup"><span data-stu-id="8a877-136">System.IO.MemoryStream.InternalGetOriginAndLength Method</span></span>](system.io.memorystream.internalgetoriginandlength.md)
* [<span data-ttu-id="8a877-137">System .Net. Connection クラス</span><span class="sxs-lookup"><span data-stu-id="8a877-137">System.Net.Connection Class</span></span>](connection.md)
* [<span data-ttu-id="8a877-138">System .Net. Connection. m\_WriteList フィールド</span><span class="sxs-lookup"><span data-stu-id="8a877-138">System.Net.Connection.m\_WriteList Field</span></span>](m_writelist.md)
* [<span data-ttu-id="8a877-139">システム .Net. ConnectionGroup クラス</span><span class="sxs-lookup"><span data-stu-id="8a877-139">System.Net.ConnectionGroup Class</span></span>](connectiongroup.md)
* [<span data-ttu-id="8a877-140">システム .Net. ConnectionGroup. m\_Connectiongroup フィールド</span><span class="sxs-lookup"><span data-stu-id="8a877-140">System.Net.ConnectionGroup.m\_ConnectionList Field</span></span>](m_connectionlist.md)
* [<span data-ttu-id="8a877-141">System .Net. ConnectStream. 接続プロパティ</span><span class="sxs-lookup"><span data-stu-id="8a877-141">System.Net.ConnectStream.Connection Property</span></span>](system.net.connectstream.connection.md)
* [<span data-ttu-id="8a877-142">CoreResponseData クラス</span><span class="sxs-lookup"><span data-stu-id="8a877-142">System.Net.CoreResponseData Class</span></span>](coreresponsedata.md)
* [<span data-ttu-id="8a877-143">CoreResponseData. m\_ResponseHeaders フィールド</span><span class="sxs-lookup"><span data-stu-id="8a877-143">System.Net.CoreResponseData.m\_ResponseHeaders Field</span></span>](coreresponsedata_m_responseheaders.md)
* [<span data-ttu-id="8a877-144">CoreResponseData\_の StatusCode フィールド</span><span class="sxs-lookup"><span data-stu-id="8a877-144">System.Net.CoreResponseData.m\_StatusCode Field</span></span>](coreresponsedata_m_statuscode.md)
* [<span data-ttu-id="8a877-145">HttpWebRequest AutoRedirects フィールドを\_します。</span><span class="sxs-lookup"><span data-stu-id="8a877-145">System.Net.HttpWebRequest.\_AutoRedirects Field</span></span>](_autoredirects.md)
* [<span data-ttu-id="8a877-146">HttpWebRequest.\_CoreResponse フィールド</span><span class="sxs-lookup"><span data-stu-id="8a877-146">System.Net.HttpWebRequest.\_CoreResponse Field</span></span>](httpwebrequest__coreresponse.md)
* [<span data-ttu-id="8a877-147">HttpWebRequest.\_Httpresponse.cache フィールド</span><span class="sxs-lookup"><span data-stu-id="8a877-147">System.Net.HttpWebRequest.\_HttpResponse Field</span></span>](_httpresponse.md)
* [<span data-ttu-id="8a877-148">System .Net. PooledStream. NetworkStream プロパティ</span><span class="sxs-lookup"><span data-stu-id="8a877-148">System.Net.PooledStream.NetworkStream Property</span></span>](system.net.pooledstream.networkstream.md)
* [<span data-ttu-id="8a877-149">システム .Net. RtcState クラス</span><span class="sxs-lookup"><span data-stu-id="8a877-149">System.Net.RtcState class</span></span>](system.net.rtcstate.md)
* [<span data-ttu-id="8a877-150">System .Net. ServicePoint. m\_ConnectionGroupList フィールド</span><span class="sxs-lookup"><span data-stu-id="8a877-150">System.Net.ServicePoint.m\_ConnectionGroupList Field</span></span>](m_connectiongrouplist.md)
* [<span data-ttu-id="8a877-151">System .Net. ServicePointManager. s\_Servicepointmanager フィールド</span><span class="sxs-lookup"><span data-stu-id="8a877-151">System.Net.ServicePointManager.s\_ServicePointTable Field</span></span>](s_servicepointtable.md)
* [<span data-ttu-id="8a877-152">M_Worker TlsStream (システム) フィールド</span><span class="sxs-lookup"><span data-stu-id="8a877-152">System.Net.TlsStream.m_Worker Field</span></span>](system.net.tlsstream.m_worker.md)
* [<span data-ttu-id="8a877-153">System .Net. Security. Sslstate プロパティ</span><span class="sxs-lookup"><span data-stu-id="8a877-153">System.Net.Security.SslState.SslProtocol Property</span></span>](system.net.security.sslstate.sslprotocol.md)
* [<span data-ttu-id="8a877-154">System.servicemodel. Channels. Message. BodyToString メソッド</span><span class="sxs-lookup"><span data-stu-id="8a877-154">System.ServiceModel.Channels.Message.BodyToString Method</span></span>](system.servicemodel.channels.message.bodytostring.md)
* [<span data-ttu-id="8a877-155">WriteStartHeaders メソッド (System.servicemodel.)</span><span class="sxs-lookup"><span data-stu-id="8a877-155">System.ServiceModel.Channels.Message.WriteStartHeaders Method</span></span>](system.servicemodel.channels.message.writestartheaders.md)
* [<span data-ttu-id="8a877-156">IsDebuggerCheckDisabledForTestPurposes フィールドの\_システム ()</span><span class="sxs-lookup"><span data-stu-id="8a877-156">System.Windows.Diagnostics.VisualDiagnostics.s\_isDebuggerCheckDisabledForTestPurposes Field</span></span>](s-isdebuggercheckdisabledfortestpurposes-field.md)
* [<span data-ttu-id="8a877-157">System.string クラス (DataMemberFieldEditor クラス)</span><span class="sxs-lookup"><span data-stu-id="8a877-157">System.Windows.Forms.Design.DataMemberFieldEditor Class</span></span>](datamemberfieldeditor-class.md)
* [<span data-ttu-id="8a877-158">System.string クラス (DataMemberListEditor クラス)</span><span class="sxs-lookup"><span data-stu-id="8a877-158">System.Windows.Forms.Design.DataMemberListEditor Class</span></span>](datamemberlisteditor-class.md)
* [<span data-ttu-id="8a877-159">System.xml. .Xml...。</span><span class="sxs-lookup"><span data-stu-id="8a877-159">System.Xml.XmlReader.CreateSqlReader Method</span></span>](system.xml.xmlreader.createsqlreader.md)
* [<span data-ttu-id="8a877-160">adodb.recordset.接続インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8a877-160">adodb.Connection Interface</span></span>](adodb.connection.md)
* [<span data-ttu-id="8a877-161">adodb.recordset.EventReason 列挙型</span><span class="sxs-lookup"><span data-stu-id="8a877-161">adodb.EventReason Enum</span></span>](adodb.eventreasonenum.md)
* [<span data-ttu-id="8a877-162">adodb.recordset.EventStatus 列挙型</span><span class="sxs-lookup"><span data-stu-id="8a877-162">adodb.EventStatus Enum</span></span>](adodb.eventstatusenum.md)
* [<span data-ttu-id="8a877-163">stdole.DISPPARAMS 構造体</span><span class="sxs-lookup"><span data-stu-id="8a877-163">stdole.DISPPARAMS Structure</span></span>](stdole.dispparams.md)
* [<span data-ttu-id="8a877-164">stdole.EXCEPINFO 構造体</span><span class="sxs-lookup"><span data-stu-id="8a877-164">stdole.EXCEPINFO Structure</span></span>](stdole.excepinfo.md)
* [<span data-ttu-id="8a877-165">stdole.IFont.Name プロパティ</span><span class="sxs-lookup"><span data-stu-id="8a877-165">stdole.IFont.Name Property</span></span>](stdole.ifont.name.md)
* [<span data-ttu-id="8a877-166">stdole.IFontDisp インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8a877-166">stdole.IFontDisp Interface</span></span>](stdole.ifontdisp.md)
* [<span data-ttu-id="8a877-167">stdole.IPicture. Handle プロパティ</span><span class="sxs-lookup"><span data-stu-id="8a877-167">stdole.IPicture.Handle Property</span></span>](stdole.ipicture.handle.md)
* [<span data-ttu-id="8a877-168">stdole.IPictureDisp プロパティ</span><span class="sxs-lookup"><span data-stu-id="8a877-168">stdole.IPictureDisp.Handle Property</span></span>](stdole.ipicturedisp.handle.md)
* [<span data-ttu-id="8a877-169">stdole.StdFont インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8a877-169">stdole.StdFont Interface</span></span>](stdole.stdfont.md)
* [<span data-ttu-id="8a877-170">stdole.StdPicture インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8a877-170">stdole.StdPicture Interface</span></span>](stdole.stdpicture.md)
  
## <a name="see-also"></a><span data-ttu-id="8a877-171">参照</span><span class="sxs-lookup"><span data-stu-id="8a877-171">See also</span></span>

* [<span data-ttu-id="8a877-172">NET Framework および特別なリリース</span><span class="sxs-lookup"><span data-stu-id="8a877-172">The .NET Framework and Out-of-Band Releases</span></span>](../get-started/the-net-framework-and-out-of-band-releases.md)
