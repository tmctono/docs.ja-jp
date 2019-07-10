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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b488b6a887b0c66d8c17f8ea78f48f7d2ea31011
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67758396"
---
# <a name="corimageunloading-function"></a><span data-ttu-id="6fba0-102">_CorImageUnloading 関数</span><span class="sxs-lookup"><span data-stu-id="6fba0-102">_CorImageUnloading Function</span></span>
<span data-ttu-id="6fba0-103">マネージド モジュール イメージがアンロードされたときに、ローダーに通知します。</span><span class="sxs-lookup"><span data-stu-id="6fba0-103">Notifies the loader when the managed module images are unloaded.</span></span>  
  
 <span data-ttu-id="6fba0-104">この関数が実装されていません。</span><span class="sxs-lookup"><span data-stu-id="6fba0-104">This function is not implemented.</span></span> <span data-ttu-id="6fba0-105">呼び出された場合、E_NOTIMPL を返します。</span><span class="sxs-lookup"><span data-stu-id="6fba0-105">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6fba0-106">構文</span><span class="sxs-lookup"><span data-stu-id="6fba0-106">Syntax</span></span>  
  
```cpp  
STDAPI (VOID) _CorImageUnloading(   
   [in] PVOID* ImageBase  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6fba0-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6fba0-107">Parameters</span></span>  
 `ImageBase`  
 <span data-ttu-id="6fba0-108">[in]アンロードするイメージの開始位置へのポインター。</span><span class="sxs-lookup"><span data-stu-id="6fba0-108">[in] A pointer to the starting location of the image to unload.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6fba0-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="6fba0-109">Requirements</span></span>  
 <span data-ttu-id="6fba0-110">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6fba0-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6fba0-111">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="6fba0-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6fba0-112">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="6fba0-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6fba0-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6fba0-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fba0-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="6fba0-114">See also</span></span>

- [<span data-ttu-id="6fba0-115">メタデータ グローバル静的関数</span><span class="sxs-lookup"><span data-stu-id="6fba0-115">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
