---
title: ICorDebugProcess6::GetCode メソッド
ms.date: 03/30/2017
ms.assetid: faa538c2-60c9-4064-b996-1b4c24ebd751
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7349a20da35eb0b87894440026a0974d49ae2aa0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59097297"
---
# <a name="icordebugprocess6getcode-method"></a><span data-ttu-id="77a0e-102">ICorDebugProcess6::GetCode メソッド</span><span class="sxs-lookup"><span data-stu-id="77a0e-102">ICorDebugProcess6::GetCode Method</span></span>
<span data-ttu-id="77a0e-103">特定のコード アドレスで、マネージド コードに関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="77a0e-103">Gets information about the managed code at a particular code address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77a0e-104">構文</span><span class="sxs-lookup"><span data-stu-id="77a0e-104">Syntax</span></span>  
  
```  
HRESULT GetCode(  
    [in] CORDB_ADDRESS codeAddress,   
    [out] ICorDebugCode **ppCode);  
```  
  
## <a name="parameters"></a><span data-ttu-id="77a0e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="77a0e-105">Parameters</span></span>  
 `codeAddress`  
 <span data-ttu-id="77a0e-106">[in]A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md)マネージ コードのセグメントの開始アドレスを指定する値。</span><span class="sxs-lookup"><span data-stu-id="77a0e-106">[in] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that specifies the starting address of the managed code segment.</span></span>  
  
 `ppCode`  
 <span data-ttu-id="77a0e-107">[out]マネージ コードのセグメントを表す"ICorDebugCode"オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="77a0e-107">[out] A pointer to the address of an "ICorDebugCode" object that represents a segment of managed code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="77a0e-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="77a0e-108">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="77a0e-109">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="77a0e-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77a0e-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="77a0e-110">Requirements</span></span>  
 <span data-ttu-id="77a0e-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="77a0e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77a0e-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="77a0e-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="77a0e-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="77a0e-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="77a0e-114">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="77a0e-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="77a0e-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="77a0e-115">See also</span></span>

- [<span data-ttu-id="77a0e-116">ICorDebugProcess6 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="77a0e-116">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)
- [<span data-ttu-id="77a0e-117">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="77a0e-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
