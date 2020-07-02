---
ms.openlocfilehash: a007022bf32ffe76861f6f9016a7edace17b0f61
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620355"
---
### <a name="data-written-to-printsystemjobinfojobstream-must-be-in-xps-format"></a><span data-ttu-id="c45c3-101">PrintSystemJobInfo.JobStream に書き込まれるデータは XPS 形式とする必要があります</span><span class="sxs-lookup"><span data-stu-id="c45c3-101">Data written to PrintSystemJobInfo.JobStream must be in XPS format</span></span>

#### <a name="details"></a><span data-ttu-id="c45c3-102">説明</span><span class="sxs-lookup"><span data-stu-id="c45c3-102">Details</span></span>

<span data-ttu-id="c45c3-103"><xref:System.Printing.PrintSystemJobInfo.JobStream> プロパティにより印刷ジョブのストリームが公開されます。</span><span class="sxs-lookup"><span data-stu-id="c45c3-103">The <xref:System.Printing.PrintSystemJobInfo.JobStream> property exposes the stream of a print job.</span></span> <span data-ttu-id="c45c3-104">ユーザーが基になるオペレーティング システム印刷コンポーネントに生のデータを送信するには、このストリームにデータを書き込みを行います。 .NET Framework 4.5 以降、Windows 8 より後のバージョンの Windows オペレーティング システムでは、このストリームに書き込むデータは XPS 形式のパッケージ ストリームにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c45c3-104">The user can send raw data to the underlying operating system printing components by writing to this stream.Starting with the .NET Framework 4.5 on Windows 8 and later versions of the Windows operating system, data written to this stream must be in XPS format as a package stream.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="c45c3-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="c45c3-105">Suggestion</span></span>

<span data-ttu-id="c45c3-106">印刷内容を出力するには、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="c45c3-106">To output print content, you can do either of the following:</span></span><ul><li><span data-ttu-id="c45c3-107"><xref:System.Windows.Xps.XpsDocumentWriter> クラスを使用して印刷内容を出力します。</span><span class="sxs-lookup"><span data-stu-id="c45c3-107">Use the <xref:System.Windows.Xps.XpsDocumentWriter> class to output print content.</span></span> <span data-ttu-id="c45c3-108">これが、推奨される方法です。</span><span class="sxs-lookup"><span data-stu-id="c45c3-108">This is the recommended alternative.</span></span></li><li><span data-ttu-id="c45c3-109"><xref:System.Printing.PrintSystemJobInfo.JobStream> プロパティによって返されるストリームに送信されるデータを、XPS 形式のパッケージ ストリームにします。</span><span class="sxs-lookup"><span data-stu-id="c45c3-109">Ensure that the data sent to the stream returned by the <xref:System.Printing.PrintSystemJobInfo.JobStream> property is in XPS format as a package stream.</span></span></li></ul>

| <span data-ttu-id="c45c3-110">名前</span><span class="sxs-lookup"><span data-stu-id="c45c3-110">Name</span></span>    | <span data-ttu-id="c45c3-111">[値]</span><span class="sxs-lookup"><span data-stu-id="c45c3-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="c45c3-112">スコープ</span><span class="sxs-lookup"><span data-stu-id="c45c3-112">Scope</span></span>   |<span data-ttu-id="c45c3-113">マイナー</span><span class="sxs-lookup"><span data-stu-id="c45c3-113">Minor</span></span>|
|<span data-ttu-id="c45c3-114">バージョン</span><span class="sxs-lookup"><span data-stu-id="c45c3-114">Version</span></span>|<span data-ttu-id="c45c3-115">4.5</span><span class="sxs-lookup"><span data-stu-id="c45c3-115">4.5</span></span>|
|<span data-ttu-id="c45c3-116">種類</span><span class="sxs-lookup"><span data-stu-id="c45c3-116">Type</span></span>|<span data-ttu-id="c45c3-117">ランタイム</span><span class="sxs-lookup"><span data-stu-id="c45c3-117">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="c45c3-118">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="c45c3-118">Affected APIs</span></span>

-<xref:System.Printing.PrintSystemJobInfo.JobStream?displayProperty=nameWithType></li></ul>|
