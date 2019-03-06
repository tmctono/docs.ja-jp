---
title: ICorDebugProcess6::GetCode メソッド
ms.date: 03/30/2017
ms.assetid: faa538c2-60c9-4064-b996-1b4c24ebd751
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1ec631c6b5c6d8ffdb74589c00e899b689b5e788
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57468118"
---
# <a name="icordebugprocess6getcode-method"></a><span data-ttu-id="173a2-102">ICorDebugProcess6::GetCode メソッド</span><span class="sxs-lookup"><span data-stu-id="173a2-102">ICorDebugProcess6::GetCode Method</span></span>
<span data-ttu-id="173a2-103">特定のコード アドレスで、マネージド コードに関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="173a2-103">Gets information about the managed code at a particular code address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="173a2-104">構文</span><span class="sxs-lookup"><span data-stu-id="173a2-104">Syntax</span></span>  
  
```  
HRESULT GetCode(  
    [in] CORDB_ADDRESS codeAddress,   
    [out] ICorDebugCode **ppCode);  
```  
  
## <a name="parameters"></a><span data-ttu-id="173a2-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="173a2-105">Parameters</span></span>  
 `codeAddress`  
 <span data-ttu-id="173a2-106">[in]A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md)マネージ コードのセグメントの開始アドレスを指定する値。</span><span class="sxs-lookup"><span data-stu-id="173a2-106">[in] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that specifies the starting address of the managed code segment.</span></span>  
  
 `ppCode`  
 <span data-ttu-id="173a2-107">[out]マネージ コードのセグメントを表す"ICorDebugCode"オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="173a2-107">[out] A pointer to the address of an "ICorDebugCode" object that represents a segment of managed code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="173a2-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="173a2-108">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="173a2-109">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="173a2-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="173a2-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="173a2-110">Requirements</span></span>  
 <span data-ttu-id="173a2-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="173a2-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="173a2-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="173a2-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="173a2-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="173a2-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="173a2-114">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="173a2-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="173a2-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="173a2-115">See also</span></span>
- [<span data-ttu-id="173a2-116">ICorDebugProcess6 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="173a2-116">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)
- [<span data-ttu-id="173a2-117">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="173a2-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
