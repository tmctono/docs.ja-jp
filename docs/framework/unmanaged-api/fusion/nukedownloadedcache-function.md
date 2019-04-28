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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774531"
---
# <a name="nukedownloadedcache-function"></a><span data-ttu-id="f171e-102">NukeDownloadedCache 関数</span><span class="sxs-lookup"><span data-stu-id="f171e-102">NukeDownloadedCache Function</span></span>
<span data-ttu-id="f171e-103">共通言語ランタイム (CLR) のダウンロード キャッシュを削除します。</span><span class="sxs-lookup"><span data-stu-id="f171e-103">Deletes the common language runtime (CLR) download cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f171e-104">構文</span><span class="sxs-lookup"><span data-stu-id="f171e-104">Syntax</span></span>  
  
```  
HRESULT NukeDownloadedCache();  
```  
  
## <a name="return-value"></a><span data-ttu-id="f171e-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="f171e-105">Return Value</span></span>  
 <span data-ttu-id="f171e-106">このメソッドは、WinError.h で定義されている標準の COM エラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="f171e-106">This method returns standard COM error codes, as defined in WinError.h.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f171e-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="f171e-107">Remarks</span></span>  
 <span data-ttu-id="f171e-108">CLR のダウンロード キャッシュは、再利用できる場合、URL からダウンロードされる厳密な名前のアセンブリが格納領域です。</span><span class="sxs-lookup"><span data-stu-id="f171e-108">The CLR download cache is the area where strong-named assemblies that are downloaded from a URL are stored for possible reuse.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f171e-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="f171e-109">Requirements</span></span>  
 <span data-ttu-id="f171e-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f171e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f171e-111">**ヘッダー:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="f171e-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="f171e-112">**ライブラリ:** Fusion.dll と Mscorwks.dll します。</span><span class="sxs-lookup"><span data-stu-id="f171e-112">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="f171e-113">Mscorwks.dll のではなく Fusion.dll を使用して、正しいバージョンの .NET Framework を対象にすることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f171e-113">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="f171e-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f171e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f171e-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="f171e-115">See also</span></span>

- [<span data-ttu-id="f171e-116">CreateHistoryReader 関数</span><span class="sxs-lookup"><span data-stu-id="f171e-116">CreateHistoryReader Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/createhistoryreader-function.md)
- [<span data-ttu-id="f171e-117">GetHistoryFileDirectory 関数</span><span class="sxs-lookup"><span data-stu-id="f171e-117">GetHistoryFileDirectory Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/gethistoryfiledirectory-function.md)
- [<span data-ttu-id="f171e-118">Fusion グローバル静的関数</span><span class="sxs-lookup"><span data-stu-id="f171e-118">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
