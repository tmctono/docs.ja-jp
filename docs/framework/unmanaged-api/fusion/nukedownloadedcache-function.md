---
title: NukeDownloadedCache 関数
ms.date: 03/30/2017
api_name:
- NukeDownloadedCache
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- NukeDownloadedCache
helpviewer_keywords:
- NukeDownloadedCache function [.NET Framework fusion]
ms.assetid: fac2b1c6-6fa3-4818-805b-b63972024c86
topic_type:
- apiref
ms.openlocfilehash: 8f97614412eb2d49b202e86bdabc727159deb5d6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131697"
---
# <a name="nukedownloadedcache-function"></a><span data-ttu-id="71dc3-102">NukeDownloadedCache 関数</span><span class="sxs-lookup"><span data-stu-id="71dc3-102">NukeDownloadedCache Function</span></span>
<span data-ttu-id="71dc3-103">共通言語ランタイム (CLR) のダウンロードキャッシュを削除します。</span><span class="sxs-lookup"><span data-stu-id="71dc3-103">Deletes the common language runtime (CLR) download cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71dc3-104">構文</span><span class="sxs-lookup"><span data-stu-id="71dc3-104">Syntax</span></span>  
  
```cpp  
HRESULT NukeDownloadedCache();  
```  
  
## <a name="return-value"></a><span data-ttu-id="71dc3-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="71dc3-105">Return Value</span></span>  
 <span data-ttu-id="71dc3-106">このメソッドは、Winerror.h で定義されているように、標準の COM エラーコードを返します。</span><span class="sxs-lookup"><span data-stu-id="71dc3-106">This method returns standard COM error codes, as defined in WinError.h.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="71dc3-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="71dc3-107">Remarks</span></span>  
 <span data-ttu-id="71dc3-108">CLR ダウンロードキャッシュは、URL からダウンロードされる厳密な名前付きアセンブリが再利用できるように格納される領域です。</span><span class="sxs-lookup"><span data-stu-id="71dc3-108">The CLR download cache is the area where strong-named assemblies that are downloaded from a URL are stored for possible reuse.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71dc3-109">［要件］</span><span class="sxs-lookup"><span data-stu-id="71dc3-109">Requirements</span></span>  
 <span data-ttu-id="71dc3-110">**:** 「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="71dc3-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71dc3-111">**ヘッダー:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="71dc3-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="71dc3-112">**ライブラリ:** Fusion .dll と Mscorwks.dll。</span><span class="sxs-lookup"><span data-stu-id="71dc3-112">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="71dc3-113">Mscorwks.dll の代わりに Fusion を使用して、正しいバージョンの .NET Framework を対象としていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="71dc3-113">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="71dc3-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71dc3-114">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71dc3-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="71dc3-115">See also</span></span>

- [<span data-ttu-id="71dc3-116">CreateHistoryReader 関数</span><span class="sxs-lookup"><span data-stu-id="71dc3-116">CreateHistoryReader Function</span></span>](createhistoryreader-function.md)
- [<span data-ttu-id="71dc3-117">GetHistoryFileDirectory 関数</span><span class="sxs-lookup"><span data-stu-id="71dc3-117">GetHistoryFileDirectory Function</span></span>](gethistoryfiledirectory-function.md)
- [<span data-ttu-id="71dc3-118">Fusion グローバル静的関数</span><span class="sxs-lookup"><span data-stu-id="71dc3-118">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
