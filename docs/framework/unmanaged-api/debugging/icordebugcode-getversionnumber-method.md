---
title: ICorDebugCode::GetVersionNumber メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetVersionNumber
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetVersionNumber
helpviewer_keywords:
- GetVersionNumber method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetVersionNumber method [.NET Framework debugging]
ms.assetid: c8e02518-679f-4e9f-8a28-ba4a89a3876f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 003b29501e8f22ed9010a9f16a4f7ee67bce03a8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61750138"
---
# <a name="icordebugcodegetversionnumber-method"></a><span data-ttu-id="c9348-102">ICorDebugCode::GetVersionNumber メソッド</span><span class="sxs-lookup"><span data-stu-id="c9348-102">ICorDebugCode::GetVersionNumber Method</span></span>
<span data-ttu-id="c9348-103">この"ICorDebugCode"を表すコードのバージョンを識別する 1 から始まる番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="c9348-103">Gets the one-based number that identifies the version of the code that this "ICorDebugCode" represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9348-104">構文</span><span class="sxs-lookup"><span data-stu-id="c9348-104">Syntax</span></span>  
  
```  
HRESULT GetVersionNumber (  
    [out] ULONG32    *nVersion  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c9348-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c9348-105">Parameters</span></span>  
 `nVersion`  
 <span data-ttu-id="c9348-106">[out]コードのバージョン番号へのポインター。</span><span class="sxs-lookup"><span data-stu-id="c9348-106">[out] A pointer to the version number of the code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c9348-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="c9348-107">Remarks</span></span>  
 <span data-ttu-id="c9348-108">バージョン番号は、コードに対してエディット コンティニュ (EnC) 操作を実行するたびにインクリメントされます。</span><span class="sxs-lookup"><span data-stu-id="c9348-108">The version number is incremented each time an edit-and-continue (EnC) operation is performed on the code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9348-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="c9348-109">Requirements</span></span>  
 <span data-ttu-id="c9348-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c9348-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c9348-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c9348-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c9348-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c9348-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c9348-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c9348-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9348-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="c9348-114">See also</span></span>
