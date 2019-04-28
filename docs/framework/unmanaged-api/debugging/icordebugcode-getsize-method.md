---
title: ICorDebugCode::GetSize メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetSize
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetSize
helpviewer_keywords:
- GetSize method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetSize method [.NET Framework debugging]
ms.assetid: 115bc6de-f5e2-4e8e-bb38-c7cf54045434
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 678b7fbd595b1238b7025c22b0ed80b02ed4becd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61750211"
---
# <a name="icordebugcodegetsize-method"></a><span data-ttu-id="67d2e-102">ICorDebugCode::GetSize メソッド</span><span class="sxs-lookup"><span data-stu-id="67d2e-102">ICorDebugCode::GetSize Method</span></span>
<span data-ttu-id="67d2e-103">この"ICorDebugCode"で表されるバイナリ コードのバイト単位のサイズを取得します。</span><span class="sxs-lookup"><span data-stu-id="67d2e-103">Gets the size, in bytes, of the binary code represented by this "ICorDebugCode".</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67d2e-104">構文</span><span class="sxs-lookup"><span data-stu-id="67d2e-104">Syntax</span></span>  
  
```  
HRESULT GetSize (  
    [out] ULONG32    *pcBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="67d2e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="67d2e-105">Parameters</span></span>  
 `pcBytes`  
 <span data-ttu-id="67d2e-106">[out]このコードのバイナリのバイト単位のサイズへのポインター`ICorDebugCode`オブジェクトが表す。</span><span class="sxs-lookup"><span data-stu-id="67d2e-106">[out] A pointer to the size, in bytes, of the binary code that this `ICorDebugCode` object represents.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67d2e-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="67d2e-107">Requirements</span></span>  
 <span data-ttu-id="67d2e-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="67d2e-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67d2e-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="67d2e-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="67d2e-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="67d2e-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="67d2e-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67d2e-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67d2e-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="67d2e-112">See also</span></span>
