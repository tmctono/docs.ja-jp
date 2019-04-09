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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4e549e13c0d51e4aa708a674a2224168ab66f8ad
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59178166"
---
# <a name="nukedownloadedcache-function"></a><span data-ttu-id="1c9c5-102">NukeDownloadedCache 関数</span><span class="sxs-lookup"><span data-stu-id="1c9c5-102">NukeDownloadedCache Function</span></span>
<span data-ttu-id="1c9c5-103">共通言語ランタイム (CLR) のダウンロード キャッシュを削除します。</span><span class="sxs-lookup"><span data-stu-id="1c9c5-103">Deletes the common language runtime (CLR) download cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c9c5-104">構文</span><span class="sxs-lookup"><span data-stu-id="1c9c5-104">Syntax</span></span>  
  
```  
HRESULT NukeDownloadedCache();  
```  
  
## <a name="return-value"></a><span data-ttu-id="1c9c5-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="1c9c5-105">Return Value</span></span>  
 <span data-ttu-id="1c9c5-106">このメソッドは、WinError.h で定義されている標準の COM エラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="1c9c5-106">This method returns standard COM error codes, as defined in WinError.h.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1c9c5-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="1c9c5-107">Remarks</span></span>  
 <span data-ttu-id="1c9c5-108">CLR のダウンロード キャッシュは、再利用できる場合、URL からダウンロードされる厳密な名前のアセンブリが格納領域です。</span><span class="sxs-lookup"><span data-stu-id="1c9c5-108">The CLR download cache is the area where strong-named assemblies that are downloaded from a URL are stored for possible reuse.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c9c5-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="1c9c5-109">Requirements</span></span>  
 <span data-ttu-id="1c9c5-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c9c5-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c9c5-111">**ヘッダー:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="1c9c5-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="1c9c5-112">**ライブラリ:** Fusion.dll と Mscorwks.dll します。</span><span class="sxs-lookup"><span data-stu-id="1c9c5-112">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="1c9c5-113">Mscorwks.dll のではなく Fusion.dll を使用して、正しいバージョンの .NET Framework を対象にすることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1c9c5-113">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 **<span data-ttu-id="1c9c5-114">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="1c9c5-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1c9c5-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="1c9c5-115">See also</span></span>

- [<span data-ttu-id="1c9c5-116">CreateHistoryReader 関数</span><span class="sxs-lookup"><span data-stu-id="1c9c5-116">CreateHistoryReader Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/createhistoryreader-function.md)
- [<span data-ttu-id="1c9c5-117">GetHistoryFileDirectory 関数</span><span class="sxs-lookup"><span data-stu-id="1c9c5-117">GetHistoryFileDirectory Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/gethistoryfiledirectory-function.md)
- [<span data-ttu-id="1c9c5-118">Fusion グローバル静的関数</span><span class="sxs-lookup"><span data-stu-id="1c9c5-118">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
