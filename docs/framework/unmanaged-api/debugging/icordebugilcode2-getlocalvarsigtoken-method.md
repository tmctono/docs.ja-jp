---
title: ICorDebugILCode2::GetLocalVarSigToken メソッド
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILCode2.GetLocalVarSigToken
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 17665b77-1342-4115-94fd-9f45b0ecfb0f
topic_type:
- apiref
ms.openlocfilehash: 3759cfa330ac37d2ed62a0b8bb70b5e10cd9d12e
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76782447"
---
# <a name="icordebugilcode2getlocalvarsigtoken-method"></a><span data-ttu-id="6f95b-102">ICorDebugILCode2::GetLocalVarSigToken メソッド</span><span class="sxs-lookup"><span data-stu-id="6f95b-102">ICorDebugILCode2::GetLocalVarSigToken Method</span></span>
<span data-ttu-id="6f95b-103">[.NET Framework 4.5.2 以降のバージョンでのみでサポート]</span><span class="sxs-lookup"><span data-stu-id="6f95b-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="6f95b-104">このインスタンスで示される関数について、ローカル変数のシグネチャのメタデータ トークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="6f95b-104">Gets the metadata token for the local variable signature for the function that is represented by this instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f95b-105">構文</span><span class="sxs-lookup"><span data-stu-id="6f95b-105">Syntax</span></span>  
  
```cpp
HRESULT GetLocalVarSigToken(  
   [out] mdSignature *pmdSig  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6f95b-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6f95b-106">Parameters</span></span>  
 `pmdSig`  
 <span data-ttu-id="6f95b-107">[out] この機能のローカル変数シグネチャの `mdSignature` トークンへのポインター、またはシグネチャがない場合 (つまり、機能にローカル変数がない場合) は `mdSignatureNil`。</span><span class="sxs-lookup"><span data-stu-id="6f95b-107">[out] A pointer to the `mdSignature` token for the local variable signature for this function, or `mdSignatureNil` if there is no signature (that is, if the function doesn't have any local variables).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6f95b-108">コメント</span><span class="sxs-lookup"><span data-stu-id="6f95b-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f95b-109">要件</span><span class="sxs-lookup"><span data-stu-id="6f95b-109">Requirements</span></span>  
 <span data-ttu-id="6f95b-110">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6f95b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f95b-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6f95b-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6f95b-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6f95b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6f95b-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f95b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f95b-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="6f95b-114">See also</span></span>

- [<span data-ttu-id="6f95b-115">ICorDebugILCode2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6f95b-115">ICorDebugILCode2 Interface</span></span>](icordebugilcode2-interface.md)
- [<span data-ttu-id="6f95b-116">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6f95b-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
