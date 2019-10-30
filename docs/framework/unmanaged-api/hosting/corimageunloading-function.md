---
title: _CorImageUnloading 関数
ms.date: 03/30/2017
api_name:
- _CorImageUnloading
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- _CorImageUnloading
helpviewer_keywords:
- _CorImageUnloading function [.NET Framework hosting]
ms.assetid: b4367214-6dac-4280-aa11-fd487ff30bc4
topic_type:
- apiref
ms.openlocfilehash: 30e3a88140c8a438001e8428df4c5ee879c83376
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136919"
---
# <a name="_corimageunloading-function"></a><span data-ttu-id="2a53f-102">_CorImageUnloading 関数</span><span class="sxs-lookup"><span data-stu-id="2a53f-102">_CorImageUnloading Function</span></span>
<span data-ttu-id="2a53f-103">マネージド モジュール イメージがアンロードされたときに、ローダーに通知します。</span><span class="sxs-lookup"><span data-stu-id="2a53f-103">Notifies the loader when the managed module images are unloaded.</span></span>  
  
 <span data-ttu-id="2a53f-104">この関数は実装されていません。</span><span class="sxs-lookup"><span data-stu-id="2a53f-104">This function is not implemented.</span></span> <span data-ttu-id="2a53f-105">呼び出された場合は E_NOTIMPL を返します。</span><span class="sxs-lookup"><span data-stu-id="2a53f-105">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a53f-106">構文</span><span class="sxs-lookup"><span data-stu-id="2a53f-106">Syntax</span></span>  
  
```cpp  
STDAPI (VOID) _CorImageUnloading(   
   [in] PVOID* ImageBase  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2a53f-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2a53f-107">Parameters</span></span>  
 `ImageBase`  
 <span data-ttu-id="2a53f-108">からアンロードするイメージの開始位置へのポインター。</span><span class="sxs-lookup"><span data-stu-id="2a53f-108">[in] A pointer to the starting location of the image to unload.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a53f-109">［要件］</span><span class="sxs-lookup"><span data-stu-id="2a53f-109">Requirements</span></span>  
 <span data-ttu-id="2a53f-110">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a53f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a53f-111">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="2a53f-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2a53f-112">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="2a53f-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2a53f-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a53f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a53f-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="2a53f-114">See also</span></span>

- [<span data-ttu-id="2a53f-115">メタデータ グローバル静的関数</span><span class="sxs-lookup"><span data-stu-id="2a53f-115">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
