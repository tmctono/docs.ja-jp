---
title: ICorDebugModule::GetBaseAddress メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetBaseAddress
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetBaseAddress
helpviewer_keywords:
- GetBaseAddress method [.NET Framework debugging]
- ICorDebugModule::GetBaseAddress method [.NET Framework debugging]
ms.assetid: 26a82815-1982-4eb7-92d1-5c3d318d5be4
topic_type:
- apiref
ms.openlocfilehash: aff8fb0a2316817e413f10e82215556f1f54fbc4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73109635"
---
# <a name="icordebugmodulegetbaseaddress-method"></a><span data-ttu-id="fed9c-102">ICorDebugModule::GetBaseAddress メソッド</span><span class="sxs-lookup"><span data-stu-id="fed9c-102">ICorDebugModule::GetBaseAddress Method</span></span>
<span data-ttu-id="fed9c-103">モジュールのベースアドレスを取得します。</span><span class="sxs-lookup"><span data-stu-id="fed9c-103">Gets the base address of the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fed9c-104">構文</span><span class="sxs-lookup"><span data-stu-id="fed9c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBaseAddress(  
    [out] CORDB_ADDRESS *pAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fed9c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fed9c-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="fed9c-106">入出力モジュールのベースアドレスを指定する `CORDB_ADDRESS`。</span><span class="sxs-lookup"><span data-stu-id="fed9c-106">[out] A `CORDB_ADDRESS` that specifies the base address of the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fed9c-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="fed9c-107">Remarks</span></span>  
 <span data-ttu-id="fed9c-108">モジュールがネイティブイメージの場合 (つまり、モジュールがネイティブイメージジェネレーター Ngen.exe によって生成された場合)、そのベースアドレスはゼロになります。</span><span class="sxs-lookup"><span data-stu-id="fed9c-108">If the module is a native image (that is, if the module was produced by the native image generator, NGen.exe), its base address will be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fed9c-109">［要件］</span><span class="sxs-lookup"><span data-stu-id="fed9c-109">Requirements</span></span>  
 <span data-ttu-id="fed9c-110">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fed9c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fed9c-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fed9c-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fed9c-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fed9c-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fed9c-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fed9c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fed9c-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="fed9c-114">See also</span></span>
