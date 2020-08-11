---
title: 追加のクラス ライブラリと API
description: 帯域外 (OOB) プロジェクト、プラットフォーム固有のライブラリ、プライベート Api など、.NET で追加のクラスライブラリと Api を探索します。
ms.date: 08/11/2020
helpviewer_keywords:
- Additional class libraries
- Additional managed libraries
- .NET Framework out-of-band releases
- out-of-band releases
ms.assetid: cf2d9006-b631-4e5d-81cd-20aab78c60f1
ms.topic: conceptual
ms.openlocfilehash: c6404df5d4f0be381bc0a9c1924fcf82cf078306
ms.sourcegitcommit: 70d6a7e4f7187cbfa332f0f8be76566f7828cfcd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/11/2020
ms.locfileid: "88075476"
---
# <a name="additional-class-libraries-and-apis"></a><span data-ttu-id="7e170-103">追加のクラス ライブラリと API</span><span class="sxs-lookup"><span data-stu-id="7e170-103">Additional class libraries and APIs</span></span>

<span data-ttu-id="7e170-104">この記事では、帯域外でリリースされた Api、特定のプラットフォームを対象とする Api、またはプライベート型または内部型の Api .NET Framework を示します。</span><span class="sxs-lookup"><span data-stu-id="7e170-104">This article lists .NET Framework APIs that either were released out of band, target a specific platform, or are private or internal types.</span></span>

## <a name="oob-projects"></a><span data-ttu-id="7e170-105">OOB プロジェクト</span><span class="sxs-lookup"><span data-stu-id="7e170-105">OOB projects</span></span>

<span data-ttu-id="7e170-106">クロスプラットフォームの開発を改善し、新しい機能を早期に導入するために、一部の .NET Framework 機能がアウトオブバンド (OOB) でリリースされました。</span><span class="sxs-lookup"><span data-stu-id="7e170-106">To improve cross-platform development and introduce new functionality early, some .NET Framework features were released out of band (OOB).</span></span>

| <span data-ttu-id="7e170-107">プロジェクト</span><span class="sxs-lookup"><span data-stu-id="7e170-107">Project</span></span> | <span data-ttu-id="7e170-108">説明</span><span class="sxs-lookup"><span data-stu-id="7e170-108">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Collections.Immutable> | <span data-ttu-id="7e170-109">スレッド セーフであり、内容が変更されないことが保証されているコレクションを提供します。</span><span class="sxs-lookup"><span data-stu-id="7e170-109">Provides collections that are thread safe and guaranteed to never change their contents.</span></span> |
| <xref:System.Net.Http.WinHttpHandler> | <span data-ttu-id="7e170-110">Windows の WinHTTP インターフェイスに基づいた <xref:System.Net.Http.HttpClient> のメッセージ ハンドラーを提供します。</span><span class="sxs-lookup"><span data-stu-id="7e170-110">Provides a message handler for <xref:System.Net.Http.HttpClient> based on the WinHTTP interface of Windows.</span></span> |
| <xref:System.Numerics> | <span data-ttu-id="7e170-111">SIMD ハードウェア ベースのアクセラレータを利用できるベクター型のライブラリを提供します。</span><span class="sxs-lookup"><span data-stu-id="7e170-111">Provides a library of vector types that can take advantage of SIMD hardware-based acceleration.</span></span>|
| <xref:System.Threading.Tasks.Dataflow> | <span data-ttu-id="7e170-112">TPL データフロー ライブラリはデータ フロー コンポーネントを提供し、コンカレンシー対応アプリケーションの堅牢性を強化します。</span><span class="sxs-lookup"><span data-stu-id="7e170-112">The TPL Dataflow Library provides dataflow components to help increase the robustness of concurrency-enabled applications.</span></span> |  

## <a name="platform-specific-libraries"></a><span data-ttu-id="7e170-113">プラットフォーム固有のライブラリ</span><span class="sxs-lookup"><span data-stu-id="7e170-113">Platform-specific libraries</span></span>

<span data-ttu-id="7e170-114">一部のライブラリは特定のプラットフォームを対象としています。</span><span class="sxs-lookup"><span data-stu-id="7e170-114">Some libraries target specific platforms.</span></span> <span data-ttu-id="7e170-115">たとえば、クラスを <xref:System.Text.CodePagesEncodingProvider> 使用すると、.NET Framework を使用して開発された UWP アプリでコードページエンコーディングを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="7e170-115">For example, the <xref:System.Text.CodePagesEncodingProvider> class makes code page encodings available to UWP apps developed using .NET Framework.</span></span>
  
| <span data-ttu-id="7e170-116">プロジェクト</span><span class="sxs-lookup"><span data-stu-id="7e170-116">Project</span></span> | <span data-ttu-id="7e170-117">説明</span><span class="sxs-lookup"><span data-stu-id="7e170-117">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Text.CodePagesEncodingProvider> | <span data-ttu-id="7e170-118">クラスを拡張して <xref:System.Text.EncodingProvider> 、ユニバーサル Windows プラットフォームを対象とするアプリでコードページエンコーディングを使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="7e170-118">Extends the <xref:System.Text.EncodingProvider> class to make code page encodings available to apps that target the Universal Windows Platform.</span></span> |  
  
## <a name="private-apis"></a><span data-ttu-id="7e170-119">プライベート API</span><span class="sxs-lookup"><span data-stu-id="7e170-119">Private APIs</span></span>  

<span data-ttu-id="7e170-120">これらの Api は製品インフラストラクチャをサポートします。コードから直接使用するためのものでも、サポートもされていません。</span><span class="sxs-lookup"><span data-stu-id="7e170-120">These APIs support the product infrastructure and are not intended or supported to be used directly from your code.</span></span>  
  
* [<span data-ttu-id="7e170-121">SmiOrderProperty プロパティの値です。</span><span class="sxs-lookup"><span data-stu-id="7e170-121">Microsoft.SqlServer.Server.SmiOrderProperty.Item property</span></span>](microsoft.sqlserver.server.smiorderproperty.item.md)
* [<span data-ttu-id="7e170-122">PrepForRemoting メソッド</span><span class="sxs-lookup"><span data-stu-id="7e170-122">System.Exception.PrepForRemoting method</span></span>](system.exception.prepforremoting.md)
* [<span data-ttu-id="7e170-123">SqlTypes プロパティ (system.object のプロパティ)</span><span class="sxs-lookup"><span data-stu-id="7e170-123">System.Data.SqlTypes.SqlChars.Stream property</span></span>](system.data.sqltypes.sqlchars.stream.md)
* [<span data-ttu-id="7e170-124">SqlTypes. SqlStreamChars コンストラクター</span><span class="sxs-lookup"><span data-stu-id="7e170-124">System.Data.SqlTypes.SqlStreamChars Constructor</span></span>](system.data.sqltypes.sqlstreamchars.-ctor.md)
* [<span data-ttu-id="7e170-125">SqlTypes プロパティの値を検索します。</span><span class="sxs-lookup"><span data-stu-id="7e170-125">System.Data.SqlTypes.SqlStreamChars.CanSeek property</span></span>](system.data.sqltypes.sqlstreamchars.canseek.md)
* [<span data-ttu-id="7e170-126">SqlTypes プロパティの値を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="7e170-126">System.Data.SqlTypes.SqlStreamChars.IsNull property</span></span>](system.data.sqltypes.sqlstreamchars.isnull.md)
* [<span data-ttu-id="7e170-127">SqlTypes プロパティ ("system.string" プロパティ)</span><span class="sxs-lookup"><span data-stu-id="7e170-127">System.Data.SqlTypes.SqlStreamChars.Length property</span></span>](system.data.sqltypes.sqlstreamchars.length.md)
* [<span data-ttu-id="7e170-128">SqlTypes メソッドを削除してください。</span><span class="sxs-lookup"><span data-stu-id="7e170-128">System.Data.SqlTypes.SqlStreamChars.Close method</span></span>](system.data.sqltypes.sqlstreamchars.close.md)
* [<span data-ttu-id="7e170-129">SqlTypes メソッド (system.object の置換メソッド)</span><span class="sxs-lookup"><span data-stu-id="7e170-129">System.Data.SqlTypes.SqlStreamChars.Dispose method</span></span>](system.data.sqltypes.sqlstreamchars.dispose.md)
* [<span data-ttu-id="7e170-130">System.string メソッド (SqlTypes...)</span><span class="sxs-lookup"><span data-stu-id="7e170-130">System.Data.SqlTypes.SqlStreamChars.Flush method</span></span>](system.data.sqltypes.sqlstreamchars.flush.md)
* [<span data-ttu-id="7e170-131">SqlTypes メソッドを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7e170-131">System.Data.SqlTypes.SqlStreamChars.Read method</span></span>](system.data.sqltypes.sqlstreamchars.read.md)
* [<span data-ttu-id="7e170-132">SqlTypes (システムのデータ. Seek メソッド)</span><span class="sxs-lookup"><span data-stu-id="7e170-132">System.Data.SqlTypes.SqlStreamChars.Seek method</span></span>](system.data.sqltypes.sqlstreamchars.seek.md)
* [<span data-ttu-id="7e170-133">SetLength メソッドを SqlTypes しています。</span><span class="sxs-lookup"><span data-stu-id="7e170-133">System.Data.SqlTypes.SqlStreamChars.SetLength method</span></span>](system.data.sqltypes.sqlstreamchars.setlength.md)
* [<span data-ttu-id="7e170-134">SqlTypes メソッドを作成してください。</span><span class="sxs-lookup"><span data-stu-id="7e170-134">System.Data.SqlTypes.SqlStreamChars.Write method</span></span>](system.data.sqltypes.sqlstreamchars.write.md)
* [<span data-ttu-id="7e170-135">MemoryStream メソッドの呼び出しを行います。</span><span class="sxs-lookup"><span data-stu-id="7e170-135">System.IO.MemoryStream.InternalGetOriginAndLength method</span></span>](system.io.memorystream.internalgetoriginandlength.md)
* [<span data-ttu-id="7e170-136">System .Net. ComNetOS クラス</span><span class="sxs-lookup"><span data-stu-id="7e170-136">System.Net.ComNetOS class</span></span>](system.net.comnetos.md)
* [<span data-ttu-id="7e170-137">System .Net. Connection クラス</span><span class="sxs-lookup"><span data-stu-id="7e170-137">System.Net.Connection class</span></span>](connection.md)
* [<span data-ttu-id="7e170-138">System .Net. 接続. m \_ writelist フィールド</span><span class="sxs-lookup"><span data-stu-id="7e170-138">System.Net.Connection.m\_WriteList field</span></span>](m_writelist.md)
* [<span data-ttu-id="7e170-139">システム .Net. ConnectionGroup クラス</span><span class="sxs-lookup"><span data-stu-id="7e170-139">System.Net.ConnectionGroup class</span></span>](connectiongroup.md)
* [<span data-ttu-id="7e170-140">System .Net. ConnectionGroup. m \_ connectiongroup フィールド</span><span class="sxs-lookup"><span data-stu-id="7e170-140">System.Net.ConnectionGroup.m\_ConnectionList field</span></span>](m_connectionlist.md)
* [<span data-ttu-id="7e170-141">System .Net. ConnectStream. 接続プロパティ</span><span class="sxs-lookup"><span data-stu-id="7e170-141">System.Net.ConnectStream.Connection property</span></span>](system.net.connectstream.connection.md)
* [<span data-ttu-id="7e170-142">CoreResponseData クラス</span><span class="sxs-lookup"><span data-stu-id="7e170-142">System.Net.CoreResponseData class</span></span>](coreresponsedata.md)
* [<span data-ttu-id="7e170-143">System CoreResponseData \_ ResponseHeaders フィールド</span><span class="sxs-lookup"><span data-stu-id="7e170-143">System.Net.CoreResponseData.m\_ResponseHeaders field</span></span>](coreresponsedata_m_responseheaders.md)
* [<span data-ttu-id="7e170-144">CoreResponseData の \_ StatusCode フィールド</span><span class="sxs-lookup"><span data-stu-id="7e170-144">System.Net.CoreResponseData.m\_StatusCode field</span></span>](coreresponsedata_m_statuscode.md)
* [<span data-ttu-id="7e170-145">System .Net. ExceptionHelper クラス</span><span class="sxs-lookup"><span data-stu-id="7e170-145">System.Net.ExceptionHelper class</span></span>](system.net.exceptionhelper.md)
* [<span data-ttu-id="7e170-146">System .Net. HttpStatusDescription クラス</span><span class="sxs-lookup"><span data-stu-id="7e170-146">System.Net.HttpStatusDescription class</span></span>](system.net.httpstatusdescription.md)
* [<span data-ttu-id="7e170-147">HttpWebRequest。 \_AutoRedirects フィールド</span><span class="sxs-lookup"><span data-stu-id="7e170-147">System.Net.HttpWebRequest.\_AutoRedirects field</span></span>](_autoredirects.md)
* [<span data-ttu-id="7e170-148">HttpWebRequest。 \_CoreResponse フィールド</span><span class="sxs-lookup"><span data-stu-id="7e170-148">System.Net.HttpWebRequest.\_CoreResponse field</span></span>](httpwebrequest__coreresponse.md)
* [<span data-ttu-id="7e170-149">HttpWebRequest。 \_Httpresponse.cache フィールド</span><span class="sxs-lookup"><span data-stu-id="7e170-149">System.Net.HttpWebRequest.\_HttpResponse field</span></span>](_httpresponse.md)
* [<span data-ttu-id="7e170-150">System .Net. Logging クラス</span><span class="sxs-lookup"><span data-stu-id="7e170-150">System.Net.Logging class</span></span>](system.net.logging.md)
* [<span data-ttu-id="7e170-151">System .Net. Mail. Mailaddressparc クラス</span><span class="sxs-lookup"><span data-stu-id="7e170-151">System.Net.Mail.MailAddressParser class</span></span>](system.net.mail.mailaddressparser.md)
* [<span data-ttu-id="7e170-152">System QuotedPairReader クラス</span><span class="sxs-lookup"><span data-stu-id="7e170-152">System.Net.Mail.QuotedPairReader class</span></span>](system.net.mail.quotedpairreader.md)
* [<span data-ttu-id="7e170-153">System .Net (Mime) のヘルパークラス</span><span class="sxs-lookup"><span data-stu-id="7e170-153">System.Net.Mime.MailBnfHelper class</span></span>](system.net.mime.mailbnfhelper.md)
* [<span data-ttu-id="7e170-154">System .Net. PooledStream. NetworkStream プロパティ</span><span class="sxs-lookup"><span data-stu-id="7e170-154">System.Net.PooledStream.NetworkStream property</span></span>](system.net.pooledstream.networkstream.md)
* [<span data-ttu-id="7e170-155">システム .Net. RtcState クラス</span><span class="sxs-lookup"><span data-stu-id="7e170-155">System.Net.RtcState class</span></span>](system.net.rtcstate.md)
* [<span data-ttu-id="7e170-156">System .Net. Security. Sslstate プロパティ</span><span class="sxs-lookup"><span data-stu-id="7e170-156">System.Net.Security.SslState.SslProtocol property</span></span>](system.net.security.sslstate.sslprotocol.md)
* [<span data-ttu-id="7e170-157">System .Net. ServicePoint. m \_ connectiongrouplist フィールド</span><span class="sxs-lookup"><span data-stu-id="7e170-157">System.Net.ServicePoint.m\_ConnectionGroupList field</span></span>](m_connectiongrouplist.md)
* [<span data-ttu-id="7e170-158">System .Net. ServicePointManager. CloseConnectionGroups メソッド</span><span class="sxs-lookup"><span data-stu-id="7e170-158">System.Net.ServicePointManager.CloseConnectionGroups method</span></span>](system.net.servicepointmanager.closeconnectiongroups.md)
* [<span data-ttu-id="7e170-159">System .Net. ServicePointManager. s \_ servicepointmanager フィールド</span><span class="sxs-lookup"><span data-stu-id="7e170-159">System.Net.ServicePointManager.s\_ServicePointTable field</span></span>](s_servicepointtable.md)
* [<span data-ttu-id="7e170-160">M_Worker TlsStream (システム) フィールド</span><span class="sxs-lookup"><span data-stu-id="7e170-160">System.Net.TlsStream.m_Worker field</span></span>](system.net.tlsstream.m_worker.md)
* [<span data-ttu-id="7e170-161">UnsafeNclNativeMethods クラス</span><span class="sxs-lookup"><span data-stu-id="7e170-161">System.Net.UnsafeNclNativeMethods class</span></span>](system.net.unsafenclnativemethods.md)
* [<span data-ttu-id="7e170-162">System .Net. WebHeaderCollection. AddInternal メソッド</span><span class="sxs-lookup"><span data-stu-id="7e170-162">System.Net.WebHeaderCollection.AddInternal method</span></span>](system.net.webheadercollection.addinternal.md)
* [<span data-ttu-id="7e170-163">System.servicemodel. Channels. Message. BodyToString メソッド</span><span class="sxs-lookup"><span data-stu-id="7e170-163">System.ServiceModel.Channels.Message.BodyToString method</span></span>](system.servicemodel.channels.message.bodytostring.md)
* [<span data-ttu-id="7e170-164">WriteStartHeaders メソッド (System.servicemodel.)</span><span class="sxs-lookup"><span data-stu-id="7e170-164">System.ServiceModel.Channels.Message.WriteStartHeaders method</span></span>](system.servicemodel.channels.message.writestartheaders.md)
* [<span data-ttu-id="7e170-165">System.web. ControlBuilderInterceptor クラス</span><span class="sxs-lookup"><span data-stu-id="7e170-165">System.Web.Compilation.ControlBuilderInterceptor class</span></span>](controlbuilderinterceptor-class.md)
* [<span data-ttu-id="7e170-166">IsDebuggerCheckDisabledForTestPurposes (システムの診断の \_ フィールド)</span><span class="sxs-lookup"><span data-stu-id="7e170-166">System.Windows.Diagnostics.VisualDiagnostics.s\_isDebuggerCheckDisabledForTestPurposes field</span></span>](s-isdebuggercheckdisabledfortestpurposes-field.md)
* [<span data-ttu-id="7e170-167">System.string クラス (DataMemberFieldEditor クラス)</span><span class="sxs-lookup"><span data-stu-id="7e170-167">System.Windows.Forms.Design.DataMemberFieldEditor class</span></span>](datamemberfieldeditor-class.md)
* [<span data-ttu-id="7e170-168">System.string クラス (DataMemberListEditor クラス)</span><span class="sxs-lookup"><span data-stu-id="7e170-168">System.Windows.Forms.Design.DataMemberListEditor class</span></span>](datamemberlisteditor-class.md)
* [<span data-ttu-id="7e170-169">System.Xml.XmlReader メソッド</span><span class="sxs-lookup"><span data-stu-id="7e170-169">System.Xml.XmlReader.CreateSqlReader method</span></span>](system.xml.xmlreader.createsqlreader.md)
* [<span data-ttu-id="7e170-170">adodb.recordset.接続インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7e170-170">adodb.Connection interface</span></span>](adodb.connection.md)
* [<span data-ttu-id="7e170-171">adodb.recordset.EventReason 列挙型</span><span class="sxs-lookup"><span data-stu-id="7e170-171">adodb.EventReason enum</span></span>](adodb.eventreasonenum.md)
* [<span data-ttu-id="7e170-172">adodb.recordset.EventStatus 列挙型</span><span class="sxs-lookup"><span data-stu-id="7e170-172">adodb.EventStatus enum</span></span>](adodb.eventstatusenum.md)
* [<span data-ttu-id="7e170-173">stdole.DISPPARAMS 構造体</span><span class="sxs-lookup"><span data-stu-id="7e170-173">stdole.DISPPARAMS Structure</span></span>](stdole.dispparams.md)
* [<span data-ttu-id="7e170-174">stdole.EXCEPINFO 構造体</span><span class="sxs-lookup"><span data-stu-id="7e170-174">stdole.EXCEPINFO Structure</span></span>](stdole.excepinfo.md)
* [<span data-ttu-id="7e170-175">stdole.IFont.Name プロパティ</span><span class="sxs-lookup"><span data-stu-id="7e170-175">stdole.IFont.Name property</span></span>](stdole.ifont.name.md)
* [<span data-ttu-id="7e170-176">stdole.IFontDisp インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7e170-176">stdole.IFontDisp interface</span></span>](stdole.ifontdisp.md)
* [<span data-ttu-id="7e170-177">stdole.IPicture. Handle プロパティ</span><span class="sxs-lookup"><span data-stu-id="7e170-177">stdole.IPicture.Handle property</span></span>](stdole.ipicture.handle.md)
* [<span data-ttu-id="7e170-178">stdole.IPictureDisp プロパティ</span><span class="sxs-lookup"><span data-stu-id="7e170-178">stdole.IPictureDisp.Handle property</span></span>](stdole.ipicturedisp.handle.md)
* [<span data-ttu-id="7e170-179">stdole.StdFont インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7e170-179">stdole.StdFont interface</span></span>](stdole.stdfont.md)
* [<span data-ttu-id="7e170-180">stdole.StdPicture インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7e170-180">stdole.StdPicture interface</span></span>](stdole.stdpicture.md)
  
## <a name="see-also"></a><span data-ttu-id="7e170-181">関連項目</span><span class="sxs-lookup"><span data-stu-id="7e170-181">See also</span></span>

* [<span data-ttu-id="7e170-182">.NET Framework および特別なリリース</span><span class="sxs-lookup"><span data-stu-id="7e170-182">.NET Framework and Out-of-Band Releases</span></span>](../get-started/the-net-framework-and-out-of-band-releases.md)
