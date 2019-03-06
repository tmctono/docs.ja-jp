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
ms.openlocfilehash: 84ab475ecb538dcf5bd24c750dfe9c993ea5a0ee
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57470901"
---
# <a name="icordebugcode2getcodechunks-method"></a><span data-ttu-id="cf0f8-102">ICorDebugCode2::GetCodeChunks メソッド</span><span class="sxs-lookup"><span data-stu-id="cf0f8-102">ICorDebugCode2::GetCodeChunks Method</span></span>
<span data-ttu-id="cf0f8-103">このコード オブジェクトを構成しているコード チャンクを取得します。</span><span class="sxs-lookup"><span data-stu-id="cf0f8-103">Gets the chunks of code that this code object is composed of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf0f8-104">構文</span><span class="sxs-lookup"><span data-stu-id="cf0f8-104">Syntax</span></span>  
  
```  
HRESULT GetCodeChunks (  
    [in]  ULONG32     cbufSize,  
    [out] ULONG32     *pcnumChunks,  
    [out, size_is(cbufSize), length_is(*pcnumChunks)]   
        CodeChunkInfo chunks[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cf0f8-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="cf0f8-105">Parameters</span></span>  
 `cbufSize`  
 <span data-ttu-id="cf0f8-106">[in]サイズ、`chunks`配列。</span><span class="sxs-lookup"><span data-stu-id="cf0f8-106">[in] Size of the `chunks` array.</span></span>  
  
 `pcnumChunks`  
 <span data-ttu-id="cf0f8-107">[out]返されるチャンクの数、`chunks`配列。</span><span class="sxs-lookup"><span data-stu-id="cf0f8-107">[out] The number of chunks returned in the `chunks` array.</span></span>  
  
 `chunks`  
 <span data-ttu-id="cf0f8-108">[out]コードの 1 つのチャンクを表す"CodeChunkInfo"構造体の配列。</span><span class="sxs-lookup"><span data-stu-id="cf0f8-108">[out] An array of "CodeChunkInfo" structures, each of which represents a single chunk of code.</span></span> <span data-ttu-id="cf0f8-109">場合の値`cbufSize`が 0 の場合このパラメーターを null にすることができます。</span><span class="sxs-lookup"><span data-stu-id="cf0f8-109">If the value of `cbufSize` is 0, this parameter can be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cf0f8-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="cf0f8-110">Remarks</span></span>  
 <span data-ttu-id="cf0f8-111">コード チャンクが重複し、は、これが連結されたによって順序に従っている[icordebugcode::getcode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getcode-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="cf0f8-111">The code chunks will never overlap, and they will follow the order in which they would have been concatenated by [ICorDebugCode::GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getcode-method.md).</span></span> <span data-ttu-id="cf0f8-112">.NET Framework version 2.0 では、Microsoft intermediate language (MSIL) コード オブジェクトには、1 つのコード チャンクが構成されています。</span><span class="sxs-lookup"><span data-stu-id="cf0f8-112">A Microsoft intermediate language (MSIL) code object in the .NET Framework version 2.0 will comprise a single code chunk.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf0f8-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="cf0f8-113">Requirements</span></span>  
 <span data-ttu-id="cf0f8-114">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cf0f8-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf0f8-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cf0f8-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cf0f8-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cf0f8-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cf0f8-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf0f8-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf0f8-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="cf0f8-118">See also</span></span>

