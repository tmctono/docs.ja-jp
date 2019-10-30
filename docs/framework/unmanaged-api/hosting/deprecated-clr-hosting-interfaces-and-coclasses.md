---
title: 非推奨の CLR のホスト インターフェイスおよびコクラス
ms.date: 03/30/2017
helpviewer_keywords:
- interfaces [.NET Framework hosting], version 1
- .NET Framework 1.1, hosting interfaces
- hosting interfaces [.NET Framework], version 1
- .NET Framework 1.0, hosting interfaces
ms.assetid: 7b3d2755-cbab-4160-bc69-eb85791e38c7
ms.openlocfilehash: 08e193ed40c6538b62d8b1af0a8c41b4225f136b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138261"
---
# <a name="deprecated-clr-hosting-interfaces-and-coclasses"></a><span data-ttu-id="1bc77-102">非推奨の CLR のホスト インターフェイスおよびコクラス</span><span class="sxs-lookup"><span data-stu-id="1bc77-102">Deprecated CLR Hosting Interfaces and Coclasses</span></span>
<span data-ttu-id="1bc77-103">ここでは、アンマネージホストが .NET Framework バージョン1.0 および1.1 の共通言語ランタイム (CLR) をアプリケーションに統合するために使用できるインターフェイスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="1bc77-103">This section describes the interfaces that unmanaged hosts can use to integrate the common language runtime (CLR) in the .NET Framework versions 1.0 and 1.1 into their applications.</span></span> <span data-ttu-id="1bc77-104">これらのインターフェイスは、ホストがランタイムを構成してプロセスに読み込むためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="1bc77-104">These interfaces provide methods for a host to configure and load the runtime into a process.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1bc77-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="1bc77-105">In This Section</span></span>  
 <span data-ttu-id="1bc77-106">IAppDomainSetup</span><span class="sxs-lookup"><span data-stu-id="1bc77-106">IAppDomainSetup</span></span>  
 <span data-ttu-id="1bc77-107">ホストが <xref:System.AppDomain>を構成するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="1bc77-107">Provides methods for the host to configure an <xref:System.AppDomain>.</span></span>  
  
 [<span data-ttu-id="1bc77-108">ICeeFileGen クラス</span><span class="sxs-lookup"><span data-stu-id="1bc77-108">ICeeFileGen Class</span></span>](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md)  
 <span data-ttu-id="1bc77-109">れネイティブのポータブル実行可能 (PE) ファイルを作成するための機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="1bc77-109">(Deprecated) Provides functionality for creating a native portable executable (PE) file.</span></span>  
  
 [<span data-ttu-id="1bc77-110">ICorRuntimeHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1bc77-110">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)  
 <span data-ttu-id="1bc77-111">ホストが CLR 設定を構成するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="1bc77-111">Provides methods for the host to configure CLR settings.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="1bc77-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="1bc77-112">Related Sections</span></span>  
 [<span data-ttu-id="1bc77-113">CLR ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1bc77-113">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 <span data-ttu-id="1bc77-114">.NET Framework バージョン2.0 以降のバージョンで提供されるホストインターフェイスについて説明するトピックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="1bc77-114">Contains topics that describe the hosting interfaces provided with the .NET Framework version 2.0 and later versions.</span></span>
