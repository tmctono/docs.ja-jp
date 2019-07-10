---
title: ICorDebugCode2::GetCodeChunks メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugCode2.GetCodeChunks
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode2::GetCodeChunks
helpviewer_keywords:
- GetCodeChunks method [.NET Framework debugging]
- ICorDebugCode2::GetCodeChunks method [.NET Framework debugging]
ms.assetid: 210a2f02-2678-4555-bc4a-78a0408764c8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4bbc7ac7d87c6a5d36dc3432c603bb7d16d62c00
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67747432"
---
# <a name="icordebugcode2getcodechunks-method"></a><span data-ttu-id="5177e-102">ICorDebugCode2::GetCodeChunks メソッド</span><span class="sxs-lookup"><span data-stu-id="5177e-102">ICorDebugCode2::GetCodeChunks Method</span></span>
<span data-ttu-id="5177e-103">このコード オブジェクトを構成しているコード チャンクを取得します。</span><span class="sxs-lookup"><span data-stu-id="5177e-103">Gets the chunks of code that this code object is composed of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5177e-104">構文</span><span class="sxs-lookup"><span data-stu-id="5177e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCodeChunks (  
    [in]  ULONG32     cbufSize,  
    [out] ULONG32     *pcnumChunks,  
    [out, size_is(cbufSize), length_is(*pcnumChunks)]   
        CodeChunkInfo chunks[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5177e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5177e-105">Parameters</span></span>  
 `cbufSize`  
 <span data-ttu-id="5177e-106">[in]サイズ、`chunks`配列。</span><span class="sxs-lookup"><span data-stu-id="5177e-106">[in] Size of the `chunks` array.</span></span>  
  
 `pcnumChunks`  
 <span data-ttu-id="5177e-107">[out]返されるチャンクの数、`chunks`配列。</span><span class="sxs-lookup"><span data-stu-id="5177e-107">[out] The number of chunks returned in the `chunks` array.</span></span>  
  
 `chunks`  
 <span data-ttu-id="5177e-108">[out]コードの 1 つのチャンクを表す"CodeChunkInfo"構造体の配列。</span><span class="sxs-lookup"><span data-stu-id="5177e-108">[out] An array of "CodeChunkInfo" structures, each of which represents a single chunk of code.</span></span> <span data-ttu-id="5177e-109">場合の値`cbufSize`が 0 の場合このパラメーターを null にすることができます。</span><span class="sxs-lookup"><span data-stu-id="5177e-109">If the value of `cbufSize` is 0, this parameter can be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5177e-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="5177e-110">Remarks</span></span>  
 <span data-ttu-id="5177e-111">コード チャンクが重複し、は、これが連結されたによって順序に従っている[icordebugcode::getcode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getcode-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="5177e-111">The code chunks will never overlap, and they will follow the order in which they would have been concatenated by [ICorDebugCode::GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getcode-method.md).</span></span> <span data-ttu-id="5177e-112">.NET Framework version 2.0 では、Microsoft intermediate language (MSIL) コード オブジェクトには、1 つのコード チャンクが構成されています。</span><span class="sxs-lookup"><span data-stu-id="5177e-112">A Microsoft intermediate language (MSIL) code object in the .NET Framework version 2.0 will comprise a single code chunk.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5177e-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="5177e-113">Requirements</span></span>  
 <span data-ttu-id="5177e-114">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5177e-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5177e-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5177e-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5177e-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5177e-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5177e-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5177e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5177e-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="5177e-118">See also</span></span>
