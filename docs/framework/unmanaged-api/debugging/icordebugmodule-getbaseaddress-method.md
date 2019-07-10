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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9ed6344f9a37d246a551699c94046b8c2b473fd8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67762694"
---
# <a name="icordebugmodulegetbaseaddress-method"></a><span data-ttu-id="adafd-102">ICorDebugModule::GetBaseAddress メソッド</span><span class="sxs-lookup"><span data-stu-id="adafd-102">ICorDebugModule::GetBaseAddress Method</span></span>
<span data-ttu-id="adafd-103">モジュールのベース アドレスを取得します。</span><span class="sxs-lookup"><span data-stu-id="adafd-103">Gets the base address of the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="adafd-104">構文</span><span class="sxs-lookup"><span data-stu-id="adafd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBaseAddress(  
    [out] CORDB_ADDRESS *pAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="adafd-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="adafd-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="adafd-106">[out]A`CORDB_ADDRESS`モジュールのベース アドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="adafd-106">[out] A `CORDB_ADDRESS` that specifies the base address of the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="adafd-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="adafd-107">Remarks</span></span>  
 <span data-ttu-id="adafd-108">ネイティブ モジュールの場合 (つまり、モジュールは、ネイティブ イメージ ジェネレーター、NGen.exe によって生成された) 場合のイメージのベース アドレスは 0 になります。</span><span class="sxs-lookup"><span data-stu-id="adafd-108">If the module is a native image (that is, if the module was produced by the native image generator, NGen.exe), its base address will be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="adafd-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="adafd-109">Requirements</span></span>  
 <span data-ttu-id="adafd-110">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="adafd-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="adafd-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="adafd-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="adafd-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="adafd-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="adafd-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="adafd-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="adafd-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="adafd-114">See also</span></span>
