---
title: 追加のクラス ライブラリと API
ms.date: 11/19/2019
helpviewer_keywords:
- Additional class libraries
- Additional managed libraries
- .NET Framework out-of-band releases
- out-of-band releases
ms.assetid: cf2d9006-b631-4e5d-81cd-20aab78c60f1
ms.topic: conceptual
ms.openlocfilehash: abf7fd20988ebaaaf1a40ccc168c636fd0dacc1d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155909"
---
# <a name="additional-class-libraries-and-apis"></a><span data-ttu-id="a6bbe-102">追加のクラス ライブラリと API</span><span class="sxs-lookup"><span data-stu-id="a6bbe-102">Additional class libraries and APIs</span></span>

<span data-ttu-id="a6bbe-103">.NET フレームワークは常に進化しています。</span><span class="sxs-lookup"><span data-stu-id="a6bbe-103">The .NET Framework is constantly evolving.</span></span> <span data-ttu-id="a6bbe-104">クロスプラットフォーム開発を改善し、新機能を早期に導入するために、新しい機能は帯域外にリリースされます (OOB).</span><span class="sxs-lookup"><span data-stu-id="a6bbe-104">To improve cross-platform development and introduce new functionality early, new features are released out of band (OOB).</span></span> <span data-ttu-id="a6bbe-105">ここでは、ドキュメントが用意されている OOB プロジェクトの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="a6bbe-105">This topic lists the OOB projects that we provide documentation for.</span></span>  
  
<span data-ttu-id="a6bbe-106">さらに、いくつかのライブラリは、特定のプラットフォームまたは .NET Framework の実装を対象にしています。</span><span class="sxs-lookup"><span data-stu-id="a6bbe-106">In addition, some libraries target specific platforms or implementations of the .NET Framework.</span></span> <span data-ttu-id="a6bbe-107">たとえば、<xref:System.Text.CodePagesEncodingProvider>このクラスは、.NET Framework を使用して開発された UWP アプリでコード ページエンコーディングを使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="a6bbe-107">For example, the <xref:System.Text.CodePagesEncodingProvider> class makes code page encodings available to UWP apps developed using the .NET Framework.</span></span> <span data-ttu-id="a6bbe-108">ここでは、これらのライブラリの一覧も示します。</span><span class="sxs-lookup"><span data-stu-id="a6bbe-108">This topic lists these libraries as well.</span></span>  
  
## <a name="oob-projects"></a><span data-ttu-id="a6bbe-109">OOB プロジェクト</span><span class="sxs-lookup"><span data-stu-id="a6bbe-109">OOB projects</span></span>
  
| <span data-ttu-id="a6bbe-110">Project</span><span class="sxs-lookup"><span data-stu-id="a6bbe-110">Project</span></span> | <span data-ttu-id="a6bbe-111">説明</span><span class="sxs-lookup"><span data-stu-id="a6bbe-111">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Collections.Immutable> | <span data-ttu-id="a6bbe-112">スレッド セーフであり、内容が変更されないことが保証されているコレクションを提供します。</span><span class="sxs-lookup"><span data-stu-id="a6bbe-112">Provides collections that are thread safe and guaranteed to never change their contents.</span></span> |
| <xref:System.Net.Http.WinHttpHandler> | <span data-ttu-id="a6bbe-113">Windows の WinHTTP インターフェイスに基づいた <xref:System.Net.Http.HttpClient> のメッセージ ハンドラーを提供します。</span><span class="sxs-lookup"><span data-stu-id="a6bbe-113">Provides a message handler for <xref:System.Net.Http.HttpClient> based on the WinHTTP interface of Windows.</span></span> |
| <xref:System.Numerics> | <span data-ttu-id="a6bbe-114">SIMD ハードウェア ベースのアクセラレータを利用できるベクター型のライブラリを提供します。</span><span class="sxs-lookup"><span data-stu-id="a6bbe-114">Provides a library of vector types that can take advantage of SIMD hardware-based acceleration.</span></span>|
| <xref:System.Threading.Tasks.Dataflow> | <span data-ttu-id="a6bbe-115">TPL データフロー ライブラリはデータ フロー コンポーネントを提供し、コンカレンシー対応アプリケーションの堅牢性を強化します。</span><span class="sxs-lookup"><span data-stu-id="a6bbe-115">The TPL Dataflow Library provides dataflow components to help increase the robustness of concurrency-enabled applications.</span></span> |  

## <a name="platform-specific-libraries"></a><span data-ttu-id="a6bbe-116">プラットフォーム固有のライブラリ</span><span class="sxs-lookup"><span data-stu-id="a6bbe-116">Platform-specific libraries</span></span>
  
| <span data-ttu-id="a6bbe-117">Project</span><span class="sxs-lookup"><span data-stu-id="a6bbe-117">Project</span></span> | <span data-ttu-id="a6bbe-118">説明</span><span class="sxs-lookup"><span data-stu-id="a6bbe-118">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Text.CodePagesEncodingProvider> | <span data-ttu-id="a6bbe-119">ユニバーサル<xref:System.Text.EncodingProvider>Windows プラットフォームを対象とするアプリでコード ページエンコーディングを使用できるようにクラスを拡張します。</span><span class="sxs-lookup"><span data-stu-id="a6bbe-119">Extends the <xref:System.Text.EncodingProvider> class to make code page encodings available to apps that target the Universal Windows Platform.</span></span> |  
  
## <a name="private-apis"></a><span data-ttu-id="a6bbe-120">プライベート API</span><span class="sxs-lookup"><span data-stu-id="a6bbe-120">Private APIs</span></span>  

<span data-ttu-id="a6bbe-121">この API は製品インフラストラクチャをサポートします。コードから直接使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="a6bbe-121">These APIs support the product infrastructure and are not intended/supported to be used directly from your code.</span></span>  
  
* [<span data-ttu-id="a6bbe-122">アイテム プロパティ</span><span class="sxs-lookup"><span data-stu-id="a6bbe-122">Microsoft.SqlServer.Server.SmiOrderProperty.Item Property</span></span>](microsoft.sqlserver.server.smiorderproperty.item.md)
* [<span data-ttu-id="a6bbe-123">メソッドの例外</span><span class="sxs-lookup"><span data-stu-id="a6bbe-123">System.Exception.PrepForRemoting Method</span></span>](system.exception.prepforremoting.md)
* [<span data-ttu-id="a6bbe-124">プロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="a6bbe-124">System.Data.SqlTypes.SqlChars.Stream Property</span></span>](system.data.sqltypes.sqlchars.stream.md)
* [<span data-ttu-id="a6bbe-125">コンストラクター</span><span class="sxs-lookup"><span data-stu-id="a6bbe-125">System.Data.SqlTypes.SqlStreamChars Constructor</span></span>](system.data.sqltypes.sqlstreamchars.-ctor.md)
* [<span data-ttu-id="a6bbe-126">プロパティを検索します。</span><span class="sxs-lookup"><span data-stu-id="a6bbe-126">System.Data.SqlTypes.SqlStreamChars.CanSeek Property</span></span>](system.data.sqltypes.sqlstreamchars.canseek.md)
* [<span data-ttu-id="a6bbe-127">プロパティ</span><span class="sxs-lookup"><span data-stu-id="a6bbe-127">System.Data.SqlTypes.SqlStreamChars.IsNull Property</span></span>](system.data.sqltypes.sqlstreamchars.isnull.md)
* [<span data-ttu-id="a6bbe-128">プロパティの長さ</span><span class="sxs-lookup"><span data-stu-id="a6bbe-128">System.Data.SqlTypes.SqlStreamChars.Length Property</span></span>](system.data.sqltypes.sqlstreamchars.length.md)
* [<span data-ttu-id="a6bbe-129">メソッドを閉じる</span><span class="sxs-lookup"><span data-stu-id="a6bbe-129">System.Data.SqlTypes.SqlStreamChars.Close Method</span></span>](system.data.sqltypes.sqlstreamchars.close.md)
* [<span data-ttu-id="a6bbe-130">メソッドを破棄します。</span><span class="sxs-lookup"><span data-stu-id="a6bbe-130">System.Data.SqlTypes.SqlStreamChars.Dispose Method</span></span>](system.data.sqltypes.sqlstreamchars.dispose.md)
* [<span data-ttu-id="a6bbe-131">メソッドをフラッシュします。</span><span class="sxs-lookup"><span data-stu-id="a6bbe-131">System.Data.SqlTypes.SqlStreamChars.Flush Method</span></span>](system.data.sqltypes.sqlstreamchars.flush.md)
* [<span data-ttu-id="a6bbe-132">メソッドを読み取る</span><span class="sxs-lookup"><span data-stu-id="a6bbe-132">System.Data.SqlTypes.SqlStreamChars.Read Method</span></span>](system.data.sqltypes.sqlstreamchars.read.md)
* [<span data-ttu-id="a6bbe-133">メソッドを検索します。</span><span class="sxs-lookup"><span data-stu-id="a6bbe-133">System.Data.SqlTypes.SqlStreamChars.Seek Method</span></span>](system.data.sqltypes.sqlstreamchars.seek.md)
* [<span data-ttu-id="a6bbe-134">メソッドを設定します。</span><span class="sxs-lookup"><span data-stu-id="a6bbe-134">System.Data.SqlTypes.SqlStreamChars.SetLength Method</span></span>](system.data.sqltypes.sqlstreamchars.setlength.md)
* [<span data-ttu-id="a6bbe-135">メソッドの書き込み</span><span class="sxs-lookup"><span data-stu-id="a6bbe-135">System.Data.SqlTypes.SqlStreamChars.Write Method</span></span>](system.data.sqltypes.sqlstreamchars.write.md)
* [<span data-ttu-id="a6bbe-136">メソッドを取得します。</span><span class="sxs-lookup"><span data-stu-id="a6bbe-136">System.IO.MemoryStream.InternalGetOriginAndLength Method</span></span>](system.io.memorystream.internalgetoriginandlength.md)
* [<span data-ttu-id="a6bbe-137">接続クラス</span><span class="sxs-lookup"><span data-stu-id="a6bbe-137">System.Net.Connection Class</span></span>](connection.md)
* [<span data-ttu-id="a6bbe-138">フィールドを\_書き込む</span><span class="sxs-lookup"><span data-stu-id="a6bbe-138">System.Net.Connection.m\_WriteList Field</span></span>](m_writelist.md)
* [<span data-ttu-id="a6bbe-139">クラス</span><span class="sxs-lookup"><span data-stu-id="a6bbe-139">System.Net.ConnectionGroup Class</span></span>](connectiongroup.md)
* [<span data-ttu-id="a6bbe-140">\_接続リスト フィールド</span><span class="sxs-lookup"><span data-stu-id="a6bbe-140">System.Net.ConnectionGroup.m\_ConnectionList Field</span></span>](m_connectionlist.md)
* [<span data-ttu-id="a6bbe-141">接続プロパティ</span><span class="sxs-lookup"><span data-stu-id="a6bbe-141">System.Net.ConnectStream.Connection Property</span></span>](system.net.connectstream.connection.md)
* [<span data-ttu-id="a6bbe-142">クラス</span><span class="sxs-lookup"><span data-stu-id="a6bbe-142">System.Net.CoreResponseData Class</span></span>](coreresponsedata.md)
* [<span data-ttu-id="a6bbe-143">\_応答ヘッダー フィールド</span><span class="sxs-lookup"><span data-stu-id="a6bbe-143">System.Net.CoreResponseData.m\_ResponseHeaders Field</span></span>](coreresponsedata_m_responseheaders.md)
* [<span data-ttu-id="a6bbe-144">\_ステータスコード フィールド</span><span class="sxs-lookup"><span data-stu-id="a6bbe-144">System.Net.CoreResponseData.m\_StatusCode Field</span></span>](coreresponsedata_m_statuscode.md)
* [<span data-ttu-id="a6bbe-145">を指定します。\_自動リダイレクトフィールド</span><span class="sxs-lookup"><span data-stu-id="a6bbe-145">System.Net.HttpWebRequest.\_AutoRedirects Field</span></span>](_autoredirects.md)
* [<span data-ttu-id="a6bbe-146">を指定します。\_コアレスポンスフィールド</span><span class="sxs-lookup"><span data-stu-id="a6bbe-146">System.Net.HttpWebRequest.\_CoreResponse Field</span></span>](httpwebrequest__coreresponse.md)
* [<span data-ttu-id="a6bbe-147">を指定します。\_応答フィールド</span><span class="sxs-lookup"><span data-stu-id="a6bbe-147">System.Net.HttpWebRequest.\_HttpResponse Field</span></span>](_httpresponse.md)
* [<span data-ttu-id="a6bbe-148">プロパティ</span><span class="sxs-lookup"><span data-stu-id="a6bbe-148">System.Net.PooledStream.NetworkStream Property</span></span>](system.net.pooledstream.networkstream.md)
* [<span data-ttu-id="a6bbe-149">クラス</span><span class="sxs-lookup"><span data-stu-id="a6bbe-149">System.Net.RtcState class</span></span>](system.net.rtcstate.md)
* [<span data-ttu-id="a6bbe-150">\_接続グループリスト フィールド</span><span class="sxs-lookup"><span data-stu-id="a6bbe-150">System.Net.ServicePoint.m\_ConnectionGroupList Field</span></span>](m_connectiongrouplist.md)
* [<span data-ttu-id="a6bbe-151">サービスポイント\_テーブル フィールド</span><span class="sxs-lookup"><span data-stu-id="a6bbe-151">System.Net.ServicePointManager.s\_ServicePointTable Field</span></span>](s_servicepointtable.md)
* [<span data-ttu-id="a6bbe-152">フィールドm_Worker</span><span class="sxs-lookup"><span data-stu-id="a6bbe-152">System.Net.TlsStream.m_Worker Field</span></span>](system.net.tlsstream.m_worker.md)
* [<span data-ttu-id="a6bbe-153">プロパティ</span><span class="sxs-lookup"><span data-stu-id="a6bbe-153">System.Net.Security.SslState.SslProtocol Property</span></span>](system.net.security.sslstate.sslprotocol.md)
* [<span data-ttu-id="a6bbe-154">メソッド</span><span class="sxs-lookup"><span data-stu-id="a6bbe-154">System.ServiceModel.Channels.Message.BodyToString Method</span></span>](system.servicemodel.channels.message.bodytostring.md)
* [<span data-ttu-id="a6bbe-155">メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="a6bbe-155">System.ServiceModel.Channels.Message.WriteStartHeaders Method</span></span>](system.servicemodel.channels.message.writestartheaders.md)
* [<span data-ttu-id="a6bbe-156">\_フィールドをテストする</span><span class="sxs-lookup"><span data-stu-id="a6bbe-156">System.Windows.Diagnostics.VisualDiagnostics.s\_isDebuggerCheckDisabledForTestPurposes Field</span></span>](s-isdebuggercheckdisabledfortestpurposes-field.md)
* [<span data-ttu-id="a6bbe-157">クラス.Windows.フォーム.デザイン.データメンバーフィールドエディタ</span><span class="sxs-lookup"><span data-stu-id="a6bbe-157">System.Windows.Forms.Design.DataMemberFieldEditor Class</span></span>](datamemberfieldeditor-class.md)
* [<span data-ttu-id="a6bbe-158">クラスをデザインします。</span><span class="sxs-lookup"><span data-stu-id="a6bbe-158">System.Windows.Forms.Design.DataMemberListEditor Class</span></span>](datamemberlisteditor-class.md)
* [<span data-ttu-id="a6bbe-159">メソッド</span><span class="sxs-lookup"><span data-stu-id="a6bbe-159">System.Xml.XmlReader.CreateSqlReader Method</span></span>](system.xml.xmlreader.createsqlreader.md)
* [<span data-ttu-id="a6bbe-160">Adodb。接続インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a6bbe-160">adodb.Connection Interface</span></span>](adodb.connection.md)
* [<span data-ttu-id="a6bbe-161">Adodb。イベント理由列挙</span><span class="sxs-lookup"><span data-stu-id="a6bbe-161">adodb.EventReason Enum</span></span>](adodb.eventreasonenum.md)
* [<span data-ttu-id="a6bbe-162">Adodb。イベントステータス列挙</span><span class="sxs-lookup"><span data-stu-id="a6bbe-162">adodb.EventStatus Enum</span></span>](adodb.eventstatusenum.md)
* [<span data-ttu-id="a6bbe-163">ストドール。ディスイスパムス構造</span><span class="sxs-lookup"><span data-stu-id="a6bbe-163">stdole.DISPPARAMS Structure</span></span>](stdole.dispparams.md)
* [<span data-ttu-id="a6bbe-164">ストドール。エクスセプインフォ構造</span><span class="sxs-lookup"><span data-stu-id="a6bbe-164">stdole.EXCEPINFO Structure</span></span>](stdole.excepinfo.md)
* [<span data-ttu-id="a6bbe-165">ストドール。IFont.Nameプロパティ</span><span class="sxs-lookup"><span data-stu-id="a6bbe-165">stdole.IFont.Name Property</span></span>](stdole.ifont.name.md)
* [<span data-ttu-id="a6bbe-166">ストドール。インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a6bbe-166">stdole.IFontDisp Interface</span></span>](stdole.ifontdisp.md)
* [<span data-ttu-id="a6bbe-167">ストドール。プロパティを処理します。</span><span class="sxs-lookup"><span data-stu-id="a6bbe-167">stdole.IPicture.Handle Property</span></span>](stdole.ipicture.handle.md)
* [<span data-ttu-id="a6bbe-168">ストドール。プロパティを処理します。</span><span class="sxs-lookup"><span data-stu-id="a6bbe-168">stdole.IPictureDisp.Handle Property</span></span>](stdole.ipicturedisp.handle.md)
* [<span data-ttu-id="a6bbe-169">ストドール。Std フォント インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a6bbe-169">stdole.StdFont Interface</span></span>](stdole.stdfont.md)
* [<span data-ttu-id="a6bbe-170">ストドール。StdPicture インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a6bbe-170">stdole.StdPicture Interface</span></span>](stdole.stdpicture.md)
  
## <a name="see-also"></a><span data-ttu-id="a6bbe-171">関連項目</span><span class="sxs-lookup"><span data-stu-id="a6bbe-171">See also</span></span>

* [<span data-ttu-id="a6bbe-172">.NET Framework および OOB リリース</span><span class="sxs-lookup"><span data-stu-id="a6bbe-172">The .NET Framework and Out-of-Band Releases</span></span>](../get-started/the-net-framework-and-out-of-band-releases.md)
