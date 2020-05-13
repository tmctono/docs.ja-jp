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
ms.openlocfilehash: 9270afa1d8c8ddd74cfe6dd05e39c1480f5767e6
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83206944"
---
# <a name="icordebugmodulegetbaseaddress-method"></a><span data-ttu-id="0341d-102">ICorDebugModule::GetBaseAddress メソッド</span><span class="sxs-lookup"><span data-stu-id="0341d-102">ICorDebugModule::GetBaseAddress Method</span></span>
<span data-ttu-id="0341d-103">モジュールのベースアドレスを取得します。</span><span class="sxs-lookup"><span data-stu-id="0341d-103">Gets the base address of the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0341d-104">構文</span><span class="sxs-lookup"><span data-stu-id="0341d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBaseAddress(  
    [out] CORDB_ADDRESS *pAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0341d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0341d-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="0341d-106">入出力`CORDB_ADDRESS`モジュールのベースアドレスを指定する。</span><span class="sxs-lookup"><span data-stu-id="0341d-106">[out] A `CORDB_ADDRESS` that specifies the base address of the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0341d-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="0341d-107">Remarks</span></span>  
 <span data-ttu-id="0341d-108">モジュールがネイティブイメージの場合 (つまり、モジュールがネイティブイメージジェネレーター Ngen.exe によって生成された場合)、そのベースアドレスはゼロになります。</span><span class="sxs-lookup"><span data-stu-id="0341d-108">If the module is a native image (that is, if the module was produced by the native image generator, NGen.exe), its base address will be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0341d-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="0341d-109">Requirements</span></span>  
 <span data-ttu-id="0341d-110">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0341d-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0341d-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0341d-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0341d-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0341d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0341d-113">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0341d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0341d-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="0341d-114">See also</span></span>
