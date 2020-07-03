---
title: FTP - .NET
description: FtpWebRequest と FtpWebResponse クラスを使用することで .NET Framework によって提供される、FTP の包括的なサポートについて学習します。
ms.date: 03/30/2017
helpviewer_keywords:
- FTP
ms.assetid: 9b43f8b4-89d7-46a7-89fc-71aca916dd32
ms.openlocfilehash: d21ca43cd1041df358dc5e2add9560fb33e85d83
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502588"
---
# <a name="ftp"></a><span data-ttu-id="22618-103">FTP</span><span class="sxs-lookup"><span data-stu-id="22618-103">FTP</span></span>

<span data-ttu-id="22618-104">.NET Framework は、<xref:System.Net.FtpWebRequest> クラスと <xref:System.Net.FtpWebResponse> クラスを使用して、FTP プロトコルの包括的なサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="22618-104">The .NET Framework provides comprehensive support for the FTP protocol with the <xref:System.Net.FtpWebRequest> and <xref:System.Net.FtpWebResponse> classes.</span></span> <span data-ttu-id="22618-105">これらのクラスは <xref:System.Net.WebRequest> と <xref:System.Net.WebResponse> から派生します。</span><span class="sxs-lookup"><span data-stu-id="22618-105">These classes are derived from <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse>.</span></span> <span data-ttu-id="22618-106">ほとんどの場合、<xref:System.Net.WebRequest> クラスと <xref:System.Net.WebResponse> クラスは、要求を行うために必要なすべてを提供しますが、プロパティとして公開されている FTP 固有の機能にアクセスする必要がある場合は、これらのクラスを <xref:System.Net.FtpWebRequest> または <xref:System.Net.FtpWebResponse> に型キャストすることができます。</span><span class="sxs-lookup"><span data-stu-id="22618-106">In most cases, the <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse> classes provide all that is necessary to make the request, but if you need access to the FTP-specific features exposed as properties, you can typecast these classes to <xref:System.Net.FtpWebRequest> or <xref:System.Net.FtpWebResponse>.</span></span>

## <a name="examples"></a><span data-ttu-id="22618-107">使用例</span><span class="sxs-lookup"><span data-stu-id="22618-107">Examples</span></span>

<span data-ttu-id="22618-108">詳細については、次のトピックを参照してください。[方法: FTP を使用してファイルをダウンロードする](how-to-download-files-with-ftp.md)、[方法:FTP を使用してファイルをアップロードする](how-to-upload-files-with-ftp.md)、[方法:FTP でディレクトリの内容を一覧表示する](how-to-list-directory-contents-with-ftp.md)。</span><span class="sxs-lookup"><span data-stu-id="22618-108">For more information, see the following topics: [How to: Download Files with FTP](how-to-download-files-with-ftp.md), [How to: Upload Files with FTP](how-to-upload-files-with-ftp.md), and [How to: List Directory Contents with FTP](how-to-list-directory-contents-with-ftp.md).</span></span>

## <a name="ftp-and-proxies"></a><span data-ttu-id="22618-109">FTP とプロキシ</span><span class="sxs-lookup"><span data-stu-id="22618-109">FTP and proxies</span></span>

<span data-ttu-id="22618-110">(<xref:System.Net.FtpWebRequest.Proxy%2A> プロパティで指定された) プロキシが HTTP プロキシの場合、<xref:System.Net.WebRequestMethods.Ftp.DownloadFile>、<xref:System.Net.WebRequestMethods.Ftp.ListDirectory>、および <xref:System.Net.WebRequestMethods.Ftp.ListDirectoryDetails> コマンドのみがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="22618-110">If a proxy (specified by the <xref:System.Net.FtpWebRequest.Proxy%2A> property) is an HTTP proxy, then only the <xref:System.Net.WebRequestMethods.Ftp.DownloadFile>, <xref:System.Net.WebRequestMethods.Ftp.ListDirectory>, and <xref:System.Net.WebRequestMethods.Ftp.ListDirectoryDetails> commands are supported.</span></span>

## <a name="see-also"></a><span data-ttu-id="22618-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="22618-111">See also</span></span>

- [<span data-ttu-id="22618-112">プロキシを介したインターネットへのアクセス</span><span class="sxs-lookup"><span data-stu-id="22618-112">Accessing the Internet Through a Proxy</span></span>](accessing-the-internet-through-a-proxy.md)
- [<span data-ttu-id="22618-113">ネットワーク プログラミングのサンプル</span><span class="sxs-lookup"><span data-stu-id="22618-113">Network Programming Samples</span></span>](network-programming-samples.md)
- [<span data-ttu-id="22618-114">アプリケーション プロトコルの使用</span><span class="sxs-lookup"><span data-stu-id="22618-114">Using Application Protocols</span></span>](using-application-protocols.md)
